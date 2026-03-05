---
title: "Conversation Log"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[pipeline]]"
  - "[[hypotheses]]"
---

# Conversation Log

Running log of all prospect and customer conversations across the company's lifecycle.

---

## Conversation Velocity

| Era | Timeline | Conversations | Rate |
|-----|----------|--------------|------|
| **Daft Cloud era** | Nov 2025 - mid-Jan 2026 | 39 | ~3/week |
| **Hackathon + Search Sprint** | Late Jan - mid-Feb 2026 | 11 | ~2.5/week |
| **Eventual era** | Feb 19 - Mar 4, 2026 (14 days) | 17 | ~1.2/day |
| **Total** | Nov 2025 - Mar 4, 2026 | **86+** | -- |

**Unique companies engaged:** 60+
**Office Hours (community):** 16

---

## Notable Logos Engaged

Harvey, OpenAI, Notion, Decagon, Snapchat, Suno, Cursor, ClickUp, Scale AI, AlphaSense

---

## Key Conversations by Era

### Daft Cloud Era (Nov 2025 - mid-Jan 2026)

- **Harvey** (dinner, Dec): "Our ingestion pipeline has been stable. What keeps us up at night is search reliability and quality."
- **Rogo** (Tumas Rackaitis, Dec 16): The pivotal call. "The money isn't in selling the infra -- it's in selling the data itself." See [[rogo-tumas]] for full summary.
- **Patreon:** Embedding cost was ~$10K for a full run. Not worth optimizing.
- **Harvey:** "Embedding pipeline cost is dwarfed by AI document reviews."
- **Cursor:** Outdated context "decreases capability by confusing the model."

**Conclusion:** Indexing is solved. The pain is downstream. Multiple conversations pointed toward the same insight: don't sell the tools to process data -- own the intelligence itself.

### Hackathon + Search Sprint (Late Jan - mid-Feb 2026)

- **Wordware:** Semantic search is "probabilistic, noisy" -- a source of context pollution.
- **Rosebud:** RAG pipeline "did not work at all."
- **Cursor:** Wants faster agents and better temporal resolution of context.
- **Nomic** (Andriy Mulyar, 3 calls -- Jan 23, Feb 9, Feb 19): Willing design partner, real pain with integrations. "Three people in Ukraine, month and a half on one integration, not even complete." But: "We keep that in-house -- that's core competency." Would only outsource commodity tail (Teams, Outlook, Gmail). See [[nomic]] for full summary.
- **Notion:** Wanted better backfills but intended to keep search in-house.
- **Wordware:** Wanted connectors via filesystem abstraction. Real need, commodity work.
- **AlphaSense:** Interested in offloading connectors but realized they care about the signals in raw documents -- the intelligence layer is their differentiator.

**Conclusion:** Internal data connectors = real pain, fatal economics, thin market. External context is the greenfield.

### Eventual Era (Feb 19 - Present)

- **Decagon** (Daniel Liem, Mar 3): Building GTM engineering team using Gumloop/Dust to Slack. Immediately engaged on data sourcing. Targets Fortune 1000 (healthcare). Offered to connect with Gumloop founder. See [[decagon-daniel]] for full summary.
- **FullEnrich:** Active GTM-focused conversation.
- **AlphaSense:** Active GTM-focused conversation.
- **ClickUp** (Borys Aptekar, Feb 27): Head of GTM Technology, mature data engineering, AI applications across GTM stack. See [[clickup-borys]] for full summary.
- **Blink Health** (Ryan): Director GTM Ops, data quality concerns. See [[blink-health-ryan]] for summary.

**Conclusion:** More engagement and curiosity than previous phases, but haven't yet proven the pain is acute enough to convert. That's what the next 8 weeks are for.

---

## Conversation Targets

- **Next 8 weeks:** 100 more conversations (targeting AEs, who are easier to book than engineers/founders)
- **Tracking per conversation:** H1 pain score, H3 coverage hit rate, demo reaction
- **Decision point:** End of April 2026
