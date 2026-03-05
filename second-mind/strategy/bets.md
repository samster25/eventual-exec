---
title: "Explicit Bets"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[strategy]]"
  - "[[hypotheses]]"
---

# Explicit Bets

These are the assumptions we are making that, if wrong, would require a fundamental change in strategy. We name them explicitly so we can track and revisit them.

Extracted from [[strategy]] Section 3 for quick reference.

---

## Bet 1: Agents Will Replace GTM Roles, Not Just Augment Them

**The bet:** Within 2–3 years, AI agents will replace the SDR/BDR function at most technology companies. Instead of scaling headcount, companies will scale agent capacity. The sales org of the future is a small team of AEs and a fleet of agents.

**Why we believe it:** The SDR role is already under pressure — high turnover, expensive at scale, and fundamentally repetitive. Early agent-forward companies are already experimenting with agent-led prospecting. The cost differential is too large to ignore: an agent doing the work of an SDR costs a fraction of the salary and works 24/7. As underlying models improve and teams refine their agent workflows, the quality gap with human SDRs narrows over time. AI SDRs are already the fastest-growing segment of AI adoption within GTM. The best human SDRs aren't fighting the trend — they're upskilling into "GTM engineering" roles, using tools like Claude Code and Cowork to build and manage agent workflows rather than doing manual outreach themselves. We're also seeing companies like Decagon build internal GTM agents (via Dust, Gumloop, etc.) that interface with their teams through Slack — these agents need the best external context to be effective, and that's exactly where we plug in.

**What changes if we're wrong:** If agents remain in a "copilot" role — assisting humans rather than replacing them — we still have a valuable product, but our TAM is smaller and our value proposition shifts from "intelligence infrastructure for your agents" to "research assistant for your reps." The product survives, but the upside is capped.

**How we'll know:** Watch for SDR hiring trends at agent-forward companies over the next 12 months. If companies that adopt agentic tools continue hiring SDRs at the same rate, the bet is weakening.

**90-day checkpoint:** By June 2026, do at least 3 of our first 10 users describe their use case as "replacing" or "reducing" SDR headcount rather than "augmenting" existing reps? If all 10 describe it as augmentation only, the replacement timeline may be longer than we think — and we should adjust our positioning accordingly.

---

## Bet 2: Deep Beats Broad

**The bet:** Going deep on individual accounts (agent-driven, dynamic, contextual) beats the batch/bulk approach to prospecting. Quality over quantity. The highest-converting GTM motion is one where every touchpoint is informed by deep intelligence about the account, the champion, and the timing.

**Why we believe it:** The sales leaders we've talked to know this intuitively — their best reps are the ones who research deeply. The constraint has always been time. Agents remove the time constraint. When depth is free, depth wins. This is doubly true upmarket: when your lead list is the Fortune 1000, every account has a complex org structure, multiple stakeholders, and a longer sales cycle — exactly the conditions where deep research compounds into higher close rates.

**What changes if we're wrong:** If the market rewards volume over depth — if spray-and-pray outbound continues to work better than targeted, researched outreach — then our navigation-and-context approach is over-engineered. Customers would prefer a bulk data export (like ZoomInfo) over a navigable intelligence layer.

**How we'll know:** Measure conversion rates for users doing deep research vs. users doing bulk export in our own product. Track whether our highest-retention users are the ones going deep or the ones pulling large lists.

**90-day checkpoint:** By June 2026, do our most engaged users (top quartile by weekly usage) primarily use the drill-down pattern (search → profile → people → person) or the bulk export pattern (search → export list)? If heavy users gravitate toward bulk, our "deep beats broad" thesis is misaligned with what the market actually wants, and we should reconsider our navigation-first product design.

---

## Bet 3: Data + Agent Interface = Compounding Moat

**The bet:** Neither proprietary data nor agent-friendly interfaces alone constitute a moat. The combination does. As more agents use our tools, we learn which navigation patterns produce the best outcomes, which makes our tools better, which attracts more agents. Meanwhile, our data gets fresher and more comprehensive, making the intelligence more valuable.

**An honest assessment of where we are:** We don't have a moat today. We have a moat hypothesis. Our current dataset — 994 companies and 117K people profiles, mostly from a Feb 2025 LinkedIn snapshot — is a proof of concept, not a defensible asset. The data is sourced from public and licensed sources that any well-funded competitor could replicate. The signal extraction pipeline is early. The agent interface, while designed thoughtfully, has been tested by one internal user.

The moat begins to form when three things happen: (1) we build proprietary data collection that competitors can't easily replicate, (2) usage-driven feedback loops make our signals and tool design measurably better, and (3) the combination of data freshness + signal quality + navigation design makes switching costly. None of these are true yet. All three are on the roadmap.

**Why we believe it:** Data alone is commoditizing — there are many providers. Tool interfaces alone are easy to copy. But a flywheel where data quality improves tool effectiveness which improves data collection is hard to replicate, because you need both pieces running simultaneously. Our team's background building Daft (a distributed data engine) gives us an unfair advantage in building the data infrastructure layer that makes this flywheel possible.

**What changes if we're wrong:** If data becomes fully commoditized (e.g., a single provider offers comprehensive, real-time data cheaply) or if agent interfaces converge on a standard (e.g., an MCP standard for sales intelligence that anyone can implement), then our moat erodes on one or both sides.

**Why this is a venture-scale bet:** If the flywheel works for GTM, it should work for any domain where agents need real-world context — recruiting, real estate, investment research, competitive intelligence. This is what makes a narrow starting ICP compatible with a large outcome: the moat compounds across domains, not just within one.

**How we'll know:** Track data exclusivity — what percentage of our signals are available elsewhere? Track tool stickiness — do users who try alternatives come back? If both numbers stay strong by Month 6, the moat is forming. If users can get equivalent intelligence from a competitor or raw web search, the moat isn't real and we need to rethink what we're building.

**90-day checkpoint:** By June 2026, can we point to at least one signal or data dimension where users say "I can't get this anywhere else"? If every piece of intelligence we provide is also available via a ZoomInfo export or a Claude web search, the data moat isn't forming, and we need to accelerate proprietary data collection or find a different axis of differentiation.
