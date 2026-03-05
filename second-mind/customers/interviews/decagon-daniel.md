---
title: "Decagon - Daniel Liem Interview"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[hypotheses]]"
  - "[[pipeline]]"
  - "[[conversation-log]]"
---

# Decagon - Daniel Liem Interview

**Date:** March 3, 2026
**Participants:** Jay Chia, Sammy Sidhu, Daniel Liem (Founder's Office, Decagon)
**Source:** Bluedot recording
**Context:** One of the first demos in the Eventual era. Daniel represents the tertiary buyer persona -- the "Founder's Office" operator building strategic functions at a fast-growing startup.

---

## Company Background

Decagon is a fast-growing AI company (only 2 years old) building customer support AI. Key facts:

- Growing rapidly, needs to build out functions in 1 year that normally take 5
- Daniel is on the "Founder's Office" team -- focused on building strategic initiatives and new functions
- Covers corp dev, startup ecosystems, GTM engineering, training data for proprietary models
- **Target market:** Fortune 1000, with a focus on healthcare
- **ICP buyer:** CXO / Customer Support team leaders
- Also expanding into the BPO world (replacing call centers)
- Currently building a GTM engineering function using Gumloop and Dust, with everything running through a Slack bot

---

## The Demo

Jay and Sammy showed the MCP-based product in Claude Code. Key demo moments:

- Searched for accounting companies and asked for top accounts to sell a GTM people search product to
- The system returned target companies with reasoning for why they'd be good targets, identified champions, and explained why each would be a good champion
- Showed real-time navigation: company search -> company profile -> people search -> person profile

---

## Daniel's Reaction and Key Questions

Daniel was immediately engaged but focused on the data sourcing question -- a sign of technical sophistication:

> "How are you getting this data? Let me see the..."

When told Eventual is buying data and crawling:

> "How much do they cost? Must be expensive."

> "How do you know if it's comprehensive or not? Because, like, why would I consider you guys over Clay?"

Jay differentiated from Clay:

> "Clay I would classify as more of an enrichment tool. You can use Clay to get columns of enrichments. What we're doing is actually a lot richer. We're aggregating across companies and pre-computing the signals. With Clay, you would still have to manually curate various signals and manage data quality yourself."

---

## Integration Path: Gumloop + Slack

Daniel's primary interest was plugging Eventual into his existing agent infrastructure, not adopting a new UI:

> "I'm in the middle of using Gumloop or Dust in order to build a simple Slack bot that is able to port all the data. Everything's going to live in a Slack UI."

> "If you could do that, I'll hook you up really easily into our platform because we just want to run everything through one Slack bot."

He offered to connect the team with Max, the founder of Gumloop:

> "I could connect you to Max, the founder or other folks at Gumloop if you want. We're like close in touch with them."

---

## Target Account Details

When asked about his ICP's target accounts:

> "All Fortune 1000."
> "We're trying to break into healthcare especially."

Buyer within those targets:

> "CXO Customer support team. And then like we are moving more into the BPO world as well, replacing the BPOs, like call centers and stuff."

This is strong evidence for H3 (our ICP sells upmarket to Series C-Fortune 500+). Decagon is a Series-stage AI company targeting Fortune 1000 healthcare companies -- exactly the pattern H3 predicts.

---

## Tool Fatigue Signal

Daniel expressed fatigue with AI tools that promise too much:

> "We are fatigued about all these different tools. We're building specific things to solve core problems instead of just building an all-in-one lighthouse-type solution that does everything. The accuracy is still difficult and you have to have all these different prompt tuning to make it work."

This validates the "intelligence not workflow" philosophy -- Daniel doesn't want another tool. He wants data he can plug into what he's already building.

---

## Key Takeaways

1. **Founder's Office / GTM Engineer is a real buyer persona.** Daniel has budget authority and a clear need. He's building GTM infrastructure for a company growing faster than its processes.

2. **Integration-first, not UI-first.** Daniel's first question was "does this work with Gumloop?" not "show me your dashboard." Validates our MCP-native, API-first approach.

3. **Fortune 1000 targets confirm H3.** Decagon is exactly the pattern: AI startup (our ICP) selling upmarket to Fortune 1000 (their targets). Our data strategy must cover enterprise healthcare companies.

4. **Data sourcing is the credibility question.** "How are you getting this data?" was Daniel's first real question. Prospects care about data pipeline quality, not just output quality.

5. **Gumloop connection is valuable.** Direct intro to the Gumloop founder could open a partnership/integration path for distribution.

6. **Tool fatigue is real.** Don't sell another tool. Sell intelligence that plugs into existing workflows.

---

## Next Steps

- Build Gumloop integration (or verify MCP compatibility)
- Ensure Fortune 1000 healthcare company coverage in our data
- Circle back with Daniel in ~2 weeks (after offsite)
- Pursue Gumloop founder connection for potential partnership
