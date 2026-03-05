# Product

[Requirements Gathering](https://www.notion.so/Requirements-Gathering-2fd091bd8634806d8537d4d5ee27d85f?pvs=21)

## ICP

- Building an AI Agent (defined as a system that non-deterministically and dynamically decides what tools to call and actions to take using AI)
- Series Seed — C, founded after ChatGPT (2022): small enough to be running large amounts of experiments with agents
- Data-heavy domains (legal, finance, healthcare, customer support, workplace productivity)
- Agents work over “private” data (not just working over publicly available web data)
- **Segments:**
    - Legal (lots of documents)
    - Finance (lots of documents)
    - Insurance (lots of documents)
    - Build-your-own-agent (lots of integration required)
    - Logistics (lots of docs like invoices)
    - Customer support (lots of per-customer context)
    - Sales/Marketing (ingesting past marketing and sales assets)
    - Recruiting (internal context to make JDs?)
    - Voice Agents (NEEDS VALIDATION)
    - Healthcare (NEEDS VALIDATION)
    - Cybersecurity (NEEDS VALIDATION)

## Problem Statement

It is difficult to build agents that rely on “private” data sources for context. This is data that isn’t publicly available (e.g. on the web) and is only accessible via tightly controlled authorized permissions for internal business consumption.

- **Permissioning:** it is difficult to scope data access for AI Agents on unstructured data purely with existing mechanisms (predominantly application-specific auth and MCP/Skills)
- **Context:** it is difficult to balance between context rot and having effective context for agent operation when building your own search engine
- **Search federation:** relying on the underlying systems’ search capabilities (e.g. Box, Google Drive, Notion, Slack search) fundamentally limits agent performance and means that the agent needs to understand how to operate these systems intimately
- **Building/maintaining data connectors:** the adoption of your product is fundamentally limited by the speed at which your team can build data connectors to enterprise data sources

## Unique Value Propositions

- **Reliable data syncing with zero operational overhead:** effortlessly connect data sources for ingestion into your agent’s context engine
- **Scoped data access:** agents only have access to data based on both ACL and semantic access policies that data owners have configured
- **Understands both structured as well as unstructured data:** Eventual’s search agents operate over both structured database tables/JSON/CSV/data lakes as well as unstructured document-based data
- **Search performance that improves over time:** Eventual constructs a context graph during ingestion, understanding pattens inherent in the unstructured data as well as the agents’ queries to power cheaper, faster and more relevant research results that improves over time and usage
- **Agent-native:** plugs directly in to your agents and provides search-specific metrics for you to eval your agents by drilling down into search metrics and audit trails

## Competitive Analysis

1. **Vector DBs**: require assembling your own pipelines and tuning your own search + a keen understanding of how to do this well. Also lots of problems around “hybrid search” and using metadata effectively to reduce the search space
2. **RAG-in-a-box:** solves the ingestion problem, but you end up with a vector DB at the end of the day. See: problems with vector DBs
3. **Graph Databases:** most of the work ends up being defining the appropriate schema/ontology for the data, which is very difficult to know upfront
4. Competitor: 
    1. Merge (for scoped auth on integrations)
    2. Cognee for agent ( knowledge / context graph layer ) 

## Key Conversations

- Nomic
- Alphasense
- Notion
- Flatiron
- Wordware
- Rogo
- Zendesk