# Marketing OS

The marketing layer of **Portfolio OS** — the operating system [Jukka Blomberg](https://jukkablomberg.com) runs 14 ventures on, with 16 standing AI agents and one founder — packaged so another company can install it, run a check on it, or hire the operator who built it.

Five skills. Each one is a job an agent runs for real, nightly, on live companies — and each `SKILL.md` says **where it runs**, with the public log. Free, in full, under MIT.

> Not a playbook written from a chair. The job split on this page is derived nightly from the studio's own system map; the marketing check is the live tool at northpoint.fi/check/marketing; the AEO audit runs on 15 properties every weekday; the competitor snapshot is delivered to strangers within 48 hours; the weekly review has been written 135 Sundays in a row about the studio itself. Proof: [jukkablomberg.com/agents](https://jukkablomberg.com/agents) · [/dashboard](https://jukkablomberg.com/dashboard) · [/marketing](https://jukkablomberg.com/marketing).

## Install

Everything:

```
npx skills add jukkablomberg/marketingos
```

One skill at a time:

```
npx skills add jukkablomberg/marketingos --skill job-split
npx skills add jukkablomberg/marketingos --skill marketing-check
npx skills add jukkablomberg/marketingos --skill aeo-visibility-audit
npx skills add jukkablomberg/marketingos --skill competitor-snapshot
npx skills add jukkablomberg/marketingos --skill weekly-marketing-review
```

Claude Code:

```
/plugin marketplace add jukkablomberg/marketingos
```

Each skill is one `SKILL.md`: plain Markdown with the method, the rules and the output format. No code, no account, no runtime. Works with Claude, Claude Code, Codex, Cursor or any agent that reads the Agent Skills spec.

## The skills

| Skill | What it does | Where it runs today |
|---|---|---|
| **`job-split`** — start here | Writes `.agents/job-split.md`: the company's marketing functions, each assigned to an agent, a human gate or *not covered*, one line of why. Every other skill reads it first. | [jukkablomberg.com/ai](https://jukkablomberg.com/ai) "Who runs what" — 29 functions, 23 automated, 5 human gates, re-derived at every build; free splits for any company since 2026-11-06 |
| **`marketing-check`** | Eight reads of one page — identity, audience, proof, next step, questions answered, category, trust, where else you are found — score /100, one suggestion per read. | [northpoint.fi/check/marketing](https://northpoint.fi/check/marketing), self-serve, since 2026-11-09 |
| **`aeo-visibility-audit`** | Twelve rules for being cited by AI answer engines, with fixes. | Head of SEO agent, weekdays 03:30 EET, 15 properties; public 4-rule check at [northpoint.fi/check/aeo](https://northpoint.fi/check/aeo) |
| **`competitor-snapshot`** | One competitor, one dated page, every row sourced, three opportunities for you. | Free snapshot at [northpoint.fi/growth](https://northpoint.fi/growth), delivered within 48 h; engine parity-tested on ten competitors |
| **`weekly-marketing-review`** | The measured week in six sections; three flat weeks trigger redesign-or-kill. | Written every Sunday about the studio itself; series at [jukkablomberg.com/dashboard](https://jukkablomberg.com/dashboard) |

**Regulated company?** The compliance layer lives in its own repository — [`jukkablomberg/northpoint`](https://github.com/jukkablomberg/northpoint): MiCA, FCA, GDPR, SEC, MAS, VARA, TGE and ad-creative rule packs, free under MIT. Run `job-split` here first, then the pack for your jurisdiction there.

## Rules this repository keeps

1. **Every skill says where it runs.** A skill with no live run and no public log does not ship here.
2. **No superlatives.** The skills describe what they read; they never grade a company "superior" or "best-in-class", and neither does this README.
3. **Facts are derived, not typed.** The counts above come from the studio's registries and are dated in each skill's metadata; a count that drifts is a bug, not a rounding.
4. **Kill before add.** A new skill replaces or merges an old one unless the set is under eight.

## Versioning

Each skill carries `version`, `authored` and `published` in its frontmatter, and a `runs_on` line naming the live surface. Changes are commits; nothing is rewritten silently.

## Licence

MIT — see [LICENSE](LICENSE). Use it, fork it, run it on a bank or a bakery. Attribution is appreciated, not required.

— JB
