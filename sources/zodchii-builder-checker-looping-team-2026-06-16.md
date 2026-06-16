---
title: "Zodchii — 'Claude Code Agent Team That Runs in Loops' (builder + checker 2-agent looping-team architecture + 5-cycle cap + same-failure-twice canonical-escalation + cycle-cheat-prevention stop-rules) (2026-06-16)"
type: source
medium: twitter-thread
url: https://x.com/zodchiii/status/2066882971374678057
ingested: 2026-06-16
---

## Summary

**[[zodchii|Zodchii]]** publishes (2026-06-16; saved as `_raw/How to Build a Claude Code Agent Team That Runs in Loops (Exact Setup Inside).md`) **"How to Build a Claude Code Agent Team That Runs in Loops (Exact Setup Inside)"** — **5th substantive Zodchii surface in 19 days**. **STRUCTURALLY MAJOR**: extends Zodchii's [[zodchii-4-agent-claude-code-roster-2026-06-14|Jun 14 4-agent roster]] from one-shot architecture to **2-agent looping-team architecture** (builder + checker) with explicit **5-cycle cap + same-failure-twice canonical-escalation + cycle-cheat-prevention canonical-stop-rules**. **First wiki-captured concrete operationalization of [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|Samuel McDonald "Design the verifier, not the prompt" canonical-corrective]]** in Claude Code roster architecture — Zodchii's builder + checker 2-agent looping-team = McDonald's verifier-discipline-first principle at the practitioner-content register tier. **First wiki-captured "looping-team vs one-shot-team" canonical-distinction in Claude Code roster architecture**. **First wiki-captured "5-cycle cap" canonical timing-anchor**. **First wiki-captured "same-failure-twice" canonical-escalation-rule**. **First wiki-captured "cycle-cheat-prevention" canonical-stop-rule** (against checker-passes-by-deleting-test failure mode). **First wiki-captured 3-language-stack canonical-checker-tools cross-language articulation** (JS/TS + Python + Rust). **First wiki-captured "CLAUDE.md as canonical stop-rules home" canonical-discipline articulation**.

## Key Claims / Takeaways

### The 3-file looping-team architecture

| File | Role | Tools | Model | Function |
|---|---|---|---|---|
| **`.claude/agents/builder.md`** | Builder | Read, Write, Edit, Glob, Grep, Bash | sonnet | Implements task on first invocation; fixes failures the checker found on subsequent invocations |
| **`.claude/agents/checker.md`** | Checker | Read, Grep, Glob, Bash | sonnet | Runs tests + types + lint in order; reports "ALL GREEN" or "FAILED" with file:line + cause + which-check-caught-it; **never edits code** |
| **`.claude/commands/loop.md`** | Loop orchestrator | Read, Grep, Glob, Bash, Task | opus | Drives the build-check-fix cycle until ALL GREEN or stop-condition; **tracks cycle count out loud** |
| **`CLAUDE.md`** | Stop-rules | — | — | 4 canonical stop-rules (ALL GREEN + 5-cycle-cap + same-failure-twice + previously-passing-check-fails) |

### Why this is structurally MAJOR

- **5th substantive Zodchii surface in 19 days** — extends [[zodchii-4-agent-claude-code-roster-2026-06-14|Jun 14 4-agent roster]] + [[zodchii-4-agent-pipeline-2026-05-30|May 30 4-agent pipeline]] + [[zodchii-opus-4-8-setup-guide-2026-05-29|May 29 Opus 4.8 setup]] + [[zodchiii-anatomy-perfect-skill|anatomy-of-perfect-skill]]. **Zodchii now consistent canonical-pattern-articulating practitioner-content register voice across 3-week cadence**.

- **First wiki-captured concrete operationalization of [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|Samuel McDonald "Design the verifier, not the prompt" canonical-corrective]]** in Claude Code roster architecture:
  - McDonald (Jun 15): *"A loop is a generator wired to a verifier. The generator was never the bottleneck. The verifier is."* + *"Design the verifier, not the prompt."*
  - Zodchii (Jun 16): builder = generator; checker = verifier; loop = generator-wired-to-verifier; 4 stop-rules = canonical-verifier-discipline at the practitioner-tier
  - **First wiki-captured 2-voice canonical-Loop-Engineering-corrective at corrective-tier + practitioner-tier same-week paired-articulation** (Samuel McDonald + Zodchii)

- **First wiki-captured "looping-team vs one-shot-team" canonical-distinction in Claude Code roster architecture**: extends Zodchii's [[zodchii-4-agent-claude-code-roster-2026-06-14|Jun 14 one-shot 4-agent roster]] to **looping-team architecture**. *"A team that runs once is a relay race with no finish line check. The writer writes, the tester tests, the reviewer reviews, and then it all lands on you, broken parts included. A looping team closes that gap."*

- **First wiki-captured "5-cycle cap" canonical timing-anchor**: *"5 cycles used: stop. Report what still fails and what was tried."* — pairs structurally with [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|Samuel McDonald "16 concurrent + 1000 agents per run" Dynamic Workflows capacity-anchor]] at the **canonical-timing-anchor multi-tier articulation** layer.

- **First wiki-captured "same-failure-twice" canonical-escalation-rule**: *"Same failure twice in a row: stop. The builder is guessing, not fixing. Escalate to me."* — **first wiki-captured operator-side canonical "guessing-not-fixing" failure-mode articulation**. Pairs structurally with [[eric-siu-single-brain-5-layer-company-brain-2026-05-29|Eric Siu "human-correction → rule" canonical feedback-loop architectural pattern]].

- **First wiki-captured "cycle-cheat-prevention" canonical-stop-rule**: *"If the checker can pass by deleting a test, it will eventually. The stop rules forbid weakening checks for a reason."* — **first wiki-captured operator-side canonical-checker-integrity-discipline articulation** addressing the **cycle-cheat-by-deleting-tests failure-mode**. Pairs structurally with [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald "A loop that goes green is not a loop that is correct"]] + [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald "agent grading its own homework grades generously"]] canonical-articulations.

- **First wiki-captured 3-language-stack canonical-checker-tools cross-language articulation**: JS/TS (`npm test` + `npx tsc --noEmit` + `npm run lint`) + Python (`pytest -q` + `pyright` + `ruff check`) + Rust (`cargo test --quiet` + `cargo check` + `cargo clippy`). **First wiki-captured operator-side canonical-checker-tool 3-stack canonical-tooling articulation**.

- **First wiki-captured "previously-passing-check-fails" canonical-stop-rule**: *"A fix makes a previously passing check fail: stop. Something is being broken to fix something else."* — **first wiki-captured operator-side canonical regression-detection-as-stop-condition articulation**.

- **First wiki-captured "never weaken a test to make it pass" canonical-discipline-rule** at builder-tier: *"Never weaken a test to make it pass. Fix the code."*

### The "what you actually see when it runs" canonical-concrete-illustration

Zodchii illustrates with a concrete `/loop add rate limiting to the login route, 5 attempts per IP per minute` execution:

```
Cycle 1
  builder  → wrote rateLimiter.ts, edited login.ts
  checker  → FAILED
             login.test.ts:42 - expected 429, got 200 - tests
             rateLimiter.ts:18 - 'window' possibly undefined - types
Cycle 2
  builder  → fixed the 429 response, added null guard on window
  checker  → FAILED
             login.test.ts:51 - counter not reset after window - tests
Cycle 3
  builder  → reset counter on window expiry
  checker  → ALL GREEN (14/14 tests, types clean, lint clean)
```

**First wiki-captured "concrete looping-team 3-cycle convergence" canonical-illustration**. **First wiki-captured "you never relayed a single failure" canonical-pattern-success-anchor**.

### Common-mistakes canonical articulation

Zodchii articulates **4 specific anti-patterns**:

1. **No cycle cap** — *"Without '5 cycles max' a stuck team loops until your tokens run out. The cap turns an infinite loop into a clear report."*
2. **Letting the builder check itself** — *"Same agent writing and judging means it grades its own work with the same blind spots that made the bug. Keep builder and checker separate."* — extends [[zodchii-4-agent-claude-code-roster-2026-06-14|Jun 14 "blind-reviewer" canonical-discipline]] to looping-team context
3. **No "same failure twice" rule** — *"Two identical failures in a row means guessing, not fixing. That's the moment to stop and look, not to spend cycle 4."*
4. **Checks the loop can cheat** — *"If the checker can pass by deleting a test, it will eventually. The stop rules forbid weakening checks for a reason."*

**First wiki-captured 4-anti-pattern canonical-discipline articulation for looping-team Claude Code roster architecture**.

### The 10-minute setup canonical-timing-anchor

Same as [[zodchii-4-agent-claude-code-roster-2026-06-14|Jun 14 4-agent roster]] — Zodchii canonical-timing-anchor for Claude Code setup. **First wiki-captured "10-minute Claude Code looping-team setup" canonical timing-anchor** + **2nd substantive surface of "10-minute Claude Code setup" canonical-timing-discipline pattern**.

### Closing canonical articulation

Zodchii's closing: *"You stop relaying failures back and forth. The team runs the loop, you read the result. It didn't get smarter, it just stopped quitting before the job was done."* — **first wiki-captured "it didn't get smarter, it just stopped quitting" canonical-Loop-Engineering-effect framing**. Pairs structurally with [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald "autonomy is not the reason; the evaluation gate is" canonical attribution-correction]] at the **looping-team-as-evaluation-gate-operationalization canonical-convergence** layer.

### Cross-cutting framings

- **5th substantive Zodchii surface in 19 days** — confirms canonical-pattern-articulating practitioner-content register voice
- **First wiki-captured concrete operationalization of Samuel McDonald "Design the verifier, not the prompt" canonical-corrective**
- **First wiki-captured 2-voice canonical-Loop-Engineering-corrective at corrective-tier + practitioner-tier same-week paired-articulation** (McDonald + Zodchii)
- **First wiki-captured "looping-team vs one-shot-team" canonical-distinction in Claude Code roster architecture**
- **First wiki-captured "5-cycle cap" canonical timing-anchor**
- **First wiki-captured "same-failure-twice" canonical-escalation-rule**
- **First wiki-captured operator-side canonical "guessing-not-fixing" failure-mode articulation**
- **First wiki-captured "cycle-cheat-prevention" canonical-stop-rule** (against checker-passes-by-deleting-test failure mode)
- **First wiki-captured operator-side canonical-checker-integrity-discipline articulation**
- **First wiki-captured 3-language-stack canonical-checker-tools cross-language articulation** (JS/TS + Python + Rust)
- **First wiki-captured "previously-passing-check-fails" canonical-stop-rule**
- **First wiki-captured operator-side canonical regression-detection-as-stop-condition articulation**
- **First wiki-captured "never weaken a test to make it pass" canonical-discipline-rule at builder-tier**
- **First wiki-captured "concrete looping-team 3-cycle convergence" canonical-illustration**
- **First wiki-captured "you never relayed a single failure" canonical-pattern-success-anchor**
- **First wiki-captured 4-anti-pattern canonical-discipline articulation for looping-team Claude Code roster architecture**
- **First wiki-captured "10-minute Claude Code looping-team setup" canonical timing-anchor** + **2nd substantive surface of "10-minute Claude Code setup" canonical-timing-discipline pattern**
- **First wiki-captured "it didn't get smarter, it just stopped quitting" canonical-Loop-Engineering-effect framing**
- **First wiki-captured "CLAUDE.md as canonical stop-rules home" canonical-discipline articulation**

## Pages Updated

- [[zodchii]] — 5th substantive surface added (Jun 16 builder + checker looping-team); 4 canonical-discipline-rules + 5-cycle cap + same-failure-twice + cycle-cheat-prevention + previously-passing-check-fails + never-weaken-a-test + 3-language-stack canonical-checker-tools
- [[concepts/loop-engineering]] — Zodchii operationalizes [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald verifier-discipline-first canonical-corrective]] at practitioner-content register tier
- [[claude-code]] — 2-agent looping-team architecture pattern added
- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15]] — paired same-week canonical-corrective + canonical-operationalization
- [[zodchii-4-agent-claude-code-roster-2026-06-14]] — extends one-shot 4-agent roster to looping-team architecture
- [[zodchii-4-agent-pipeline-2026-05-30]] — extends sequential-pipeline to looping-team architecture
- [[concepts/agentic-engineering]] — 4-anti-pattern canonical-discipline articulation for looping-team architecture
- [[eric-siu-single-brain-5-layer-company-brain-2026-05-29]] — paired "human-correction → rule" canonical feedback-loop architectural pattern

## Adjacent sources

- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15]] — Samuel McDonald verifier-discipline-first canonical-corrective (paired same-week)
- [[zodchii-4-agent-claude-code-roster-2026-06-14]] — prior Jun 14 4-agent roster (writer + reviewer + tester + coach)
- [[zodchii-4-agent-pipeline-2026-05-30]] — prior May 30 4-agent pipeline
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — prior May 29 Opus 4.8 setup
- [[zodchiii-anatomy-perfect-skill]] — prior anatomy-of-perfect-skill
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny canonical recipe
- [[karpathy-loopcraft-stacking-loops-2026-06-12]] — Karpathy loopcraft canonical-naming
- [[zaharia-omnigent-multi-agent-meta-harness-2026-06-13]] — Zaharia meta-harness governance-tier
- [[eric-siu-single-brain-5-layer-company-brain-2026-05-29]] — Single Brain feedback-loops layer

## Verification-pending

- Specific Zodchii name + canonical-handle identity
- Specific user-reported results from /loop workflow adoption
- Specific Zodchii reception of Samuel McDonald verifier-bottleneck thesis (would expect explicit cross-reference)
- Specific comparison to native Claude Code looping primitives (subagents + `Task` tool)
- Specific 5-cycle cap empirical-tuning rationale (why 5 not 3 or 10?)
- Specific cross-language checker-tools coverage gaps (Go? Java? Ruby? C#?)
- Specific Zodchii vs other practitioner-content-register voices (0x-rody + Nate Herk + Ruben Hassid + matt-pocock) comparative-discipline analysis
