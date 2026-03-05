# Processed Intake Files

Claude checks this list before processing intake to avoid reprocessing files that have already been ingested into the vault. If a file in `intake/` matches an entry here (by original filename or content), skip it.

---

## 2026-03-05 — Initial Vault Build

All files below were processed during the initial vault creation. Raw files archived in `source-documents/`.

### Board Decks
| Original Path | Archived To |
|---|---|
| `intake/board-meetings/2026/Q1/board-deck-q1-2026.md` | `source-documents/board-decks/board-deck-q1-2026.md` |
| `intake/board-meetings/2026/Q1/post-meeting-action-items.txt` | `source-documents/board-decks/post-meeting-action-items-q1-2026.txt` |

### Product Docs
| Original Path | Archived To |
|---|---|
| `intake/eventual-entity-product/eventual-product-vision.md` | `source-documents/product-docs/eventual-product-vision.md` |
| `intake/eventual-entity-product/eventual-product-strategy.md` | `source-documents/product-docs/eventual-product-strategy.md` |
| `intake/eventual-entity-product/eventual-market-hypotheses.md` | `source-documents/product-docs/eventual-market-hypotheses.md` |

### User Interviews
| Original Path | Archived To |
|---|---|
| `intake/user-interviews/rogo-transcript.txt` | `source-documents/interviews/rogo-tumas-2025-12-16.txt` |
| `intake/user-interviews/daniel-transcript.txt` | `source-documents/interviews/decagon-daniel-2026-03-03.txt` |
| `intake/user-interviews/nomic/nomic-transcript-1.txt` | `source-documents/interviews/nomic-call-1-2026-01-23.txt` |
| `intake/user-interviews/nomic/nomic-transcript-2.txt` | `source-documents/interviews/nomic-call-2-2026-02-09.txt` |
| `intake/user-interviews/nomic/nomic-transcript-3.txt` | `source-documents/interviews/nomic-call-3-2026-02-19.txt` |
| `intake/user-interviews/borys.md` | `source-documents/interviews/clickup-borys-notes.md` |
| `intake/user-interviews/borys-transcript.txt` | `source-documents/interviews/clickup-borys-transcript.txt` |
| `intake/user-interviews/ryan.txt` | `source-documents/interviews/blink-health-ryan-transcript.txt` |

### All-Hands & Memos
| Original Path | Archived To |
|---|---|
| `intake/all-hands-02-27-26/memo-v4.md` | `source-documents/memos/all-hands-memo-2026-02-27.md` |
| `intake/all-hands-02-27-26/inputs/memo.md` | `source-documents/memos/hackathon-wrap-up-memo.md` |
| `intake/all-hands-02-27-26/inputs/gtm-internal-memo-shared-version.md` | `source-documents/memos/gtm-internal-memo-shared.md` |
| `intake/all-hands-02-27-26/inputs/full-gtm-memo-not-shared.md` | `source-documents/memos/gtm-internal-memo-full.md` |
| `intake/all-hands-02-27-26/inputs/mid-sprint-refocusing.md` | `source-documents/memos/mid-sprint-refocusing.md` |
| `intake/all-hands-02-27-26/inputs/02-23-26-kickoff.md` | `source-documents/memos/search-sprint-kickoff-2026-02-23.md` |
| `intake/all-hands-02-27-26/inputs/Search_standup_learnings.txt` | `source-documents/memos/search-standup-learnings.txt` |
| `intake/all-hands-02-27-26/inputs/memo-meeting-transcript.md` | `source-documents/transcripts/memo-meeting-transcript.md` |
| `intake/all-hands-02-27-26/inputs/Refocusing Transcript - 01-20-26.txt` | `source-documents/transcripts/refocusing-transcript-2026-01-20.txt` |
| `intake/all-hands-02-27-26/inputs/prompts-v2.md` | `source-documents/product-docs/signal-prompts-v2.md` |
| `intake/all-hands-02-27-26/inputs/sales/deck.md` | `source-documents/product-docs/sales-deck.md` |
| `intake/all-hands-02-27-26/inputs/eventual-search-sprint.prd` | `source-documents/product-docs/eventual-search-sprint.prd` |

### Skipped (Duplicates)
The following were identified as duplicates during initial processing and were NOT imported separately:
- `intake/hack-sprint-wrap-up/*` — exact duplicates of `all-hands-02-27-26/inputs/*`
- `intake/loud-prd-search-sprint/loup.md` — archived as `source-documents/product-docs/loup-technical-docs.md`
- `intake/loud-prd-search-sprint/eventual-prd.md` — archived as `source-documents/product-docs/search-sprint-prd.md`
- `intake/loud-prd-search-sprint/initial-design-doc.md` — archived as `source-documents/product-docs/initial-design-doc.md`
- `intake/loud-prd-search-sprint/prd-structure.md` — archived as `source-documents/product-docs/prd-structure.md`
- `intake/loud-prd-search-sprint/product-icp.md` — archived as `source-documents/product-docs/product-icp-old.md`
- `intake/loud-prd-search-sprint/eventual-overview-notion.md` — archived as `source-documents/product-docs/eventual-overview-notion.md`
- `intake/loud-prd-search-sprint/gtm-reachouts.md` — archived as `source-documents/product-docs/gtm-reachouts-old.md`
- `intake/loud-prd-search-sprint/hacksprint-demo-and-discussion-transcript.md` — archived as `source-documents/transcripts/hacksprint-demo-transcript.md`

## 2026-03-05 — Stephen Transition

| Original Path | Archived To | Vault Pages Updated |
|---|---|---|
| `intake/stephen-transition-plan.md` | `source-documents/memos/stephen-transition-plan-2026-03-04.md` | `decisions/active/stephen-transition.md` (created), `decisions/decision-log.md`, `people/daft-team.md`, `dashboard.md` |
