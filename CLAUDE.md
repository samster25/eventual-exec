# Eventual Exec — Claude Instructions

## Overview
This repo contains the CEO's second brain for running Eventual, built as an Obsidian vault in `second-mind/`.

## Key Files
- `second-mind/README.md` — **Read this first.** Full instructions for navigating and maintaining the vault, including the intake pipeline, conventions, and classification rules.
- `second-mind/dashboard.md` — Daily landing page with links to all key pages.
- `second-mind/intake/` — Drop zone for new documents. Process with "process intake" command.

## Intake Pipeline
When the user asks to "process intake" or mentions new documents:
1. Read `second-mind/README.md` for full instructions
2. Check `second-mind/intake/` for new files
3. Classify, move to `source-documents/`, create/update vault pages, link back to source

## Notion Access
The company also uses Notion for operational data (CRM, engineering planning, market research). Use the Notion MCP tools to fetch current data when needed. See `second-mind/references/notion-index.md` for key page URLs.

## Conventions
- File names: lowercase kebab-case
- Cross-references: `[[wikilinks]]`
- Frontmatter: YAML with title, created, updated, status, related
- Tags: `#hypothesis/h1`, `#hypothesis/h2`, `#hypothesis/h3`, `#evidence/confirms`, `#evidence/weakens`, `#status/active`, `#status/superseded`
