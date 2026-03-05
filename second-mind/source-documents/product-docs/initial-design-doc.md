 **\[Draft\] Context Layer**

## **The Knowledge Layer for Agentic AI**

*WorkOS for auth. Plaid for finance. Context Broker for knowledge retrieval.*

---

## **Problem**

Agent Builders (ABs) need access to their customers' (Agent Customers \- ACs) data to power vertical AI workflows. Today, this means:

* Custom integrations per data source, per customer
* Syncing entire datasets (expensive, stale, compliance nightmare)
* No permission granularity \- either all-or-nothing access
* Agents hallucinate when they lack context but can't request more

---

## **Solution**


**Key insight**: Don't sync data blindly. Let agents query what they need, with AC-controlled permissions, and evolve from returning raw information to synthesized knowledge.


![][image1]

\[Figure 1: System Architecture\]

---

## **How It Works**

### **For Agent Builders**

Integrate once via SDK. Expose tool calls to your agents:

* **Natural language search** across customer's connected sources
* **Vector and full-text search** for precise retrieval
* **Sandboxed tool execution** (grep, glob, cat on permissioned filesystem abstraction)
* **Permission escalation** when agents need more context

### **For Agent Customers**

1. **Connect** \- OAuth into data sources (GitHub, Salesforce, GDrive, Linear, etc.)
2. **Approve** \- Review and approve AB permission requests
3. **Control** \- Set policies, revoke access, audit agent queries

---

## **Core Capabilities**

**Unified Connectors** \- Pre-built integrations to common SaaS, code repos, and file storage

**Permissioned Indexing** \- Store/index in AC's cloud or ours; AC controls data residency

**Multi-Modal Search** \- NL search, vector search, full-text search, structured queries

**Agent Sandbox** \- Expose filesystem-like tools (glob, grep, cat) scoped to permissions

**Consent Flow** \- AC approves AB access; runtime escalation for missing permissions

**Knowledge Evolution** \- Learn from queries → build proprietary indexes → deploy sub-agents

---

## **System Architecture**

![][image2]

\[Figure 2: System Architecture\]

The platform consists of six layers:

**API Gateway** \- Rate limiting, AB authentication, request routing

**Query Engine** \- Four query modes: Natural Language Search (LLM \+ reranking), Vector Search (embeddings), Full-Text Search (BM25), and Agent Sandbox (glob, grep, cat)

**Access Control Engine** \- Permission intersection between AB requests and AC approvals, scope enforcement, audit logging

**Index & Storage Layer** \- Vector indexes, full-text indexes, metadata store, and cache. Can be hosted by Context Broker or in AC's own cloud/S3 bucket.

**Knowledge Evolution Layer** \- Query logging and analytics, feedback learner (Q→A pairs), and Knowledge Agent for multi-hop reasoning and synthesized answers

**Connector Infrastructure** \- Pre-built connectors to GitHub, Salesforce, GDrive, Linear, Notion, Slack, and more

---

## **Permission & Consent Flow**

1. AB registers their app and defines required permission scopes
2. AC connects their data sources via OAuth (similar to Plaid Link experience)
3. Context Broker presents AB's permission request to AC
4. AC approves or modifies the requested scopes
5. AB's agent queries data via SDK
6. Results are scoped to approved permissions only
7. If agent needs more context, it triggers an escalation request
8. Escalation request is sent to AC for approval
9. AC approves or denies the expanded access
10. Agent receives expanded results or denial with reason

![][image3]

\[Figure 3: Goal Access Flow\]

---

## **Knowledge Evolution Roadmap**

**Phase 1: Raw Information** \- Federated search across AC sources. Pass-through queries to source APIs.

**Phase 2: Indexed Information** \- Proprietary embeddings and retrieval infrastructure per AC. Unified ranking across sources, cross-source retrieval, lower latency.

**Phase 3: Curated Knowledge** \- Learn from query patterns, cache common answers, tune retrieval based on agent workloads.

**Phase 4: Synthesized Knowledge** \- Our sub-agent reasons over AC data and returns answers, not documents. Multi-hop reasoning handled internally.

![][image4]\[Figure 4: The Path to Knowledge\]

---

## **Competitive Positioning**

**vs RAG-as-a-Service (Pinecone, Weaviate)**: They're single-tenant. No B2B2B model, no AC consent flow, no agent-native tools like sandbox and escalation.

**vs iPaaS (Zapier, Merge)**: They're CRUD-focused, not retrieval-focused. No consent flow, no knowledge evolution, no agent-native design.

**Context Layer differentiators**: First-class B2B2B model, built-in consent flow, agent-native tools (sandbox, escalation), and learning layer that evolves from information to knowledge.

---

## **Open Questions**

1. **Pricing model** \- Per query? Per AC seat? Per indexed GB?
2. **Data residency** \- How much complexity to support AC-hosted indexes?
3. **Real-time sync** \- Webhooks vs polling vs hybrid per connector?
4. **Knowledge agent liability** \- Who's responsible when our agent gives wrong answers?
