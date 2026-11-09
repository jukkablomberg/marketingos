---
name: weekly-marketing-review
description: The measured week — write the weekly marketing review the way Portfolio OS writes its own every Sunday. Use when a user asks for a weekly marketing report, a Monday number, a review of the week's growth or marketing KPIs, a client or board update on marketing, or wants a fixed weekly format their team or agents can fill. Takes the week's numbers (search impressions and clicks, sessions, leads, replies, revenue, spend, shipped items) and returns six sections: north stars moved or not, per-channel one-liners with flat-week counts, redesign-due items, kill or double-down candidates, the top three moves for next week, and decisions waiting on a human. Numbers only from sources named in the review; never estimated.
license: MIT
metadata:
  source: https://jukkablomberg.com/marketing
  author: Jukka Blomberg
  version: 1.0.0
  authored: 2026-08-24
  published: 2026-11-09
  runs_on: Portfolio OS nightly-reconcile, every Sunday since 2026-08 (W18 written 2026-11-08, 135th run) across 15 properties; the public weekly series at jukkablomberg.com/dashboard; the Friday client report of one venture (VINCAP) since 2026-10-16
---

# weekly-marketing-review — the measured week

**Where this runs.** Portfolio OS writes this review of itself every Sunday night (the W18 review, 2026-11-08, was the 135th run of the agent that writes it) across 15 live properties, and publishes the headline series at **jukkablomberg.com/dashboard** — appended by the system, never backfilled. The same six-section shape is the Friday client report one venture sends its partner. Part of Marketing OS — the marketing layer of Portfolio OS: jukkablomberg.com/marketing.

**Before you start:** if `.agents/job-split.md` exists, its *Agent* table tells you which channels have a standing owner (and therefore a number that should move every week) and which are human gates (whose waiting decisions belong in section 6).

---

## Inputs — named sources only

Every number in the review carries its source and as-of date in brackets. Accept: analytics exports (Search Console, GA4 or equivalent), the CRM or inbox counts (leads, replies, bounces), billing (MRR, collected, active subscriptions), ad platforms (spend, sessions), and the shipped log (what went live). **If a number has no source, the line says "not measured" — never an estimate, never last week's figure carried forward.** The user's own words are context, not data.

---

## The six sections

```
# Weekly marketing review — W<n> (<Mon> → <Sun>), written <date>

Headline: <one sentence: the number that moved most, the one that did not, and the one decision this week needs — all with figures.>

## 1. North stars — moved or not, with numbers
- Revenue: MRR · collected (28 d) · active subscriptions [source, as-of]. Flat-week count if flat.
- Organic: impressions · clicks (28 d), top three properties or pages [source].
- Pipeline: leads · replies · meetings, by channel [source].
- Paid: spend · sessions · engaged share · cost per engaged session [source].
- Distribution: placements, referring domains, mentions [source].
- Decision queue: open items · median age · oldest.

## 2. Per-channel one-liners — KPI · direction · flat-weeks
One line per channel that has an owner: the KPI, ↑ ↓ →, and how many weeks it has been flat.

## 3. Redesign-due
Any channel or loop flat for three weeks: say so, name the redesign-or-kill proposal.

## 4. Kill / double-down candidates
Up to three of each, each with the number that argues for it.

## 5. Top three moves for next week
Three, scored impact · effort · confidence, each with an owner and a date.

## 6. Decisions waiting on a human
Each open decision in one row: what, since when, the recommended answer, the value at stake.
```

Word budget: the whole review under 600 words. A table beats a paragraph; a number beats an adjective.

---

## Rules that make it a review and not a newsletter

1. **One KPI per channel.** If a channel has two, the review picks the one money follows.
2. **Three flat weeks triggers section 3.** Not two, not four. The rule is the point: it removes the argument.
3. **Shipped ≠ moved.** What went live is context in section 1; it earns nothing until a number moves.
4. **Paid is reported ex-paid too.** Organic and paid human visits are stated separately so a budget cannot flatter a channel.
5. **No celebration without a figure, no alarm without one either.**

---

## What this skill never does

- Estimate, interpolate or carry a number forward.
- Rename a KPI mid-series (the series is the asset; a rename is a new series with a dated note).
- Hide a flat week behind a shipped list.
