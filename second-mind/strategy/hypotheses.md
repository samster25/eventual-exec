---
title: "Eventual — Market Hypotheses & Assumptions"
created: 2026-03-05
updated: 2026-03-06
status: active
related:
  - "[[vision]]"
  - "[[strategy]]"
  - "[[bets]]"
  - "[[conversation-log]]"
---

> Source: [[source-documents/product-docs/eventual-market-hypotheses.md]]

# Eventual — Market Hypotheses & Assumptions

**Author:** Sammy Sidhu, CEO
**Date:** March 2026
**Status:** Living Document — updated as we learn from users
**Companion:** [[vision]] · [[strategy]]

---

## How to Use This Document

We are pre-PMF. Most of what we believe about our market is hypothesis, not fact. This document separates what we're actively testing from what we're assuming — so we know where to focus, what to watch, and when to change course.

**Hypotheses** are beliefs we must validate in the next 90 days. Each has a test and a kill condition.
**Assumptions** are beliefs we hold strongly enough to build on without actively testing right now. We name them so we notice if they start breaking.

---

## Core Hypotheses (Actively Testing)

### H1: AEs Have an Acute, Unsolved Research Pain

**The belief:** Account Executives spend 30–50% of their pre-call prep time on manual, unstructured research — browsing LinkedIn, reading blog posts, scanning funding announcements, mapping org charts. This work is painful, repetitive, and directly competes with time spent selling. No existing tool solves this well because the workflow is navigational, not tabular.

**Why it matters:** If this pain isn't real — or isn't acute enough to drive adoption — we don't have a product anyone needs. This is the most fundamental hypothesis. Everything else assumes this is true.

**How we test it:**

- In every sales conversation, ask: *"Walk me through how you prep for a call today. How long does it take? What tools do you use? What do you wish you had?"*
- Listen for specificity and emotion. The signal is a prospect describing the pain unprompted, with detail — not polite agreement after we describe it.
- Track the ratio of "yes, this is a real problem" vs. "it's fine, I have a process" across the first 20 conversations.

**What confirms it:** 10+ out of 20 prospects independently describe manual research as a significant pain point, with specific examples and time estimates.

**What kills it:** Fewer than 5 out of 20 prospects recognize this as a meaningful pain. Or: prospects acknowledge the pain but say they've already solved it with existing tools, web search, or internal processes. If the pain is real but already solved, we're late, not wrong.

**Current evidence:** Early AE conversations suggest ~50% of prep time goes to unstructured research. Promising but anecdotal — need to validate at scale.

> Signal log: [[hypothesis-tracker]] — 4 scored calls. Avg: 3.0. 1 positive, 1 negative, 1 neutral, 1 no data.

- **Mar 6 — GoLinks (Jake Summers, AE):** 2/5. Research used to take days (reading 50-page 10Ks). AI has solved ~90% of it — now 15 min to 1-2 hrs. Biggest pain is Salesforce admin, not research.
- **Mar 6 — Hyperscience (Kyle Del Francia, Enterprise AE):** 3/5. Gemini Deep Research handles most research/personalization. But the hardest part is getting people to reply, and the most important qualification signal ("have they failed at AI?") can't be surfaced by any current tool.
- **Mar 3 — Decagon (Daniel Liem, GTM Eng):** 4/5 (retroactive). Building GTM infra from scratch, fragmented context problem across Gumloop/Dust/Slack.
- **Feb 27 — ClickUp (Borys Aptekar, GTM Leader):** 4/5 (retroactive). BDR use case — calling 20 people then scrambling across ZoomInfo, Outreach, Gong to act on what was learned.

---

### H2: Curated Context Is Meaningfully Better Than Agents + Web Search

**The belief:** There is a large, durable gap between the intelligence Eventual provides and what an agent can piece together through general web search. Our structured, signal-rich, navigable context produces materially better research outputs than an agent doing its best with Google and LinkedIn.

**Why it matters:** Claude with web search is free. If an agent can get 80% of what Eventual provides on its own, no one pays for the last 20%. This is our existential risk — and it's a moving target, because base model capabilities improve every quarter.

**How we test it:**

- **Head-to-head comparison.** Pick 10 accounts that prospects actually care about. Research each two ways: Eventual vs. Claude with web search (same model, same prompt, only the tools differ). Compare outputs side by side.
- Show both outputs to prospects (blind if possible). Ask: *"Which of these would you use to prep for a call? Which gives you something you didn't already know?"*
- Track where Eventual wins and where web search is "good enough." The wins tell us our differentiation; the losses tell us where to invest.

**What confirms it:** Prospects consistently prefer the Eventual output — and can articulate why (richer signal, better org navigation, information they couldn't find on their own). The delta is obvious without explanation.

**What kills it:** Prospects can't tell the difference, or say the web search output is "close enough." If the gap is small and narrowing, we're building a feature, not a product.

**Current evidence:** Untested head-to-head comparison. This is the most important experiment to run in the first 6 weeks.

> Signal log: [[hypothesis-tracker]] — 2 scored calls. Avg: 3.0. 1 positive, 1 negative. 2 calls have no H2 data.

- **Mar 6 — GoLinks (Jake Summers, AE):** 2/5. Uses ChatGPT with web search daily and says it "generally solves more of their cases." Acknowledges gaps ("pieces the AI is just not going to pick up") but overall satisfied.
- **Mar 6 — Hyperscience (Kyle Del Francia, Enterprise AE):** 4/5. Uses Gemini Deep Research for account plans — finds it "pretty good." But golden question ("have they failed at AI before?") can't be answered by Gemini or ZoomInfo. **Would pay MORE than ZoomInfo** for that intelligence.

**The moving target risk:** Even if we win the head-to-head today, we need to win it again in 6 months. Agents are getting better at web research. Our differentiation must come from data assets and signal extraction that improve faster than the baseline — not from a static advantage.

---

### H3: Our Data Should Go Deep on Who Our ICP Sells To

**The belief:** Our ICP is startups selling upmarket. They're not researching other startups — they're researching their *buyers*: Series C companies through the Fortune 500 (excluding the Fortune 100, which require a different depth of data mining that takes longer to produce value). Therefore our data strategy should prioritize deep coverage of mid-market and enterprise companies (the targets our ICP sells to), not broad coverage of the startup ecosystem (our ICP itself).

**Why it matters:** This determines what data we collect, how we prioritize coverage expansion, and whether our demos actually land. If we have deep data on seed-stage AI startups but our ICP is trying to sell to Datadog, Snowflake, and ServiceNow, every demo fails — not because the product is bad, but because we indexed the wrong part of the market.

**How we test it:**

- In every demo, ask: *"Who are your top 10 target accounts right now?"*
- Track what those companies are. Log company size, stage, and industry.
- Measure our coverage hit rate: what percentage of a prospect's target accounts are in our system with sufficient depth to deliver a "wow" moment?

**What confirms it:** The majority of prospects' target accounts cluster in the Series C–Fortune 500 range (excluding Fortune 100). Our coverage hit rate improves as we prioritize this segment. Demos that hit produce strong engagement; demos that miss produce polite exits.

**What kills it:** Prospects' target accounts are widely distributed — some sell to startups, some to enterprise, some to SMB. If there's no clustering, the data strategy can't be opinionated and we need a different approach to coverage.

**Implication for data strategy:** If confirmed, our coverage expansion priority order is:
1. Series C–Fortune 500 companies (our ICP's targets) — go deep
2. The ICP companies themselves (so we understand our prospects) — moderate depth
3. Fortune 100 (revisit later when data mining investment is justified)
4. Broader startup ecosystem (low priority — not who our users are researching)

**Current evidence:** Anecdotal from early conversations. Jay's observation that deep research is "doubly important for going upmarket when you have a lead list of the Fortune 1000" supports this. Jeetu's advice to "focus on the Doordashes" aligns — high-growth companies selling upmarket, not down.

> Signal log: [[hypothesis-tracker]] — 3 scored calls. Avg: 3.7. 2 positive, 1 negative.

- **Mar 6 — GoLinks (Jake Summers, AE):** 4/5. Targets span 5 to 5,000+ employees. Currently working CrowdStrike (11K seats). Customers include Anthropic and OpenAI. Org charts matter starting at ~200 employees. High coverage overlap.
- **Mar 6 — Hyperscience (Kyle Del Francia, Enterprise AE):** 2/5. Targeting transportation/logistics companies (DISA, Algo/DAT, Hirschbach). Also healthcare, government (IRS, VA), financial services (Charles Schwab). Low overlap with our current AI/ML company coverage.
- **Mar 3 — Decagon (Daniel Liem, GTM Eng):** 5/5 (retroactive). Fortune 1000 healthcare targets. Exactly the pattern H3 predicts — AI startup selling upmarket.

---

## Assumptions (Not Actively Testing — But Named)

These are beliefs we hold with enough conviction to build on. We don't have the resources or timeline to test them right now, but we name them so we can track them and react if they start breaking.

### A1: Agent Adoption in GTM Is Real and Accelerating

We assume our ICP is already using or actively adopting agents for GTM workflows. We filter for this in our ICP criteria (agent-forward engineering culture) rather than testing it. If the agent-forward segment is smaller than we think, our addressable market shrinks — but we'll see this in the funnel (not enough qualified prospects) rather than in product feedback.

**What would break it:** If we can't find 50 companies that match our ICP criteria, or if companies that look agent-forward on paper turn out to still be running manual playbooks in GTM.

### A2: MCP Is a Durable Distribution Channel

We're building on MCP as the standard interface for agent tool calls. This is a bet on Anthropic's ecosystem and on MCP becoming the de facto standard (or at least one of the dominant ones). If MCP gets replaced, fragmented, or marginalized, our distribution thesis breaks.

**What would break it:** A competing standard emerges and gains traction (e.g., OpenAI ships a proprietary tool protocol that most agent builders adopt). Or MCP adoption stalls and agent builders revert to custom integrations.

### A3: Deep Beats Broad (Product Design Bet)

We've built the product for depth — navigable drill-downs, not bulk exports. We believe the highest-value GTM motion is deep research per account, not spray-and-pray enrichment across thousands of leads. We're not actively testing this — we're watching usage patterns.

**What would break it:** Our most engaged users gravitate toward bulk export patterns (search → export list) rather than drill-down patterns (search → profile → people → person). If heavy users want wide tables, our navigation-first design is misaligned.

**How we'd notice:** 90-day checkpoint in the [[strategy]]. By June 2026, observe whether top-quartile users by usage are going deep or going wide.

### A4: Agents Will Keep Getting Better at Reasoning

Our product gets more valuable as agents improve at multi-step research, context synthesis, and follow-up questioning. We assume model capabilities will continue improving on a trajectory that makes our "navigation layer" paradigm increasingly powerful.

**What would break it:** Model capabilities plateau at a level where agents can do basic lookups but can't reason across complex research sessions. If agents stay at "search and summarize" rather than reaching "research and judge," our navigation primitives are over-built.

### A5: The Infrastructure Generalizes Across Domains

We build everything assuming the same collect → extract → serve → learn pattern works for recruiting, real estate, investment research, and other domains. We won't test this until we enter a second domain — but we design for it now.

**What would break it:** When we attempt a second domain, we discover the infrastructure doesn't transfer — the data models, signal extraction, or agent interface patterns are too GTM-specific to generalize. If this happens, we're a GTM company, not a platform company. That's still a good business — but a different one.

---

## Review Cadence

**Hypotheses:** Revisit weekly during the first 6 weeks of go-to-market. Each sales conversation, demo, and user session produces signal. Log it.

**Assumptions:** Revisit monthly. Ask: "Is there any evidence that this assumption is breaking?" If yes, escalate to a hypothesis and start testing.

**Kill conditions:** If any hypothesis hits its kill condition, call a team meeting within 48 hours. The response is either (a) pivot the approach, (b) reframe the hypothesis, or (c) accept the finding and adjust strategy.

---

*This document is the complement to our vision and strategy. The vision says what we believe. The strategy says how we'll win. This document says what we need to prove — and what happens if we're wrong.*
