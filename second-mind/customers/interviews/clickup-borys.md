---
title: "ClickUp - Borys Aptekar Interview"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[hypotheses]]"
  - "[[conversation-log]]"
---

# ClickUp - Borys Aptekar Interview

**Date:** February 27, 2026
**Participants:** Sammy Sidhu, Jay Chia, Borys Aptekar (Head of GTM Technology, ClickUp)
**Source:** Bluedot recording
**Context:** Expert interview with a deeply experienced GTM technology leader. Borys is building AI into ClickUp's GTM workflows -- automated inbound, NL quoting, AI-driven MEDDPICC evaluation. Uniquely positioned because he's both a builder and a buyer of GTM tools.

---

## Borys's Background

Borys has a deep career arc in GTM systems and technology:

- Started in sales ops, moved to marketing ops, landed in RevOps
- "Master's degree" in CPQ (Configure Price Quote) tools -- ran a giant change management implementation
- Ran a GTM tech stack solo at a ~400-person company
- At ClickUp: initially PM for a GTM technology team, now leading AI applications across GTM
- Previous companies include Instabase, Motive, AppDynamics, VMware

---

## ClickUp's GTM Technology Maturity

ClickUp is unusually mature in data engineering for a GTM org:

> "We are particularly blessed here at ClickUp with a really, really well-invested-in and very mature data engineering function. We have a very well modeled set of data and tables and we just kind of have already done a lot of the stitching that is oftentimes like 80% of what these tools do."

Example: Before Gong, they already had Chorus transcripts flowing into a data warehouse pipeline with LLM extraction layered on top:

> "When Gong came knocking and they were like, look at all this stuff we can do. And we're like, well we already do that. We've already built the infrastructure to handle that."

This positions ClickUp as a sophisticated evaluator -- they won't be impressed by basic enrichment. They need differentiated intelligence.

---

## AI Projects at ClickUp

Borys walked through several AI-in-GTM projects:

### AI SDR / Automated Inbound
- Built an AI SDR for inbound lead handling
- Mixed results: works well enough to be useful, but not good enough to fully replace humans
- Political dynamics emerged: VP Sales pushes back when AI "takes leads away from human sellers"

> "People were like, oh my God, we're gonna deploy this everywhere, we're not gonna need reps. Then rubber meets the road. Expectations meet reality. It's not as good. And people are like, this is actually taking leads away from human sellers."

> "Guess who's pretty powerful in a sales org? The VP of Sales. And they're like, why are we sending these leads to something that doesn't get credit for them?"

This led to push-pull cycles of enthusiasm vs. protectionism.

### NL Quoting
- Natural language interface for generating quotes
- Leverages their mature data engineering foundation

### AI-Driven MEDDPICC Evaluation
- Using AI to evaluate deal qualification against the MEDDPICC framework
- Pulls from call recordings, CRM data, email -- mostly internal data
- The "three whys" approach: don't hand a finished document, hand something that says "go find out ways to fill these next two or three bullet points"

---

## The BDR Research Use Case

Borys described a compelling use case from one of their BDRs that maps directly to Eventual's value proposition:

> "He will call a bunch of BTLs -- managers, ICs, team leads. If they pick up, he does some discovery. 'What's your company's AI appetite?' 'Oh, we actually have really draconian policies in place.' Or 'What's your most painful process in marketing?'"

The problem comes after the calls:

> "He calls 20 people. Now what do I do next? Okay, I want to follow up on that AI security thing. So I need to go find their security and IT people. So let me go back out to ZoomInfo. Let me go find their security, import them, import them into Outreach, get them into a sequence. Meanwhile, I have to keep all the notes on the side because all that information is somewhere in Gong."

This is the **fragmented context problem** -- information is scattered across Gong notes, ZoomInfo lookups, Outreach sequences, and the rep's memory. No single system stitches it together.

---

## What Borys Wants from AI in GTM

### Augmentation, Not Replacement

> "You're not looking to replace your reps. You're looking to actually increase the effectiveness of your organization overall."

### Opinionated Intelligence, Not Just Information

> "That's where I really want to see the market go -- not just presenting information but presenting opinionated information. Like Cloud Code with a developer: this is what I want and it generates the code for you. You can't quite do that in sales. But you can make that job easier."

> "Not just 'will give you more information, more stuff.' It was actually 'you can get better as a seller using this.'"

### Active Coaching Over Data Dumps

The "three whys" MEDDPICC approach impressed him:

> "Hey, we can help you connect the dots. But ultimately I'm not handing you a finished document. I'm handing you something that says, go find out ways to fill these next two or three bullet points. Because I only got one from what you said. Now I'm going to guess at the others."

---

## Build vs. Buy Evaluation Framework

ClickUp constantly evaluates build vs. buy for GTM tools:

> "We're constantly in that evaluation cycle. Build this ourselves specifically for us or are there vendors on the market that we can integrate into the tech stack and leverage instead of having to go through the build and maintenance cycle ourselves?"

They've built some things that still stand, others that didn't work and were replaced by vendors. The bar for buying is:
1. Does it do something we haven't already built?
2. Is the data quality and accuracy reliable?
3. Does it integrate with our existing stack (they have a very mature data warehouse)?

---

## On Sales Process Maturity

Borys noted that AI tools for GTM work better with companies that have mature sales processes:

> "It probably applies more to companies that have more mature sales processes. Because then you have directionality."

This aligns with our ICP requirement for companies with 3+ outbound reps and established GTM motions.

---

## Key Takeaways

1. **The fragmented context problem is real.** The BDR use case (call 20 people, then scramble across ZoomInfo, Outreach, Gong to act on what you learned) is exactly the research pain H1 tests.

2. **Augmentation > replacement.** VP Sales will resist tools that threaten the human sales motion. Position as "make your reps 2x more effective" not "replace your reps."

3. **Opinionated intelligence is the unlock.** Not just information presentation -- the AI should tell you what to do next, which gaps to fill, who to call.

4. **ClickUp is a sophisticated buyer.** They've already built most of what basic enrichment tools offer. They need something differentiated -- deep intelligence, not data aggregation.

5. **Mature data engineering is both opportunity and risk.** They already have the stitching layer most tools provide. Eventual needs to offer intelligence on top that they can't build themselves (external context about the world).

6. **AISDR political dynamics are important.** VP Sales ownership and credit structures create real organizational resistance to AI replacing any part of the human sales motion.

---

## Relevance to Eventual

Borys's BDR use case is a near-perfect match for what Eventual's drill-down pattern enables: after a round of discovery calls, the agent could navigate org charts, find the right security/IT people, surface context about AI policies, and synthesize everything -- all from within a single conversation. The fragmented context problem (Gong + ZoomInfo + Outreach + memory) is exactly what a unified intelligence layer solves.

His emphasis on "opinionated information" aligns with our philosophy of deep intelligence over shallow enrichment.
