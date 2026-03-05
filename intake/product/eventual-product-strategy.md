# Eventual GTM Search — Product Strategy

**Author:** Sammy Sidhu, CEO
**Date:** March 2026
**Status:** Living Document — v1.0
**Companion:** [Eventual Product Vision](./eventual-product-vision.md)

---

## Purpose of This Document

This document captures our assumptions, our thesis, and the explicit bets we are taking. It is designed to inform our PRD process and to serve as a reference point when we iterate on the product. If a decision contradicts something written here, either the decision is wrong or this document needs updating.

---

## 1. Strategic Context

The vision document articulates our durable thesis: agents need external context about the real world to be useful, and we're building the system that provides it. This strategy document is about how we win the first domain — GTM — and prove that thesis.

### The Market Shift

The global sales intelligence market is ~$4B today, growing at ~11% CAGR to ~$10B by 2032 (Fortune Business Insights, IMARC Group). The largest incumbent, ZoomInfo, does $1.25B in annual revenue but is growing at only 1-3% — the market is shifting beneath them. The broader GTM technology stack (data + engagement + CRM + intelligence) is significantly larger, but the segment we compete in directly — sales intelligence and data — is the ~$4B number.

This market has been organized around the same fundamental architecture for two decades: static databases of company and contact information, enriched in batch, scored by rules, and pushed through linear workflows. The major players (ZoomInfo, Apollo, Cognism, Clay) all optimize for the same paradigm — making human-designed processes faster. Put simply, the old world is **wide tables**: many accounts, surface-level enrichments, heavy reliance on data science and handcrafted signals to ascertain buying intent. This is the prospecting and lead scoring market. The new world is **deep tables**: fewer accounts, much deeper research and analysis per account, powered by agents that never sleep. This is the lead and account intelligence market — and it's where we play.

AI agents represent a structural break from this paradigm. Agents don't need batch operations because they can operate in parallel. They don't need pre-computed scores because they can reason in real-time. They don't need linear workflows because they can branch, backtrack, and adapt. The entire GTM stack was built for human limitations that agents don't have.

We believe this creates a window — likely 12–18 months — during which the intelligence layer for agent-native GTM will be established. The company that wins this layer wins a durable position in the new stack.

### Beyond GTM: The Expansion Thesis

The vision document makes the full case for why external context for agents is a cross-domain opportunity (see "The Bigger Picture"). The strategic summary: we start with GTM because it's the domain we know, the pain is acute, and agent adoption is fastest here. But the underlying capability — deep, navigable, real-time intelligence exposed through agent tool calls — is not GTM-specific.

The same product pattern (collect → extract → serve → learn) applies wherever agents need to understand real-world entities before making high-stakes decisions: recruiting, real estate, investment research, competitive intelligence, and more. Each new domain brings its own data sources and signals, but the core infrastructure — the ingestion pipelines, the signal extraction engine, the agent-native serving layer — carries over. This is why we build the GTM product as a vertical instance of a general capability, not as a GTM-only tool.

### Where We Sit (And Where We're Going)

Our end-state ambition is to be the **real-time sales intelligence backbone** for the agent-native GTM stack — the intelligence layer that any agent, tool, or team plugs into.

We are not there today. Today, we are a vertical tool that serves a specific, underserved workflow: deep account research for agent-forward GTM teams. We aim to win by being the best tool for that workflow — better than ZoomInfo's stale exports, better than Clay's table-based enrichment, better than an agent's raw web search. We haven't proven these "better than" claims yet. That's what the first 10 users will tell us.

The path from "best tool for deep account research" to "intelligence layer" is earned through adoption, not declared. The sequence:

**Phase 1 (Now):** Win the deep account research workflow for agent-forward teams. Prove that agents using Eventual produce meaningfully better sales outcomes than agents without it. Establish the tool as indispensable for the first 10–50 users.

**Phase 2:** Expand from research into persistent monitoring — always-on intelligence that alerts agents to signal changes, champion moves, and timing windows. This shifts us from a point-in-time tool to infrastructure.

**Phase 3:** Become the default intelligence plugin across agent platforms. At this point, the data flywheel and tool stickiness should make us the natural choice when any agent framework needs sales intelligence.

Our position in the stack:

```
[ Agent (Claude, GPT, etc.) ]
         ↓ tool calls
[ Eventual GTM Search ]  ← We are here
         ↓ signals + context
[ Data Sources: LinkedIn, ATS, Content, Social, Firmographic ]
```

The Google Maps analogy is useful but imperfect — Maps had massive first-party data collection (Street View cars, billions of mobile data points) from early on, which we don't have yet. Still, the core lesson holds: Maps didn't start as the intelligence layer for all apps. It started as the best way to get driving directions. The layer position was a consequence of being indispensable for a core use case first.

---

## 2. Why Us, Why Now

### Why This Team

The Eventual founding team comes from self-driving — an industry where you live or die by data flywheels. In autonomous vehicles, the companies that win are the ones that collect the most driving data, extract the best signals, use those signals to improve the system, and then collect better data because the system is better. This is the same flywheel we're building for GTM intelligence: collect data → extract signals → serve agents → learn from agent usage → collect better data.

We built Daft, a distributed data engine designed for processing large volumes of unstructured data at scale. The core challenge in building an external context system — ingesting messy, heterogeneous data from dozens of sources (LinkedIn profiles, job postings, blog content, social signals, financial filings) and extracting structured, actionable intelligence — is exactly the problem Daft was built to solve. Most GTM companies struggle with data freshness and coverage because data engineering at scale is genuinely hard. It's our core competency. Critically, this capability is what makes the multi-domain expansion credible — the same infrastructure that ingests GTM data can ingest recruiting, real estate, or investment research data.

We are also agent-native builders. We use Claude Code and Claude Cowork daily. We understand how agents reason because we live it — we're not adding "AI features" to a legacy product, we're building from first principles for how agents consume and navigate information. This matters because tool design for agents is a craft, not a checkbox.

### Why Now

Three conditions are true simultaneously for the first time:

**Agent capability has crossed the threshold.** As of early 2026, agents (Claude, GPT) can reliably make multi-step tool calls, reason about structured data, and maintain context across complex research sessions. This wasn't true 18 months ago. The technology is now good enough to support the deep research workflow we're building for.

**MCP has created a distribution channel.** The Model Context Protocol gives us a standard way to expose our intelligence to any agent framework. Before MCP, every integration was custom. Now, a single MCP server makes our data accessible to Claude Cowork, Claude Code, and any MCP-compatible agent. This dramatically lowers our go-to-market cost.

**Incumbents are structurally slow to respond.** ZoomInfo's revenue growth is 1-3%. Their business model depends on per-seat pricing and annual contracts for bulk data access. Building agent-native delivery cannibalizes their core revenue stream. Clay is growing fast but is architecturally committed to a table-based UI that requires a human workflow designer. Both will adapt, but the structural transition takes 12–18 months — and that's our window.

---

## 3. Explicit Bets

These are the assumptions we are making that, if wrong, would require a fundamental change in strategy. We name them explicitly so we can track and revisit them.

### Bet 1: Agents Will Replace GTM Roles, Not Just Augment Them

**The bet:** Within 2–3 years, AI agents will replace the SDR/BDR function at most technology companies. Instead of scaling headcount, companies will scale agent capacity. The sales org of the future is a small team of AEs and a fleet of agents.

**Why we believe it:** The SDR role is already under pressure — high turnover, expensive at scale, and fundamentally repetitive. Early agent-forward companies are already experimenting with agent-led prospecting. The cost differential is too large to ignore: an agent doing the work of an SDR costs a fraction of the salary and works 24/7. As underlying models improve and teams refine their agent workflows, the quality gap with human SDRs narrows over time. AI SDRs are already the fastest-growing segment of AI adoption within GTM. The best human SDRs aren't fighting the trend — they're upskilling into "GTM engineering" roles, using tools like Claude Code and Cowork to build and manage agent workflows rather than doing manual outreach themselves. We're also seeing companies like Decagon build internal GTM agents (via Dust, Gumloop, etc.) that interface with their teams through Slack — these agents need the best external context to be effective, and that's exactly where we plug in.

**What changes if we're wrong:** If agents remain in a "copilot" role — assisting humans rather than replacing them — we still have a valuable product, but our TAM is smaller and our value proposition shifts from "intelligence infrastructure for your agents" to "research assistant for your reps." The product survives, but the upside is capped.

**How we'll know:** Watch for SDR hiring trends at agent-forward companies over the next 12 months. If companies that adopt agentic tools continue hiring SDRs at the same rate, the bet is weakening.

**90-day checkpoint:** By June 2026, do at least 3 of our first 10 users describe their use case as "replacing" or "reducing" SDR headcount rather than "augmenting" existing reps? If all 10 describe it as augmentation only, the replacement timeline may be longer than we think — and we should adjust our positioning accordingly.

### Bet 2: Deep Beats Broad

**The bet:** Going deep on individual accounts (agent-driven, dynamic, contextual) beats the batch/bulk approach to prospecting. Quality over quantity. The highest-converting GTM motion is one where every touchpoint is informed by deep intelligence about the account, the champion, and the timing.

**Why we believe it:** The sales leaders we've talked to know this intuitively — their best reps are the ones who research deeply. The constraint has always been time. Agents remove the time constraint. When depth is free, depth wins. This is doubly true upmarket: when your lead list is the Fortune 1000, every account has a complex org structure, multiple stakeholders, and a longer sales cycle — exactly the conditions where deep research compounds into higher close rates.

**What changes if we're wrong:** If the market rewards volume over depth — if spray-and-pray outbound continues to work better than targeted, researched outreach — then our navigation-and-context approach is over-engineered. Customers would prefer a bulk data export (like ZoomInfo) over a navigable intelligence layer.

**How we'll know:** Measure conversion rates for users doing deep research vs. users doing bulk export in our own product. Track whether our highest-retention users are the ones going deep or the ones pulling large lists.

**90-day checkpoint:** By June 2026, do our most engaged users (top quartile by weekly usage) primarily use the drill-down pattern (search → profile → people → person) or the bulk export pattern (search → export list)? If heavy users gravitate toward bulk, our "deep beats broad" thesis is misaligned with what the market actually wants, and we should reconsider our navigation-first product design.

### Bet 3: Data + Agent Interface = Compounding Moat

**The bet:** Neither proprietary data nor agent-friendly interfaces alone constitute a moat. The combination does. As more agents use our tools, we learn which navigation patterns produce the best outcomes, which makes our tools better, which attracts more agents. Meanwhile, our data gets fresher and more comprehensive, making the intelligence more valuable.

**An honest assessment of where we are:** We don't have a moat today. We have a moat hypothesis. Our current dataset — 994 companies and 117K people profiles, mostly from a Feb 2025 LinkedIn snapshot — is a proof of concept, not a defensible asset. The data is sourced from public and licensed sources that any well-funded competitor could replicate. The signal extraction pipeline is early. The agent interface, while designed thoughtfully, has been tested by one internal user.

The moat begins to form when three things happen: (1) we build proprietary data collection that competitors can't easily replicate, (2) usage-driven feedback loops make our signals and tool design measurably better, and (3) the combination of data freshness + signal quality + navigation design makes switching costly. None of these are true yet. All three are on the roadmap.

**Why we believe it:** Data alone is commoditizing — there are many providers. Tool interfaces alone are easy to copy. But a flywheel where data quality improves tool effectiveness which improves data collection is hard to replicate, because you need both pieces running simultaneously. Our team's background building Daft (a distributed data engine) gives us an unfair advantage in building the data infrastructure layer that makes this flywheel possible.

**What changes if we're wrong:** If data becomes fully commoditized (e.g., a single provider offers comprehensive, real-time data cheaply) or if agent interfaces converge on a standard (e.g., an MCP standard for sales intelligence that anyone can implement), then our moat erodes on one or both sides.

**Why this is a venture-scale bet:** If the flywheel works for GTM, it should work for any domain where agents need real-world context — recruiting, real estate, investment research, competitive intelligence. This is what makes a narrow starting ICP compatible with a large outcome: the moat compounds across domains, not just within one.

**How we'll know:** Track data exclusivity — what percentage of our signals are available elsewhere? Track tool stickiness — do users who try alternatives come back? If both numbers stay strong by Month 6, the moat is forming. If users can get equivalent intelligence from a competitor or raw web search, the moat isn't real and we need to rethink what we're building.

**90-day checkpoint:** By June 2026, can we point to at least one signal or data dimension where users say "I can't get this anywhere else"? If every piece of intelligence we provide is also available via a ZoomInfo export or a Claude web search, the data moat isn't forming, and we need to accelerate proprietary data collection or find a different axis of differentiation.

---

## 4. Target Customer

*(Full ICP documented separately. Summary here for strategic context.)*

### Core ICP — Deliberately Small

AI/ML companies, Series A through C, 50–500 employees, with 3+ outbound reps, outbound-heavy sales motion, $30K+ ACV, and an agent-forward engineering culture. The cultural indicator is the strongest predictor: if engineering uses agents (Claude Code, Cursor, Copilot), GTM leadership is far more receptive to agentic tooling. We also include later-stage "rocketship" companies (Series D+, up to ~500 employees) that exhibit high funding velocity — a useful heuristic is total funding raised divided by years since founding, with a lower bound on total capital (e.g., $50M+). Companies like Decagon fit this profile: fast-growing, agent-forward, and actively building GTM motions that need deep intelligence.

**This ICP is intentionally narrow.** We estimate 200–500 companies globally match all six criteria simultaneously. That's the point. If we can't become indispensable for 50 of these companies, we have no business chasing 5,000. A narrow beachhead lets us build deep conviction about what works, iterate on the product with users who genuinely need it, and avoid the trap of building shallow features for a broad audience.

The risk of a narrow ICP is that even at full penetration, the revenue is small. At estimated usage-based ARPU of $500–2,000/month, full penetration of the core ICP generates $1.2M–$12M in annual revenue. This is not a venture-scale outcome on its own. It's a beachhead — the goal is to prove the product and the data flywheel, not to capture a large market immediately.

### Primary Buyer

Head of Sales / VP Sales — the person who owns pipeline and feels the pain daily. Their team spends 30–60 minutes researching each account manually. Pipeline generation doesn't scale linearly with headcount because research, not outreach volume, is the bottleneck.

### Secondary Buyer

Technical founder doing founder-led sales — closes at 3x the rate of hired reps because they actually research, but can't scale themselves or teach the process.

### Tertiary Buyer

Chief of Staff or "Founder's Office" operator — the person who buys and wires together tools like ChatGPT, Claude Cowork, Gumloop, and n8n to automate workflows across the company. They may not own pipeline directly, but they're the ones building the agent infrastructure that GTM runs on. When they evaluate Eventual, they're thinking about it as a building block in a broader automation stack, not as a standalone sales tool.

### Expansion Path (Beachhead → Market)

The core ICP is the starting point, not the destination. Expansion happens by relaxing criteria one at a time, each step validated by the previous:

**Step 1 — Go upmarket + adjacent verticals (after 10+ AI company logos):** The natural pull is toward larger, later-stage companies selling to enterprise buyers. Deep account research becomes more valuable as deal complexity increases — more stakeholders, longer cycles, higher ACV. Expand from our beachhead (Series A–D, 50–500 employees) to mid-market companies (500–2,000 employees) and adjacent verticals: developer tools, cybersecurity, partnerships/BD teams at platforms, and VC/PE firms doing deal sourcing. These share the same signal-rich, research-heavy sales motion. This expands the addressable pool to 2,000–5,000 companies.

**Step 2 — Drop the agent-forward requirement (after product proves value with non-technical users):** Broader B2B SaaS companies with outbound teams and $30K+ ACV. These teams may not use Claude Code today, but if the product is good enough, they'll adopt agent-assisted workflows for GTM specifically. This expands the pool to 10,000–20,000 companies.

**Step 3 — New domains (after the data flywheel is working):** Recruiting, real estate, investment research — anywhere professionals need deep research on entities before making high-stakes decisions. Each domain brings a new TAM and new data requirements, but the core infrastructure carries over. (See "Beyond GTM: The Expansion Thesis" above.)

---

## 5. Competitive Landscape

### Clay

Clay is the most formidable company in our orbit. Reportedly ~$100M ARR with rapid year-over-year growth, $3.1B valuation, 10,000+ customers including Anthropic and OpenAI. They are defining the "GTM Engineer" role as a new category. We take them seriously.

**Where Clay sits:** Clay is a workflow orchestration layer. It connects to 150+ external data sources, lets users define enrichment and scoring workflows in a table-based UI, and outputs structured results. Its value is in the aggregation and transformation of data from other providers — Clay has some proprietary data, but it's minimal and not a core competitive advantage.

**Where we differ — stack position:** We sit at a different layer. Clay is orchestration; Eventual is data + intelligence. In principle, these could be complementary — a Clay user could consume Eventual as a data source. Whether this makes us partners or competitors depends on whether our data is differentiated enough to justify a separate relationship.

**Where we differ — interaction model:** Clay's core UX is a spreadsheet where humans design the workflow: add a column, define an enrichment step, write an AI prompt. Even with AI-powered columns, the human architects the sequence. Eventual removes the human from workflow design — the agent decides what to research, how deep to go, and what thread to pull next. These are genuinely different interaction paradigms.

**Where we differ — data ownership:** Clay aggregates data from 150+ providers. We are building a proprietary data pipeline with signals that Clay's providers don't offer. If our signal extraction produces intelligence that can't be replicated by chaining Clay's existing data sources, that's a durable wedge.

**Where we differ — bet on the future:** Clay's model depends on the "GTM Engineer" role — a human who designs and maintains AI-powered workflows. Our model depends on agents operating autonomously with the right intelligence. If agents increasingly design their own workflows, Clay's table-builder UX becomes less central. If humans remain the workflow architects, Clay's model wins. This is an honest disagreement about where the market goes.

**The market segmentation we're betting on:** Clay's core user today is the SDR or GTM engineer building prospecting and lead scoring workflows — high-volume, systematic, top-of-funnel. Our primary user is the AE or founder doing deep account research before a high-stakes call — low-volume, high-context, mid-to-bottom-of-funnel. Today, AEs largely do this research manually by browsing LinkedIn, reading blog posts, and piecing together context. A table-based workflow doesn't map well to this problem — it's not about enriching rows, it's about navigating an organization and building judgment. If this segmentation holds, we're not competing with Clay for the same buyer.

**The real risk from Clay:** Clay could ship an MCP server, exposing their aggregated data to agents directly and closing the interaction model gap. If they do, the competition shifts entirely to data quality and signal differentiation — which is where we want it, because we own our pipeline and they don't. But we should assume they will do this within 12 months and plan accordingly.

### Exa (Websets)

Semantic search over the web. Powerful for finding entities that match a description, but not purpose-built for GTM. Exa finds companies — it doesn't help you navigate the org, identify champions, track buying signals, or understand timing. It returns search results; we return contextualized intelligence with suggested follow-up threads. The difference is analogous to Google Search vs. a research analyst: one gives you links, the other gives you answers and tells you what to ask next.

The risk from Exa is that they build GTM-specific layers on top of their search infrastructure. Their data coverage is broad (the entire web), which gives them a starting advantage on breadth. Our advantage is depth — going further on each account than a general web search can.

### Apollo / ZoomInfo / Cognism

The incumbents. ZoomInfo does $1.25B in revenue but is growing at only 1-3%. Apollo has broader self-serve adoption but thinner data. These companies have massive customer bases and data assets, but their architecture and business models are built for the CRM era: bulk export, per-seat pricing, and quarterly data refreshes.

**The honest threat:** These companies will add AI features. ZoomInfo's Copilot already accounts for 20%+ of their ACV. They have the data and the distribution. Their challenge is that agent-native delivery cannibalizes their per-seat pricing model and requires rearchitecting how data is exposed. Incumbents can do this, but it's slow and organizationally painful. Our advantage is that we have no legacy to protect — we can build agent-native from day one.

**The honest weakness:** Their data coverage dwarfs ours. ZoomInfo has 35,000 customers and billions of data points. We have 994 companies and 117K people profiles. In a straight data coverage comparison today, we lose badly. We win only if the quality, freshness, and navigability of our intelligence matters more than breadth — which brings us back to Bet 2 (Deep Beats Broad).

### Our Differentiation (Summary)

We are not claiming to be better than these competitors across the board. We are making a specific bet: that agent-native delivery of deep, navigable intelligence — backed by a proprietary data pipeline — serves the emerging market better than workflow orchestration (Clay), general web search (Exa), or bulk data export (incumbents). If that bet is right, we win a durable position. If it's wrong, we've learned something valuable about what agents actually need.

---

## 6. Product Strategy

### Strategic Principles

**Intelligence, not workflow.** We provide the answers and context; the agent decides what to do with them. We never constrain the agent's decision-making by imposing a fixed sequence.

**Navigable, not exportable.** Our primary interaction pattern is "pull the next thread" — each response includes context and suggested follow-ups. Bulk export is a feature, not the product.

**Contextualized, not raw.** We don't return raw data dumps. Every response is structured for what the agent is trying to accomplish, with additional threads it can follow. The agent gets intelligence, not information.

**Agent-first, human-readable.** Our tools are designed for agent consumption (structured MCP tool calls), but every response should also be comprehensible to the human in the loop. The human supervises; the agent navigates.

### The Product Today

Eventual GTM Search exposes five core tools via MCP:

| Tool | Purpose |
|------|---------|
| `search_companies` | Find companies by industry, funding, size, signals, keywords |
| `get_company_profile` | Complete company brief: info, people, jobs, content, signals — one call |
| `search_people` | Find people by role, title, company, seniority — always with LinkedIn URLs |
| `get_person_profile` | Full person dossier: experience, posts, current role, connections |
| `search_content` | Search blog posts, job descriptions, LinkedIn job listings |

These tools implement the core drill-down pattern: search → profile → people → person → content. Each step is a navigable branch point where the agent decides what thread to pull next.

### Near-Term Roadmap (6 Weeks)

**Weeks 1–2:** Internal MVP and strategic decisions. Jay (GTM lead) uses the product daily. Team offsite to make foundational decisions on signal architecture, data strategy, and ICP configuration.

**Weeks 3–4:** First external users. ICP context injection so the agent adapts to any customer's target profile. Generalized signal framework. 3–4 external demos with feedback integration.

**Weeks 5–6:** Scale to 10 users. Multi-user support, quality improvements, structured feedback collection, retention analysis. The goal is not revenue — it's product-market fit signal.

### Medium-Term Strategic Priorities

**Signal pipeline ownership.** Move from licensed/scraped data to a proprietary collection and extraction pipeline. Leverage our expertise with Daft (our distributed data engine) to build a best-in-class GTM data engine.

**Coverage expansion.** Current dataset is 994 companies and 117K people profiles, skewed toward AI/ML. Expand to broader tech, cybersecurity, devtools, and fintech to support expansion ICP segments.

**Platform integrations.** Native plugins for Claude Cowork, Claude Code, and other agent frameworks. Goal: become the default sales intelligence tool that ships with agent environments — starting with Anthropic's ecosystem.

**Watch and monitor.** Continuous monitoring of target accounts — signal changes, champion moves, hiring surges, funding events. Move from point-in-time research to always-on intelligence.

---

## 7. Data Strategy

### Current State (Honest Assessment)

Our dataset includes ~994 company profiles, ~117K LinkedIn people profiles (snapshot from Feb 2025), job posting data from ATS scraping and LinkedIn, blog content, and precomputed GTM signals. This is sufficient for internal testing and early demos with users whose targets overlap with our existing coverage (AI/ML companies), but it is not sufficient for general-purpose sales intelligence. Our coverage is narrow, our people data is stale, and most of our raw data comes from sources any competitor could access.

This is expected at our stage. The question is not whether our data is defensible today (it isn't) but whether we can build a data engine that becomes defensible over the next 6–12 months.

### Build vs. Buy Philosophy

We own the pipeline. We are a data infrastructure company at our core — Daft is our proof of that. Short term, we bootstrap by licensing raw data (Bright Data, LinkedIn feeds, Crunchbase). Medium term, we build proprietary collection, extraction, and freshness infrastructure. Long term, our data pipeline is the moat.

The sequence: buy raw data to get to market → build extraction and signal pipelines to differentiate → own collection to lock in freshness and exclusivity.

**Key milestone:** By Month 3, at least one major data source should be proprietary (not available through the same providers our competitors use). If we can't achieve this, the "data moat" thesis is in trouble and we should reassess.

### Data Freshness Targets

People data must be refreshed at least monthly (current snapshot is stale). Company signals should update within 48 hours of a real-world event. Job posting data should be near-real-time. Content data (blogs, social) should be within a week. Freshness is a competitive advantage — stale data is the number one complaint about incumbents.

---

## 8. Monetization

### Model: Usage-Based, Value-Tiered Pricing

Charge based on the intelligence consumed, not per seat. This aligns with agent usage patterns — more agents researching more accounts means more revenue — without penalizing the small teams we're building for.

### Why Deep Research Means High Usage

A potential concern: if our thesis is "deep beats broad," won't depth-first users generate fewer API calls than bulk prospecting users? In practice, we believe the opposite. Going deep on a single account generates significantly more tool calls than a shallow lookup: company profile → org chart navigation → champion research across multiple contacts → signal analysis → content review → historical deal tracking → timing assessment. A single account researched deeply might generate 15–30 tool calls. A shallow lookup generates 1–2. Our highest-value users will be our highest-usage users.

### Value-Tiered Pricing

Not all API calls deliver equal value. A `search_companies` call that returns a list is less valuable than a `get_company_profile` call that produces a complete intelligence brief, which is less valuable than a signal-based alert that surfaces a time-sensitive buying window. Pricing should reflect this: basic navigation calls at one rate, deep intelligence calls at a higher rate, and premium signals (real-time alerts, proprietary data) at the highest rate.

### Why Not Per-Seat

Per-seat pricing doesn't map to the agent-native world. A team of 3 people with 20 agents shouldn't pay for 3 seats — they should pay for the intelligence their agents consume. Usage-based pricing also lowers the adoption barrier (start small, scale with value) and creates natural expansion revenue.

### Pricing Development

Too early to lock in specific tiers or rates. The first 10 users will be free or heavily discounted in exchange for feedback. The key questions we need to answer from early users: how many tool calls does a typical deep research session generate? Which calls deliver the most perceived value? At what price point does a VP Sales consider this a no-brainer compared to their current research costs (30–60 minutes of rep time per account)?

---

## 9. Distribution Strategy

How we get in front of customers is as important as what we build. Our distribution strategy is phased, recognizing that different channels work at different scales.

### The Core Insight: The Demo IS the Product

Our single biggest distribution advantage is that we can demonstrate value in real-time on a prospect's own accounts. When Jay gets on a call, he doesn't show slides — he asks "who are you trying to sell to?" and then uses Eventual to find their customers, champions, and signals live. When this works, it creates a compelling demo moment. The constraint: this only works when the prospect's targets overlap with our current coverage (~1,000 AI/ML companies). Expanding coverage is a prerequisite for this becoming a reliable distribution motion. Every GTM motion should be designed to get us into that demo moment as quickly as possible.

### The Demo UI: Distribution as Product

To turn that demo moment into a scalable lead engine, we will build a lightweight web UI — not a full dashboard, but a shareable entry point. A prospect types in their ICP, sees results, and provides their email to receive the full intelligence output. This serves three purposes: it's a self-serve demo, it's a lead capture mechanism (now we have their email and their ICP definition), and it's a shareable artifact (a prospect can forward the link to their VP Sales or founder). This is not "building a dashboard" — it's building distribution into the product.

### Phase 1: Founder-Led Sales + Dogfooding (0→10 users)

Our ICP is small enough that we can name every prospect. We use our own product to find and research them — the ultimate dogfooding.

Jay does outbound and demo calls. Sammy does founder-to-founder conversations with the technical founder persona. Every call follows the same pattern: learn the prospect's ICP, demo Eventual live finding their customers, send them the shareable results link afterward.

Sammy and Jay build founder brand on LinkedIn and Twitter around the "agent-native GTM" thesis. The vision document content is the thought leadership — this isn't a marketing exercise, it's sharing what we genuinely believe about where the market is going.

**Target:** 10 users by Week 6.

### Phase 2: Platform Distribution + Word of Mouth (10→100 users)

Get listed in Anthropic's MCP ecosystem and Claude Cowork plugin marketplace. This puts us in front of exactly our buyer — people who are already using agents for daily work. MCP ecosystem is new and growing; early movers get disproportionate visibility.

Word of mouth compounds fast in tight communities. Agent-forward GTM people talk to each other in specific Slack groups, Twitter circles, and at conferences (SaaStr, Pavilion). Publish case studies: "How [Company X] reduced account research from 45 minutes to 3 minutes with Eventual."

**Target:** 100 users by Month 6.

### Phase 3: Partnerships + Category Creation (100→1,000 users)

Partner with AI SDR tools (11x, Artisan) who need better intelligence to feed their agents. Partner with CRM and engagement platforms who want agent-native intelligence in their ecosystem. Build the "agent-native GTM" category through content, events, and community.

At this stage, evaluate whether the demo UI should evolve into a fuller product experience for non-agent-native users — a lightweight dashboard for signal monitoring, saved research, and team sharing. If the expansion ICP includes teams that aren't using Claude Cowork, we may need a direct interface.

**Target:** 1,000 users by end of 2026.

### What We Deprioritize

Paid advertising (ICP too small to justify), enterprise sales (too early), and broad content marketing (our buyer isn't reading generic blog posts — they're in specific communities). These become relevant at Phase 3 scale, not before.

---

## 10. Measuring Success

### Product-Market Fit Indicators (End of 2026)

We are optimizing for product-market fit, not revenue, in this phase. The signals we're watching:

**Retention:** Users who start using Eventual in their agent workflows don't stop. Weekly active usage remains flat or grows after the first month.

**Organic pull:** Prospects come to us through referrals or word-of-mouth, not just outbound. Users mention Eventual unprompted in conversations with peers.

**Can't-live-without signal:** When we ask users "how would you feel if you could no longer use Eventual?", the majority say "very disappointed."

**Agent integration depth:** Users move from one-off queries to embedding Eventual in their persistent agent workflows. The product becomes infrastructure, not a tool they occasionally open.

### Operational Metrics

| Metric | Week 1 | Week 3 | Week 6 | End of 2026 |
|--------|--------|--------|--------|-------------|
| Active users | 1 (internal) | 2 | 10+ | PMF signal |
| ICP types supported | 1 (GTM) | 3 | 5+ | Any B2B ICP |
| Avg query latency | ~15s | ~10s | <8s | <5s |
| Eval quality score | Baseline | +20% | +40% | Continuously improving |
| Data freshness (people) | Feb 2025 | Monthly | Weekly | Near-real-time |

---

## 11. Risks and Mitigations

### Platform Risk

**Risk:** LLM providers build or acquire native GTM intelligence for their agent platforms, commoditizing our layer.

**The real scenario isn't that Anthropic builds a data pipeline from scratch** — it's that they partner with or acquire an incumbent who already has one. ZoomInfo has 35K customers and $1.25B in revenue. Apollo has broad self-serve adoption. If Anthropic ships "Claude for Sales" powered by a ZoomInfo partnership, we're competing against a platform-native integration backed by the largest B2B dataset in the world.

**Mitigation:** Three layers of defense. First, we move fast — the 12–18 month window exists because platform partnerships take time to negotiate, integrate, and ship. We need meaningful adoption before that happens. Second, we position as a partnership candidate ourselves — if our product is good and our users love it, we become the partner the platforms want, not the one they replace. Third, we differentiate on depth and freshness. A ZoomInfo partnership gives platforms breadth (millions of contacts) but not the navigable, real-time, signal-rich intelligence that makes agents effective. Incumbents optimized for bulk export; we optimize for agent navigation. If our quality is demonstrably better for the agent use case, the platform partnership is with us, not them.

**What we should do now:** Build a relationship with Anthropic's partnerships team. Make Eventual the best MCP server in the Anthropic ecosystem for sales intelligence. If they're going to partner with someone, we want to be first in line.

### Data Commoditization Risk

**Risk:** A competitor aggregates the same data sources and offers comparable intelligence at lower cost.

**Mitigation:** Our moat is the combination of data and agent-native interface design, not data alone. We also invest in proprietary collection (not just aggregation) and signal extraction that compounds over time. The signal pipeline is the hard part, not the raw data.

### Adoption Risk

**Risk:** GTM teams are conservative and slow to adopt agent-native tooling. The "agent replaces SDR" bet takes longer than expected.

**Mitigation:** Our core ICP is specifically agent-forward companies — teams whose engineering culture already embraces AI tools. We're not trying to convince skeptics. We're serving the vanguard. If broader adoption takes longer, we still have a strong niche with early adopters.

### Execution Risk

**Risk:** Three-person team trying to build a data platform, an intelligence layer, and go to market simultaneously.

**Mitigation:** Ruthless prioritization. The 6-week roadmap is designed to get to 10 users with the minimum viable product, not to build the full vision. We use our own product to find our own customers (dogfooding). Every feature ships only if it directly enables the next user milestone.

---

## 12. What We Are Not Doing

### Strategic Choices (Durable — These Define What We Are)

These are decisions about the kind of company we're building. They should be stable across stages and only change if our thesis changes.

**Building a CRM.** CRM is a crowded, low-margin market. We want to be the intelligence that flows into any CRM, not another CRM. CSV/JSON/API export for CRM import is sufficient. This is a scope boundary, not a resource constraint.

**Building outreach/sequencing tools.** Outreach is downstream of intelligence. If we get the intelligence right, users will pair us with whatever outreach tool they prefer. We are the research layer, not the action layer.

**Competing on data breadth alone.** We will not try to out-ZoomInfo ZoomInfo on the number of contacts or companies in our database. We compete on signal quality, freshness, and navigability — not on having the most rows.

### Staging Choices (Temporary — These Change as We Grow)

These are decisions driven by our current stage, team size, and resources. They have explicit revisit dates.

**Targeting enterprise (5,000+ employees).** The sales cycle is too long and procurement too complex for a 3-person team. As Jeetu put it: "focus on the Doordashes" — high-growth companies where we can move fast, not Fortune 500 procurement cycles. **Revisit:** When we have 50+ customers and at least one enterprise-adjacent logo pulling us upmarket.

**Building a full product dashboard.** Our primary interface is the agent. We will build a lightweight demo/share UI for lead capture (see Distribution Strategy), but not a full dashboard. The tradeoffs: limited brand presence, limited stickiness, no direct user habits. **Revisit by Month 3:** If users want signal monitoring, saved research, or team sharing, we build it.

**International expansion.** Our ICP is US-centric. International markets have different data sources, regulations, and buyer behavior. **Revisit:** When US market penetration reaches Phase 2 targets (~100 users).

**Multi-product.** We're building one product (GTM Search) for one domain. New domains (recruiting, real estate) are part of the expansion thesis but not on the roadmap. **Revisit:** When the core GTM product has clear PMF signal and the data flywheel is working.

---

*This strategy document will be reviewed monthly and updated as we learn from users. The bets section is the most important — if our bets change, everything downstream changes with them.*
