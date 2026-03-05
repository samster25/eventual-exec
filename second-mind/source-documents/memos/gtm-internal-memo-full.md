Daft GTM Internal Memo
In 2025 we tested two GTM theses for Daft. We got real validation, but also clear signals that our current wedge won’t scale. This memo summarizes what we learned and what it implies for a pivot in 2026.
H1 2025: Training data curation as our AI beachhead
Thesis: Training dataset curation would be the dominant AI data-systems workload (pre-“agent” mainstreaming, when training data quality felt like the primary lever).
Signals it was real:
Apple paid for and adopted Daft
ByteDance promoted internal usage
EssentialAI ran Daft at meaningful scale for training data workflows
Where it broke:
Frontier labs didn’t adopt Daft OSS at scale (Anthropic/OpenAI/xAI/Thinking Machines/Cohere relationships weren’t enough). Many had built equivalents in-house or staffed strong data systems teams.
Monetization was structurally hard: too few labs doing this at the required scale; broader OSS user base didn’t translate into repeatable design partners.
In the Ray ecosystem, distribution beat technology: Ray Data “good enough + pre-installed” often won over Daft OSS.
Implication: Training data curation is a real workload, but not a scalable GTM wedge for us (limited buyer universe + strong in-house tooling + weak pull to switch).
Q3 2025: Reframing to “indexing data for AI”
We asked: if recommender systems + analytics drove Spark, what breakout workload drives Daft?
We identified three opportunities:
Training dataset construction (what we had been doing)
Unstructured/multimodal analysis (extraction before analytics) — deprioritized due to weak defensibility vs Snowflake/Databricks/BigQuery OLAP + AI function ecosystems
Ingestion for AI (indexing data to enable retrieval) — where we doubled down
Q3–Q4 2025: “AI ingestion pipelines” and Daft Cloud
New ICP: SWEs building retrieval/search systems that run LLM-based transformations in the ingestion path.
GTM shift: from OSS-first PLG to direct outbound.
Initial value props:
Serverless operations
Managed inference (429s/GPU wrangling)
Versioned, git-powered workflow
This refocusing of the use-case brought much needed clarity.
Product: the Ideal Customer Profile (ICP) narrowed greatly from “anyone who runs Daft”
Engineering: prioritized sources/sinks, workload expectations, and how to handle inference
GTM: switched gears from an OSS-first PLG strategy to direct outbound, skipping the need for Daft OSS adoption as an intermediate requirement
What we learned (the big takeaways)
Indexing infra is not the core pain.
In practice, teams can assemble indexing pipelines with whatever their infrastructure provider of choice is with relative ease.
Exa/Suno: Modal for online custom embedding models
Notion: Ray Data for Python GPU batch jobs
Patreon: Spark for loading lakes + calling hosted endpoints + Workarounds for provider rate limits (429s)
Etsy: Dataflow for orchestration + Gemini APIs and LiteLLM for 429 issues
Rogo: “if you’re just offering parallelization, we’re not interested – our engineers have solved that”
“Indexing but easier/faster” isn’t enough to earn a switch. Distribution and “good enough” stacks win unless we deliver step-function ROI.
The problem is how to build good search (design + iteration on signals), not what infra to use
Teams described their problem as hard because it’s genuinely hard to build good search/data systems overall. We consistently heard questions around:
Patreon, SafetyKit: What embeddings do you suggest?
Notion: How do we search images?
Moreover, we found ourselves getting tripped up when thinking about how to allow users to retrieve the indexed data if they were using a custom embedding model on our batch inference  (see: Patreon call). As an indexing-only product, we were only a part of the overall solution that these teams wanted.
As a pure indexing-only (no retrieval!) solution, we are not able to deliver the end outcome which is truly desired by the customer: a better search system for AI.
Data volumes are small (for now), so “cost of indexing” is weak positioning
For customer support agents and many coding agent scenarios, datasets are MBs, not TBs. “The revenue opportunity is in the generative workloads, not discriminative ones” (Karan @ Cartesia).
We placed a bet that there would be many more teams actively generating signals (e.g. what color is this shirt, please caption this image). However, aside from the Etsy scenario, this turned out to not really be the case.
Patreon: $10,000 for one run of embeddings through all the data
Noon: $1,000 for one run of embeddings through all the data
Harvey: our embedding pipeline cost is dwarfed by the “AI document reviews” functionality
Embedding is such a cheap workload that teams don’t bother optimizing cost in this component. Some teams are running generative workloads (e.g. Harvey reviews functionality) but they simply use normal microservices for that. We need to anchor to a higher value problem.
Macro headwinds: semantic search / “vector DB as the product”
In 2025, AI coding agents drove mindshare, and many leaders shifted from “RAG over vectors” to tool-based/agentic retrieval (grep/bash, structured tools). The vibe became “RAG is dead.”
“We make RAG easier” is not a compelling headline. We need to anchor to the modern conversation around agents to drive GTM traffic.
Customer segmentation matters: not all “AI teams” are the same buyers
We can roughly segment into:
Agent Labs (frontier builders such as Cursor, Claude Code, Suno, Notion, Wordware): strong eng, built in-house pipelines; will talk if we have a differentiated take (they chase alpha).

However, Daft Cloud today isn’t interesting for them as they aren’t investing anymore into their code chunking/embedding pipelines – that’s work that they did 2 years ago. They are exploring the next generation of techniques now (agentic search etc) to get that next edge over the competition.
Vertical AI startups (Harvey, Rogo, Noon): adopt frontier patterns later; care about product UX, shipping velocity and “it just works” more than absolute SOTA performance.

Harvey: “we would rather optimize for a product that can scale to 100M lawyers instead of hyper-optimizing the product right now by trying new embeddings from Voyage”. This is why they are migrating off of Lance to Turbopuffer.
Mid-tier tech (Etsy, Patreon, …): LLMs and AI adoption is incremental; they’re attached to existing platforms; procurement patterns differ.

They have existing ways of doing things (RecSys, Search, Analytics etc) and existing commitments to platforms such as Spark/Ray. Any new initiative is first met with: “can we do this on our existing vendor?” and unless there is a compelling reason (cost/capability) they will not learn and adopt something new.
Our GTM strategy must match a segment. “Everyone with unstructured data” is not a market.
Where we feel pull
We felt pull to go further upstream in terms of data sources: S3/Parquet is insufficient. We found teams that wanted help with going further upstream to OneDrive/Sharepoint (Rogo, Nomic), Slack/Notion (Wordware) etc. Syncing data from 3rd party platforms is a pain-point and a challenge to do in a reliable, privacy-preserving way.


We feel pulled to go downstream: teams don’t know what to do with just the vector DB. They want an end solution.
Rogo wants agentic deep-research style “web datasets” on sharepoint (not a search endpoint!)
Flatiron Health is investing into embeddings, but still worries about not being able to evaluate or improve this system without involving biology experts manually sift through the data and agent traces
Cursor wants a solution that can resolve the temporal nature of agent trajectories and conversations, so that they can incorporate this external source of data into their agent.


Performance/speed: Cursor is prioritizing faster agents. Overall, agents are slow and cost a ton of money.

