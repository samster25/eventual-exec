---
title: "Nomic - Consolidated Interview Notes (3 Calls)"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[hypotheses]]"
  - "[[conversation-log]]"
---

# Nomic - Consolidated Interview Notes

**Call 1:** January 23, 2026 -- Andriy Mulyar (co-founder) + Sammy
**Call 2:** February 9, 2026 -- Andriy Mulyar + Jay + Sammy (deep technical session)
**Call 3:** February 19, 2026 -- Bob (engineering lead) + Jay + Sammy (PRD walkthrough)
**Company:** Nomic -- vertical AI for built-world sectors (architecture, engineering, construction)
**Context:** Nomic was the most engaged design partner prospect during the Search Sprint / B2B2B connector phase. Across three calls, the iceberg of complexity emerged -- and ultimately the realization that B2B2B connectors was the wrong business to build.

---

## Company Background

Nomic pivoted from an infrastructure company (vector lake / embedding models) to a verticalized AI product for the built-world sector (architecture, engineering, construction). Key facts:

- Previously an ollama-style company with quarter million monthly active users, stuck at ~$500K ARR for 3 years selling infrastructure
- Pivoted to vertical AI about a year ago -- building custom parsing models for architectural drawings (400-page multimodal PDFs)
- Post-trained VLMs that outperform foundation models (and sometimes human architects) on domain-specific tasks
- **Explosive growth:** Grew pipeline by $3-4 million in 30 days, onboarded 10 new customers in one week (from zero two months prior)
- ~20-person team with engineers in Ukraine building integrations
- Customers are primarily Microsoft shops (Teams + Outlook + SharePoint) -- "I don't know if we've talked to a single one that uses Notion or Slack"

---

## Call 1 (Jan 23): The Problem Statement

Andriy framed the problem as a "WorkOS for data integrations" -- a B2B2B model where Eventual would handle the long tail of data source connectors so Nomic's agents could access customer data.

### The Integration Pain

> "We have three people in Ukraine smacking out these integrations because the product doesn't exist. Someone will have to maintain those as those APIs change. We'll have production outages in the future, I'm sure of it."

> "We thought we'd do two integrations a month. We've spent a month and a half doing one. And it's not even complete because of the long tail."

### The Ideal Product (as Andriy described it)

> "There's a gallery of integrations this product supports. I pick Autodesk Construction Cloud. Our app is now integrated. When a customer onboards, they hit go. We are now getting charged $100/month for that one integration. And then there's usage-based components for tool calls against the index."

He compared the pricing model to WorkOS -- per-integration fees plus usage.

### Progressive Indexing (Not Full Indexing)

A critical nuance: Nomic doesn't want to index everything. A 20-person engineering company can have 50 terabytes of data on SharePoint.

> "It is number one infeasible to index all of that data. It is also not valuable. And also they won't work with you if you try to do that."

> "We've realized we have to do this smart progressive indexing where, as our agent needs a piece of data indexed, we can have layers from a fast index all the way up to running through a parsing model where neural nets are doing inference."

Their agents have a hierarchy of operation costs and navigate from cheap (glob/scan) to expensive (full parse) as needed.

### But: "We Keep That In-House"

Even in this first call, the boundary was clear:

> "There are certain things that the business wants to own, and there are certain things they don't want to own."

Nomic wanted to keep ownership of:
- The blob store / data storage
- The parsing and ML layer (their core competency)
- Deep integrations with domain-specific platforms (Autodesk Construction Cloud, Procore)

They'd only outsource:
- The commodity tail: Teams, Outlook, Gmail
- Simpler integrations where search-based endpoints suffice

---

## Call 2 (Feb 9): Deep Technical Session

This was a detailed technical requirements gathering session. Key topics:

### Data Source Complexity

- Primary sources: SharePoint (500K+ files per customer), Ignite, Autodesk Construction Cloud, Procore, Bentley
- One customer had 500K files in a single SharePoint drive -- "it took two days at SharePoint's max rates"
- File types: 400-page multimodal PDFs (architectural drawings), project data, email, chat
- Privacy/permissions: Row-level access controls, per-file permissions, must mirror source system permissions exactly
- Volume: Terabytes per customer, but only a subset should be indexed

### How Their Agent Works

The agent operates in a mixed mode:
1. **Intensive document work** on a few key files (deep parsing, multimodal analysis)
2. **Broader search** over codes/standards, knowledge bases, and external sources
3. **Light operations** (glob, metadata scan) over the full file system

> "People have intensive problems focused on a couple key documents... then they can do really intensive multi-agent flows on them."

### What They'd Outsource vs. Keep

Bob (Call 3) was even more explicit:

> "My sense is the core competencies we've built up -- how to deal with a shit ton of data and figure out how to deal with it -- has been decently scalable. When I look at ways third-party services can help me, I'm primarily thinking about the long tail of integrations."

The first problem (large file processing) and third problem (permissions) are core competency. The second problem (building each integration) is the pain they'd outsource.

---

## Call 3 (Feb 19): PRD Walkthrough with Bob

Bob is the engineering lead managing the integration team. This was a detailed walkthrough of the Eventual PRD and technical requirements.

### The Three Classes of Problems (Sammy's Summary, Bob Agreed)

1. **Cost of parsing large files** at customer scale -- core competency, they want to keep
2. **Fixed labor cost of building each integration** -- the big blocker, willing to outsource
3. **Heterogeneous permissioning models** across sources -- has to be good enough, but sunk cost already invested

### SharePoint Dominance

> "All of our customers are Microsoft companies. I genuinely don't know if we've talked to a single one that uses Notion or Slack. They are almost all Teams plus Outlook plus SharePoint."

### Integration Complexity

Bob built the SharePoint integration himself -- it took months:

> "I built the SharePoint one. For months, essentially. Went through multiple different versions of it. We got to the point that it is working successfully for these document sets."

Each new integration breaks existing abstractions:

> "You can try to build some abstractions around integrations, and then a new service comes in, and it breaks all your abstractions because they do things differently."

### What They'd Want from Eventual

For commodity integrations (email, chat):
- Search-based endpoints are sufficient
- Don't need deep parsing -- "I just wanna be able to say, 'you had an email three days ago from the guy on the job site'"

For domain-specific integrations (ACC, Procore):
- Need brokered access to raw files (for their own parsing pipeline)
- Won't go through a third party's indexing

### Sync and Freshness

> "Keeping data in sync when it comes to very large sets is often one of the hardest parts of this."

They need different sync strategies per data source -- some can be brokered real-time, some need periodic sync with storage.

---

## Why This Design Partnership Didn't Proceed

Across three calls, the pattern became clear:

1. **Real pain** in building integrations -- undeniable, quantified (months of engineering time, team in Ukraine)
2. **But the intelligence layer is core competency** -- they'd never outsource parsing, document understanding, or domain-specific integrations
3. **Only the commodity tail was available** -- Teams, Outlook, Gmail. Low pricing power, high competition
4. **The economics don't work** for a startup: build bespoke connectors for enterprise data sources, charge $100/month per integration, compete with Merge/Paragon on the commodity end

This pattern was universal across Search Sprint conversations (Nomic, Notion, Wordware, AlphaSense): real pain in connectors, but everyone keeps the intelligence in-house. The addressable market for "general-purpose data connectors to your customers' data" was too small.

---

## Key Quotes

On integration pain:
> "Three people in Ukraine, month and a half on one integration, not even complete."

On keeping intelligence in-house:
> "We keep that in-house -- that's core competency."

On their growth:
> "We grew pipeline by $3-4 million bucks in the last 30 days and onboarded 10 new customers last week. And we were onboarding zero customers two months ago."

On the infrastructure trap (Andriy on Nomic's own pivot):
> "We got a bunch of users of our open source product... We raised a crap ton of money and then we were stuck at half a million ARR for three years because nobody wanted to buy the infra shit."

---

## Impact on Company Direction

The Nomic calls were a key input into the decision to abandon the B2B2B connector path and pursue Eventual Entity Search. The iceberg pattern -- real pain on the surface, core competency underneath, commodity tail with no pricing power -- repeated across every Search Sprint conversation. External context became the greenfield by elimination.
