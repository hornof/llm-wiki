---
title: "Raw batch roundup — 2026-10-15 (opusplan: Opus plans, Sonnet builds; shapeshifting software and its 22-year prior art)"
type: source
medium: article
ingested: 2026-10-15
local_source: "_raw/Claude Code has an opusplan mode....md; _raw/Shapeshifting Software....md"
---

## Summary

Two `_raw` drops, both about **model-tier assignment** — one as a shipped flag, one as an architectural proposal that the room dismantled.

## 1. `opusplan` — a documented tiering flag, not a prompt hack

> *"You don't need your most expensive model doing every part of a coding task. Claude Code has a built-in option for splitting the work: **`claude --model opusplan`**. In Plan Mode, Claude Code uses **Opus**. When you leave Plan Mode and move into execution, it switches to **Sonnet**. **That behavior is documented — not a prompt hack.**"*

**The stated division:**

| Tier | Job |
|---|---|
| **Opus** | *"investigate the problem, weigh tradeoffs, and design the change"* |
| **Sonnet** | *"implement the approved plan"* |
| **Haiku subagents** | *"focused supporting tasks — repository searches, test runs, documentation lookups"* |

**Honest about what the flag does and does not do**: *"the first two are handled by `opusplan`. **The Haiku workers are an additional configuration you create — not something the flag automatically sets up.**"*

**Three rules for returning to planning**, which is the part worth keeping:

> *"1. Before a new feature. 2. Before a design decision with meaningful tradeoffs. **3. When the first attempted bug fix fails.** The point is to **reconsider the approach before generating another pile of edits.**"*

The post ships a paste-ready configuration prompt that inspects existing settings, proposes three Haiku subagents in `.claude/agents/` (`search` read-only, `tests` that *"does not edit source files"*, `docs` with no file edits), and **verifies supported setting names first.**

### Judgment

**This is the third model-tiering pattern the wiki has recorded in three weeks, and it is the only one that is a vendor-documented flag rather than a practitioner configuration.** The [[raw-batch-roundup-2026-10-02|`/advisor` tree]] puts a *different model* in the reviewer seat; [[pachaar-llm-routing-can-cost-more-2026-09-06|infrastructure routing]] decides per request; **`opusplan` splits by phase.** All three are the same insight — capability is not needed uniformly — applied at three different granularities.

**And phase is the granularity that avoids the cache problem.** Pachaar's finding is that switching models mid-session destroys the prefix cache, worth **45–80% of input-token cost**. **A phase boundary is a natural session boundary** — plan ends, implementation begins, context is deliberately re-established — so `opusplan` switches at the one moment the cache was going to be invalidated anyway. **That is a better-designed switch than per-request routing**, and neither source notices.

**Rule 3 is the genuinely good one and it is the [[undefinedki-how-to-design-an-agent-harness-2026-08-15|stall-and-reflect round]] under a different name.** *"When the first attempted bug fix fails"* → go back to planning, *"before generating another pile of edits."* **Same trigger as the `/advisor` tree's middle question** (*"when the same error comes back: am I digging in the wrong place?"*) and the same instinct as the hillclimb round that makes no edit. **Three independent sources now say the same thing: a repeated failure is a signal to change frame, not to try harder.**

**The subagent tool restrictions are least-privilege applied inside a harness** — *"read-only"*, *"does not edit source files"*, *"no file edits"* — which is the [[agent-teams-opus-55-course-2026-10-07|"every tool a role does not need is a mistake it can now make"]] principle, in a config file.

*(Single practitioner post. No measurement of cost or quality effect — and the claim that is easiest to check and least examined is **whether Sonnet implementing an Opus plan is as good as Opus implementing it.** The flag's existence is verifiable; its value is not demonstrated here. Not tested by the owner.)*

## 2. Shapeshifting Software — and the room's response is better than the proposal

An architectural proposal (r/softwarearchitecture, 2026-10-10) for applications that **modify their own UI, workflows and behaviour from natural-language instruction**, with a demo at `TriptoAfsin/shape-shifter`. The author's framing:

> *"The interesting part isn't simply adding an AI chatbot to an application. I'm thinking about **an architecture where AI is built into the application from the beginning, with a controlled set of tools and capabilities it can use to modify the system**… **Conceptually, this is similar to how coding agents like Claude Code and OpenAI Codex interact with codebases** through tools, instructions, permissions, and execution workflows. The application would define **what the AI can change, what must remain protected, how modifications are tested, and when human approval is required.**"*

His own open questions are well-posed: configuration versus code, preventing the AI from *"accidentally weakening permissions, bypassing business rules, or exposing sensitive data"*, rollback when *"database schemas and interconnected workflows are involved"*, and **consistency** — *"how do we make sure similar instructions produce predictable outcomes without making the system too restrictive?"*

**The top replies are the content:**

> *"I don't think it's vastly different from some existing heavily customizable software like **Salesforce** — what you call a 'shape layer' is just the user-customizable part. In fact, **your architecture quite constrains the customizability**. For existing ideas check **'malleable software'**. There's also the whole **'generative UI'** shtick… This reminds me of those old **Smalltalk** environments where the whole system was open for modification at runtime, **but with AI as the interface instead of needing to know the language.**"* (13 points)

> *"This idea, and implementations of it, has existed for a long time already. **Twenty-two years ago** … a company called **Codeless** … customers could 'design' or 'assemble' their own software based on their requirements, without writing code… **Nowadays I see no point in such dynamic platforms. Rewriting a codebase is now much faster than 3 years ago thanks to AI, so why add that extra abstraction layer of doing it at the deployment site if you can directly manipulate the code itself.**"*

### Judgment

**The second objection is the strongest argument against runtime adaptivity the wiki holds, and it is an argument *from* AI capability rather than against it.** The case for a self-modifying application was always that changing code was slow and required a developer. **If agents make rewriting cheap, the dynamic abstraction layer loses its reason to exist** — you edit the source and deploy, which is observable, reviewable, version-controlled and testable. **The adaptive layer trades all four of those for immediacy.**

**That generalises past this proposal and is worth holding against a thread this wiki tracks.** [[model-rendered-ui]] records the model generating interfaces; **the distinction this surfaces is *generate-then-commit* versus *generate-at-runtime*, and the first is strictly more auditable.** It is the same argument as [[raw-batch-roundup-2026-10-14|architectural drift]] from the other end: a change you can diff is governable, and a change that happens in the running system is not.

**The author's instinct to copy the coding-agent model is right, and it is also the weakness.** Claude Code's safety comes from **the repository** — git history, tests, review, revert. *"Conceptually similar to how coding agents interact with codebases"* is true of the *tool* structure and false of the *substrate*: **there is no `git revert` for a production database schema.** His own third question admits this and nothing in the proposal answers it.

**Recorded because the question is good and the answer is "the prior art says no."** *"Malleable software"*, generative UI and Smalltalk's runtime-modifiable image are named by the room as existing lineages — **and the wiki holds none of them.** Those are the fetch items, not the demo.

*(Early-stage experiment by the author's own description; demo not run. The 22-year prior-art reply is one practitioner's recollection of a defunct company. 13 and 7 points — a small thread.)*

## Pages Updated

- [[claude-code]]
- [[loop-engineering]]
- [[model-rendered-ui]]
