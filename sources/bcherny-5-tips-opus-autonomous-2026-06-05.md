---
title: "Boris Cherny (@bcherny) — 5 tips for running Opus autonomously for hours/days (X, 2026-06-05)"
type: source
medium: twitter-thread
url: https://x.com/bcherny/status/2063792263067754658
ingested: 2026-06-08
---

## Summary

[[boris-cherny|Boris Cherny]] publishes (2026-06-05 X) a **5-tip canonical practitioner-content recipe for running Claude Opus autonomously for hours-to-days**. First wiki-captured Cherny-direct-voice operator recipe for long-horizon unattended Opus operation. Posted in response to *"a number of benchmarks showing Opus is the best model for long-running work"* (referencing [[mvanhorn-wtf-is-a-loop-2026-06-07|Rishi Desai's SWE-Marathon benchmark]] for ~1B-token coherent autonomous coding). Same-thread reply to Justin Morin contains **first wiki-captured Cherny counter-claim on context rot**: *"Context rot isn't a thing with 4.8 imo"* — direct contradiction of [[linas-beliunas-claude-goal-guide-2026-05-14|Linas's "context rot silently degrades long runs"]] framing at the Anthropic-internal voice layer. Same-thread reply by Ray Amjad reports a **19-hour `/goal` run verifying ~300 user flows** — first wiki-captured concrete operator-side duration receipt for `/goal` at this magnitude.

## Key Claims / Takeaways

### The 5-tip recipe (Cherny direct voice)

> *"Seeing a number of benchmarks showing Opus is the best model for long-running work. Five tips for running Opus autonomously for hours/days:"*

1. **Auto mode for permissions** — *"so Claude doesn't ask for approval"*
2. **Dynamic workflows** — *"to have Claude orchestrate hundreds/thousands of agents to get a task done"* — direct cross-reference to [[anthropic-dynamic-workflows-official-docs-2026-06|Anthropic Dynamic Workflows]]
3. **`/goal` or `/loop`** — *"to nudge Claude to keep going until it's done"*
4. **Claude Code in the cloud** — *"so you can close your laptop (easiest way is the desktop or mobile app)"*
5. **Self-verify end to end** — *"Claude in Chrome browser extension for web, iOS/Android sim MCP for mobile, a way to start the full web server or service for backend work"*

**Pattern**: first wiki-captured **5-component canonical recipe for autonomous-Opus operation directly from the Claude Code creator's voice**. Pairs structurally with [[linas-beliunas-claude-goal-guide-2026-05-14|Linas's operator-side `/goal` guide]] and [[trq-dynamic-workflows-harness-2026-06-02|Thariq's harness post]] — Cherny supplies the **5-element checklist** at the Anthropic-internal-creator voice layer above both.

### Context rot counter-claim

Reply to Justin Morin (*"My concern is how do you deal with compaction and / or the session getting too long and context rot at 600-700k+ sets in.."*):

> **Boris Cherny**: *"Context rot isn't a thing with 4.8 imo, but curious if that's been your experience also"*

**First wiki-captured Cherny counter-claim on context rot at the Anthropic-internal voice layer**. Direct contradiction of [[linas-beliunas-claude-goal-guide-2026-05-14|Linas's "context rot silently degrades long runs well before the window fills"]] framing — *imo* hedge but unambiguous claim that **context rot ceased to be a load-bearing failure mode at the [[claude-opus-4-8]] generation**. Cross-reference for [[claude-md-pattern|context-rot framing]] track: pre-4.8 practitioner-canonical concern; Cherny disputes for 4.8.

> [!contradiction] Conflict with [[linas-beliunas-claude-goal-guide-2026-05-14]]
> Linas (2026-05-14) frames *"context rot silently degrades long runs well before the window fills"* as a load-bearing failure mode for `/goal` runs. Cherny (2026-06-08 reply) counters: *"Context rot isn't a thing with 4.8 imo."* Resolution-pending — Cherny's view from the Claude Code creator's seat vs Linas's framing as practitioner synthesis. Pattern-watch for additional Anthropic-internal voices weighing in.

### Ray Amjad 19-hour /goal receipt

Reply by Ray Amjad (@theramjad):

> *"It's pretty good! I just had a goal running for 19 hours which verified almost 300 user flows with Chrome."*

Cherny replies *"Nice!"* — implicit endorsement. **First wiki-captured concrete operator-side duration receipt for `/goal` at the 19-hour / ~300-user-flows scale**. Pairs structurally with [[anthropic-dynamic-workflows-primary-2026-05-28|Bun Zig→Rust 11-day rewrite]] (canonical Anthropic-side long-horizon receipt) as **operator-side 19-hour verification-loop receipt** — distinct workload-class (continuous self-verification, not parallel code-migration).

### "What kinds of tasks run for days?"

Reply to Greg_TheBuilder (*"What kind of task needs thousands of agents? Genuinely curious. What kinds of tasks runs for days?"*):

> **Boris Cherny**: *"A few things I've used very long running sessions for:*
> - *Building complex features*
> - *Migrating code from language X to Y*
> - *Migrating code from framework X to Y*
> - *Repeatedly profiling and optimizing code to hit a specific memory or CPU target*
> - *Finding and fixing flaky tests in..."* [truncated in source]

**First wiki-captured Cherny-direct-voice taxonomy of long-horizon Claude Code workload-classes** — 5 archetypes: feature-building / language-migration / framework-migration / iterative-optimization / flaky-test-resolution. Matches the workload-class profile of [[anthropic-dynamic-workflows-primary-2026-05-28|the Bun Zig→Rust rewrite]] (language migration) and [[trq-dynamic-workflows-harness-2026-06-02|Thariq's parallel-debugging pattern]] (flaky tests).

### Usage-limit pushback + `/usage` slash command

Reply to Adrien Valcke (*"get out of usage limit in 2.5 hours even on the $200 Max plan"*):

> **Boris Cherny**: *"Run `/usage` to see a breakdown of the specific skills, mcps, and plugins that are using your tokens"*

**First wiki-captured `/usage` slash command** — token-breakdown primitive surfaced by skills / MCPs / plugins. Operator-side diagnostic for the *"why am I burning my $200/mo Max plan in 2.5h"* failure mode. Pairs with [[claude-code|Claude Code]] taxonomy: complements `/cost` (already-captured aggregate token/cost primitive) with **per-skill / per-MCP / per-plugin breakdown** — first wiki-captured breakdown-by-tool-type cost-visibility primitive.

### SWE-Marathon benchmark context

Quoted post by Rishi Desai (@rishi_desai2) — 2026-06-05:

> *"Can coding agents stay coherent over a 1 billion token budget? Can they build Slack from scratch? Rewrite a JAX codebase in PyTorch? Build a C compiler in Rust? Enter SWE-Marathon: a benchmark for autonomous long-horizon software work."*

**First wiki-captured SWE-Marathon benchmark surface** — 1-billion-token-budget coherent-autonomous-coding benchmark for tasks at the *build-Slack-from-scratch* / *JAX→PyTorch* / *C-compiler-in-Rust* scale. Cherny references it as the benchmark family showing *"Opus is the best model for long-running work."* Verification-pending: full SWE-Marathon spec, scoring methodology, current leaderboard.

## Cross-cutting framings

- **First wiki-captured Cherny-direct-voice 5-tip canonical recipe** for autonomous-Opus operation (auto + dynamic workflows + /goal-or-/loop + cloud + self-verify)
- **First wiki-captured Cherny context-rot counter-claim** at the Anthropic-internal voice layer (counter to Linas)
- **First wiki-captured 19-hour /goal receipt** (Ray Amjad ~300 user flows verified with Chrome)
- **First wiki-captured Cherny-direct-voice 5-workload-class taxonomy** for long-horizon Claude Code sessions
- **First wiki-captured `/usage` slash command** — per-skill / per-MCP / per-plugin token breakdown
- **First wiki-captured SWE-Marathon benchmark surface** — 1-billion-token coherent-autonomous-coding benchmark family
- **Pairs with [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn synthesis article]]** as the **same-week Cherny-voice receipt** behind the *"the loop is the expensive part"* framing — Cherny's 5 tips are the operator-side checklist; Van Horn's article is the practitioner-side narrative synthesis
- **Pairs with [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger Loops Engineering surface]]** — Cherny supplies the **Anthropic-internal-creator-voice 5-tip checklist** Steinberger's *"design loops that prompt your agents"* thesis implies

## Pages Updated

- [[boris-cherny]] — substantial update: 5-tip recipe + context-rot counter-claim + 19-hour /goal-via-Amjad receipt + Cherny long-horizon workload taxonomy + `/usage` primitive
- [[claude-code]] — `/usage` slash command added to taxonomy
- [[linas-beliunas-claude-goal-guide-2026-05-14]] — contradiction callout for context-rot counter-claim
- [[loop-engineering]] — new concept page links this as Cherny-voice canonical checklist

## Adjacent sources

- [[mvanhorn-wtf-is-a-loop-2026-06-07]] — same-week Van Horn synthesis article that quotes this post verbatim
- [[steipete-loops-engineering-vision-md-2026-06-07]] — Steinberger's *"design loops that prompt your agents"* thesis paired with Cherny's checklist
- [[linas-beliunas-claude-goal-guide-2026-05-14]] — Linas's `/goal` operator-synthesis (context-rot framing contradicted here)
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq's harness-for-every-task framing
- [[anthropic-dynamic-workflows-official-docs-2026-06]] — Anthropic Dynamic Workflows canonical docs
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — Bun Zig→Rust 11-day rewrite (canonical Anthropic-side long-horizon receipt)

## Verification-pending

- Full SWE-Marathon benchmark spec (scoring methodology, leaderboard, repo)
- Truncated last bullet of Cherny's workload-class taxonomy (*"flaky tests in..."*) — exact completion
- Whether `/usage` is already documented in [[anthropic-dynamic-workflows-official-docs-2026-06|Anthropic docs]] or first publicly disclosed in this reply thread
- Cherny's specific context-rot test methodology behind *"isn't a thing with 4.8 imo"*
- Ray Amjad's 19-hour /goal run venue / spec / target product
