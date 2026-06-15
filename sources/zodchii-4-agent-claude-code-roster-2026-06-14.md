---
title: "Zodchii — 4-agent Claude Code roster (writer + reviewer + tester + coach) via Knicks-team analogy + 10-minute setup canonical articulation (2026-06-14)"
type: source
medium: twitter-thread
url: https://x.com/zodchiii/status/2066084065510302029
ingested: 2026-06-15
---

## Summary

**[[zodchii|Zodchii]]** publishes (2026-06-14; saved as `_raw/How to Build a Claude Code Team Where Every Agent Knows Its Role.md`) **"How to Build a Claude Code Team Where Every Agent Knows Its Role (Exact Setup Inside)"** — **4-agent Claude Code roster pattern** via **Knicks-team analogy** (*"The Knicks just won their first title in 53 years without the most talented roster in the league! They won, because every player knew exactly one job and did it"*). **3rd Zodchii focused source surface** (extends [[zodchii-4-agent-pipeline-2026-05-30|May 30 4-agent pipeline]] + [[zodchii-opus-4-8-setup-guide-2026-05-29|May 29 Opus 4.8 setup]] + [[zodchiii-anatomy-perfect-skill|anatomy-of-perfect-skill]]) — **4th-substantive-surface entity-page threshold confirmed met**. **First wiki-captured "4-agent Claude Code roster: writer + reviewer + tester + coach" canonical-team-architecture articulation**. **First wiki-captured "spec-first-tester-not-implementation-first-tester" canonical agentic-testing discipline-rule**. **First wiki-captured "coach orchestrator as slash-command not subagent" canonical architecture pattern**. **First wiki-captured "stay-in-your-lane single-role agent" canonical sportsstram-analogy framing for role-specialization**.

## Key Claims / Takeaways

### The 4-agent roster

| Role | File | Tools | Model | Function |
|---|---|---|---|---|
| **Writer** | `.claude/agents/writer.md` | Read, Write, Edit, Glob, Grep, Bash | sonnet | Implements features; *"You do not review, you do not test. Stay in your lane."* |
| **Reviewer** | `.claude/agents/reviewer.md` | Read, Grep, Glob, Bash | sonnet | Reviews diff via `git diff`; output: Critical / Important / Nitpick with file:line; *"Attack the code, never the person."* |
| **Tester** | `.claude/agents/tester.md` | Read, Write, Edit, Bash | sonnet | Writes tests from **spec, not code**; priorities: edge cases first, error paths second, happy path last; *"Never weaken a test to make it green."* |
| **Coach** | `.claude/commands/ship.md` | Read, Grep, Glob, Bash, Task | opus | **Slash-command orchestrator** (not subagent); writes brief → dispatches writer + tester in parallel → dispatches reviewer on diff → returns one summary; *"Do not commit. Wait for my call."* |

### Why this is structurally MAJOR

- **3rd Zodchii focused source surface** (4th-substantive-surface counting `zodchiii-anatomy-perfect-skill`) — **entity-page threshold confirmed met past lint-recommendation tier**. Per [[meta/lint-report-2026-06-14|prior lint]] pattern-watch policy: zodchii has consistently surfaced canonical Claude Code patterns; entity page creation now triggered.
- **First wiki-captured "4-agent Claude Code roster: writer + reviewer + tester + coach" canonical-team-architecture articulation**: extends [[zodchii-4-agent-pipeline-2026-05-30|prior 4-agent pipeline]] (which is a sequential-pipeline pattern) to **role-specialization-team architecture** (which is a parallel-fanout + reviewer-blind-to-writer-reasoning architecture). Pairs structurally with:
  - [[concepts/loop-engineering|Loop Engineering canonical cluster]] — Zodchii at practitioner-content register tier
  - [[zaharia-omnigent-multi-agent-meta-harness-2026-06-13|Zaharia Omnigent]] = governance-tier meta-harness; Zodchii = role-specialization-tier team-architecture (operator-side direct-articulation)
  - [[bcherny-5-tips-opus-autonomous-2026-06-05|Cherny canonical recipe]] — Cherny: vendor-side canonical primitive; Zodchii: operator-side canonical recipe
- **First wiki-captured "spec-first-tester-not-implementation-first-tester" canonical agentic-testing discipline-rule**: *"You let the tester read the implementation first. Tests then mirror the code instead of the spec, and they pass even when the logic is wrong. Spec first, always."* — addresses the **mirror-the-code-not-the-spec test-failure-mode** that plagues naive AI-coding workflows. **First wiki-captured operator-side canonical-discipline-rule on AI-coding-test-architecture**.
- **First wiki-captured "coach orchestrator as slash-command not subagent" canonical architecture pattern**: the orchestrator is a `.claude/commands/ship.md` slash-command (not a subagent) — distinguishes **user-facing-task-trigger** (slash-command) from **agent-as-tool** (subagent). Pairs with [[concepts/skill-md|SKILL.md pattern]] + [[claude-agent-sdk|Claude Agent SDK]] at the **user-trigger-vs-agent-as-tool canonical-distinction** layer.
- **First wiki-captured "stay-in-your-lane single-role agent" canonical sports-team-analogy framing for role-specialization**: Knicks-analogy frames role-specialization as **load-bearing canonical-discipline rule** rather than mere optimization. *"The tighter the tools, the sharper the role."*

### The 4 common-mistakes canonical articulation

Zodchii articulates **4 specific anti-patterns** to avoid:

1. **Letting the writer review itself** — *"That's the star player grading his own game. Keep the reviewer separate and blind to the writer's reasoning."* — **first wiki-captured "blind-reviewer-discipline" canonical articulation**
2. **Letting the tester read the implementation first** — addressed above; spec-first canonical discipline-rule
3. **Giving every agent every tool** — *"The reviewer doesn't need Write. The tighter the tools, the sharper the role."* — **first wiki-captured "tool-restriction-as-role-sharpening" canonical discipline-rule**
4. **Skipping the brief** — *"Without the coach writing a shared brief, each agent interprets the task differently and they drift apart. The brief is the playbook."* — **first wiki-captured "shared-brief-as-agent-drift-prevention" canonical articulation**

**First wiki-captured 4-anti-pattern canonical-discipline articulation for multi-agent Claude Code roster architecture**.

### The 10-minute setup canonical timing

Zodchii articulates **specific setup timing**:
- **3 minutes**: create writer + reviewer + tester
- **2 minutes**: create coach
- **2 minutes**: commit to share with team
- **3 minutes**: run `/ship` on real task
- **Total**: 10 minutes

**First wiki-captured "10-minute Claude Code 4-agent roster setup" canonical timing-anchor**. Pairs structurally with [[you-dont-need-100-hours-claude-7-setups|prior 100-hours-claude practitioner-content]] at the **practitioner-content register canonical-timing-anchor** layer.

### Cross-cutting framings

- **3rd Zodchii focused source surface** + **4th-substantive-surface entity-page threshold confirmed met**
- **First wiki-captured "4-agent Claude Code roster: writer + reviewer + tester + coach" canonical-team-architecture articulation**
- **First wiki-captured "spec-first-tester-not-implementation-first-tester" canonical agentic-testing discipline-rule**
- **First wiki-captured "coach orchestrator as slash-command not subagent" canonical architecture pattern**
- **First wiki-captured "stay-in-your-lane single-role agent" canonical sports-team-analogy framing for role-specialization**
- **First wiki-captured 4-anti-pattern canonical-discipline articulation** (blind-reviewer + spec-first-tester + tool-restriction + shared-brief)
- **First wiki-captured "10-minute Claude Code 4-agent roster setup" canonical timing-anchor**
- **First wiki-captured "blind-reviewer-discipline" canonical articulation**
- **First wiki-captured "tool-restriction-as-role-sharpening" canonical discipline-rule**
- **First wiki-captured "shared-brief-as-agent-drift-prevention" canonical articulation**
- **Extends [[zodchii-4-agent-pipeline-2026-05-30|Zodchii 4-agent pipeline]] from sequential-pipeline to parallel-fanout team-architecture**

## Pages Updated

- [[zodchii]] — new entity page (4th-substantive-surface threshold confirmed met; practitioner-content register canonical Claude Code patterns voice)
- [[claude-code]] — 4-agent roster pattern added to canonical practitioner-content surfaces
- [[concepts/loop-engineering]] — Zodchii at practitioner-content register tier (operator-side canonical recipe articulation)
- [[zodchii-4-agent-pipeline-2026-05-30]] — extends from sequential-pipeline to parallel-fanout role-specialization
- [[zodchiii-anatomy-perfect-skill]] — cross-reference Zodchii canonical practitioner-content voice
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — cross-reference Zodchii canonical practitioner-content voice
- [[concepts/agentic-engineering]] — 4-anti-pattern canonical-discipline articulation added
- [[concepts/skill-md]] — coach-as-slash-command canonical-architecture-pattern noted
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — paired vendor-side canonical-primitive context

## Adjacent sources

- [[zodchii-4-agent-pipeline-2026-05-30]] — prior 4-agent pipeline pattern
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — prior Opus 4.8 setup guide
- [[zodchiii-anatomy-perfect-skill]] — prior anatomy-of-perfect-skill
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny vendor-side canonical recipe
- [[karpathy-loopcraft-stacking-loops-2026-06-12]] — Karpathy Loop Engineering canonical-naming
- [[zaharia-omnigent-multi-agent-meta-harness-2026-06-13]] — Zaharia meta-harness governance-tier
- [[dailybrief-roundup-2026-06-15]] — not surfaced in brief but adjacent practitioner-content

## Verification-pending

- Specific Zodchii name + canonical-handle (Telegram t.me/zodchixquant); specific identity
- Specific user-reported results from /ship workflow adoption
- Specific writer/reviewer/tester model-choice rationale (sonnet × 3 + opus orchestrator)
- Specific comparison to [[claude-code]] built-in subagent system + `Task` tool primitives
- Specific Zodchii-prior Claude Code patterns convergence pattern
- Specific Knicks-analogy team-sport-discipline AI-coding-discipline cross-domain mapping rationale
