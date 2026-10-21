---
name: gstack
type: tool
category: software-factory
status: emerging
last_updated: 2026-10-21
---

## What It Is

**gstack** ([github.com/garrytan/gstack](https://github.com/garrytan/gstack), MIT) is [[garry-tan|Garry Tan]]'s (YC President/CEO) open-source **software factory**: 23 opinionated [[claude-code|Claude Code]] skills that turn one agent into a virtual engineering team — slash-command roles across a Think → Plan → Build → Review → Test → Ship → Reflect sprint loop (`/plan-ceo-review`, `/plan-eng-review`, `/design-review`, `/review`, `/qa`, `/cso`, `/ship`, `/canary`, `/retro`, …). Installs into `~/.claude/skills/gstack/`; without it Claude Code starts blank.

README claims (his numbers, unverified): **135K+ GitHub stars** (as of 2026-10-01) and shipping at *"~810× my 2013 pace."*

## gbrain

Companion but separate project ([github.com/garrytan/gbrain](https://github.com/garrytan/gbrain)): a **memory layer for agents** — *"Give the agent you already use a memory you control."* Stores explicit facts with sources, supports corrections, keyword + semantic retrieval, runs locally (PGLite) or on Postgres, exposed via CLI or MCP. gstack integrates it optionally (`/setup-gbrain`, `/sync-gbrain`) and falls back to grep-based search without it.


**2026-10-16: launched as a product, "GBrain Tools", on Product Hunt** ([[raw-batch-roundup-2026-10-17]], @gbrainio), billed as *"Garry Tan's AI memory, tools, & skills for any harness."* The pitch adds two things to the memory layer above: **saving time "each time you try a new AI"** (one memory carried across harnesses) and **"visibility into how AI is using your apps."** The second is an audit claim the memory-layer description did not make. The replies are launch-day engagement, not usage reports. *(Launch post; the linked video and thread were not captured.)*

## Traction Signals

- **GitHub, 2026-10-21:** ~137.2k stars on `garrytan/gstack` (`gh api`), up from the README's 135K+ on 2026-10-01.
- **2026-10-16:** the companion GBrain launched as a product on Product Hunt (see gbrain above).
- **Cited as the reference point for two October positions:** Osmani's 25-skill pack is read against it ([[addyosmani-agent-skills-repo-2026-10-03]]), and DHH's "barely any skills" setup against it ([[dhh-no-magic-sauce-harness-setup-2026-10-06]]).

- **Tan himself, daily** — the [[garrytan-capy-harness-4x-2026-09-23|Capy 4× post]] is about his own GStack/GBrain PRs.
- Star count is the main adoption proxy; third-party explainers exist (Augment Code, Epsilla, Vectorize) but the wiki holds no independent practitioner receipts yet.

## Why It Matters Here

The highest-profile instance of the [[domain-specific-harness]] / [[loop-engineering]] thesis practiced in public by a principal: the roles-and-review-gates layer, not the model, is where Tan locates the speedup. Owner backlog holds an open "spend a day evaluating gstack?" item.
