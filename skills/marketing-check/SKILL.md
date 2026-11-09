---
name: marketing-check
description: The Marketing check — eight reads of one page (identity, audience, proof, next step, questions answered, category, trust, where else you are found), a score out of 100 and one suggestion per read. Use when a user pastes or links a homepage or landing page and asks whether it says what the company is, how clear or convincing it is, how it reads to a first-time visitor or to an AI assistant, or asks for a marketing check / homepage review / positioning read. Returns the same card as the public check at northpoint.fi/check/marketing. Heuristic: information about the page, not a verdict on the company. Not a compliance check — for MiCA, FCA, GDPR, SEC, MAS or VARA use jukkablomberg/northpoint.
license: MIT
metadata:
  source: https://jukkablomberg.com/marketing
  author: Jukka Blomberg
  version: 1.0.0
  authored: 2026-11-09
  published: 2026-11-09
  runs_on: northpoint.fi/check/marketing (public, self-serve, live since 2026-11-09); the same eight reads, same weights, same bands
---

# marketing-check — eight reads, one page

**Where this runs.** This is the rule set behind the public, self-serve check at **northpoint.fi/check/marketing** (URL or pasted text → scored card, shareable link, printable). It is the first horizontal check on the shelf next to NorthPoint's eleven compliance checks. Every other "AI marketing assessment" we could find in November 2026 is a self-reported survey; this one reads the page. Part of Marketing OS — the marketing layer of Portfolio OS: jukkablomberg.com/marketing.

**Before you start:** if `.agents/job-split.md` exists, read its *Context the other skills read* block (category words, audience, markets) and use those words when you judge reads 1, 2 and 6. If it is absent, run `job-split` once, or proceed on the page alone and say so.

---

## Input

One page's text: the homepage by default, or any landing page the user names. If you can fetch the URL, read the rendered text (headings, body, buttons, footer). If the fetched text is under ~200 words, say the page is thin or script-rendered and ask for pasted copy rather than grading an empty document.

---

## The eight reads

Each read returns **STRONG** (1), **WEAK** (½) or **GAP** (0), a one-sentence message that describes what was read, and — when not STRONG — one suggestion. Messages never say what the company *should be*; they say what the page *does*.

| # | Read | STRONG when | Severity if missing |
|---|---|---|---|
| 1 | **Identity** — one sentence says what you are | a sentence in the first screen has the shape *[Name] is a [category] for [who] that [does what]* | GAP |
| 2 | **Audience** — names who it is for | the buyer is named on the first screen ("for Nordic agencies", "for founders raising a seed round") | WEAK |
| 3 | **Proof** — proof on the page, not adjectives | at least two of: a number with a unit, a named customer or partner, a dated fact, a named credential or licence. Adjectives without proof ("leading", "world-class", "seamless", "superior") are quoted back | WEAK |
| 4 | **Next step** — one clear ask | at least one imperative ask (start free, book a demo, request a quote, apply) and no more than four competing ones | GAP if none; WEAK if more than four |
| 5 | **Questions answered** — answer-shaped content | FAQ or direct question-and-answer content the reader (or an answer engine) can lift | WEAK |
| 6 | **Category** — a phrase an AI can attach | a plain category noun is present and repeated (software, agency, bank, marketplace, platform …) | WEAK |
| 7 | **Trust basics** — a place, a legal entity, a named person, policies | at least two of the four | WEAK |
| 8 | **Where else you are found** — the places a buyer checks | the page points to a store listing, a review site or a profile (App Store, Google Play, LinkedIn, GitHub, Trustpilot, G2, Capterra …) | WEAK |

---

## Score and bands

Score = round(100 × (STRONG + ½ × WEAK) / 8).

- **CLEAR** — 75 and above. The page says what it is, for whom, and proves it; fix the weak reads in order.
- **UNEVEN** — 35 to 74. Some reads land, some do not; the suggestions are the work list.
- **UNCLEAR** — below 35. A first-time visitor cannot tell what this is or what to do; start with reads 1 and 4.

---

## Output — the card

```
MARKETING CHECK — <host or "pasted text"> — <YYYY-MM-DD>
<BAND> · score <n>/100 · <s> strong · <w> weak · <g> gap

1. Identity — STRONG|WEAK|GAP
   <what was read>
   Suggested fix: <one line>            ← only when not STRONG
… (reads 2–8 in order)

Eight reads of one page, as text heuristics. Information about the page, not a verdict on the company.
```

When the user wants it for a job application or a client conversation, keep the card as is and add one closing line of your own observation; do not inflate the score.

---

## What this skill never does

- Grade the company, its team or its product — only the page.
- Use "superior", "best-in-class" or any superlative in its own messages.
- Invent a fact the page does not carry. If a read cannot be made from the text given, say so and mark it WEAK with the reason.
- Replace the compliance layer: a regulated company's claims still go through the relevant `jukkablomberg/northpoint` pack.
