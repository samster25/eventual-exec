---
title: "Vault README — Instructions for Claude"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[dashboard]]"
---

# Eventual CEO Second Brain — Vault Guide

This README is written for Claude (AI agent) to understand, navigate, and maintain this Obsidian vault. It is the primary reference when processing new documents or updating existing pages.

## Vault Purpose

This is Sammy Sidhu's (CEO of Eventual) second brain for running the company. It contains strategy, product plans, customer insights, decisions, meeting notes, and reference material. The vault is designed to be agent-friendly — Claude Code can read, search, and update any file.

## Folder Structure

```
second-mind/
├── README.md              # THIS FILE — instructions for Claude
├── dashboard.md           # Daily landing page with links to key pages
├── intake/                # DROP ZONE — new files land here for processing
├── source-documents/      # Permanent archive of all processed raw files
│   ├── board-decks/       # Board decks, investor updates
│   ├── memos/             # Internal memos, all-hands, sprint wrap-ups
│   ├── interviews/        # Raw interview/call transcripts
│   ├── transcripts/       # Meeting transcripts, recordings notes
│   ├── product-docs/      # PRDs, design docs, technical specs
│   └── misc/              # Anything that doesn't fit above
├── strategy/              # Vision, strategy, hypotheses, bets, competitive landscape
├── product/               # Roadmap, MCP tools, data strategy, pricing
├── customers/             # ICP, personas, pipeline, conversation log
│   └── interviews/        # Structured interview summaries (NOT raw transcripts)
├── people/                # Team, Daft team, board & advisors
├── decisions/             # Decision log + active decisions
│   └── active/            # Decisions currently being tracked
├── meetings/              # Meeting notes (board, all-hands, offsite, 1:1s)
├── journal/               # Weekly reviews, daily notes
├── archive/               # Historical phases, superseded documents
├── references/            # Notion summaries, external reference material
└── templates/             # Templates for recurring note types
```

## Intake Pipeline

### How to Process New Documents

When the user says "process intake" or drops files into `intake/`:

1. **Read** each file in `intake/`
2. **Classify** the document type (see classification rules below)
3. **Move** the raw file to the appropriate `source-documents/` subfolder
   - Use a descriptive kebab-case name: `{topic}-{date-or-context}.md`
   - Example: `nomic-call-3-2026-02-19.txt`, `board-deck-q1-2026.md`
4. **Create or update** the relevant vault pages (see routing rules below)
5. **Link** the new vault page back to the source: `> Source: [[source-documents/interviews/company-name-date.md]]`
6. **Remove** the file from `intake/` (it now lives in `source-documents/`)
7. **Check** `PROCESSED.md` in this folder — skip any file already listed there
8. **Log** the processed file in `PROCESSED.md` with date, source path, and destination
9. **Report** to the user: files processed, pages created/updated, items needing review

### Classification Rules

| Document Type | How to Identify | Source Destination | Vault Pages to Update |
|---|---|---|---|
| Interview / call transcript | Q&A format, names + companies, "transcript" in name | `source-documents/interviews/` | Create `customers/interviews/{company}.md`, add to `customers/conversation-log.md`, tag with hypothesis evidence |
| Board deck / investor update | Slides, metrics, runway, asks | `source-documents/board-decks/` | Create `meetings/board-{date}.md`, update strategy/ and product/ pages as needed |
| All-hands / team memo | Internal comms, team updates, morale | `source-documents/memos/` | Create `meetings/all-hands-{date}.md`, update `decisions/decision-log.md` if decisions mentioned |
| Product doc / PRD | Requirements, specs, architecture, design | `source-documents/product-docs/` | Update relevant `product/*.md` pages |
| Sprint / retro doc | Sprint goals, learnings, demos | `source-documents/memos/` | If historical: `archive/`. If current: update `product/roadmap.md` |
| Raw notes / misc | Unclear structure, personal notes | `source-documents/misc/` | Ask user where it belongs |

### Routing: Which Vault Pages to Update

When processing an intake document, use this guide:

- **Contains hypothesis evidence (H1/H2/H3)?** → Update `strategy/hypotheses.md` evidence section
- **Contains a strategic decision?** → Add to `decisions/decision-log.md`
- **Contains customer/prospect interaction?** → Add to `customers/conversation-log.md`
- **Contains product changes or roadmap updates?** → Update `product/roadmap.md`
- **Contains competitive intelligence?** → Update `strategy/competitive-landscape.md`
- **Contains team changes or org updates?** → Update `people/team.md` or `people/daft-team.md`
- **Contains ICP refinement?** → Update `customers/icp.md`

## Conventions

### File Naming
- All lowercase kebab-case: `board-2026-q1.md`, `clickup-borys.md`
- No spaces, no special characters
- Dates in ISO format when included: `2026-03-05`

### Frontmatter (YAML)
Every page gets:
```yaml
---
title: "Page Title"
created: 2026-03-05
updated: 2026-03-05
status: active  # or: superseded, template, reference
related:
  - "[[page-name]]"
  - "[[other-page]]"
---
```

### Wikilinks
- Always link to canonical vault pages, NOT to source documents or intake files
- Use `[[page-name]]` format (Obsidian resolves across folders)
- For section links: `[[hypotheses#H1]]`
- For display text: `[[hypotheses|market hypotheses]]`

### Tags
Keep the tag vocabulary small:
- `#hypothesis/h1`, `#hypothesis/h2`, `#hypothesis/h3` — evidence related to specific hypotheses
- `#evidence/confirms`, `#evidence/weakens` — on interview/conversation notes
- `#status/active`, `#status/superseded` — document lifecycle
- `#action-item` — tasks needing follow-up

### Source References
When creating vault pages from source documents, always include:
```
> Source: [[source-documents/{subfolder}/{filename}]]
```

## What Lives in Obsidian vs. Notion

**Obsidian (this vault):** CEO thinking, strategy, hypotheses, decisions, customer insights, weekly reviews, meeting summaries. Updated by Sammy via Claude Code.

**Notion (source of truth for team ops):**
- CRM database (Outreach CRM) — live prospect tracking
- Weekly engineering planning — team coordination
- Market research tables — collaborative research
- Daft roadmap — engineering milestones
- GTM Goals — weekly targets and champion tracker

See `references/notion-index.md` for links to all key Notion pages. The `references/` folder contains condensed summaries of Notion content with links back for full detail. These summaries may go stale — re-fetch from Notion when accuracy matters.

## How to Update Existing Pages

- **Append, don't overwrite** — add new entries to logs (decision-log, conversation-log) at the top
- **Update frontmatter** — always bump `updated:` date when modifying a page
- **Mark superseded** — if a page is no longer current, change status to `superseded` and add a note pointing to the replacement
- **Link new to existing** — when creating a new page, add wikilinks to/from related existing pages

## Key Pages Quick Reference

| Need | Go To |
|------|-------|
| Daily overview | `dashboard.md` |
| Current strategy | `strategy/strategy.md` |
| What we're testing | `strategy/hypotheses.md` |
| Product roadmap | `product/roadmap.md` |
| Who we're selling to | `customers/icp.md` |
| Prospect pipeline | `customers/pipeline.md` |
| Recent decisions | `decisions/decision-log.md` |
| Notion links | `references/notion-index.md` |
| Templates | `templates/` folder |
