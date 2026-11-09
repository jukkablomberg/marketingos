---
name: job-split
description: The foundation skill of Marketing OS — write the company's Job Split once, before any other marketing skill runs. Use when a user asks which marketing jobs could go to AI agents and which should stay with a person, asks to "split" or map a marketing function, says "who runs what", is setting up Marketing OS for a company, or when any other skill in this repository is about to run and `.agents/job-split.md` does not exist. It writes `.agents/job-split.md` — the company's marketing functions, each assigned to an agent, a human gate or "not covered", with one line of why — which `marketing-check`, `aeo-visibility-audit`, `competitor-snapshot` and `weekly-marketing-review` read first. It contains no rules and returns no verdict; it is the facts file, not an audit.
license: MIT
metadata:
  source: https://jukkablomberg.com/marketing
  author: Jukka Blomberg
  version: 1.0.0
  authored: 2026-11-09
  published: 2026-11-09
  runs_on: jukkablomberg.com/ai "Who runs what" (29 functions · 23 automated · 5 human gates, derived nightly from the Portfolio OS system map); the free split at jukkablomberg.com/ai#job-split (delivered within 48 h since 2026-11-06)
---

# job-split

Write the split down once. Every other skill in this repository reads the result before it does anything.

**Where this runs.** This is the frame Portfolio OS — the operating system behind 14 ventures, 16 standing agents and one founder — runs on. The live split of the studio itself is published at **jukkablomberg.com/ai** ("Who runs what": 29 functions, 23 automated, 5 human gates, 0 not covered, 1 not pursued, re-derived at every build from the system map so it cannot drift). Since 2026-11-06 any company can request its own split free at jukkablomberg.com/ai#job-split; the Convertor agent drafts it from the company's public site and sends it within 48 hours. Marketing OS is the marketing layer of Portfolio OS: jukkablomberg.com/marketing.

---

## When to activate

- The user asks which marketing jobs could go to AI agents and which should stay human, or says "split", "job split", "who runs what", "map our marketing function".
- Any other Marketing OS skill is about to run and `.agents/job-split.md` is missing or older than the company's last material change (a new channel, a new market, a team change, a product launch).
- The user is setting up Marketing OS for a company — their own or a client's.

Do not activate this skill to grade anything. It produces facts and assignments; the checks produce verdicts.

---

## Inputs — in this order, and only these

1. **The company's public surfaces**: homepage, product pages, team/about, careers, pricing, blog or newsletter, social profiles, app-store listings. Read what is there. **Never invent a fact about the company**; where a function is invisible from outside, write "not visible from outside" rather than guessing.
2. **The user's answers**, if they volunteer them: team size, channels, tools, budget, regulated or not.
3. **The default human gates** (below). They apply to every company unless the user removes one in writing.

---

## The function inventory

List every marketing job the company has or should have, grouped. Use these seven groups — the same ones the live studio table uses — and add functions, never groups:

| Group | Typical functions |
|---|---|
| **Strategy** | positioning and messaging · opportunity research and prioritisation · market and competitor research · pricing |
| **Build** | website and landing pages · design and brand identity · content production · release and deploy |
| **Growth** | SEO · AI-search visibility (AEO) · growth execution and distribution · paid media · inbound and conversion · outbound drafting · community and social · partnerships · customer support (marketing-facing) · contacts and relationship graph |
| **Measure** | analytics and user behaviour · weekly review and reporting · experiments |
| **Operate** | marketing state and nightly reconcile · the leader's daily brief · organisational learning · systems maintenance |
| **Human gates** | external sends · money go-live and spend · secrets and access · signing and accepting terms · key personal relationships |
| **Not pursued** | anything the company has decided not to do, named, so the gap is visible |

A function that is nobody's is written as **not covered** — the gap is the finding, not an embarrassment.

---

## Assignment — three answers, one line of why each

For every function, one of:

- **Agent** — a standing AI agent can do the volume: it is repeatable, its inputs are on disk or public, its output is reviewable, and a wrong run is reversible. Name the cadence (daily / weekdays / weekly) and what the agent reads and writes.
- **Human gate** — a person decides or presses: it spends money, sends to a third party, signs, grants access, or touches a relationship only that person holds. Name the person's role.
- **Not covered** — nobody does it today. One line on what it would take.

The **five default human gates** travel with every split: *external sends · money go-live · secrets and access · signing and accepting terms · key personal relationships*. An agent may draft inside each; the press is a person's. Removing a gate is the user's written decision, recorded in the file with a date.

The *why* line is one sentence, in plain words, from the company's own situation — "answered from your FAQ and order history", "anything that spends", "nobody writes the Monday number today".

---

## Output — `.agents/job-split.md`

```markdown
# Job Split — <Company> — <YYYY-MM-DD>

Source: <the public URLs read>, <user answers if any>. Facts not visible from outside are marked.

## Summary
<n> functions · <a> agent · <h> human gates · <u> not covered · <p> not pursued

## Agent
| Function | Cadence | Reads → writes | Why |
|---|---|---|---|

## Human gates
| Function | Who | Why |
|---|---|---|

## Not covered
| Function | What it would take |
|---|---|

## Not pursued
| Function | Decision (dated) |
|---|---|

## Context the other skills read
- Category words the company uses for itself: …
- Audience named on its surfaces: …
- Markets / languages: …
- Regulated: yes/no — if yes, run the compliance layer (`jukkablomberg/northpoint`) after this file exists.
```

Keep it to one page. Counts are computed from the tables, never typed separately.

---

## Worked example — the studio's own split (abridged, as of the metadata date)

29 functions. **Agent (23):** opportunity research (daily 01:10), brand and marketing strategy (weekdays 03:30), SEO across 15 properties (weekdays 03:30), growth execution and distribution (weekdays 03:30), inbound and conversion + outbound drafting + customer support (daily 06:20 and 13:00), analytics and user behaviour (daily 00:05), product build (daily 02:40), design and brand identity (weekdays 15:07), nightly self-heal (23:00), the founder's daily brief (weekdays 07:30), organisational learning and systems maintenance (Mondays), app teardowns (daily 09:11), monitoring runs (daily 02:13), weekly client report (Fridays). **Human gates (5):** external sends, money go-live, secrets and access, signing and accepting terms, key personal relationships. **Not covered (0). Not pursued (1):** fundraising and investor relations, by choice. The live, current version is the table at jukkablomberg.com/ai.

---

## What this skill never does

- Invent a company fact, a team size or a tool the company does not show.
- Grade the company. No score, no verdict, no "superior".
- Remove a human gate on its own.
