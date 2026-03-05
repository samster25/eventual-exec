---
title: "SUPERSEDED: Search Sprint PRD"
created: 2026-03-05
updated: 2026-03-05
status: superseded
related:
  - "[[phase-search-sprint]]"
  - "[[strategy]]"
---

# SUPERSEDED: B2B2B Context Platform PRD

**Status:** SUPERSEDED
**Original date:** February 4, 2026
**Killed:** February 21, 2026

## What This Was
The product spec for the search sprint era — building connectors for agent builders to access their customers' internal data.

**Vision:** Pre-built connectors (GitHub, Slack, Notion, Linear, Salesforce, etc.), unified search/retrieval, enterprise access control (natural language policy generation + deterministic enforcement), observability and audit logging.

**Three-party model:** Agent Builder (AB) builds AI product -> Agent Customer (AC) owns data, connects via OAuth -> End User interacts with agent.

**Core capabilities planned:**
- Data connectors & ingestion (OAuth, incremental sync, schema normalization)
- Agentic search & navigation (hybrid search, multi-turn, cross-source)
- Access control (hard rules + natural language policy generation)
- Observability & audit (query logs, access logs, token metrics)

**Design partnership structure:** 3-month paid engagements, weekly syncs, milestone-based delivery.

## Why It Was Killed
The connector market is commodity infrastructure and everyone keeps intelligence in-house.

- Nomic, AlphaSense: wanted to keep intelligence in-house, would only outsource commodity tail.
- Notion, Wordware: only needed commodity plumbing with no pricing power.
- Not enough customers with strong enough pain. Fatal economics.

## What Survived
The current product (Eventual Entity Search) takes a fundamentally different approach: **own the intelligence, don't just connect to it.** External context about the world (companies, people, signals) rather than internal data connectors.

Technical concepts that carried forward: agentic search patterns, access control architecture, MCP-native delivery.

**Source:** [[source-documents/product-docs/search-sprint-prd.md]]
