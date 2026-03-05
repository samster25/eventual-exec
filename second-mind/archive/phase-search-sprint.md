---
title: "Phase: Search Sprint (B2B2B)"
created: 2026-03-05
updated: 2026-03-05
status: superseded
related:
  - "[[phase-hackathon]]"
  - "[[decision-log]]"
---

# Phase: Search Sprint (B2B2B)

**Status:** superseded
**Phase:** Feb 9 - 21, 2026 (2 of 3 planned weeks, cut short)
**Conversations:** 11

## What We Tried
WorkOS-for-data — connectors letting agent builders integrate with their customers' internal data sources. B2B2B search product: a context platform for the agent ecosystem.

## Key Learnings
- Everyone keeps intelligence in-house.
- Real pain in building connectors, but no one pays for commodity plumbing.
- Market too small for venture scale — 50+ vertical AI companies all build their own connectors.
- Must pick a specific pain for a specific person (not "better search for agents").
- Had design partners willing to pay — said no because the market signal wasn't right.

## Conversations
- **Nomic** (vertical AI, construction, $4M pipeline in 30 days): Real pain — "Three people in Ukraine, month and a half on one integration." But: "We keep that in-house — that's core competency." 500K SharePoint files, row-level permissions, GPU parsing budgets.
- **Notion:** Wanted better backfills but intended to keep search in-house. Not a buyer — a builder.
- **Wordware:** Wanted connectors via filesystem abstraction. Real need, but commodity infrastructure work.
- **AlphaSense:** Initially interested, but realized they care about signals in raw documents — intelligence layer is their differentiator, not the plumbing.

## Kill Reason
Fatal economics — connector market is commodity infrastructure, not venture-scale. Every conversation had the same shape: real pain in building connectors, but companies either keep intelligence in-house or only need commodity plumbing.

**Conclusion:** Internal data connectors = real pain, fatal economics, thin market. External context is the greenfield.
