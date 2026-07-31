---
name: QM
type: tool
category: platform
status: emerging
last_updated: 2026-07-31
---

## What It Is

**QM** is an **open-source (MIT) "multiplayer agent harness for work"** that **[[y-combinator|Y Combinator]]** built internally and open-sourced on 2026-07-31 (`github.com/yc-software/qm`). YC describes it as *"easy to customize, like Hermes or [[openclaw|OpenClaw]], but useful for a whole company"* — they run it across **accounting, legal, events, and engineering** (including building QM itself). Cloud-first, with **Slack and web UI natively**. It lands squarely in the **multiplayer / org-scale agent-harness** category the wiki has been tracking (Jack Dorsey's [[buzz|Buzz]], PromptQL, Shopify's [[river|River]]) — the "harness escaping the repo" pattern where the unit of tooling is the *organization*, not the repository.

## Traction Signals

- **2026-07-31 open-source release** by Y Combinator (MIT, `yc-software/qm`). Institutional pedigree (YC dogfooding it company-wide) is the strongest signal; explicitly *"an experiment… early and has bugs."* No external-adoption metrics yet.
- **Self-hosting pitch is itself an agentic-engineering artifact**: YC suggests you deploy it by *telling your coding agent of choice to* set it up — the tool assumes you have a coding agent.
- Positioned alongside **[[openclaw|OpenClaw]] / Hermes** as a customizable-harness peer, and against [[buzz|Buzz]] as the company-scale multiplayer variant.

## Key Concepts / Features

- **Triggers** — crons + webhooks (agents run on infrastructure time, not attention time — the [[loop-engineering|scheduling]] primitive).
- **Memory + shared files** — persistent state across runs.
- **Connectors for a "company brain"** — pulls org context in; the [[company-brain]] substrate made operational.
- **Agent browser support** — agents can drive a browser.
- **Shareable web-app artifacts** — agents produce shareable apps (the [[karpathy-html-output-taxonomy-2026-05-08|render-the-output]] pattern).
- **Multi-player projects** — humans + agents collaborating in shared projects (the "multiplayer" in the name).

## Compared To

- **[[buzz|Buzz]]** (Block/Dorsey) — the closest peer: both are open-source multiplayer agent harnesses aimed at the whole company. Buzz is Nostr-based with cryptographic identity (governance by signed attribution); QM is cloud-first with Slack/web UI and "company brain" connectors. Two open-source takes on [[dailybrief-roundup-2026-07-27|"the first proper multiplayer agent harness"]] layer.
- **[[openclaw|OpenClaw]] / Hermes** — the single-user/customizable harnesses QM is modeled on but scales to a company.
- **PromptQL** (Hasura), **[[river|River]]** (Shopify) — adjacent "agent-collaboration layer" contenders.

## Resources
- `github.com/yc-software/qm` — MIT, cloud-first
- [[buzz]] — the closest peer in the multiplayer-agent-harness category
- [[raw-batch-roundup-2026-07-31]] — surfacing source (YC announcement)
