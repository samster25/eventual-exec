Daft GTM Internal Memo
Team — as we step into 2026, it’s worth taking a clear-eyed look back at 2025. Here is a GTM perspective to help us all own the lessons learned and understand the opportunity that lies in front of us.
Where we started (and what we learned)
We began 2025 believing the big commercial wedge would be training data curation. That hypothesis was partially validated. Daft OSS is real. Apple pays us a lot, ByteDance champions adoption in China, and EssentialAI leveraged Daft at true pretraining scale.
But we also felt something in our gut: “being better than Spark/Ray” wasn’t working. The frontier teams we most wanted to onboard (OpenAI, Anthropic, Thinking Machines etc.) already had deep internal expertise. OSS adoption was growing, but not compounding into something we could use for product-led GTM.
So midway through 2025, we sharpened focus and shifted to AI ingestion pipelines — with a clearer customer: not researchers, but SWE teams building retrieval/search systems.
The hard GTM lessons (2025)
We got early interest (Notion, Noon, Patreon, SafetyKit) around a pattern: teams onboarding Turbopuffer needed help computing embeddings and writing data into their index.
But here’s the truth: these didn’t convert into meaningful pilots or usage, and we need to own why.
Lesson 1: Indexing infrastructure wasn’t the pain.
Embedding compute is cheap so cost optimization isn’t compelling. “Map-only GPU workloads” are a commodity. Once people have something “good enough”, our product becomes a “nice-to-have”.
Teams pay a lot for Turbopuffer. But it’s a lot harder for them to build a production-grade database themselves than it is to build a “good-enough” data pipeline. Existing solutions (Daft, Spark, Ray Data, Modal, or even just EC2) all provide a good-enough mechanism for writing a UDF and running it in parallel.
Lesson 2: Customers wanted outcomes, not better legos.
The questions weren’t “how do I run indexing faster?” They were: What embeddings should we use? How do we handle images? Is a VectorDB even the right approach? We didn’t have a strong enough answer. “We improve indexing” doesn’t land. “We help your agents access data dramatically better” might.
[Pause Here]
Lesson 3: We were late to the narrative.
RAG had tailwinds in 2023; in 2025 it faced headwinds (“filesystem is all you need,” “agentic search > embeddings”). Teams weren’t excited to revisit embedding pipelines — but they were excited to talk about what comes after RAG. That’s where we earned some conversations (Cursor, Harvey): bring “alpha,” show better outcomes, and prove it with evals they actually care about.
The Opportunity
In 2026, we will take on customer problems with clear high-value revenue signals, and a crisp value proposition tied to end outcomes.
Two directions push us toward more valuable product value propositions:
Move Upstream: Data connectors
Secure, privacy-preserving sync from platforms like OneDrive, SharePoint, Slack, Notion — a “data clean room” problem. This is hard, messy, and high-value (convos: Rogo, Nomic, Wordware).


Move Downstream: own the end outcome
Customers don’t want a pipeline. They want a better AI system. And specifically in 2026, we think that they will want better AI Agents.


Rogo: give me research agents that can surface datasets from the data
Flatiron Health: RAG is hard to evaluate and issues are difficult to triage
Cursor: agent trace data is temporal + conversational and hard to use for better agents
AI in 2026 will be defined by agents. We’re early, this stuff just started getting really good and not just another buzzword in Q4’25. We think that option (2), while being the more ambiguous one, represents a tremendous opportunity for us to really build for.
Our job now is to deeply understand what breaks in agentic products — then leverage our unfair advantage: large-scale, unstructured data systems, built over the last four years, applied to the problems that matter for teams using or trying to build AI Agents.


