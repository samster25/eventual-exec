The Agentic Search Agent
How our search agent leverages this index

                        ┌───────────────┐
                        │     QUERY     │
                        └───────┬───────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │                       │
                    │     ┌───────────┐     │
                    │     │   ◉ ◉     │     │
                    │     │   AGENT   │     │
                    │     └─────┬─────┘     │
                    │           │           │
                    │      ┌────┴────┐      │
                    │      │         │      │
                    │      ▼         ▼      │
                    │    THINK    SEARCH    │
                    │      │         │      │
                    │      └────┬────┘      │
                    │           │  ↻        │
                    └───────────┼───────────┘
                                │
                                ▼
                    ┌────────────────────┐
                    │  [1] result        │
                    │  [2] result        │
                    │  [3] result        │
                    └─────────┬──────────┘
                              │
                              ▼
                    ┌────────────────────┐
                    │   CITED ANSWER     │
                    └────────────────────┘
The search agent follows a ReAct-style pattern: an iterative reasoning loop where the LLM decides when to search, formulates queries based on the user's question, and can iterate multiple times to gather comprehensive information. This isn't just keyword extraction—the agent reasons about what information it needs and refines its approach based on what it finds.

For each search, the agent chooses the appropriate method: hybrid search (the default) for general queries, text search for exact terms like identifiers or error messages, and vector search for conceptual questions about relationships and meaning. This flexibility lets the agent adapt its retrieval strategy to the nature of the question.

Results are tracked with [1], [2] style citations, deduplicated across iterations to avoid redundancy. The agent answers using only information from search results, never external knowledge—ensuring every claim can be traced back to an indexed source.

                               Agentic Search Flow

     ┌──────────┐                                              ┌───────────────┐
     │  Query   │                                              │ Cited Answer  │
     └────┬─────┘                                              └───────▲───────┘
          │                                                            │
          ▼                                                            │
    ┌─────┴──────┐     ┌────────┐     ┌───────┐     ┌────────┐     ┌───┴────┐
    │    LLM     │────▶│ Search │────▶│ Index │────▶│ Filter │────▶│  LLM   │
    │ Reasoning  │     │  Tool  │     │   ○   │     │ Policy │     │ Answer │
    └─────┬──────┘     └────────┘     └───────┘     └────────┘     └────────┘
          │                                              │
          │              ↻ iteration loop                │
          └──────────────────────────────────────────────┘

                  ┌──────────────────────────────────────────┐
                  │  Results tracked with [1] [2] citations  │
                  │  Deduplicated across iterations          │
                  └──────────────────────────────────────────┘
# Agent search loop (simplified)
for iteration in range(max_iterations):
    response = await adapter.chat(messages, tools)

    if response.tool_calls:
        for tool_call in response.tool_calls:
            results = await index.search(query, method)
            # Filter results by policy BEFORE agent sees them
            results = filter_results(policy, results, "read")
            chunks = tracker.add_chunks(results)
    else:
        # No tool calls, agent is done
        answer = response.content
        break
Key files: loup-index/src/core/agent.py, loup-index/src/core/llm.py

Agent Roles
The vibes part: agent role definitions in natural language

      "Engineering team             "Sales rep needing
       with code access"             customer data"
              │                             │
              ▼                             ▼
        ┌───────────┐                 ┌───────────┐
        │    ___    │                 │    ___    │
        │   /◉ ◉\   │                 │   /$ $\   │
        │   \___/   │                 │   \___/   │
        │   /│ │\   │                 │   /│ │\   │
        │    │ │    │                 │    │ │    │
        └─────┬─────┘                 └─────┬─────┘
              │                             │
              ▼                             ▼
        ┌─────────────────┐           ┌─────────────────┐
        │ ▸ org.eng.code  │           │ ▸ org.sales.*   │
        │ ▸ org.eng.docs  │           │ ▸ org.customers │
        │ ▸ org.eng.prs   │           └─────────────────┘
        └─────────────────┘
Instead of manually configuring access rules, you describe what an agent should do in plain English. Say "Engineering team member who needs access to code reviews and documentation"—that's it. The system takes this natural language description and figures out the rest.

Under the hood, a Claude-powered AgentGeneratorAgent explores the available resources using the list_resources tool, discovers what exists in your index, and generates appropriate policies with glob-pattern rules. It follows the principle of least privilege—only granting the permissions actually implied by the role description, nothing more.

This is the "vibes" layer of Loup: you think in terms of what an agent should be able to do, and the system translates that intent into precise, enforceable rules. The human describes the role; the machine handles the policy mechanics.

                           AgentGeneratorAgent Workflow

  ┌─────────────────────────┐
  │    Role Description     │
  │ "Engineering team that  │
  │  needs code review and  │
  │  documentation access"  │
  └───────────┬─────────────┘
              │
              ▼
  ┌───────────────────────────┐
  │      Claude Agent         │
  │  (AgentGeneratorAgent)    │
  └───────────┬───────────────┘
              │
              ▼
  ┌───────────┴─────────────┐        ┌───────────────────────────┐
  │  list_resources()       │───────▶│  ▸ org.engineering.code   │
  │  Resource Exploration   │        │  ▸ org.engineering.docs   │
  └─────────────────────────┘        │  ▸ org.engineering.prs    │
                                     └───────────────────────────┘
              │
              ▼
  ┌───────────┴─────────────┐
  │   Policy Generation     │
  │  { "rules": [...],      │
  │    "default": "deny" }  │
  └─────────────────────────┘
# Example: role description becomes policy
"Engineering team member who needs access to
 code reviews and documentation"
        │
        ▼
Discovers: org.engineering.code, org.engineering.docs, org.engineering.prs
        │
        ▼
{
  "rules": [{ "action": "allow", "paths": ["org.engineering.**"], "permissions": ["read"] }],
  "default": "deny"
}
Key file: loup-index/src/core/agent_generator.py

Access Control
The non-vibes part: how access control is enforced deterministically

                          REQUEST
                             │
                             ▼
                      ┌────────────────┐
                      │     POLICY     │
                      │    CHECKER     │
                      └───────┬────────┘
                              │
             ┌────────────────┴────────────────┐
             │                                 │
             ▼                                 ▼
      ┌──────────────────┐            ┌──────────────────┐
      │                  │            │                  │
      │  ┌────────────┐  │            │  ┌────────────┐  │
      │  │ ✓  ALLOW   │  │            │  │ ✗  DENY    │  │
      │  └────────────┘  │            │  └────────────┘  │
      │                  │            │                  │
      │   org.eng.**     │            │   org.hr.*       │
      │        │         │            │        ╳         │
      │        ▼         │            │                  │
      │    RESULTS       │            │       403        │
      │                  │            │                  │
      └──────────────────┘            └──────────────────┘
While roles are defined in natural language, enforcement is entirely deterministic. Policies consist of ordered rules with first-match-wins semantics—each rule specifies an action (allow or deny), paths (using glob patterns where * matches one segment and ** matches any depth), and permissions (read, write, delete, admin).

The system is fail-closed by design: default deny, malformed policies return 403, and every request path is evaluated against explicit patterns with deterministic results. There's no ambiguity at runtime—either a rule matches and grants access, or it doesn't.

{
  "version": 1,
  "rules": [
    { "action": "allow", "paths": ["org.engineering.**"], "permissions": ["read"] },
    { "action": "deny", "paths": ["org.engineering.secrets"], "permissions": ["*"] }
  ],
  "default": "deny"
}
Enforcement happens at multiple layers: the Rust API validates tokens and loads agent policies (encoding them in a Loup-Policy header), the Python index middleware decodes and stores the policy, and critically, search results are filtered by policy before the LLM ever sees them. The agent literally cannot access what it's not authorized to see.

                              Policy Enforcement Flow

  ┌──────────┐     ┌───────────┐     ┌──────────────────┐     ┌──────────────────┐
  │ Request  │────▶│  API Auth │────▶│   Loup-Policy    │────▶│ Index Middleware │
  │ + Token  │     │   (Rust)  │     │  Header Added    │     │    (Python)      │
  └──────────┘     └───────────┘     └──────────────────┘     └────────┬─────────┘
                                                                       │
                                                                       ▼
                                                              ┌────────┴─────────┐
                                                              │ evaluate_access()│
                                                              │  path, permission│
                                                              └────────┬─────────┘
                                                                       │
                                          ┌────────────────────────────┴────────────────────────────┐
                                          │                                                         │
                                          ▼                                                         ▼
                                   ┌──────┴──────┐                                          ┌───────┴──────┐
                                   │ ✓   ALLOW   │                                          │ ✗   DENY     │
                                   │ Rule matched│                                          │ No match or  │
                                   │ action=allow│                                          │ action=deny  │
                                   └─────────────┘                                          └──────────────┘
def evaluate_access(policy: Policy | None, path: str, permission: str) -> bool:
    """First-match-wins policy evaluation."""
    if policy is None:
        return True  # No policy = full access

    for rule in policy.rules:
        paths_match = any(path_matches(pattern, path) for pattern in rule.paths)
        permission_match = "*" in rule.permissions or permission in rule.permissions
        if paths_match and permission_match:
            return rule.action == PolicyAction.ALLOW

    return policy.default == PolicyAction.ALLOW
Key files: loup-index/src/core/policy.py, loup-api/src/state.rs, loup-index/src/server/app.py

Putting It Together
The complete picture: from role description to search response

    ┌─────────┐     ┌─────────┐     ┌─────────┐     ┌─────────┐
    │  ROLE   │────▶│  AGENT  │────▶│ POLICY  │────▶│  TOKEN  │
    │  desc   │     │   GEN   │     │  rules  │     │         │
    └─────────┘     └─────────┘     └─────────┘     └────┬────┘
                                                         │
    ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┼ ─ ─ ─
                                                         │
                                                         ▼
    ┌─────────┐     ┌─────────┐     ┌─────────┐     ┌────┴────┐
    │ ANSWER  │◀────│  FILTER │◀────│ SEARCH  │◀────│   API   │
    │ [1][2]  │     │ by rule │     │  index  │     │  AUTH   │
    └─────────┘     └─────────┘     └─────────┘     └─────────┘

            ≈ VIBES ≈                     ✱ DETERMINISTIC ✱
       (natural language)                  (policy rules)

               │                                │
               └───────────────┬────────────────┘
                               │
                               ▼
                        ┌─────────────┐
                        │    LOUP     │
                        └─────────────┘
The full flow starts with a human describing what an agent should be able to do—"Sales team needs customer data access." The AgentGeneratorAgent takes this description, explores available resources, and outputs a concrete policy with explicit rules. That policy gets stored with the agent definition.

When someone creates an API token for that agent, the token carries a reference to its policy. Every request made with that token includes the policy in a Loup-Policy header, which flows through to the search index. Before the LLM ever sees search results, they're filtered against this policy—unauthorized content is simply removed.

                                    End-to-End Flow

                      SETUP                                       RUNTIME
    ╔════════════════════════════════════════╗    ╔════════════════════════════════════════╗
    ║                                        ║    ║                                        ║
    ║  "Sales team needs                     ║    ║     Request                            ║
    ║   customer data"                       ║    ║        │                               ║
    ║         │                              ║    ║        ▼                               ║
    ║         ▼                              ║    ║  ╭─────┴──────╮    ╭───────╮           ║
    ║  ╭──────┴───────╮                      ║    ║  │   Token    │───▶│  API  │           ║
    ║  │AgentGenerator│                      ║    ║  │ + Policy   │    │ Auth  │           ║
    ║  │    Agent     │                      ║    ║  ╰────────────╯    ╰───┬───╯           ║
    ║  ╰──────┬───────╯                      ║    ║                        │               ║
    ║         │                              ║    ║                        ▼               ║
    ║         ▼                              ║    ║                  ╭─────┴─────╮         ║
    ║  ╭──────┴───────╮    ╭──────────╮      ║    ║                  │   Index   │         ║
    ║  │    Policy    │───▶│  Agent   │      ║    ║                  │  Search   │         ║
    ║  │   (rules)    │    │          │      ║    ║                  ╰─────┬─────╯         ║
    ║  ╰──────────────╯    ╰────┬─────╯      ║    ║                        │               ║
    ║                           │            ║    ║                        ▼               ║
    ║                           ▼            ║    ║                  ╭─────┴─────╮         ║
    ║                      ╭────┴─────╮      ║    ║                  │  Filter   │         ║
    ║                      │  Token   │──────╫───▶║                  │  Policy   │         ║
    ║                      ╰──────────╯      ║    ║                  ╰─────┬─────╯         ║
    ║                                        ║    ║                        │               ║
    ╚════════════════════════════════════════╝    ║                        ▼               ║
                                                  ║                  ╭─────┴─────╮         ║
                                                  ║                  │  Answer   │         ║
                                                  ║                  ╰───────────╯         ║
                                                  ╚════════════════════════════════════════╝
The result is a system where natural language role definitions get translated into deterministic access control. Agents only see what they're authorized to see, with no way to circumvent the restrictions. You get the flexibility of describing roles in human terms, with the security guarantees of explicit, enforceable policies.
