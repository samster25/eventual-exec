Customer Conversations
ICP: vertical b2b companies building AI/Agentic products (Nomic, Zendesk, Wordware, Rogo)
We are seeing a use-case around search over your customer’s data
Zendesk has forward-deployed engineers maintaining integrations to sync their customers’ order data etc to power their agents – “data integration is the biggest problem today”
Nomic syncs terabytes of customer files and documents – “indexing everything is infeasible”
Access control and permissioning is difficult to get right
Customer datasources + sync mechanism
Agentic search to power a search API
Search API is used by end user's agents
The pain-points we solve here:
Difficult to build and maintain these custom data connectors to sync data
Privacy/permissioning is tricky to get right in a way that inspires trust from customers
Difficult to build good information retrieval for agents over these data sources
Open Questions
What is the best way to retrieve this context/data for an AI Agent? Natural language vs MCP vs API vs filesystem vs subtask…
Knowledge – what does this mean and does this even improve our evals? Traces may be useful to bootstrap this knowledge component, but we will likely have to grow into this over time.
Things to work on

[Sam/Srinu/Rohit]		[Colin, YK]			[Team 3]
Realtime Sync 	-> 	Search Engine 	-> 	Agent Builder
			[Conner/Desmond]
			End to end observability
[Team 3] Build an agent and Evals using context / knowledge…
GTM 
Ops/Cost
Recruiting
Oncall
Methods for retrieving knowledge [Colin, YK]
Try Methods?
Baseline on RAG Library
Hosted RAG solutions (e.g. Ragie.ai and Shaped)
Expose tools to end agent
APIs
MCP
Tools
Knowledge Sandbox

Real Time Durable Sync from data sources [Sam, Srinu, Rohit]
Sources TBD -> realtime -> update librarian
Look into hosted observability solutions (Braintrust, Wandb, Langsmith) and see if we can invest in those instead of building out our own for running Evals and understanding how to make agents better with knowledge [Team 1]

