---
name: competitor-snapshot
description: One competitor, one dated page. Use when a user names a competitor and asks what it is doing in marketing, asks for a competitor snapshot / teardown-lite / "what are they running", or wants a dated record of a rival's markets, campaigns, offers, claims and listings before a strategy decision or a sales conversation. Reads only the competitor's public surfaces (homepage + up to six same-site pages it links: press, blog, careers, pricing, app listings), records every row with a numbered source and an as-of date, and ends with three growth opportunities for the user's own company. Not a compliance audit and never legal advice.
license: MIT
metadata:
  source: https://jukkablomberg.com/marketing
  author: Jukka Blomberg
  version: 1.0.0
  authored: 2026-10-28
  published: 2026-11-09
  runs_on: the free "one competitor snapshot" at northpoint.fi/growth (delivered within 48 h; engine growth-v0.4, parity-tested on ten competitors 2026-10-30 → 11-01); the Convertor agent reads requests daily at 06:20 and 13:00
---

# competitor-snapshot — one competitor, one dated page

**Where this runs.** This is the method behind the free *one competitor snapshot* at **northpoint.fi/growth**: a founder names one competitor, and within 48 hours receives a dated one-page record. The engine (growth-v0.4) was parity-tested against hand-written snapshots of ten competitors on 2026-10-30, 10-31 and 11-01 (44 matched rows, 7 conflicts, 33 consistent absences on the last run); the Convertor agent of Portfolio OS reads the requests twice a day. Part of Marketing OS — the marketing layer of Portfolio OS: jukkablomberg.com/marketing.

**Before you start:** if `.agents/job-split.md` exists, read the user's company context from it (category words, audience, markets) so the three opportunities at the end are written for *that* company. If it is absent, ask for the user's own company in one line.

---

## Inputs

1. **The competitor's homepage URL.** Fetch it; then fetch up to **six same-site pages it links to**, in this priority: press/news · blog or newsletter · careers/jobs · pricing · product · about/team. Stop at six.
2. **App-store and profile presence**: search the competitor's name on the App Store, Google Play, LinkedIn, X and one review site (Trustpilot or G2) — presence and the listing's own claims only.
3. **Nothing private, nothing invented.** No login, no scraping behind consent, no inference stated as fact. A row you cannot source is written as *not visible* with the surfaces checked.

---

## The record — one page, in this order

```
COMPETITOR SNAPSHOT — <Competitor> — prepared for <User's company> — as of <YYYY-MM-DD>
Record ID: CS-<YYMMDD>-<4 chars>     Sources: numbered [1]…[n] at the foot; every row cites one.

| Dimension | What was read | Source |
|---|---|---|
| Positioning line | the sentence they lead with, verbatim, in quotes | [1] |
| Markets and languages | countries/regions named; site languages; currencies | [1][k] |
| Audience | who they say it is for | [1] |
| Offers and pricing | plans, prices, free tier, trial, promotions, as printed | [k] |
| Campaigns and launches (dated, newest first) | press releases, blog posts, product launches, with dates — only items dated on or before the as-of date | [k] |
| Claims and proof | numbers with units, named customers, awards, licences; adjectives without proof noted as such | [1][k] |
| Channels | newsletter, podcast, YouTube, communities, events — what exists, not how well it performs | [k] |
| Hiring signal | open marketing/growth roles and what they say about the next quarter | [careers] |
| App and profile presence | App Store · Google Play · LinkedIn · X · review site — present/absent, headline rating if shown | [k] |
| Not visible | the dimensions no public surface answered | — |

What this means for <User's company> — three growth opportunities
1. <title> — <two sentences: the gap or the move, and the first step this week>
2. …
3. …

Sources
[1] <url> (read <date>) … [n]
```

Rules for the opportunities: each must trace to a row above; each names a first step the user can take in a week; none proposes a call, a price or a retainer; none is a compliance finding (for a regulated competitor, note "compliance view available separately" and stop there).

---

## Recency and honesty rules (the parity lessons)

- A dated item is included only if its date is **on or before the as-of date**; undated items go in with "undated".
- The positioning line is **verbatim**; everything else is a paraphrase of what was read, never a judgment of the competitor.
- A conflict between two of their surfaces (two prices, two customer counts) is recorded as a conflict, not resolved by guessing.
- Dimensions with no evidence are written as *not visible*, with the surfaces checked — a consistent absence is a finding too.

---

## Output

The one-page record above, plus — if the user wants it as a file — the same content laid out on one A4 page (title block, the table, the three opportunities, numbered sources). Nothing is sent anywhere; delivery is the user's.

## What this skill never does

- Infer internal facts (budgets, team size beyond what careers pages show, revenue) or present estimates as facts.
- Grade or rank the competitor. Every row is a description with a source.
- Propose a call, quote a price, or sell anything inside the record.
