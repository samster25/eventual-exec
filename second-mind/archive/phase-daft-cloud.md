---
title: "Phase: Daft Cloud"
created: 2026-03-05
updated: 2026-03-05
status: superseded
related:
  - "[[phase-hackathon]]"
  - "[[decision-log]]"
---

# Phase: Daft Cloud

**Status:** superseded
**Phase:** Nov 2025 - mid-Jan 2026
**Conversations:** 39

## What We Tried
Managed ingestion platform for AI teams (Daft Cloud). Thesis: AI teams need to process massive unstructured data for embeddings, indexing, extraction. Daft Cloud would commercialize the Daft engine.

## Key Learnings
- Indexing/embedding infrastructure isn't the bottleneck — it's a solved problem for sophisticated teams.
- Teams want outcomes, not infra.
- Cost of embeddings is trivial (Patreon: ~$10K for full run). Not worth optimizing.
- Search reliability and quality is the real pain, not ingestion.
- Sales pipeline was getting smaller, not bigger.

## Evidence
- **Harvey** (dinner, Dec): "Our ingestion pipeline has been stable. What keeps us up at night is search reliability and quality."
- **Rogo** (Tumas, Dec 16): "If you're just offering parallelization, we're not interested." But planted the seed: "You guys are sitting atop technology that could kill any data provider. The money isn't in selling the infra — it's in selling the data itself."
- **Patreon:** Embedding cost was ~$10K for a full run. Not worth optimizing.
- **Harvey:** "Embedding pipeline cost is dwarfed by AI document reviews."
- **OpenAI, Notion, SafetyKit:** Additional conversations confirming the pattern.

## Kill Reason
Market signals showed customers didn't have strong pain in indexing. The road was getting narrower while opportunities around us were growing faster.

**Source:** [[source-documents/memos/all-hands-memo-2026-02-27.md]]
