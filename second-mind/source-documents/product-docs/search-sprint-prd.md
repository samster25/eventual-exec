# Eventual: Product Requirements Document

**Version:** 0.1 (Draft)
**Date:** February 4, 2026

---

## 1. Executive Summary

Eventual is a context platform for AI agents. We enable Agent Builders to connect their agents to their customers' data sources, enforce access policies, and give their agents the context they need to perform better.

Agent Builders integrate once. Their customers connect their data sources (GitHub, Slack, Notion, Salesforce, etc.) via OAuth. Eventual handles ingestion, indexing, access control, and observability. The agent gets better context. The customer stays in control.

---

## 2. Problem Statement

**Agent Builders have a context problem.**

AI agents are only as good as the context they have. To build a great agent for legal document review, customer support, or sales intelligence, you need access to your customer's private data: their repos, tickets, docs, and conversations.

Today, Agent Builders face a painful choice:

1. **Build it yourself** - Write custom integrations for each data source, each customer. Handle OAuth flows, data syncing, permission scoping, and compliance. This takes months and distracts from building the actual agent.

2. **Go without** - Ship an agent that can't access customer data. It hallucinates more, misses context, and loses to competitors who solved the data problem.

**The B2B2B complexity makes this harder.**

This isn't a simple two-party problem. There are three parties:
- **Agent Builder (AB):** Building the AI product
- **Agent Customer (AC):** Using the AI product, owns the data
- **End User:** Interacting with the agent

The Agent Builder needs the Agent Customer's data. But the Agent Customer needs to control what the agent can see, audit what it accessed, and revoke access if needed. There's no good infrastructure for this today.

---

## 3. Why Existing Solutions Fall Short

**RAG-as-a-Service (Pinecone, Weaviate, etc.)**
- Single-tenant architecture - no B2B2B model
- No consent or permission flow for data owners
- You still build all the connectors yourself
- No agent-native features (policies, audit, observability)

**iPaaS (Zapier, Merge, etc.)**
- CRUD-focused, not retrieval-focused
- Built for workflows, not agents
- No semantic search, no intelligent navigation
- No access control beyond source-level OAuth

**Raw MCP**
- Each server has its own auth model - no unified policies
- No virtual addressing (can't define resources the upstream doesn't expose)
- No cross-source observability
- Agent Builder still assembles everything themselves

**The common thread:** None of these solutions optimize for retrieving the most relevant documents efficiently. When agents can't find what they need quickly, they wander—consuming more tokens, taking longer, and costing more. Better retrieval means lower token usage, faster agents, and reduced costs.

---

## 4. Our Unique Insight

**Don't be the bottleneck. Be the navigation layer.**

Retrieval quality depends heavily on the data source and how searchable it is. Searching Slack conversations is fundamentally different from searching Google Drive documents or GitHub issues. One-size-fits-all retrieval doesn't work.

When you can address and retrieve the most relevant documents, agents use fewer tokens, run faster, and cost less. Our approach helps agents *navigate* data sources efficiently:

1. **Virtual Addressing** - We present a unified resource namespace to agents. We can define resources that upstream sources don't natively expose (e.g., "all Slack threads mentioning customer X" even if Slack's API doesn't support that query).

2. **Natural Language Policy Generation** - Define roles in plain English ("Customer support agent who can see tickets but not internal Slack"). Eventual generates a traditional ACL with glob-pattern rules that you can review and enforce.

3. **Navigation, Not Synthesis** - We index for fast retrieval and direct the agent to relevant resources. The agent retrieves the raw data and reasons over it. Our quality doesn't cap theirs.

4. **Simplicity Through Consolidation** - Without Eventual, agents connect to M different MCP servers, each with its own auth model, failure modes, and rate limits. With Eventual, there's one integration point. This isn't just simpler—it's more reliable. Agent Builders stop debugging MCP auth issues and start shipping features.

**The business unlock:** Agent Builders who use Eventual can support more customer integrations (faster GTM) and offer enterprise-grade access control (larger deals). We expand their addressable market.

---

## 5. Solution Overview

Eventual is the context platform between Agent Builders and their customers' data.

```
┌───────────────────────────────────────────────────────────────────────────┐
│                            AGENT CUSTOMER                                 │
│  ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐ ┌────────────┐              │
│  │ GitHub │ │ Slack  │ │ Notion │ │ Linear │ │ SharePoint │  ...         │
│  └───┬────┘ └───┬────┘ └───┬────┘ └───┬────┘ └─────┬──────┘              │
└──────┼──────────┼──────────┼──────────┼────────────┼─────────────────────┘
       │          │          │          │            │
       └──────────┴─────┬────┴──────────┴────────────┘
                        │ OAuth + Sync
                              ▼
                    ┌───────────────────┐
                    │                   │
                    │     EVENTUAL      │
                    │                   │
                    │  ┌─────────────┐  │
                    │  │ Connectors  │  │
                    │  ├─────────────┤  │
                    │  │    Index    │  │
                    │  ├─────────────┤  │
                    │  │  Policies   │  │
                    │  ├─────────────┤  │
                    │  │ Observability│ │
                    │  └─────────────┘  │
                    │                   │
                    └─────────┬─────────┘
                              │ API / MCP
                              ▼
                    ┌───────────────────┐
                    │   AGENT BUILDER   │
                    │                   │
                    │  ┌─────────────┐  │
                    │  │   Agent     │  │
                    │  └─────────────┘  │
                    └───────────────────┘
```

**How it works:**

1. **Agent Builder** integrates Eventual SDK/API into their product
2. **Agent Customer** connects their data sources via OAuth (Plaid Link-style experience)
3. **Agent Builder** defines access policies (hard rules or natural language policy generation)
4. **Agent** queries Eventual for context, receives policy-filtered results
5. **Everyone** can audit what was accessed

---

## 6. Core Capabilities (V1)

### 6.1 Data Connectors & Ingestion

Pre-built connectors to common enterprise data sources:
- **Code:** GitHub, GitLab
- **Docs:** Notion, Google Drive, Confluence
- **Communication:** Slack, Microsoft Teams
- **Project Management:** Linear, Jira, Asana
- **CRM:** Salesforce, HubSpot

Each connector handles:
- OAuth flow for Agent Customer authorization
- Incremental sync (webhooks where available, polling otherwise)
- Schema normalization into unified resource model

### 6.2 Agentic Search & Navigation

A search interface designed for agents, not humans:
- **Hybrid search:** Vector + full-text + structured queries
- **Multi-turn navigation:** Agent can drill down, go wide, refine
- **Resource references:** Results include URIs for raw data retrieval
- **Cross-source:** Single query spans all connected sources

Key principle: We help the agent find what it needs, then get out of the way. The agent retrieves and reasons over raw data.

### 6.3 Access Control

Two layers of policy enforcement:

**Hard Rules (Deterministic)**
- Glob-pattern policies: `allow: org.engineering.**`, `deny: org.hr.salaries`
- First-match-wins evaluation
- Fail-closed by default

**Natural Language Policy Generation**
- Natural language role definitions: "Customer support agent who can see tickets but not internal Slack"
- Translated to hard rules by our policy generator agent
- Human-reviewable before enforcement

**Enforcement:**
- Policies evaluated at query time
- Results filtered before agent sees them
- Agent cannot access what it's not authorized to see

### 6.4 Observability & Audit

Full visibility into agent data access:
- **Query logs:** What did the agent ask for?
- **Access logs:** What was returned vs. denied?
- **Token metrics:** How much context is being consumed?
- **Policy hits:** Which rules are firing?

Enables Agent Builders to debug and optimize. Enables Agent Customers to audit and trust.

---

## 7. User Journeys

### Agent Builder Journey

1. **Integrate** - Add Eventual SDK, configure API keys
2. **Embed Connect Flow** - Drop in our OAuth component for customer onboarding
3. **Define Policies** - Set default access rules, create role templates
4. **Ship** - Agent queries Eventual for context during operation
5. **Observe** - Monitor query patterns, optimize retrieval, debug issues
6. **Expand** - Request new connectors, unlock new customer segments

### Agent Customer Journey

1. **Connect** - OAuth into data sources via Agent Builder's product
2. **Review** - See what access the agent is requesting
3. **Approve** - Grant scoped permissions (not all-or-nothing)
4. **Use** - Interact with the agent, which now has better context
5. **Audit** - Review what the agent accessed (if desired)
6. **Revoke** - Remove access at any time

---

## 8. Success Metrics

For Agent Builders using Eventual:

| Metric | Why It Matters |
|--------|----------------|
| **Reduced token usage** | Navigation layer directs agent better, less wandering |
| **Reduced agent latency** | Faster retrieval, fewer round-trips |
| **Reduced improper data access** | Policies prevent overfetch and leakage |
| **More integrations shipped** | Connectors are pre-built, not custom |
| **Larger deal sizes** | Enterprise-grade access control unlocks bigger customers |

---

## 9. Ideal Design Partner Profile

We're looking for design partners who can help us build the right product while we help them ship faster.

### Characteristics of a Good Partner

- **Building agents in production** - Not prototypes. Real agents serving real users.
- **Knows how to evaluate agents** - Has metrics, evals, feedback loops. Understands what "better" means for their use case.
- **Wants more customer context** - Believes their agent would improve with access to customer data sources.
- **Data-heavy domain** - Legal, finance, customer support, sales, recruiting. Lots of documents and context.
- **Series Seed to D** - Small enough to move fast, big enough to have real customers.

### Red Flags

- **Too big** - Will build it themselves, too slow to iterate with us
- **Too early** - No real customers, no real data to connect
- **Workflows, not agents** - Hardcoded sequences masquerading as AI. We need partners building systems that dynamically decide what tools to call based on context.

### What We Learn From Partners

Our team has deep systems engineering expertise but limited production agent experience. We want partners who can teach us:
- How they evaluate agent performance
- What "good context" looks like for their domain
- Where retrieval quality matters most

---

## 10. Design Partnership Structure

### Terms
- **Duration:** 3 months
- **Cost:** Paid engagement (validates real pain)
- **Cadence:** Weekly syncs + async feedback channel

### Phase 0: Discovery (Week 1)

Before building, we interview the partner's team to understand:
- What agents are they building? What do those agents need to do well?
- How do they evaluate agent performance today?
- What data sources do their customers have? Which are highest priority?
- What access control requirements do their enterprise customers ask for?
- What have they tried? What's worked, what hasn't?

This shapes the milestones for the rest of the engagement.

### Milestones

Based on discovery, we agree on concrete milestones. Example structure:

| Milestone | Deliverable | Timeline |
|-----------|-------------|----------|
| M1: Core Integration | SDK integrated, basic search working | Week 3 |
| M2: Priority Connectors | 2-3 connectors partner needs most | Week 6 |
| M3: Policy Enforcement | Partner can define and enforce policies | Week 9 |
| M4: Production Ready | Observability, hardening, docs | Week 12 |

### What We Deliver
- Priority connector development for their data sources
- White-glove integration support
- Custom policy templates for their use case
- Roadmap influence

### What They Deliver
- Real production use cases to test against
- Agent expertise and evaluation frameworks
- Honest feedback on what's working and what's not
- Intent to convert to commercial contract

### Success Criteria

At the end of 3 months:
1. Their customers can connect data sources through our flow
2. They can define policies that we enforce
3. Our system integrates cleanly into their agent
4. We observe measurable improvement in: token usage, agent time, or data access accuracy

---

## 11. Technical Architecture (High-Level)

```
┌─────────────────────────────────────────────────────────────────┐
│                         API GATEWAY                             │
│              (Auth, Rate Limiting, Request Routing)             │
└─────────────────────────────────┬───────────────────────────────┘
                                  │
        ┌─────────────────────────┼─────────────────────────┐
        │                         │                         │
        ▼                         ▼                         ▼
┌───────────────┐       ┌─────────────────┐       ┌───────────────┐
│    SEARCH     │       │     POLICY      │       │  OBSERVABILITY│
│    ENGINE     │       │     ENGINE      │       │               │
├───────────────┤       ├─────────────────┤       ├───────────────┤
│ Hybrid Search │       │ Rule Evaluation │       │ Query Logs    │
│ Vector Index  │       │ NL Policy Gen   │       │ Access Logs   │
│ Text Index    │       │ Scope Enforce   │       │ Metrics       │
└───────┬───────┘       └────────┬────────┘       └───────────────┘
        │                        │
        └────────────┬───────────┘
                     │
                     ▼
        ┌────────────────────────┐
        │    INDEX & STORAGE     │
        │                        │
        └────────────┬───────────┘
                     │
                     ▼
        ┌────────────────────────┐
        │  CONNECTOR FRAMEWORK   │
        ├────────────────────────┤
        │ GitHub │ Slack │ Notion│ ...
        └────────────────────────┘
```

### Core Abstractions

Agent Builders interact with Eventual through these key abstractions:

| Abstraction | Description |
|-------------|-------------|
| **Source** | A connected data source (GitHub org, Slack workspace, Notion space). Created when Agent Customer completes OAuth. |
| **Resource** | An addressable unit within a source (repo, channel, document, ticket). Resources form a hierarchy that can be queried and filtered. |
| **Agent Role** | A named identity with associated policies. Agent Builders create roles for different use cases (support bot, sales assistant). |
| **Policy** | Rules governing what a role can access. Can be hard rules (glob patterns) or generated from natural language descriptions. |
| **Query** | A search request from the agent. Includes query text, role context, and search parameters. |
| **Session** | Optional multi-turn context. Allows agents to drill down, refine, and navigate across queries. |

### Key Design Principles

- **Policy enforcement at the index level** - Filters applied before results reach the agent. No leakage through the intelligence layer.
- **Serverless, managed deployment** - We run the infrastructure. Future: options for customer-owned storage.
- **MCP-compatible** - Can act as an MCP server, proxying to upstream sources with unified policy enforcement.
- **Single integration point** - Agent connects to Eventual once, gets access to all sources. No M×N complexity.

---

## 12. Open Questions / Roadmap

### Near-Term (V1.1)
- **Semantic Policy Enforcement** - Beyond allow/deny. Define policies like "summarize compensation discussions without revealing specific numbers" or "redact customer names from support threads." Content is transformed (redacted or summarized) to comply with the policy before reaching the agent.
- **More connectors** - Prioritized by design partner needs
- **Policy templates** - Pre-built roles for common use cases
- **Improved observability UI** - Dashboards for Agent Builders

### Medium-Term
- **Data residency options** - Agent Customer or Agent Builder owned buckets
- **Consent flow & escalation** - Agent can request expanded access at runtime, routed to AC for approval
- **Real-time sync** - Webhooks for all major sources

### Long-Term (Knowledge Evolution)
- **Query pattern learning** - Optimize retrieval based on what agents actually ask for
- **Cross-customer insights** - Aggregate patterns (privacy-preserving) to improve search quality
- **Specialized sub-agents** - Domain-specific retrieval agents that understand legal docs, support tickets, etc.

---

## Appendix: Glossary

| Term | Definition |
|------|------------|
| **Agent Builder (AB)** | Company building an AI agent product |
| **Agent Customer (AC)** | Customer of the Agent Builder, owns the data |
| **Virtual Addressing** | Unified resource namespace that can define resources upstream sources don't expose |
| **Natural Language Policy Generation** | Describe roles in plain English; Eventual generates traditional ACLs you can review and enforce |
| **Hard Rules** | Deterministic glob-pattern policies (allow/deny) |
| **Semantic Policy Enforcement** | Policy-aware transformation of content (redaction or summarization) before it reaches the agent |
