# Eventual — Q1 2026 Board Deck

**Date:** March 5, 2026
**Duration:** 45 minutes
**Presenter:** Sammy Sidhu, CEO

---

## SECTION 1: The Journey — Daft Cloud to Eventual Entity Search (10 min)

---

### Slide 1: The Arc

**From infrastructure tool to intelligence layer — 4 learning cycles in 16 weeks**

| Phase | Timeline | What We Tried | What We Learned |
|-------|----------|---------------|-----------------|
| Daft Cloud | Nov 2025 – mid-Jan 2026 | Managed ingestion for AI teams | Indexing is not the pain. Cost of embeddings is trivial. Teams want outcomes, not infra. |
| Hackathon | Jan 20 – Feb 2 (2 weeks) | Company-wide agent sprint: observability, connectors, retrieval, agentic search | Internal context is easy at small scale, only hard at enterprise scale (where Glean wins). Two paths emerged: B2B2B connectors or external context. |
| Search Sprint | Feb 9 – ~Feb 21 (2 of 3 planned weeks, cut short) | B2B2B search/connector product for agent builders (Nomic, Notion, Wordware, AlphaSense) | Not enough customers with strong enough pain. Everyone keeps the intelligence in-house. Must pick a specific pain for a specific person. |
| Eventual Entity Search | Feb 23 → present | Deep people + company search, starting with GTM (Sammy, Jay, Colin) | More interest and engagement in conversations, but still need to nail the specific pain and prove the product delivers. |

---

### Slide 2: Evidence Along the Way — What We Heard

**Daft Cloud era (Nov 2025 – mid-Jan 2026 | 39 convos):**

- Harvey (dinner, Dec): *"Our ingestion pipeline has been stable. What keeps us up at night is search reliability and quality."*
- Rogo (Tumas, Dec 16): *"If you're just offering parallelization, we're not interested — our engineers have solved that."* But more importantly, Tumas challenged us: *"You guys are sitting atop technology that could kill any data provider. The money isn't in selling the infra — it's in selling the data itself. Capture the value you create."* He told the Berkeley Lights cautionary tale — a company that built machines creating enormous value but captured none of it.
- Patreon: Embedding cost was ~$10K for a full run. Not worth optimizing.
- Harvey: *"Embedding pipeline cost is dwarfed by AI document reviews."*
- Cursor: Outdated context *"decreases capability by confusing the model."*

**Conclusion:** Indexing is solved. The pain is downstream. And multiple conversations pointed us toward the same insight: don't sell the tools to process data — own the intelligence itself.

**Hackathon era (Jan 20 – Feb 2 | company-wide agent sprint):**

- Wordware: Semantic search is *"probabilistic, noisy"* — a source of context pollution.
- Rosebud: RAG pipeline *"did not work at all."*
- Cursor: Wants faster agents and better temporal resolution of context.
- Internal signal: Our agents did better with more context, but the problem only becomes acute at enterprise scale.

**Conclusion:** At small scale, internal context is straightforward — a single engineer can wire up a RAG pipeline in a week. The problem only gets hard at enterprise scale (permissions, sync, hundreds of data sources), and that's well-served by incumbents like Glean. This gave us two paths to explore: (1) B2B2B — help agent builders connect to *their customers'* internal data, or (2) external context — build intelligence about the outside world that no one owns yet.

**Search Sprint / B2B2B Detour (Feb 9–21, cut short from 3 planned weeks) — We tried path 1 first:**

We explored building a WorkOS-for-data: connectors that let agent builders integrate with their customers' internal data sources. We talked to several companies about this path:

- **Nomic** (vertical AI for construction, $4M pipeline in 30 days): First call during hackathon (Jan 23), two follow-ups during search sprint (Feb 9, Feb 19). Willing design partner, real pain — *"Three people in Ukraine, month and a half on one integration, not even complete."* But across three calls, the iceberg emerged: 500K SharePoint files, row-level permissions, GPU parsing budgets. And critically: *"We keep that in-house — that's core competency."* They'd only outsource the commodity tail (Teams, Outlook, Gmail).
- **Notion:** Wanted better backfills for their data, but intended to keep search in-house for third-party integrations. Not a buyer — a builder.
- **Wordware:** Wanted connectors for their product via a filesystem abstraction. Real need, but commodity infrastructure work.
- **AlphaSense:** Initially interested in offloading their connector story, but realized they care about the *signals* in the raw documents — like identifying whether something is a board deck vs. a pitch deck. The intelligence layer is their differentiator, not the plumbing.

Every conversation had the same shape: real pain in building connectors, but the companies either wanted to keep the intelligence in-house (Nomic, AlphaSense) or only needed commodity plumbing (Wordware, Notion). No one was willing to pay for the hard part, and the easy part had no pricing power.

We also mapped the broader market: 50+ vertical AI companies across finance (Ramp, Hebbia, Rogo, Vic.ai), legal (Harvey, Clio, Everlaw, Luminance), customer service (Sierra, Decagon, Zendesk), sales (11x, Artisan, Regie.ai), marketing, and recruitment. The pattern was universal — every company builds their own data connectors and keeps the intelligence layer in-house. The addressable market for "general-purpose data connectors to your customers' data" was simply too small. Vertical AI companies don't want a horizontal connector layer; they want domain-specific intelligence, and that's their core product.

**Conclusion:** Internal data connectors = real pain, fatal economics, and a thin market. This sharpened our conviction: external context is the greenfield, not internal.

**Eventual era (Feb 19 → present | 17 convos in 14 days):**

- Decagon (Daniel Liem, Founder's Office, Mar 3): Building a GTM engineering team using Gumloop/Dust → Slack. Immediately engaged on data sourcing: *"How are you getting this data?"* — wanted to understand our pipeline, not just the output. Targets Fortune 1000 (healthcare focus). Offered to connect us with Gumloop founder directly. Wants to plug Eventual into their existing agent infrastructure.
- FullEnrich, AlphaSense, ClickUp, Blink Health: Active GTM-focused conversations.

**Conclusion:** More engagement and curiosity than previous phases, but we haven't yet proven the pain is acute enough to convert. That's what the next 8 weeks are for.

---

### Slide 3: The Rogo Moment — The Seed of Eventual

The December 16 call with Tumas Rackaitis (co-founder, Rogo — deployed with JP Morgan, Wells Fargo, ~90 people) was a turning point. Key moments:

**On our infrastructure pitch:** *"I have the parallelism already. I put an engineer on a data source and they'll have it up in a week in my stack."*

**On what he actually wants:** *"Exa and Parallels are such good pieces of underlying infrastructure that are not imaginative whatsoever of what power you could do. Give me every single store Sweet Green has opened in the Southwest every single day — literally Google Maps over time."* He wanted curated, structured intelligence about the world — not tools to build it himself.

**On capturing value:** Told the Berkeley Lights story — a company that built machines creating enormous value for pharma but captured $2M while their customers captured billions. His advice: *"You guys are going to create a ton of value if you make this work. Capture it yourselves. Why not?"*

**On buying data:** *"I would pay $50K without batting an eye"* for a curated dataset. Unilateral buying authority, no committee.

**On being specific:** *"Don't leave room for imagination. Come with something specific."*

This conversation crystallized the shift from "sell the infrastructure" to "own the intelligence." It planted the seed that became Eventual: we don't sell the tools to process data — we build curated, navigable intelligence about real-world entities and sell that directly.

---

### Slide 4: Themes Across the Journey

**1. Listening > Building**
We killed Daft Cloud when the market said the pain wasn't enough. We said no to search sprint design partners who offered to pay. We followed pain, not revenue.

**2. Specific > Generic**
"Better search for agents" → "Better search for whom, doing what?" → "Deep account research for agent-forward GTM teams selling upmarket." Rogo's advice was the sharpest version: *"Don't leave room for imagination."* The Nomic detour reinforced this — B2B2B connector infrastructure for every possible data source was the opposite of specific.

**3. Own the Intelligence, Not Just the Infrastructure**
The through-line from Harvey → Rogo → Eventual: customers don't want a pipeline, a database, or a retrieval layer. Rogo told us directly: the money is on the other end — sell the data, not the infra. Eventual is us taking that advice.

**4. External Context Is the Greenfield — Internal Context Will Be Solved by Partners**
Internal context (knowledge bases, codebases, CRMs, Slack, email) is being solved by partner integrations and MCP — Glean, Notion, and dozens of startups are racing to connect agents to your company's internal data. External context — structured intelligence about the *outside world* (companies, people, markets, signals) — is wide open. No one owns it for agents yet. The Nomic calls showed us the internal side firsthand: massive complexity, entrenched players, low differentiation. External context is where a 3-person team can win.

**5. Speed of Learning Is Our Advantage**
4 major phases in 16 weeks. 86 conversations since November. Most startups take longer to reach this clarity. The cost was real (team morale, context-switching), but the learning compounds.

---

### Slide 5: By the Numbers

| Metric | Value |
|--------|-------|
| Total conversations since Nov 2025 | 86 |
| Unique companies engaged | 60+ |
| Conversations per month (avg) | ~17 |
| Eventual conversation pace | 17 in 14 days (~1.2/day) |
| Daft Cloud era convos | 39 (Nov – mid-Jan) |
| Hackathon + Search Sprint era convos | 11 (late Jan – mid-Feb) |
| Eventual era convos | 17 (Feb 19 – Mar 4, 14 days) |
| Office Hours (community) | 16 |
| Notable logos engaged | Harvey, OpenAI, Notion, Decagon, Snapchat, Suno, Cursor, ClickUp, Scale AI, AlphaSense |

---

## SECTION 2: Core Hypotheses & How We Test (8 min)

*Board ask #1: What are the core hypotheses, how many people are you talking to, and what is the time horizon to make decisions?*

---

### Slide 6: Hypothesis Framework

We are pre-PMF. Most of what we believe is hypothesis, not fact. We separate what we're testing from what we're assuming — so we know when to change course.

- **Hypotheses** = beliefs we must validate in the next 8 weeks. Each has a test and a kill condition.
- **Assumptions** = beliefs we hold strongly enough to build on. Named so we notice if they break.

**Time horizon for hypothesis decisions: 8 weeks (end of April 2026)**
Week 1 is offsite + Q2 kickoff for Eventual. Week 2–3 is ramp before Jay can daily-drive the product. Real hypothesis testing begins Week 3.
**People we're talking to: 86 conversations to date, targeting 100 more in the next 8 weeks** — AEs are much easier to get calls with than engineers or founders, so we're raising our target accordingly.

---

### Slide 7: H1 — AEs Have an Acute, Unsolved Research Pain

| | |
|---|---|
| **The belief** | AEs spend 30–50% of pre-call prep on manual research (LinkedIn, blogs, Crunchbase, org mapping). No existing tool solves this because the workflow is navigational, not tabular. |
| **Why it matters** | If this pain isn't real or isn't acute enough, we don't have a product. This is the most fundamental hypothesis. |
| **How we test** | In every conversation: *"Walk me through how you prep for a call today."* Listen for specificity and emotion — unprompted detail, not polite agreement. |
| **What confirms it** | 50+ out of 100 prospects independently describe manual research as significant pain with specific examples and time estimates. |
| **What kills it** | Fewer than 25/100 recognize it as meaningful pain, OR they say they've already solved it with existing tools. |
| **Current evidence** | Early AE convos suggest ~50% of prep time goes to unstructured research. Promising but anecdotal. |
| **People testing on** | All prospect conversations (targeting 100 in next 8 weeks) |
| **Decision date** | End of April 2026 |

---

### Slide 8: H2 — Curated Context Is Meaningfully Better Than Agents + Web Search

| | |
|---|---|
| **The belief** | Large, durable gap between Eventual's intelligence and what an agent can piece together via web search. Our structured, signal-rich context produces materially better outputs. |
| **Why it matters** | Claude + web search is free. If agents get 80% of what we provide on their own, no one pays for the last 20%. This is our existential risk. |
| **How we test** | Head-to-head: 10 accounts, researched two ways (Eventual vs. Claude + web search). Show both outputs to prospects blind. Ask: *"Which would you use to prep for a call?"* |
| **What confirms it** | Prospects consistently prefer Eventual and can articulate why. Delta is obvious without explanation. |
| **What kills it** | Prospects can't tell the difference, or say web search is "close enough." |
| **Current evidence** | Untested. This is the most important experiment to run in the next 8 weeks. |
| **People testing on** | First 10 external users |
| **Decision date** | End of April 2026 |

---

### Slide 9: H3 — Our Data Should Go Deep on Who Our ICP Sells To

| | |
|---|---|
| **The belief** | Our ICP is startups selling upmarket. They're researching their *buyers* (Series C → Fortune 500), not other startups. Data strategy should prioritize deep coverage of mid-market/enterprise. |
| **Why it matters** | If we index the wrong slice of the market, every demo fails — not because the product is bad, but because we don't have data on the companies our users care about. |
| **How we test** | In every demo: *"Who are your top 10 target accounts?"* Track what those companies are. Measure coverage hit rate. |
| **What confirms it** | Majority of targets cluster in Series C–Fortune 500. Demos that hit produce strong engagement; demos that miss produce polite exits. |
| **What kills it** | Targets are widely distributed — no clustering. Can't be opinionated about coverage. |
| **Current evidence** | Decagon targets Fortune 1000 (healthcare focus). Aligns with hypothesis. Anecdotal — need more data points. |
| **People testing on** | All demo conversations |
| **Decision date** | End of April 2026 |

---

### Slide 10: Assumptions (Not Actively Testing — But Named)

| Assumption | What Would Break It |
|------------|---------------------|
| **A1: Agent adoption in GTM is real and accelerating** | Can't find 50 companies matching our ICP; agent-forward companies still running manual playbooks |
| **A2: MCP is a durable distribution channel** | Competing standard emerges; MCP adoption stalls |
| **A3: Deep beats broad (product design bet)** | Most engaged users gravitate to bulk export, not drill-down |
| **A4: Agents keep getting better at reasoning** | Model capabilities plateau at "search and summarize" |
| **A5: Infrastructure generalizes across domains** | Second domain attempt reveals GTM-specific architecture |

**Review cadence:** Hypotheses weekly. Assumptions monthly.

---

## SECTION 3: Hypothesis Validation Actions & Timeline (7 min)

*Board ask #3: What specific actions are being taken to prove or disprove each hypothesis, and on what timeline?*

---

### Slide 11: Validation Action Plan

**H1: AE Research Pain — Conversation-Driven Validation**

| Week | Action | Target |
|------|--------|--------|
| 1 (Mar 10–14) | Offsite + Q2 kickoff. Align team on Eventual strategy, interview scripts, success criteria. | Team alignment |
| 2–3 (Mar 17–28) | Jay + Sammy outbound while Colin builds product. Jay ramps to daily-driving product. | 15 conversations |
| 4–6 (Mar 31–Apr 18) | First external users. Track whether users independently describe research as pain. | 50 cumulative conversations |
| 7–8 (Apr 21–May 1) | Compile results. Score conversations: "strong pain" / "moderate" / "solved already." | 100 cumulative conversations |
| **Decision point** | If <25/100 describe acute pain → revisit product thesis | End of April |

**H2: Curated Context vs. Web Search — Head-to-Head Experiment**

| Week | Action | Target |
|------|--------|--------|
| 1–2 | Build eval harness. Select 10 target accounts from real user ICPs. | Eval framework ready |
| 3–4 | Run head-to-head: same model, same prompt, Eventual vs. Claude + web search. | 10 account comparisons |
| 5–7 | Show blind outputs to 20+ prospects. Score preference + articulated delta. | 20 blind evaluations |
| **Decision point** | If prospects can't tell the difference → existential risk, reassess | End of April |

**H3: Data Coverage Strategy — Demo Hit Rate Tracking**

| Week | Action | Target |
|------|--------|--------|
| 1–3 | Ask every prospect for top 10 target accounts. Log company stage/size/industry. Begin data acquisition. | 15 prospects' target lists |
| 4–6 | Measure coverage hit rate. Prioritize data expansion based on gaps. Deploy $250K data budget. | 50%+ hit rate on demo accounts |
| 7–8 | Track correlation: coverage hit → engagement. Coverage miss → polite exit. | Pattern confirmed or denied |
| **Decision point** | If no clustering in targets → can't be opinionated on data strategy | End of April |

---

### Slide 12: Tracking Dashboard

We log every conversation with structured fields:

- **Pain score** (H1): Does this person describe research as acute pain? (1–5)
- **Coverage hit** (H3): What % of their targets are in our system?
- **Demo reaction** (all): Hair on fire / interested / lukewarm / not relevant

| Week | New Convos | H1 Pain Confirmed | H2 Head-to-Head Run | H3 Coverage Hit Rate |
|------|-----------|-------------------|---------------------|---------------------|
| 1 (offsite) | — | — | — | — |
| 2–3 | 15 | TBD | Building eval | Collecting target lists |
| 4–6 | 50 | TBD | 10 comparisons done | First measurement |
| 7–8 | 100 | Decision point | 20 blind evals done | Pattern confirmed? |

---

## SECTION 4: Product Vision & Strategy (10 min)

---

### Slide 13: What Eventual Is

**Eventual is the external context layer for knowledge agents — starting with GTM.**

We collect entity data (companies, people, organizations) and signals (what people write, publish, hire for, fund), extract structured intelligence, and serve it through agent-native interfaces.

```
[ Agent (Claude, GPT, etc.) ]
         ↓ tool calls (MCP)
[ Eventual Entity Search ]  ← We are here
         ↓ signals + context
[ Data Sources: LinkedIn, ATS, Content, Social, Firmographic ]
```

**Today:** 5 MCP tools, ~1,000 companies, ~117K people profiles, concentrated in AI/ML.
**The product pattern:** collect → extract → serve → learn → improve.

---

### Slide 14: The 5 Tools

| Tool | Purpose | Interaction |
|------|---------|-------------|
| `search_companies` | Find companies by industry, funding, size, signals | Entry point — wide search |
| `get_company_profile` | Complete brief: info, people, jobs, content, signals | Go deep on one company |
| `search_people` | Find people by role, title, company, seniority | Navigate the org |
| `get_person_profile` | Full person dossier: experience, posts, connections | Understand the champion |
| `search_content` | Search blogs, JDs, LinkedIn posts | Surface timing signals |

**Core drill-down pattern:** search → profile → people → person → content.
Each step is a navigable branch point where the agent decides what thread to pull next.

---

### Slide 15: Why GTM First

- **Pain is acute and quantifiable:** 30–60 min of manual research per account, every day.
- **Agent adoption is fastest here:** SDR/BDR function already under pressure. AI SDRs are the fastest-growing AI adoption segment in GTM.
- **Buyers are willing to try:** Our ICP's engineering culture already uses Claude Code / Cursor.
- **Data problem is a good proving ground:** Messy, multi-source, multi-format — representative of every future domain.

**Expansion thesis:** GTM → recruiting → real estate → investment research. Same infrastructure (collect → extract → serve → learn), different data sources.

---

### Slide 16: Competitive Positioning

| Competitor | Their Model | Our Differentiation |
|-----------|------------|---------------------|
| **Clay** (~$100M ARR) | Workflow orchestration. Human designs enrichment in a table UI. 150+ data source aggregation. | We are intelligence, not orchestration. Agent decides what to research. We own our data pipeline. |
| **ZoomInfo** ($1.25B rev) | Static database. Bulk export. Per-seat pricing. 1–3% growth. | Agent-native delivery. Real-time signals. Usage-based pricing. |
| **Exa** | Semantic web search. Broad but not deep. | We return contextualized intelligence with follow-up threads, not search results. |
| **Apollo / Cognism** | Self-serve contact databases. Broad but shallow. | Deep account research > spray-and-pray enrichment. |

**Our bet:** Agent-native delivery of deep, navigable intelligence — backed by a proprietary data pipeline — serves the emerging market better than workflow orchestration, web search, or bulk export.

**Honest assessment:** We don't have a moat today. We have a moat hypothesis: data + agent interface = compounding flywheel. Our dataset is a proof of concept, not a defensible asset. The moat begins to form when we build proprietary data collection, usage-driven feedback loops, and switching costs.

---

### Slide 17: Target Customer

**Core ICP (deliberately narrow):**
AI/ML companies, Series A–D, 50–500 employees, 3+ outbound reps, outbound-heavy motion, $30K+ ACV, agent-forward engineering culture. Including "rocketship" companies (Series D+) with high funding velocity.

**Estimated addressable pool:** 200–500 companies globally.

**This is a beachhead, not a destination.**

| Expansion Step | Trigger | Addressable Pool |
|---------------|---------|-----------------|
| Upmarket + adjacent verticals | 10+ AI company logos | 2,000–5,000 |
| Drop agent-forward requirement | Product proves value with non-technical users | 10,000–20,000 |
| New domains (recruiting, real estate, etc.) | Data flywheel working | TAM expands dramatically |

**Buyers:** VP Sales (primary) → Technical founder doing founder-led sales (secondary) → Chief of Staff / GTM engineer (tertiary, e.g., Daniel at Decagon)

---

### Slide 18: Distribution Strategy

**Core insight: the demo IS the product.**

Jay asks "who are you trying to sell to?" then uses Eventual to find champions and signals live. When it works, it's a compelling moment. Constraint: only works when targets overlap with our coverage.

| Phase | Target | Channel |
|-------|--------|---------|
| **Phase 1** (now → 10 users) | Founder-led sales + dogfooding. We use our own product to find prospects. | Jay outbound + Sammy founder-to-founder. Demo UI for lead capture. |
| **Phase 2** (10 → 100 users) | MCP ecosystem + word of mouth in agent-forward GTM communities. | Anthropic plugin marketplace. Case studies. Slack/Twitter communities. |
| **Phase 3** (100 → 1,000 users) | Partnerships with AI SDR tools (11x, Artisan). Category creation. | Partner integrations. Events. Evaluate expanding demo UI to lightweight dashboard. |

---

## SECTION 5: 8-Week Product Roadmap (7 min)

*Board ask #2: Week-by-week view of what's being built and when it gets into customers' hands.*

---

### Slide 19: 8-Week Roadmap Overview

**Team:** Sammy, Jay, Colin (3 people)
**Current state:** Week 1–2 of build. Internal MVP exists. 5 MCP tools working. 1–5 external demos completed.
**Week 1:** Offsite + Q2 kickoff (no shipping). **Week 2–3:** Jay ramps to daily-driving.
**Goal by Week 8:** 10 active external users + H1/H2/H3 decisions.

```
Week 1       Week 2-3      Week 4-6      Week 7-8
Offsite +    Jay Ramps +   First Users   10 Active
Q2 Kickoff   Data Acq      + Scale       Users +
             Begins                      Decisions
```

---

### Slide 20: Week-by-Week Detail

**Week 1 (Mar 10–14): Offsite + Q2 Kickoff**

| What | Who | Outcome |
|------|-----|---------|
| Team offsite: align on Eventual strategy, product direction, hypothesis framework | All | Shared context + conviction |
| Finalize data acquisition plan + begin vendor outreach ($250K budget) | Sammy | Data pipeline plan ready |

**Weeks 2–3 (Mar 17–28): Jay Ramps + Data Acquisition Begins**

| What | Who | Outcome |
|------|-----|---------|
| Jay ramps to daily-driving product for outbound | Jay | Dogfood feedback loop |
| Data strategy decisions: coverage priorities based on H3 | Sammy + Colin | Prioritized data expansion plan |
| Begin data acquisition: people data, company data, signals | Sammy + Colin | First data drops landing |
| Signal architecture: which signals to pre-compute | Colin | Signal framework v1 |
| Build H2 eval harness (Eventual vs. Claude + web search) | Colin | Eval framework ready |
| 3–5 external demos (live research on prospect's targets) | Jay + Sammy | First H1/H3 data points |

**Weeks 4–6 (Mar 31–Apr 18): First External Users + Scale**

| What                                                                         | Who           | Outcome                          |
| ---------------------------------------------------------------------------- | ------------- | -------------------------------- |
| ICP context injection (agent adapts to each user's target profile)           | Colin         | Users can configure their ICP    |
| 5+ external users onboarded (MCP key distribution)                           | Jay           | First external usage data        |
| Run H2 head-to-head on 10 real accounts                                      | Sammy + Colin | Quantified delta vs. web search  |
| Demo UI v1 (shareable link for lead capture)                                 | Colin         | Scalable demo motion             |
| Data coverage expansion (Series C → Fortune 500 based on H3 + acquired data) | Sammy + Colin | Higher demo hit rate             |
| Multi-user support (API keys, usage tracking)                                | Colin         | Can support 10+ concurrent users |
| 5 blind H2 evaluations with prospects                                        | Jay + Sammy   | H2 data points                   |
| Structured feedback collection framework                                     | Jay           | Consistent H1/H2/H3 scoring      |

**Weeks 7–8 (Apr 21–May 1): 10 Active Users + Hypothesis Decisions**

| What | Who | Outcome |
|------|-----|---------|
| Compile H1/H2/H3 results. Make go/no-go decisions. | Sammy + Jay + Colin | Strategic clarity |
| Watch/monitor v1 (persistent signal alerts for key accounts) | Colin | Move from point-in-time to always-on |
| Retention analysis: who's using it daily vs. tried-and-left? | Jay | PMF signal strength |
| Begin MCP ecosystem listing process (Anthropic) | Jay + Sammy | Distribution pipeline |
| If H1+H2+H3 confirmed: plan Phase 2 (10 → 100 users) | All | Next phase plan |
| If any hypothesis killed: regroup within 48 hours | All | Rapid response |

---

### Slide 21: Milestones Summary

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| Internal MVP working | Pre-Week 1 ✓ | Done |
| First external demo (Decagon) | Pre-Week 1 ✓ | Done |
| Offsite + Q2 kickoff | Week 1 | Next week |
| Data acquisition begins ($250K budget) | Week 2 | — |
| Jay daily-driving product | Week 3 | — |
| H2 eval framework built | Week 3 | — |
| 5 external users onboarded | Week 5 | — |
| H2 head-to-head complete (10 accounts) | Week 5 | — |
| Demo UI v1 live | Week 5 | — |
| 10 active external users | Week 7–8 | — |
| H1/H2/H3 decision point | Week 8 | — |
| MCP ecosystem listing submitted | Week 8 | — |

---

### Slide 22: What Happens After Week 8 — Success and Failure Paths

**At Week 8 (end of April), we make a decision. Here's what each path looks like.**

**SUCCESS PATH (H1 + H2 + H3 confirmed):**

Weeks 9–12 are about distribution, not revenue. Revenue follows distribution.

| Week | Action | Goal |
|------|--------|------|
| 9–10 | Submit to Anthropic MCP marketplace. Begin partnership conversations with AI SDR tools (11x, Artisan, Dust). | Distribution pipeline live |
| 9–10 | Publish case studies from first 10 users. Launch in agent-forward GTM communities. | Organic inbound begins |
| 11–12 | Partner integrations: Eventual as a tool inside existing agent workflows (Gumloop, Dust, etc.) | 10 → 50 users |
| 11–12 | First pricing experiments. Usage-based model with early adopter discounts. | Revenue signal, not revenue target |

**FAILURE PATH (any hypothesis killed):**

If the pain isn't real (H1), the product isn't differentiated (H2), or the data strategy is wrong (H3) — we don't force it. We regroup within 48 hours.

| Scenario | What We Do | Timeline |
|----------|-----------|----------|
| **H1 fails** (AEs don't have acute research pain) | Same data + infrastructure, different persona. Recruiting, investor research, or real estate analysts have analogous research workflows. Run 2-week discovery sprint on next persona. | 2 weeks to new hypothesis |
| **H2 fails** (web search is "good enough") | Shift from serving curated context to enhancing agent capabilities — become the extraction/curation layer that makes web search *better*, not a replacement for it. Or: go deeper on a niche where web search demonstrably fails (private company data, org charts, non-indexed signals). | 2 weeks to new hypothesis |
| **H3 fails** (targets don't cluster) | Broaden data strategy. If we can't be opinionated about coverage, shift to on-demand enrichment model — user requests a company, we build the profile in real-time. Trade depth for breadth. | 1 week to adjust |

**The infrastructure we're building (collect → extract → serve → learn) transfers across all these paths.** The sunk cost is low. The learning compounds.

---

## SECTION 6: Key Risks & Financial Position (3 min buffer / appendix)

---

### Slide 23: Top Risks

| Risk | Severity | Mitigation |
|------|----------|------------|
| **Enterprise data complexity:** If value concentrates in enterprise accounts, computing signals (org charts, hiring patterns, news) for large companies is orders of magnitude harder. Data is sparser and noisier for non-tech-native enterprises vs. the AI/ML startups we know well. | High | Start with ICP's targets (Series C–Fortune 500 in tech-adjacent verticals). Use $250K data budget to buy coverage strategically. If enterprise data proves too hard, narrow to mid-market first. |
| **Platform risk — already materializing:** ZoomInfo launched an MCP connector on Claude in January 2026. Users can build prospecting lists inside Claude using ZoomInfo's 300M+ profiles. This is the "Claude for Sales" scenario we flagged — and it's live. | High | ZoomInfo's MCP is their existing product through a new interface: bulk contact lookup (name, email, phone, company). Static, tabular data. We are building something they're not — navigable intelligence with signals, org charts, content, and drill-down. They solve *who to contact*. We solve *how to prepare for the conversation*. The real risk is if ZoomInfo expands their MCP tools into signals and research — but incumbents typically port old products to new interfaces, not reinvent them. We need to move fast and own the "research + context" layer before they do. |
| **H2 fails:** Agents + web search is "good enough" | Existential | Running the head-to-head experiment by Week 5. If the gap is small, we're building a feature, not a product. We'll know by end of April. |
| **Data moat risk:** We're buying/scraping data others can buy too | Medium | Moat comes from extraction + curation + agent-native serving, not raw data alone. Proprietary signal computation (org charts, content graphs) is the defensible layer. |
| **Execution risk:** 3-person team building data platform + intelligence layer + GTM | Medium | Ruthless prioritization. 8-week roadmap is minimum viable, not full vision. Daft team supports infrastructure. |
| **Adoption risk:** GTM teams too conservative for agent-native tools | Low (for ICP) | ICP is specifically agent-forward. Not trying to convince skeptics. |

---

### Slide 24: Data Acquisition Budget

**Proposed budget: $250K for data acquisition over the next 8–12 weeks.**

To test our hypotheses and serve our ICP, we need data that doesn't exist in our system today. Our current dataset is concentrated in AI/ML startups — but our users' *targets* are Series C → Fortune 500 enterprises. H3 can't be tested without the data, and demos can't convert without coverage.

| Category | Estimated Spend | What It Gets Us |
|----------|----------------|-----------------|
| People data (LinkedIn profiles, org charts) | $100–150K | Broader people coverage for ICP's target accounts. Enable the "who should I talk to?" workflow. |
| Company data (firmographic, funding, technographic) | $50–75K | Fill gaps in Series C–Fortune 500 coverage. Expand beyond AI/ML beachhead. |
| Signal data (job postings, content, news) | $25–50K | Timing signals: who's hiring, publishing, expanding. Makes Eventual proactive, not just reactive. |
| Scraping infrastructure + compute | $25K | Proprietary collection pipelines. Begin building the data moat. |

**Why now:** Every week without coverage is a demo that misses. Data acquisition is the bottleneck to testing H2 and H3. The $250K is an investment in hypothesis velocity.

---

### Slide 25: Financial Position & Team

- **Runway:** 3+ years (inclusive of the $250K data budget)
- **Commercial team:** Sammy (CEO), Jay (GTM lead), Colin (Engineering)
- **Daft team:** Varun (lead) + engineering team. Priorities: Eventual → Apple → ByteDance → Community.
- **Daft is the foundation:** Eventual runs on Daft. Every Daft improvement directly improves Eventual. Not adjacent work — foundational work.

---

### Slide 26: What We're Asking From the Board

1. **Patience on revenue.** We are optimizing for PMF, not revenue, for the next 8 weeks. To us, PMF means 10 people who would be genuinely unhappy if we took the tool away. First 10 users are free or heavily discounted.
2. **Trust the speed of learning.** 86 conversations and 4 phases in 16 weeks. We move fast and kill things that don't work.
3. **Hold us accountable to the hypotheses.** By end of April: H1, H2, H3 each have a clear confirmed/killed status. If any hypothesis dies, we regroup within 48 hours.
4. **Approve the $250K data acquisition budget.** Data coverage is the bottleneck to testing H2 and H3. Every week without coverage is a demo that misses.

---

*End of deck. Total estimated presentation time: ~42 minutes with Q&A buffer.*
