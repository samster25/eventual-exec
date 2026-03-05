---
title: "Daft Roadmap 2026 (from Notion)"
created: 2026-03-05
updated: 2026-03-05
status: reference
related:
  - "[[daft-team]]"
  - "[[notion-index]]"
---

# Daft Roadmap 2026

> For full detail and live updates, see [Notion: Daft Roadmap 2026](https://www.notion.so/303091bd86348042aa0dc6c28967c035)

## Performance

| Project | Timeline | Owner | Description |
|---------|----------|-------|-------------|
| Flight Shuffles | Q1 | Srinu | Native shuffling services for Flotilla data transfer via Arrow Flight RPC |
| Flotilla 1.75 | Q2 | - | Next-gen distributed engine — dynamic task scheduling to minimize worker setup overhead |
| Swordfish Memory Management | - | Srinu | Track/manage memory in local runner — reduce OOMs, inform backpressure, dynamic batching/partitioning |
| Improved Joins & Aggregations | - | Srinu | Better partitioning and hash-table techniques for groupby aggregations and hash joins (low-cardinality) |
| Dynamic Batching Strategies | - | Cory | Improved dynamic batching |
| Adaptive Partitioning | - | Srinu | Adaptively distribute partitions |

## Features

| Project | Timeline | Owner | Description |
|---------|----------|-------|-------------|
| Key-based Checkpointing | Q2 | Rohit | Incremental processing with key-based checkpoints |
| Multi-write Sinks | - | Rohit | Write to multiple destinations |
| Variant Types | - | Kevin | VARIANT type compatible with Parquet VARIANT |
| Result Types | - | Kevin | Result<T> (Either) type for graceful fallible operation handling |
| Native Extensions | - | Kevin | Arrow C interface extensions — extend Daft in any language with C interop |
| Task-based Checkpointing | - | Rohit | Checkpoint at task granularity |

## Observability

| Project | Timeline | Owner | Description |
|---------|----------|-------|-------------|
| OTEL Support | Q1 | Sam | Metrics, traces, and logs via OpenTelemetry |
| Dashboard + Flotilla Integration | - | Sam | More query visualizations, Flotilla integration |

## Maintenance

| Project | Timeline | Owner | Description |
|---------|----------|-------|-------------|
| Arrow2 Deprecation | - | Cory | Migration from Arrow2 (~90% complete as of Mar 2026) |

## Current Sprint (Week of Mar 2, 2026)

Key items from latest planning:
- **Shuffles:** Srinu writing design doc (EOD Mon), lineage tracking, Flight shuffle on other operations
- **Observability:** Sam getting dashboard working in Ray runner, Desmond improving backend metrics
- **Checkpointing:** Rohit doing requirements gathering from Eventual team (Wed)
- **Community:** Arrow migration EOW goal — Cory cleanups, Kevin Parquet work (~3 PRs away)
- **Infra:** YK doing account consolidation, SOC2 minutes
