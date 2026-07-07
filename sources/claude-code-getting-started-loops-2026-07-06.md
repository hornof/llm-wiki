---
title: "Getting started with loops (Claude Code team)"
type: source
medium: article
url: https://x.com/ClaudeDevs/status/2074208949205881033
ingested: 2026-07-07
---

## Summary

The first **official Claude Code team taxonomy of loops**, written by [[delba-oliveira|Delba Oliveira]] and published on the Claude Blog / `@ClaudeDevs` on 2026-07-06, boosted the same day by [[thariq-shihipar|Thariq]] (322K views on the repost). It answers the "what actually *is* a loop" question that the practitioner discourse ([[loop-engineering]]) had left ambiguous, giving Anthropic's own definition and a 4-type classification tied to concrete Claude Code primitives. This is the vendor-canonical articulation the [[loop-engineering]] concept had been assembling from third-party voices (Steinberger, Cherny, Van Horn, McDonald, Sydney Runkle).

## Key Claims / Takeaways

- **Official Anthropic definition**: *"loops as agents repeating cycles of work until a stop condition is met."* Loops are categorized by how they are triggered, how they are stopped, which Claude Code primitive is used, and what task type fits.
- **Four loop types** (each with a "you hand off X" framing):

  | Loop | You hand off | Use it when | Reach for |
  |---|---|---|---|
  | **Turn-based** | The check | You're exploring or deciding | Custom verification skills (`SKILL.md`) |
  | **Goal-based** | The stop condition | You know what "done" looks like | `/goal` |
  | **Time-based** | The trigger | Work happens outside your project on a schedule | `/loop`, `/schedule` |
  | **Proactive** | The prompt | Work is recurring and well-defined | Dynamic workflows + all of the above |

- **Turn-based (agentic loop)**: every prompt starts a manual loop — Claude gathers context, acts, checks, repeats, responds; the human directs each turn. Improve the verification step by encoding manual QA as a `SKILL.md` so Claude self-verifies end-to-end (the article gives a `verify-frontend-change` skill example: start dev server, interact, check console for zero new errors, run a Chrome DevTools MCP performance trace).
- **Goal-based (`/goal`)**: an evaluator model checks your success condition each time Claude tries to stop, sending it back until the goal is met or a turn cap is reached. Deterministic criteria (tests passed, score threshold) work best. Example: `/goal get the homepage Lighthouse score to 90 or above, stop after 5 tries.`
- **Time-based (`/loop`, `/schedule`)**: `/loop` re-runs a prompt on an interval on your machine (stops if you turn it off); `/schedule` moves the loop to the cloud as a routine. Example: `/loop 5m check my PR, address review comments, and fix failing CI`.
- **Proactive loops**: event/schedule-triggered with no human in real time; compose `/schedule` + `/goal` + skills + dynamic workflows + **auto mode**. Best for recurring streams of well-defined work (bug triage, migrations, dependency upgrades). Manage cost by routing routines to smaller/faster models and reserving the most capable model for judgment calls.
- **Maintaining code quality**: keep the codebase clean (Claude follows existing patterns); give Claude a way to verify its own work via skills; make framework/library docs reachable; **use a second agent with fresh context for code review** (`/code-review`) since a reviewer isn't biased by the main agent's reasoning. When a result misses the standard, encode the fix into the system so all future iterations improve — not just the one issue.
- **Managing token usage**: choose the right primitive and model; define clear success/stop criteria; **pilot before a large run** (dynamic workflows can spawn hundreds of agents); use scripts for deterministic work (cheaper than re-reasoning); match interval to how often the watched thing changes; review with `/usage` (breaks down usage by skills, subagents, MCPs), `/goal` (turns + tokens so far), and `/workflows` (per-agent token usage, stop any agent).
- **Getting started**: look at the work you already do, find one task where you're the bottleneck, and ask which piece you can hand off — the check, the stop condition, or the trigger.

## Community signal (from Thariq's boost thread)

- Practitioner skepticism co-exists with the vendor framing: `@CallofdutyFan32` — *"loops are really bad I burned one of my fable max 20x limits on a loop and it did not do well on its own vs me attending it… a 500% improvement"* when babysat. Consistent with [[loop-engineering]]'s "closed loops beat open loops" and verifier-discipline threads.
- Access-gating friction: multiple users note `/loop`, `/goal`, and `/skills` aren't yet available in the Claude app (Claude Code / CLI only).
- Timing overlap with the Fable-5 pricing cliff (Jul 7 pay-per-use transition) colored the replies — several "just tell me when Fable is back on subscription" jokes.

## Pages Updated

- [[loop-engineering]] — added the official Anthropic 4-type taxonomy section
- [[delba-oliveira]] — new person page (author)
- [[thariq-shihipar]] — 4th surface (boost of the canonical loops post)
