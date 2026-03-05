# Eventual (2026)

We’ve spent the last several weeks pressure-testing our strategy with teams across the industry. The market is shifting quickly, and we needed clarity on where durable value will be created.

# **The Search Team (Conner, Sam, Oliver, Colin \+ Sammy)**

Over the last month, we explored search from many angles. We felt a pull here because retrieval is now a core primitive for agents: agents dynamically pull information into their context window to plan and act.

But as we looked at “search-over-your-data” systems, we questioned what enduring value we could provide. Building connectors and improving search quality generically over our customers’ data felt uninspiring and hard to defend in a world where connectors could be vibe-coded and context windows were growing increasingly large.

We came to the conclusion that we are best positioned to build enduring value in one of two places:

* Build a database (e.g. Turbopuffer)  
* Build a search engine for a vertical (e.g. Juicebox people search)

Based on our early exploration with sales founders and teams, the “agent moment” for non-technical users is arriving fast. Teams are already experimenting with tools like OpenClaw and agents to do GTM workflows. And the world of People \+ Company search is surprisingly nascent: existing providers (e.g., Exa, Parallel) are early, and when we tried to use these services to power our own GTM agent, the results were poor.

So, we’re doubling down\! If there was ever an ambitious goal for us to rally around, this is it. Where is the largest amount of multimodal/unstructured compute happening today aside from training models? Organizing the world’s information.

**Eventual provides agentic search over People and Companies — the highest-quality deep search for any AI agent over specific entities.**

# **What stays the same**

**Daft stays open-source, and we will keep investing in it.** We’re doubling down on Daft as our unfair infrastructure advantage — the engine that lets us out-execute on the commercial product.

Just as Google’s product advantage was reinforced by an infrastructure bet (PageRank \+ MapReduce), we’re making a long-term bet on Daft: a purpose-built system for multimodal data processing that helps us iterate quickly on the signals and features required for world-class People/Company search.

# **What Changes**

* The commercial team will operate as **Eventual** and will be **3 people: Sammy, Jay, Colin**.  
* Everyone else will double down on **Daft**, led by Varun.  
* As we lay strong foundations, we’ll incrementally bring more folks onto Eventual.

## **Daft priorities**

1. **Eventual**  
2. **Apple**  
3. **ByteDance**  
4. **Rest of the community**  
    (+ one additional high-value prospect in progress)

DRIs for each workstream should build their understanding of requirements and roadmap by talking to key stakeholders across Eventual, Apple, ByteDance, and the community (via GitHub discussions).

Each thread:

	Half pager on the goals

Starting now:

* **Shuffles** (joins for entity resolution & dedup) – DRI: @Srinu \-  @Oliver, @Chris  
  * Characterizing flight shuffles vs legacy ray shuffles  
  * Shuffle Plugin \- putting in new shuffles  
  * Lineage tracking in for partitions for failures   
* **Observability** (debugging \+ dashboard) – DRI: @Sam  
  * OTEL compat \- Export metrics, logging and traces to an OTEL endpoint  
  * Perform post analysis \- Explains, analyze (Post query understanding of what happened)  
  * Dashboard \- Daft UI to understand failures, perf, etc  
* **Checkpointing** (towards incremental processing) – DRI: @Rohit  
  * Goal: Bytedance to decompose \- Hash Antijoin \+ Broadcast Join  
  * IP: Document to get requirements from Apple \+ Bytedance  
* **AI Functions** (LLM-powered transforms; efficient batch inference) – DRI: @Conner  
* **Community \+ Extensions** (drive arrow2 migration to completion, build in extension points and encourage community progress) – DRI: @Cory,  @Desmond  
  * Arrow2 migration  
  * Extension Points \- supporting new IO protocols (now supports OpenDAL)  
  * Native UDF \- Like plug in Rust Functions (leverage Datafusion FFI) \<DRI: Conner\>  
  * Native Table Sources like Lance Rust SDK  
  * Plug in packages for (UDFs, Sources, Sinks, etc)  
    * Import daft-my-co  
      * Registers everything…   
  * Extension points for Sinks

Later (TBD after mapping out resourcing and requirements with Varun and Sammy):

* Reliability and scalability (“Flotilla 2.0”) – \<Requires DRIs: @Srinu \+ @Sam \+ @Chris?\>  
* Custom model infrastructure – \<Requires DRI\>  
* Modality-specific primitives (docs/audio/video) – \<Requires DRI: @Desmond?\>  
* Streaming data sources (freshness) – \<Requires DRI\>  
* Upserts (for incremental updates – TBD?)

## **Eventual priorities**

1. **Build the flywheel:** dogfood our MVP by generating a lead list for our own GTM.  
    Example: “Find GTM/sales people trying to use agents for sales at companies that have raised \>$10M.”

2. **Build a list of champions:** identify the most agent-native salespeople already using tools like Claude Code / Claude Cowork / OpenClaw, and build a waitlist via a landing page.

3. **Stretch target:** build a tool that Jay can plug into Claude Code to show potential customers 5 strong leads for their team via a Loom video

# **FAQ**

1. **Can this even be done?**  
   Yes – we’ve learned that companies such as Ramp and Verkada have built internal versions of this system for their sales teams, and that is a crucial part of their success. I.e. Ramp outcompeted Brex somehow. Juicebox internally powers their search with something similar (they call it PeopleGPT).

2. **Why is this hard today?**  
   We surveyed the existing tools (Exa, Parallel, Crustdata) and they are catered for more generic web search/high level signals. Without knowing “search-for-what” it’s difficult to make it good. We just end up with generic descriptions of people rather than answers to specific questions (e.g. “is Jay or Sammy the better person to sell my accounting software to at Eventual?”).

3. **How is this different from the incumbents?**  
   The incumbents here aren’t actually Exa/Parallel – it’s actually systems such as Zoominfo, Clearbit etc. They are largely optimized for providing specific enrichments to the data (email addresses, headcount, address etc). The type of rich information that we think will be most useful for the agents will go beyond into something such as – what are someone’s key beliefs/theses about their industry etc.

4. **Is there an opportunity to expand beyond People and Companies?**  
   Yes – we think that this is the lowest-hanging fruit for us, but it is likely that the same data processing techniques we do here will generalize to other “entities/concepts” such as: Zipcodes, Stores, Addresses, Products etc. Google today helps you find Webpages – we think that there is immense opportunity in helping AI Agents access curated context for many other types of entities.

5. **Is there an opportunity to sell to AI Labs?**  
   Yes – this was a big part of our thinking here. AI Labs already buy things such as web search infrastructure. If we can actually pull this off, it is a highly differentiated product offering that we think will be highly sought after by the labs. AI Labs already buy high quality data for training today (it is a multi-billion dollar industry for Surge, Mercor, Handshake etc): we see high value in providing runtime data.

