---
title: "Phase: Hackathon"
created: 2026-03-05
updated: 2026-03-05
status: superseded
related:
  - "[[phase-daft-cloud]]"
  - "[[phase-search-sprint]]"
  - "[[loup-technical-docs]]"
---

# Phase: Hackathon

**Status:** superseded
**Phase:** Jan 20 - Feb 2, 2026
**Conversations:** 11

## What We Tried
Company-wide 2-week agent sprint exploring observability, connectors, retrieval, agentic search. Went broad deliberately — teams explored agent observability, knowledge retrieval, agentic search, data connectors.

## Key Learnings
- Agents are "context-starved" — retrieval is the bottleneck, not generation.
- Internal context is easy at small scale, only hard at enterprise scale (where Glean dominates).
- Two paths emerged: B2B2B connectors or external context.
- Built working prototypes: **Loup** (agentic search), real-time sync.
- Models are only as good as the context you feed them.

## Customer Evidence
- **Wordware:** Semantic search is "noisy" and creates context pollution.
- **Rosebud:** RAG pipeline "didn't work at all."
- **Cursor:** Outdated context "decreases capability by confusing the model." Wants faster agents and better temporal resolution.

## What Went Wrong
- Hackathon felt scattered, ending anticlimactic — leadership didn't provide clear finish line.
- Jay and Sammy were deep in customer conversations and didn't bring the team along well enough.
- No crisp "here's what we do next" moment in final presentations.

**Source:** [[source-documents/memos/all-hands-memo-2026-02-27.md]]
