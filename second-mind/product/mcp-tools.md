---
title: "MCP Tools"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[strategy]]"
  - "[[roadmap]]"
---

# MCP Tools

Eventual delivers intelligence through 5 MCP tools that agents can call. No UI, no workflow builder, no dashboard -- the agent decides what to research.

---

## The 5 Tools

| Tool | Purpose | Interaction |
|------|---------|-------------|
| `search_companies` | Find companies by industry, funding, size, signals | Entry point -- wide search |
| `get_company_profile` | Complete brief: info, people, jobs, content, signals | Go deep on one company |
| `search_people` | Find people by role, title, company, seniority | Navigate the org |
| `get_person_profile` | Full person dossier: experience, posts, connections | Understand the champion |
| `search_content` | Search blogs, JDs, LinkedIn posts | Surface timing signals |

---

## The Drill-Down Pattern

```
search_companies  -->  get_company_profile  -->  search_people  -->  get_person_profile  -->  search_content
     (wide)              (deep on one)           (navigate org)       (understand person)      (timing signals)
```

**search -> profile -> people -> person -> content**

Each step is a navigable branch point where the agent decides what thread to pull next. This is fundamentally different from batch enrichment (Clay) or bulk export (ZoomInfo) -- it's a conversational, drill-down research pattern that mirrors how a skilled AE actually thinks.

---

## Product Philosophy / Strategic Principles

### Intelligence, Not Workflow
We don't orchestrate workflows. We don't have a table UI. We don't ask the user to design enrichment steps. The agent decides what to research based on context. We provide the intelligence; the agent provides the reasoning.

### Navigable, Not Exportable
The value is in the drill-down: start broad, go deep, follow threads. Not in exporting a flat CSV of 10,000 contacts. Each tool call returns rich context with natural follow-up paths -- not rows in a spreadsheet.

### Agent-Native, Not Human-Native
Built for MCP tool calls, not for humans clicking buttons. The interface is the protocol. Works with Claude, GPT, or anything that supports MCP. The demo IS the product -- Jay asks "who are you trying to sell to?" then uses Eventual to find champions and signals live.

### Deep, Not Broad
We serve high-ACV, account-based sellers who need to deeply understand 100 target accounts -- not spray-and-pray SDR teams who need 10,000 email addresses. 15-30 tool calls per deep research session vs. 1-2 for shallow lookup.

### Fresh, Not Static
Signals matter: who's hiring, publishing, expanding, leaving. A static database tells you who works at a company. Eventual tells you what's changing at that company right now. The watch/monitor feature (Weeks 7-8) inverts the direction -- signals come to you.

### The Demo IS the Product
Jay asks "who are you trying to sell to?" then uses Eventual to find champions and signals live. When it works, it's a compelling moment. Constraint: only works when targets overlap with our coverage.

---

## Compatibility

- Works with Claude Code / Claude Desktop (primary)
- Works with OpenAI (via MCP)
- Works with any MCP-compatible client
- Pluggable into agent frameworks: Gumloop, Dust, custom builds
- API key distribution for multi-user support (Weeks 4-6)

---

## Current State (as of Mar 5, 2026)

- 5 MCP tools working
- ~994 companies indexed
- ~117K people profiles
- Concentrated in AI/ML sector
- 1-5 external demos completed
- Internal MVP in daily use
