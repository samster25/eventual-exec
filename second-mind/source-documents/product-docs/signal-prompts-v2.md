# Eventual — Sample Prompts

Your reps spend hours researching accounts manually — piecing together funding announcements, job postings, conference talks, and LinkedIn profiles before they can even write a first email. That research is tedious, inconsistent, and doesn't scale.

Eventual replaces that with signal-based intelligence. One sentence of intent in, structured and sourced research out. Your team gets the same quality of account research in seconds that used to take 45 minutes per account — and every data point links back to its source.

---

## How It Works

**Intent → Signals → Approve → Structured Data**

1. **State intent.** Your rep (or their agent) describes what they care about in plain language.
2. **Eventual proposes signals.** The platform translates that intent into concrete, trackable signals — conference talks, hiring patterns, content activity, social posts, code contributions.
3. **Approve and run.** Your team reviews the proposed signals, adjusts if needed, and kicks off the search.
4. **Get structured, sourced results.** Every result comes back as structured data with evidence links — ready to pipe into Salesforce, Outreach, Slack, or your own agent workflows.

### Output Modes

| Mode | What it returns | Use case |
|------|----------------|----------|
| `companies` | Name, domain, stage, headcount, location, signals matched, signal evidence, key contacts | SDR building a prospecting list |
| `people` | Name, title, company, LinkedIn, signal history, relevance score, suggested outreach angle | SDR researching who to contact |
| `brief` | Account brief with expandable sections: overview, team, tech stack, signals, competitors, talking points | AE prepping for a call |
| `watch` | Ongoing alerts as structured events with signal type, entity, evidence, and suggested action | Continuous team monitoring |

---

## The Prompts

---

### 1. Signal-Based ICP Search

**Role:** SDR Manager / SDR | **Output:** `companies` + `people`

> Build my SDR team a target list of Pre-Series B companies, under 500 employees, that genuinely care about open-weight models. Include confidence scores and the strongest signal per company.

#### How it works

Eventual proposes signals to validate genuine interest (not just keyword matches):

- **Conference signal** — Employee gave a talk about open-weight topics (LLaMA, Mistral, Qwen, fine-tuning, GGUF)
- **Content signal** — Engineering blog post about deploying, fine-tuning, or benchmarking open-weight models
- **Code signal** — GitHub contributions to open-weight model repos or tooling (vLLM, llama.cpp, Hugging Face transformers)
- **Hiring signal** — Job postings requiring experience with open-weight models or referencing them in the stack
- **Social signal** — Technical leaders posting about open-weight models on LinkedIn, Twitter, or Hacker News

Your team approves. Eventual runs and returns a structured dataset:

```
Company           | Stage    | Headcount | Top Signal         | Confidence | Contact          | Evidence
Acme AI           | Series A | 85        | conference_talk    | High       | Jane Chen, VP Eng | MLOps Meetup talk: "Fine-Tuning LLaMA for Production" (link)
Inference Labs    | Seed     | 30        | code_contribution  | High       | Alex Park, CTO    | 140+ commits to vLLM in last 90 days (link)
ModelStack        | Series A | 120       | hiring_pattern     | Medium     | —                 | 4 roles mentioning open-weight model experience (link)
```

#### Where the data comes from

| Signal type | Sources |
|-------------|---------|
| Conference talks | Luma, YouTube, Meetup.com, published session lists from major ML conferences |
| Content | Company engineering blogs, Medium, dev.to, Substack |
| Code | GitHub public repos, contribution graphs, org activity |
| Hiring | Greenhouse, Lever, Ashby, LinkedIn Jobs |
| Social | LinkedIn posts, Twitter/X, Hacker News threads |

#### Why this is different

**Before:** An SDR spends 30+ minutes per batch manually checking LinkedIn, GitHub, and job boards, guessing which companies actually care about open-weight models vs. which ones just mention "AI" on their homepage. Results are inconsistent across the team — every rep has different research quality.

**After:** One prompt, one approval step. The entire SDR team works from the same signal-validated list. Each company comes with evidence links and a confidence score, so reps prioritize the strongest signals first. Pipe the output straight into Salesforce or Outreach.

---

### 2. Competitive Displacement

**Role:** AE | **Output:** `companies` + `people`

> Find companies that are likely outgrowing or frustrated with [Competitor] and would be open to switching. Show me the evidence.

#### How it works

Eventual proposes signals for competitive displacement — each one tied to a specific, verifiable source:

- **Review signal** — Negative or "switching" language in recent G2, Capterra, or TrustRadius reviews from identifiable companies
- **Forum signal** — Reddit, Hacker News, or community threads where employees describe workarounds, limitations, or frustration with [Competitor]
- **Hiring signal** — Job postings mentioning "migration," "evaluating alternatives," or "replacing [Competitor]"
- **Content signal** — Engineering blog posts describing workarounds for [Competitor]'s limitations or evaluations of alternative tools
- **Movement signal** — Senior engineering or exec hires who previously led a migration away from [Competitor] at a prior company

Your team approves. Eventual returns structured results with every claim linked to its source:

```
Company        | Frustration Signal     | Evidence (linked)                                          | Confidence | Decision Maker
DataFlow Inc   | review + forum         | G2 review: "scaling limits" (link) · HN thread (link)      | High       | Sarah Kim, VP Eng
Korra Systems  | hiring + content       | JD: "migrate off [Competitor]" (link) · Blog post (link)   | High       | Mike Torres, Head of Platform
Orbit AI       | movement               | New CTO previously led [Competitor] → [Your Product] at Co | Medium     | James Liu, CTO
```

#### Where the data comes from

| Signal type | Sources |
|-------------|---------|
| Reviews | G2, Capterra, TrustRadius (public reviews with company attribution) |
| Forum discussion | Reddit, Hacker News, Stack Overflow, vendor community forums |
| Hiring language | Greenhouse, Lever, Ashby, LinkedIn Jobs, Indeed |
| Content | Engineering blogs, Medium, dev.to (workaround and evaluation posts) |
| Exec movement | LinkedIn career history, press announcements |

#### Why this is different

**Before:** Your AE manually scans G2 reviews, searches Reddit, and hopes to stumble onto a signal that someone is unhappy with the competitor. It's hours of work for maybe 2–3 leads, and there's no systematic way to cover all the places frustration surfaces.

**After:** Eventual searches across reviews, forums, job boards, engineering blogs, and exec career moves simultaneously. Every result includes the source link — your AE walks into the conversation already knowing *why* the prospect is frustrated, with evidence they can reference. Push displacement alerts to Slack so your team catches signals the week they happen, not the month after.

---

### 3. Pre-Call Intelligence Brief

**Role:** AE | **Output:** `brief`

The simplest version:

> Build me a brief on Acme Corp. I have a discovery call Thursday.

Or, for structured output your agent can traverse:

> Build me a structured brief on Acme Corp for my Thursday discovery call. Include confidence indicators on data points and flag anything that's more than 90 days old.

#### How it works

Eventual assembles a sourced, structured brief:

```
brief.overview        → Series B, $40M raised (Crunchbase, Mar 2025), 180 employees, AI-powered logistics
brief.team            → CTO: Pat Rivera (ex-Google Brain) · VP Eng: Dana Choi (ex-Uber ML Platform) ↗ High confidence
                        Head of Product: Morgan Wells (ex-Stripe) ↗ Medium confidence (LinkedIn last updated 6mo ago)
brief.tech_stack      → Python, Kubernetes, Ray, currently using [Competitor] for model serving
                        Sources: 3 job postings (Lever), GitHub org repos, CTO conference talk
brief.signals         → CTO gave a talk at MLOps Community about inference cost — Oct 2025 (link) ↗ High
                        VP Eng blog post about outgrowing current infra — Aug 2025 (link) ↗ High
                        3 ML platform roles posted in last 45 days (links) ↗ High
brief.competitors     → [Competitor A] (enterprise), [Competitor B] (OSS) — Acme likely cost-sensitive based on funding stage
brief.talking_points  → Lead with CTO's inference cost talk — reference specific points they made
                        VP Eng's blog post describes the exact problem your product solves
                        They're hiring ML platform engineers — position as buy vs. build
```

Each section links to its source. Confidence indicators (High / Medium / Low) flag data freshness and reliability. Downstream agents can drill in: *"Expand brief.team — what's the VP Eng's full career history?"* or *"Which signals are from the last 30 days?"*

**Try it on an account you already know well.** Run a brief on a company where you have inside knowledge and see how Eventual's output compares. That's the fastest way to calibrate trust.

#### Where the data comes from

| Data point | Sources |
|------------|---------|
| Funding & stage | Crunchbase, PitchBook, press releases |
| Team & people | LinkedIn profiles, company about pages |
| Tech stack | Job descriptions (Greenhouse, Lever), GitHub repos, engineering blogs |
| Signals (talks) | YouTube, Luma, conference session archives |
| Signals (content) | Company blogs, Medium, dev.to |
| Signals (code) | GitHub public activity, contribution graphs |
| News & press | News APIs, TechCrunch, company newsrooms |

#### Why this is different

**Before:** Your AE spends 45 minutes before every discovery call: scanning LinkedIn, Googling the company, reading Crunchbase, checking job postings, searching for recent news. The research quality depends entirely on how thorough that individual rep is. New reps miss signals that veterans would catch.

**After:** One prompt produces a structured, sourced brief in seconds. Every data point has a confidence indicator and a source link. Senior AEs get the same quality they'd produce manually — faster. Junior AEs get research quality they couldn't produce on their own. The brief is a live object your tools can query, not a static doc that goes stale.

---

### 4. Champion Discovery

**Role:** AE | **Output:** `people`

> I'm trying to sell into [Target Company]. Who's my champion? Use our closed-won customers as a pattern — the people who bought from us before tend to share certain traits.

#### How it works

Eventual learns what your champions look like by analyzing patterns across your closed-won deals (imported from your CRM). Then it proposes signals for finding similar people at the target company:

- **Authority signal** — Title suggests decision-making power over the problem your product solves (platform, infrastructure, ML engineering leadership)
- **Familiarity signal** — Previously evaluated or purchased similar tools at a prior company. Worked at one of your existing customers.
- **Conviction signal** — Spoke publicly about the problem space you solve (conference talks, blog posts, podcasts)
- **Accessibility signal** — Active on LinkedIn or Twitter, engages with industry content, responds to outreach
- **Career pattern signal** — Career trajectory matches your champion profile from closed-won deals (e.g., rose through platform engineering, moved from IC to management)

Returns a ranked list with evidence:

```
Rank | Name           | Title           | Champion Signals                        | Confidence | Evidence
1    | Dana Choi      | VP Engineering  | authority + familiarity + conviction    | High       | Ex-[Customer], spoke at KubeCon on infra tooling (link), active on LinkedIn
2    | Raj Patel      | Sr Staff Eng    | familiarity + conviction + accessibility| High       | Ex-[Customer], 12 blog posts on ML platforms (links), 2K LinkedIn followers
3    | Morgan Wells   | Head of Product | authority + career_pattern              | Medium     | Career path matches champion profile, no public content yet
```

**The compounding value for your team:** When a new SDR joins, they don't need to spend months learning "what kind of person buys from us." Eventual encodes your champion criteria from historical wins. The new rep queries Eventual and gets the same champion identification quality as your best AE on day one.

#### Where the data comes from

| Signal type | Sources |
|-------------|---------|
| Profiles & career history | LinkedIn (current role, past roles, tenure, progression) |
| Public speaking | Conference speaker lists (Luma, YouTube, session archives), podcast guest lists |
| Content authorship | Engineering blogs, Medium, dev.to, Substack (byline matching) |
| Code contributions | GitHub (repos, contribution frequency, project types) |
| Social activity | Twitter/X, LinkedIn posts and engagement |
| Champion patterns | Your CRM data — closed-won contacts, buyer personas, deal history |

#### Why this is different

**Before:** "Who's my champion?" depends entirely on the rep's intuition and experience. A senior AE might know to look for an ex-customer or a conference speaker. A new SDR checks LinkedIn titles and guesses. There's no systematic way to transfer champion-finding expertise across the team.

**After:** Eventual learns your champion pattern from your actual wins and applies it at every target account. New reps inherit the team's collective intelligence from day one. Every recommendation comes with evidence links — your AE doesn't just know *who* to reach out to, they know *why* this person is likely a champion, and they have a warm angle to open with.

---

### 5. Continuous Watch

**Role:** SDR Manager / AE Manager | **Output:** `watch` (ongoing alerts)

> Watch my team's ICP for buying signals. We sell AI infrastructure to Series A–C startups. Route alerts to the rep who owns the account, or to round-robin if it's net-new.

#### How it works

Eventual proposes signals to monitor continuously:

- **Conference signal** — Technical leader gives a talk about infrastructure challenges you solve
- **Content signal** — Engineering blog post about scaling AI workloads or evaluating tooling
- **Hiring surge signal** — 2+ relevant platform roles posted in the same week at a single company
- **Funding signal** — Company in your pipeline (or matching your ICP) raises a new round
- **Re-entry signal** — Former customer employee joins a new company in a senior role
- **Code signal** — Company appears in a relevant GitHub trending repo's contributor list for the first time

Your team approves the signal set. Eventual monitors and delivers structured alerts:

```json
{
  "signal": "conference_talk",
  "person": { "name": "Jane Chen", "title": "VP Engineering", "linkedin": "..." },
  "company": { "name": "Acme AI", "stage": "Series B", "headcount": 120 },
  "evidence": {
    "event": "MLOps Community Meetup",
    "title": "Why We're Rebuilding Our Inference Stack",
    "date": "2026-02-20",
    "url": "..."
  },
  "routing": { "assigned_rep": "Taylor (owns Acme AI in Salesforce)", "channel": "#acme-ai-signals" },
  "suggested_action": "Reference her talk about rebuilding the inference stack. She described exactly the problem your product solves. Reach out within 48 hours while the talk is fresh."
}
```

**Alerts route to the right place.** If the account exists in Salesforce, the alert goes to the owning rep via Slack. If it's net-new, it enters the round-robin queue. Managers get a weekly digest of all signals across the team's pipeline — a single view of what's happening across every account.

**It gets smarter over time.** Every alert your team acts on (or ignores) teaches Eventual which signals actually convert. After 30 days, signal quality improves. After 90 days, Eventual can tell you which signal *types* drive the most pipeline for your team — so you double down on what works.

#### Where the data comes from

All signal sources are monitored on a continuous polling basis:

| Signal type | Sources | Polling frequency |
|-------------|---------|-------------------|
| Conference talks | Luma, YouTube, Meetup.com, conference calendars | Daily |
| Content | Engineering blogs, Medium, dev.to, Substack | Daily |
| Hiring | Greenhouse, Lever, Ashby, LinkedIn Jobs | Daily |
| Funding | Crunchbase, PitchBook, news APIs, press releases | Real-time where available |
| People movement | LinkedIn career changes, press announcements | Daily |
| Code activity | GitHub public repos, trending repos | Daily |
| Social | LinkedIn posts, Twitter/X, Hacker News | Hourly |

#### Why this is different

**Before:** Your team checks job boards and LinkedIn once a week — maybe. Buying signals are spotted days or weeks late, if they're spotted at all. There's no system for routing signals to the right rep, so half of them fall through the cracks. Managers have no visibility into what signals are hitting across the pipeline.

**After:** One setup prompt creates a persistent, multi-signal monitoring pipeline for the entire team. Alerts are structured, sourced, and routed — to Slack, to Salesforce, to the rep who needs them. Managers get a pipeline-level view of every signal across every account. And the system compounds: the more your team uses it, the better it gets at surfacing the signals that actually drive pipeline.

---

## The Pattern

Every prompt follows the same flow:

**Intent → Signals → Structured Data → Action**

The intelligence lives in the platform, not the prompt. Your team doesn't need to know what signals to look for — that's Eventual's job. And the output isn't a report for a human to read and retype — it's structured data that flows straight into Salesforce, Outreach, Slack, or your agent workflows.

| What traditional tools give you | What Eventual gives you |
|------|----------------|
| Filters (stage, headcount, geo) | Filters + signals + evidence + confidence scores |
| Static CSV exports | Structured data your tools can query and act on |
| User defines every parameter | Platform proposes signals from intent |
| One-shot search results | Persistent watches with routed alerts |
| Results vary by rep quality | Consistent, sourced intelligence across the team |
