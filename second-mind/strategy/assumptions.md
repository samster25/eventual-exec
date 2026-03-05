---
title: "Assumptions — Not Actively Testing"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[hypotheses]]"
  - "[[strategy]]"
---

# Assumptions (Not Actively Testing — But Named)

These are beliefs we hold with enough conviction to build on. We don't have the resources or timeline to test them right now, but we name them so we can track them and react if they start breaking.

Extracted from [[hypotheses]] for quick reference.

---

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
