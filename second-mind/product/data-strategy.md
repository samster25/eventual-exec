---
title: "Data Strategy"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[hypotheses]]"
  - "[[roadmap]]"
  - "[[pricing]]"
---

# Data Strategy

---

## Current Dataset State

| Metric | Value |
|--------|-------|
| Companies indexed | ~994 |
| People profiles | ~117K |
| Sector concentration | AI/ML |
| Coverage gap | Series C to Fortune 500 (where our ICP's targets are) |

The current dataset is a proof of concept, not a defensible asset. It is concentrated in AI/ML startups -- but our users' targets are Series C to Fortune 500 enterprises. H3 cannot be tested without expanding coverage, and demos cannot convert without data on the companies our users care about.

---

## $250K Data Acquisition Budget

**Proposed spend over the next 8-12 weeks.** Data coverage is the bottleneck to testing H2 and H3. Every week without coverage is a demo that misses.

| Category | Estimated Spend | What It Gets Us |
|----------|----------------|-----------------|
| **People data** (LinkedIn profiles, org charts) | $100-150K | Broader people coverage for ICP's target accounts. Enable the "who should I talk to?" workflow. |
| **Company data** (firmographic, funding, technographic) | $50-75K | Fill gaps in Series C to Fortune 500 coverage. Expand beyond AI/ML beachhead. |
| **Signal data** (job postings, content, news) | $25-50K | Timing signals: who's hiring, publishing, expanding. Makes Eventual proactive, not just reactive. |
| **Scraping infrastructure + compute** | $25K | Proprietary collection pipelines. Begin building the data moat. |

**Why now:** Every week without coverage is a demo that misses. Data acquisition is the bottleneck to testing H2 and H3. The $250K is an investment in hypothesis velocity.

---

## Data Freshness Targets

Freshness is a core differentiator vs. static databases (ZoomInfo, Apollo). Targets:

- **People moves** (joins, departures, promotions): Daily detection goal
- **Job postings** (new roles, hiring signals): Daily ingestion
- **Content** (blog posts, LinkedIn posts): Weekly refresh
- **Company firmographics** (funding, headcount): Weekly refresh
- **Org charts** (reconstructed from people data): Weekly recomputation

The watch/monitor feature (Weeks 7-8 of [[roadmap]]) inverts the direction -- instead of point-in-time lookups, signals come to the user when something changes at a target account.

---

## Build vs. Buy Philosophy

We are not a data aggregator. We are an intelligence layer. The moat comes from:

1. **Extraction + curation** -- not raw data alone. Others can buy the same raw feeds. Our value is in what we compute on top: org charts, content graphs, signal scoring.
2. **Agent-native serving** -- structured for drill-down tool calls, not bulk export.
3. **Proprietary signal computation** -- org charts, content graphs, hiring velocity, leadership changes. The defensible layer.
4. **Usage-driven feedback loops** -- what users search for tells us what to index deeper. The flywheel.

Raw data is a commodity. Buying it is faster than scraping it ourselves for most categories. We buy where speed matters and build proprietary collection pipelines where unique signals exist (scraping infra budget: $25K).

---

## Data Priority Order (If H3 Confirmed)

If H3 is confirmed -- our ICP's targets cluster in Series C to Fortune 500 -- then data expansion follows this priority:

1. **People data for ICP target accounts** -- org charts, key decision-makers, champions. This is the most valuable layer because it powers the "who should I talk to?" workflow.
2. **Company profiles for Series C to Fortune 500** -- firmographic depth, tech stack, recent funding, strategic initiatives. Fill the coverage gap that causes demos to miss.
3. **Timing signals** -- job postings, leadership moves, content publication, funding announcements. These are what make Eventual proactive rather than reactive.
4. **Content corpus** -- blog posts, podcast appearances, LinkedIn posts by key people. Powers the "understand the champion" workflow.

If H3 is NOT confirmed (targets are widely distributed, no clustering), shift to on-demand enrichment model -- user requests a company, we build the profile in real-time. Trade depth for breadth.

---

## Data Moat Hypothesis

We don't have a moat today. The moat hypothesis:

- **Data** + **agent interface** = compounding flywheel
- Proprietary data collection (scraping infra)
- Usage-driven feedback loops (what people search for guides what we index)
- Switching costs (once your agent workflow depends on our tool schema, migration is costly)

The moat begins to form when we build proprietary data collection, usage-driven feedback loops, and switching costs. That's a Week 9+ concern -- for now, the priority is hypothesis validation.
