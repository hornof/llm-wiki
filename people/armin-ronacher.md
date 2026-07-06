---
name: Armin Ronacher
type: person
affiliation: independent (creator of Flask; early Sentry)
signal_sources: [blog, github, twitter]
last_updated: 2026-07-06
---

## Who They Are

Armin Ronacher is a well-known open-source developer — creator of the Flask web framework and the Jinja2 template engine, and an early engineer at Sentry. In 2026 he is building **Pi**, a coding harness that competes with [[claude-code|Claude Code]], and writing high-signal posts on the practical friction of building agent/tool-use infrastructure on top of frontier models.

## Their Current Focus

- **Agent/tool-use infrastructure** via Pi — including how different frontier models behave against non-native tool schemas.
- Practitioner-level analysis of model regressions that only show up when you're building the harness, not just using it.

## Notable Takes

- **"Better Models: Worse Tools" (2026-07-04)**: newer Claude models ([[claude-opus-4-8|Opus 4.8]], [[claude-sonnet-5|Sonnet 5]]) are *worse* than their predecessors at calling Pi's edit tool — they invent schema fields that don't exist, causing the harness to reject otherwise-correct edits. His hypothesis: RL-tuning the models to excel at Claude Code's *native* search-and-replace edit tool degraded their handling of *third-party* schemas. "The SOTA models of the family are worse at this specific tool schema than their older siblings." A concrete capability-alignment gap and a caution against "newer = strictly better integration." — [[armin-ronacher-better-models-worse-tools-2026-07-04]] (surfaced via [[simon-willison|Willison]]).

## Where to Follow

- Blog: lucumr.pocoo.org
- GitHub: github.com/mitsuhiko
- Twitter/X: @mitsuhiko
