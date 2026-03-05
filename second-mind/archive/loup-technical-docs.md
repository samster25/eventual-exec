---
title: "Loup — Agentic Search Index (Technical Reference)"
created: 2026-03-05
updated: 2026-03-05
status: reference
related:
  - "[[phase-hackathon]]"
  - "[[mcp-tools]]"
---

# Loup — Agentic Search Index System

**Status:** reference
Built during the hackathon phase (Jan 20 - Feb 2, 2026).

## Three Main Components

### 1. Agentic Search Agent
ReAct-style THINK -> SEARCH loop. Iterative reasoning where the LLM decides when to search, formulates queries, and can iterate multiple times.

- **Hybrid search** (default) for general queries
- **Text search** for exact terms like identifiers or error messages
- **Vector search** for conceptual questions about relationships and meaning
- Results tracked with [1][2][3] citations, deduplicated across iterations
- Agent answers using only information from search results — never external knowledge

Key files: `loup-index/src/core/agent.py`, `loup-index/src/core/llm.py`

### 2. Agent Roles (Natural Language -> Policy)
Role descriptions in plain English -> Claude-powered AgentGeneratorAgent -> glob-pattern rules.

- Follows principle of least privilege — only grants permissions implied by the role description.
- AgentGeneratorAgent explores available resources using `list_resources` tool.
- Discovers what exists in the index and generates appropriate policies.
- Human-reviewable before enforcement.

Example: "Engineering team member who needs access to code reviews and documentation" becomes `allow: org.engineering.**` with `default: deny`.

Key file: `loup-index/src/core/agent_generator.py`

### 3. Access Control (Deterministic Enforcement)
First-match-wins policy checker. Entirely deterministic at runtime.

- **Rules:** Ordered list with action (allow/deny), paths (glob patterns), permissions (read/write/delete/admin).
- **Glob patterns:** `*` matches one segment, `**` matches any depth.
- **Fail-closed by default:** Default deny, malformed policies return 403.
- **Multi-layer enforcement:** Rust API validates tokens -> Python index middleware decodes policy -> search results filtered before LLM sees them.

Key files: `loup-index/src/core/policy.py`, `loup-api/src/state.rs`, `loup-index/src/server/app.py`

## Key Innovation
Combines "vibes" (natural language role descriptions) with deterministic policy enforcement. The human describes the role; the machine handles the policy mechanics. Agents literally cannot access what they're not authorized to see.

**Source:** [[source-documents/product-docs/loup-technical-docs.md]]
