---
title: "Hypothesis Signal Tracker"
created: 2026-03-06
updated: 2026-03-06
status: active
related:
  - "[[hypotheses]]"
  - "[[conversation-log]]"
  - "[[icp]]"
---

# Hypothesis Signal Tracker

Source of truth for hypothesis signal across all discovery calls. One row per call, all scores in columns. See [[hypotheses]] for hypothesis definitions and kill conditions.

**Scale:** 1 = strong negative, 2 = weak negative, 3 = neutral, 4 = weak positive, 5 = strong positive. `—` = no data.

---

## Signal Summary

| Hypothesis | Avg Score | Positive (4-5) | Negative (1-2) | Neutral (3) | No Data | Kill Condition Proximity |
|------------|-----------|-----------------|-----------------|-------------|---------|--------------------------|
| **H1** — Research Pain | 3.25 | 2 of 4 | 1 of 4 | 1 of 4 | 0 of 4 | Need 10+ of 20 positive. Currently 2/4. Mixed — GTM leaders see fragmented context pain; AEs say AI already solved it. |
| **H2** — Curated > Web Search | 3.0 | 1 of 2 | 1 of 2 | 0 of 2 | 2 of 4 | Untested head-to-head. Kyle's "would pay more than ZoomInfo" for AI failure history is strongest signal. |
| **H3** — Data Depth on ICP's Targets | 3.7 | 2 of 3 | 1 of 3 | 0 of 3 | 1 of 4 | Mixed — Decagon confirms (Fortune 1000), GoLinks partial, Hyperscience targets logistics (outside coverage). |

---

## Signal Log

| Date | Company | Person | Persona | H1 | H2 | H3 | Bet 1 | Earlyvangelist | Verdict | Key Insight |
|------|---------|--------|---------|----|----|-----|-------|----------------|---------|-------------|
| 2026-03-06 | GoLinks | Jake Summers | AE | 2 | 2 | 4 | Exploring | 2/4 | Zombie | AI solved 90% of research pain. Biggest pain is Salesforce admin. |
| 2026-03-06 | Hyperscience | Kyle Del Francia | AE | 3 | 4 | 2 | Exploring | 2/4 | Zombie | "Have they failed at AI?" is golden question. Would pay more than ZoomInfo for it. |
| 2026-03-03 | Decagon | Daniel Liem | GTM Eng | 4 | — | 5 | Deploying | 3/4 | Good | Integration-first buyer. Fortune 1000 healthcare targets. Offered Gumloop intro. |
| 2026-02-27 | ClickUp | Borys Aptekar | GTM Leader | 4 | — | — | Deploying | 2/4 | Expert | Fragmented context problem is real. "Opinionated intelligence" is the unlock. High bar — already built internal tooling. |

*Blink Health (Ryan) — planned, not yet conducted.*

---

## Notes

- **Pre-scorecard calls** (Decagon, ClickUp): Scores estimated retroactively from interview notes. No formal 1-5 ratings were collected at time of call.
- **H2 is undertested.** Only 2 of 4 calls have H2 signal. Head-to-head comparison still not run. This is the most important experiment.
- **Earlyvangelist 3+:** Decagon/Daniel is the only prospect at 3/4. High-priority follow-up.
