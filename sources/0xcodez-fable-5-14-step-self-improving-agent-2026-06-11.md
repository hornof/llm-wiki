---
title: "0xCodez — Build self-improving agent system with Fable 5 in 14 steps (loops, dynamic workflows, routines, 2026-06-11)"
type: source
medium: article
url: https://x.com/0xCodez/status/2065089060104720776
ingested: 2026-06-12
---

## Summary

**0xCodez (@0xCodez)** publishes (2026-06-11) **Build self-improving agent system with Fable 5 in 14 steps** — comprehensive practitioner-content guide. **First wiki-captured 0xCodez surface**. **First wiki-captured "self-improving is not self-learning" canonical distinction**. **First wiki-captured 4-layer compound stack** (Primitives + Orchestration + Memory + Self-improvement). **First wiki-captured 5-stage memory progression** (Fail + Investigate + Verify + Distill + Consult) sourced from Anthropic Continual Learning Bench 1.0. **First wiki-captured Anthropic-canonical model-routing-by-task-complexity matrix** (Fable 5 orchestrator + Opus 4.8 hard-bounded + Sonnet 4.6 workers + Haiku 4.5 graders). Substantive references to Anthropic internal experiments: **Parameter Golf** + **Continual Learning Bench 1.0** + Anthropic-engineering-blog Prithvi Rajasekaran self-critique work. Pairs structurally with [[anthropic-fable-5-prompting-playbook-2026-06-11|Anthropic-canonical Fable 5 prompting playbook]] + [[loop-engineering|Loop Engineering]] + [[alokbishoyi-evo-self-evolving-autoresearch-workflows-2026-06-09|Bishoyi evo 0.5]] at the **production-grade self-improving-system canonical practitioner-content register** layer. **Highly substantive — 14 steps + 3 tiers + Fable 5 pricing + Mythos safety boundary**.

## Key Claims / Takeaways

### Pricing + plan availability (first wiki-captured specifics)

> *"$10 per million input tokens, $50 per million output tokens, with the existing 90% input token discount for prompt caching."*

**First wiki-captured Fable 5 specific pricing**: $10/M input + $50/M output + 90% prompt-cache discount. *"This is not a subscription model. Heavy use earns its own bill."* Available on: Claude API + AWS + Amazon Bedrock + Vertex AI + Microsoft Foundry + consumption-based Enterprise plan.

### Self-improving ≠ self-learning canonical distinction

> *"Self-learning — the agent updates its own weights based on what it learns. Fable 5 does not do this. No publicly available model does this in production."*
>
> *"Self-improving — the system around the agent compounds. Each session writes lessons to memory. Skills sharpen as edge cases get added. State files accumulate verified facts. Eval loops refine prompts and rubrics. The model stays the same; the environment it runs in gets sharper."*

**First wiki-captured "self-improving is a property of the system you build" canonical framing**. Pairs structurally with [[concepts/recursive-self-improvement|RSI concept]] at the **RSI-vs-system-improvement architectural-distinction** layer + [[shane-legg-four-pathways-agi-superintelligence-2026-06-12|same-day Legg 4-pathway framework]] at the **pathway-2-RSI is long-term-direction-not-current-capability** layer.

### The 4-layer compound stack

**First wiki-captured 4-layer compound-stack architecture**:

| Layer | Components | Compound function |
|---|---|---|
| **Layer 1: Primitives** | Fable 5 + sub-agents + worktrees + tools | Raw capability |
| **Layer 2: Orchestration** | `/goal` + Outcomes + Dynamic Workflows + Routines | Self-correcting loops |
| **Layer 3: Memory** | STATE.md + Skills + Knowledge Bases + lessons | Resume vs restart |
| **Layer 4: Self-improvement** | Vision self-checks + eval loops + rule distillation | Grade-distill-write-back loop closure |

**Pattern**: *"every output from layer 1 flows up through layer 4, where it gets graded, distilled, and written back to layer 3. Tomorrow's run at layer 1 inherits the sharpened memory and refined Skills from yesterday."* **First wiki-captured "4-layer compound stack inheritance" canonical framing**.

### Cost-capability matrix — model-routing-by-task-complexity

**First wiki-captured Anthropic-canonical model-routing-by-task-complexity matrix** (per 0xCodez attribution to Anthropic-internal practice):

| Model | Role | Use-case |
|---|---|---|
| **Fable 5** | **Orchestrator** | Days-long planning + delegating + checking-with-vision + rule-distilling |
| **Opus 4.8** | Hard-but-bounded subtasks + classifier-block fallback | Architecture decisions + complex debugging + deep code reviews + cyber/bio/chem/distillation fallback |
| **Sonnet 4.6** | High-volume worker | Lint passes + simple refactors + test scaffolding + doc updates |
| **Haiku 4.5** | Grader sub-agents + cheap classifiers | Independent verifier (separate context window, low cost) |

**Cost pattern**: *"orchestrator on Fable 5, workers on Sonnet 4.6, graders on Haiku 4.5, fallback to Opus 4.8 on classifier blocks. Same pattern Anthropic engineers use internally."* **First wiki-captured Anthropic-engineering-internal model-routing-pattern attribution**.

### Verifier sub-agent beats self-critique (Anthropic-engineering quote)

> *"We've found that a verifier sub-agent tends to outperform self-critique with Fable 5"* — Anthropic Claude Code team

> *"A model evaluating its own output sees its own reasoning trail and prefers conclusions consistent with what it already wrote. A separate model evaluating the same output sees only the artifact and the rubric. The verifier has no skin in the maker's game."*

**First wiki-captured Anthropic-canonical "verifier sub-agent outperforms self-critique" attribution**. Pairs structurally with [[trq-dynamic-workflows-harness-2026-06-02|Thariq's 3-failure-mode framework]] ("self-preferential bias") at the **Anthropic-canonical-self-preferential-bias-solution** layer + [[akshay-pachaar-opik-self-repairing-harness-2026-06-08|Akshay/Opik Ollie verifier-agent]] at the **verifier-as-load-bearing-primitive** layer.

### Parameter Golf experiment results — Fable 5 vs Opus 4.7

**First wiki-captured Anthropic-canonical Parameter Golf experiment results articulation**:

- **Fable 5** with independent verifier: explored larger architectural changes; pushed through quantization regression to land biggest win
- **Opus 4.7**: small first-experiment win; nearly everything that followed used same template (adjust scalar + measure + keep-if-positive); *"the shape is safer, not better"*
- **Outcome**: *"Fable 5 with an independent verifier explored larger hypothesis spaces and recovers from negative intermediate results"*

**Pattern**: *"Same model in both halves of every comparison. The system around it is what changed."*

### 5-stage memory progression (Continual Learning Bench 1.0)

**First wiki-captured Anthropic Continual Learning Bench 1.0 5-stage memory progression**:

1. **Fail** — document failure with detail
2. **Investigate** — figure out why
3. **Verify** — diagnosis → checked fact
4. **Distill** — verification → general rule beyond specific case
5. **Consult** — read rule on next task instead of re-deriving

**Per-model exit-stage measurement** (SQL exploration task):

| Model | Exit stage | Verification coverage |
|---|---|---|
| **Sonnet 4.6** | Stage 1 (Fail-only) | "rarely consults prior notes" |
| **Opus 4.7** | Stage 3 (Verify) | **7-33%** (median ~17%) |
| **Fable 5** | Stage 5 (Consult) | **73%** (22 of 30) |

**First wiki-captured 73%-Fable-5-vs-17%-Opus-4.7 verification-coverage canonical measurement**.

### STATE.md canonical template (5-section state-file architecture)

**First wiki-captured 5-section STATE.md canonical template** (matching 5-stage memory progression):

| Section | Memory-stage | Function |
|---|---|---|
| **Verified facts** | Stage 3 | Stop guessing about these |
| **General rules** | Stage 4 | Consult before re-deriving |
| **Open failures** | Stages 1→2 | Investigate next session |
| **Lessons learned** | Stage 4 | Distillations |
| **Last session** | Stage 5 | Resume pointer (don't restart) |

**2 operational rules**:
1. **Write before walking away** — every session ends by updating STATE.md
2. **Read at session start** — every new session begins by reading STATE.md + most relevant Skills

**Pattern**: *"STATE.md is project-scoped and dies with the project. Skills live in ~/.claude/skills/ and travel with you."* Pairs structurally with [[whrrari-obsidian-claude-30-point-second-brain-2026-06-06|rari's "Separate Vaults for Separate Contexts"]] canonical articulation at the **project-scoped-vs-global-scoped memory architecture** layer.

### Vision-verify pattern

**First wiki-captured vision-verify canonical pattern**: maker writes UI code + renders screenshot → verifier reads screenshot + compares against goal description + design tokens + previous screenshot → match/mismatch verdict → loop continues or closes.

*"Fable 5 looked at training charts (visual artifact) and decided whether the curve matched the criterion. No human in the loop reading the chart. The verifier read the chart."* — Parameter Golf experiment

### Routines — laptop-off cloud orchestration (April 14, 2026 launch)

**First wiki-captured Anthropic Routines April-14-2026 launch date confirmation**. **First wiki-captured 3-Routine-trigger-type canonical taxonomy**:

1. **Schedule triggers** — morning briefing pattern (daily 7am: re-run yesterday's eval suite + distill new failure modes into Skills + write digest to Slack)
2. **API triggers** — fire on event (CI fails → investigate; Sentry alert → triage)
3. **GitHub event triggers** — learn from real work (PR open → evaluate against latest Skills; merge → write new patterns back to Skill)

**Routine code-pattern example** (Anthropic-canonical attribution):
```
/schedule daily at 7am, use Fable 5 in CMA
  Goal: Re-run yesterday's eval suite against the latest skills.
  Any test that newly passes → distill the pattern into the skill.
  Any test that newly fails → investigate, document in STATE.md.
  Post the digest to #engineering. /goal don't stop until digest is
  posted and STATE.md is updated.
```

### The Mythos safety boundary — 319-page system card

**First wiki-captured Fable 5 319-page system card length attribution**. *"The launch generated controversy in mid-June 2026 because some downgrade behaviors were discovered buried in the document. Read it before deploying to production."*

**Pairs with [[anthropic-walks-back-sabotage-policy-2026-06-11|same-week Anthropic walk-back]]** + [[claudeai-fable-5-mythos-5-official-launch-2026-06-09|3-category safeguard architecture]] at the **safety-boundary-as-known-fallback-not-failure-mode design discipline** layer.

### Cross-cutting framings

- **First wiki-captured 0xCodez substantive practitioner-content register surface**
- **First wiki-captured "self-improving is not self-learning" canonical distinction**
- **First wiki-captured 4-layer compound stack architecture** (Primitives + Orchestration + Memory + Self-improvement)
- **First wiki-captured Anthropic-canonical model-routing-by-task-complexity matrix** (Fable 5 orchestrator + Opus 4.8 fallback + Sonnet 4.6 workers + Haiku 4.5 graders)
- **First wiki-captured Anthropic-canonical "verifier sub-agent outperforms self-critique" attribution**
- **First wiki-captured Anthropic Parameter Golf experiment results articulation** + 6× improvement framing
- **First wiki-captured Anthropic Continual Learning Bench 1.0 5-stage memory progression** + 73% Fable 5 vs 17% Opus 4.7 verification-coverage measurement
- **First wiki-captured 5-section STATE.md canonical template** matching 5-stage memory progression
- **First wiki-captured vision-verify canonical pattern**
- **First wiki-captured Routines April-14-2026 launch date + 3-trigger-type canonical taxonomy** (schedule + API + GitHub event)
- **First wiki-captured Fable 5 319-page system-card length attribution**
- **First wiki-captured Fable 5 specific pricing** ($10/M input + $50/M output + 90% prompt-cache discount)
- **First wiki-captured 10-mistakes-that-keep-Fable-5-at-10%-potential canonical taxonomy**
- **Pairs with [[anthropic-fable-5-prompting-playbook-2026-06-11|same-week Anthropic-canonical Fable 5 playbook]]** at the practitioner-content register + Anthropic-canonical convergence layer
- **Pairs with [[alokbishoyi-evo-self-evolving-autoresearch-workflows-2026-06-09|Bishoyi evo 0.5]]** at the production-grade self-improving-system canonical-practitioner-content register layer

## Pages Updated

- [[claude-fable-5]] — major update: $10/$50/M pricing + 319-page system card + Continual Learning Bench 1.0 73% verification-coverage + Parameter Golf 6× improvement + Routines + STATE.md canonical template
- [[loop-engineering]] — 4-layer compound stack + 5-stage memory progression + Anthropic Parameter Golf + Continual Learning Bench attributions
- [[claude-md-pattern]] — STATE.md 5-section canonical template + Memory Instruction + verifier-sub-agent-beats-self-critique discipline added
- [[concepts/recursive-self-improvement]] — "self-improving is not self-learning" canonical distinction added
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — back-link as Cherny 5-tip recipe + 0xCodez 14-step expansion-companion
- [[0xCodez]] — entity-page candidate flagged (single substantive surface; defer)

## Adjacent sources

- [[anthropic-fable-5-prompting-playbook-2026-06-11]] — same-week Anthropic-canonical playbook
- [[claudeai-fable-5-mythos-5-official-launch-2026-06-09]] — Anthropic-canonical official launch
- [[anthropic-walks-back-sabotage-policy-2026-06-11]] — Anthropic walk-back of silent-restriction
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny 5-tip canonical recipe
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq's 3-failure-mode framework
- [[alokbishoyi-evo-self-evolving-autoresearch-workflows-2026-06-09]] — Bishoyi evo 0.5 self-evolving production case study
- [[akshay-pachaar-opik-self-repairing-harness-2026-06-08]] — Opik Ollie verifier-sub-agent pattern
- [[cherny-nested-subagent-claude-code-2026-06-09]] — Cherny nested-subagent stacking primitive
- [[karpathy-loopcraft-stacking-loops-2026-06-12]] — Karpathy loopcraft canonical-naming
- [[dailybrief-roundup-2026-06-12]] — brief surfacing context

## Verification-pending

- 0xCodez full identity / X-bio
- 0xCodez substack `movez.substack.com` content quality
- Specific Anthropic engineer Prithvi Rajasekaran engineering-blog post on self-critique
- Specific Continual Learning Bench 1.0 full results (paper / preprint / blog)
- Specific Parameter Golf full experiment details + 6× improvement attribution
- Specific 319-page Fable 5 system card key sections + downgrade-behaviors buried in doc
- June 22 paid-plans-end date confirmation
- Specific Routines April-14-2026 launch event details
- Specific Anthropic-engineering-internal model-routing pattern attribution source
- Whether 0xCodez = previous wiki entity 0xchromium (pattern: similar handle; verification-pending)
