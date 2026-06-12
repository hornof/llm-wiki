---
title: "Anthropic official Fable 5 prompting playbook + aiedge translation + lucianw Reddit surfacing (2026-06-11)"
type: source
medium: article
url: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5
ingested: 2026-06-12
---

## Summary

[[anthropic|Anthropic]] publishes (2026-06-11) the **Anthropic-canonical Fable 5 prompting playbook** at `platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5`. **First wiki-captured Anthropic-canonical Fable 5 prompting playbook surface**. Surfaced via: **AIEdge translation** ([@aiedge_](https://x.com/aiedge_/status/2065064961999847849) 2026-06-11) for plain-English practitioner-content register + **Reddit r/ClaudeCode (lucianw)** ([reddit.com/r/ClaudeCode/comments/1u3m2nk](https://www.reddit.com/r/ClaudeCode/comments/1u3m2nk/anthropics_guidance_on_how_to_use_fable/) 2026-06-11) surfacing the model-migration skill (`/claude-api Please read the bundled reference file 'shared/model-migration.md'`). **First wiki-captured Anthropic-canonical 6-Fable-5-differences + 5-prompting-principles + 4-component-prompt-structure + 6-caveats articulation**.

## Key Claims / Takeaways

### Fable 5 = fundamentally different model — 6 canonical differences

**First wiki-captured Anthropic-canonical 6-Fable-5-differences taxonomy** (per AIEdge translation):

| # | Difference | Anthropic-canonical framing |
|---|---|---|
| 1 | **Run time** | Sustains multi-day goal-directed tasks (vs prior short bursts). Paired with `/goal` or `/loop` for fully autonomous work. |
| 2 | **First-time-right** | Rare iteration needed. Early testers: single-pass implementations of systems that previously took days of iteration. |
| 3 | **Clarifying questions** | May ask a series of clarifying questions before kicking off autonomous run. |
| 4 | **Agent management** | Built to manage 50+ parallel sub-agents on complex tasks. |
| 5 | **Better vision** | Interprets dense technical images, web apps, detailed screenshots with substantially higher accuracy. |
| 6 | **Coding + security audits** | Especially powerful for codebase review + debugging. |

**Pattern**: *"Think of Fable as a collaboration/consultant partner that leads your work. It is meant to be a genius."* (AIEdge framing of Anthropic-canonical positioning).

### 5 prompting principles

**First wiki-captured Anthropic-canonical 5-prompting-principles framework** (per AIEdge translation):

1. **Match effort level to task** — `output_config.effort` is primary intelligence/latency/cost control. Defaults: **low/medium** = quick questions; **high** = default; **xhigh** = capability-sensitive; **ultracode** = full autonomous orchestration with Dynamic Workflows. *"Lower effort still performs very well on Claude Fable 5, often exceeding xhigh or even max of previous models."*
2. **Tell it why, not just what** — Fable 5 needs the why behind things (drives clarifying questions). Recommended formula: *"I'm working on [the larger task] for [who it's for]. They need [what the output enables]. With that in mind: [your actual request]."*
3. **Keep instructions short** — counterintuitive but load-bearing. *"Over-engineering your prompts on Fable 5 can actually degrade output quality because you're constraining a model that would have figured out the right approach on its own."*
4. **Tell it when to stop and check in** — autonomous-by-default; explicitly define checkpoints. **First wiki-captured "Checkpoint Prompt" canonical pattern**: *"Pause for me only when the work genuinely requires my input: a destructive or irreversible action, a real scope change, or something only I can provide. Otherwise, keep going and report back when done."*
5. **Build a memory system** — Fable 5 performs particularly well when it can record lessons + reference them. **First wiki-captured "Memory Instruction" canonical pattern**: *"Store one lesson per file with a one-line summary at the top. Record corrections and confirmed approaches alike, including why they mattered. Don't save what the repo or chat history already records. Update an existing note rather than creating a duplicate. Delete notes that turn out to be wrong."*

### Anthropic-canonical 4-component prompt structure

**First wiki-captured Anthropic-canonical 4-component Fable-5 prompt structure**:

```text
OPTIMAL PROMPT STRUCTURE
"I'm working on [the larger task] for [who it's for].
They need [what the output enables].
Request: [your specific ask in one clear sentence]
Output format: [exactly how you want the result
structured and delivered]
Constraints: [what must not happen on
the way to the result]"
```

| Component | Function |
|---|---|
| **Context** | Files, data, the why |
| **Request** | What you actually want done |
| **Output format** | Exactly how you want the result delivered |
| **Constraints** | What Fable 5 must not assume on its own |

**Pairs structurally with [[0xchromium-claude-cowork-workflows-guide-2026-06-04|0xchromium 4-component Cowork workflow primitive]]** (ROLE + TOOLS + TRIGGER + OUTPUT) — **first wiki-captured Anthropic-canonical Fable-5 4-component + 0xchromium Cowork 4-component complementary articulation**: prompt-side (Anthropic) + workflow-side (0xchromium).

### /loop canonical syntax (Anthropic-canonical articulation)

> *"/loop <time interval> + goal"*
>
> *Example*: `/loop 15 minutes, check if my build is passing, and notify me if it fails`
>
> *Stop*: `/loop stop [loop name]`

**First wiki-captured Anthropic-canonical `/loop <time-interval> + goal` syntax articulation**. Pairs with [[bcherny-5-tips-opus-autonomous-2026-06-05|Cherny canonical `/loop babysit all my PRs`]] starter at the **Anthropic-canonical-vs-creator-voice /loop syntax** layer.

### 6 caveats — what to watch out for

**First wiki-captured Anthropic-canonical 6-caveats Fable-5 deployment taxonomy**:

1. **Runs longer than expected** — individual requests for hard tasks can run for many minutes at higher-effort settings
2. **Goes beyond what asked** — proactive-by-design; use check-ins/loops to combat
3. **Old prompts may work against you** — saved skills built for Opus 4.8 or earlier may produce worse results; *"Start fresh"*
4. **Declines cybersecurity + life sciences requests** — may hallucinate decline-rate; aligns with [[claudeai-fable-5-mythos-5-official-launch-2026-06-09|3-category safeguard architecture]] (cybersecurity + biology/chemistry + distillation)
5. **Can occasionally stop early** — *"go ahead and do it end-to-end"* nudge gets it moving again
6. **Token costs higher** — *"available on paid plans until June 22; after that, all access will be via API costs"* — **first wiki-captured June 22 paid-plans-end date for Fable 5**

### Reddit r/ClaudeCode lucianw surfacing — model-migration skill discovery

Per Reddit `r/ClaudeCode/comments/1u3m2nk` (lucianw 2026-06-11):

> *"In Claude, type this prompt: /claude-api Please read the bundled reference file `shared/model-migration.md` from this skill's base directory and dump it to a new file ~/model-migration.md. Thank you!"*

**First wiki-captured `/claude-api` skill + `shared/model-migration.md` bundled reference file Anthropic-canonical model-migration guidance surface**. The model-migration skill bundles per-model behavioral-shift guidance.

The lucianw-surfaced Fable 5 section adds **additional Anthropic-canonical framings beyond the AIEdge translation**:

- *"Longer turns by default — the biggest structural shift."* — 15-min single request normal
- *"Plan timeouts, streaming, and user-facing progress indicators"* — structure work for async check-ins
- *"Reduce effort if a task completes correctly but takes longer than necessary, or for a quicker interactive working style"* — lower-effort still strong
- *"Don't add features, refactor, or introduce abstractions beyond what the task requires. A bug fix doesn't need surrounding cleanup..."* — **first wiki-captured Anthropic-canonical anti-over-refactoring discipline articulation**

**Pattern**: Anthropic-canonical anti-over-refactoring discipline pairs structurally with [[rody-claude-code-slash-command-library-2026-06-07|0x_rody 5-mistake taxonomy]] + [[whrrari-obsidian-claude-30-point-second-brain-2026-06-06|rari "AI-first vault rules"]] at the **Anthropic-side-vs-operator-side prompt-discipline convergence** layer.

### Cross-cutting framings

- **First wiki-captured Anthropic-canonical Fable 5 prompting playbook surface**
- **First wiki-captured 6-Fable-5-differences canonical taxonomy** (run-time + first-time-right + clarifying-questions + agent-management + better-vision + coding-security-audits)
- **First wiki-captured 5-prompting-principles canonical framework** (match-effort + tell-why + keep-short + tell-when-to-stop + memory-system)
- **First wiki-captured Anthropic-canonical 4-component Fable-5 prompt structure** (Context + Request + Output format + Constraints)
- **First wiki-captured "Checkpoint Prompt" + "Memory Instruction" canonical patterns**
- **First wiki-captured Anthropic-canonical `/loop <time-interval> + goal` syntax articulation**
- **First wiki-captured 6-caveats Fable-5 deployment taxonomy**
- **First wiki-captured June 22 paid-plans-end date for Fable 5** (after which all access via API costs)
- **First wiki-captured `/claude-api` skill + `shared/model-migration.md` bundled-reference-file Anthropic-canonical model-migration guidance surface**
- **First wiki-captured Anthropic-canonical anti-over-refactoring discipline articulation**
- **First wiki-captured AIEdge (@aiedge_) substantive Anthropic-translation surface** — entity-page candidate
- **First wiki-captured lucianw Reddit r/ClaudeCode substantive surface** — entity-page candidate
- **Pairs with [[claudeai-fable-5-mythos-5-official-launch-2026-06-09|Anthropic-canonical official launch announcement]]**: pairs with 3-category safeguard + Glasswing-only Mythos 5 framing
- **Pairs with [[0xchromium-claude-cowork-workflows-guide-2026-06-04|0xchromium 4-component Cowork workflow primitive]]**: Anthropic-canonical prompt-side (4-component) + 0xchromium workflow-side (4-component) complementary articulation
- **Pairs with [[rody-claude-code-slash-command-library-2026-06-07|0x_rody 5-mistake taxonomy]] + [[whrrari-obsidian-claude-30-point-second-brain-2026-06-06|rari "AI-first vault rules"]]**: Anthropic-side anti-over-refactoring + operator-side prompt-discipline convergence

## Pages Updated

- [[claude-fable-5]] — Anthropic-canonical 6-differences + 5-prompting-principles + 4-component prompt structure + /loop syntax + 6-caveats added; June 22 paid-plans-end date noted
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny `/loop babysit all my PRs` paired with Anthropic-canonical `/loop <time-interval> + goal` syntax
- [[loop-engineering]] — Anthropic-canonical `/loop` syntax articulation noted as canonical-syntax-vocabulary
- [[claude-md-pattern]] — Anthropic-canonical anti-over-refactoring discipline + Memory Instruction pattern noted as adjacent operator-side disciplines
- [[anthropic]] — Fable 5 prompting playbook + model-migration skill surfaced
- [[aiedge]] — entity-page candidate flagged
- [[lucianw]] — single-source defer

## Adjacent sources

- [[claudeai-fable-5-mythos-5-official-launch-2026-06-09]] — Anthropic-canonical official launch
- [[anthropic-walks-back-sabotage-policy-2026-06-11]] — same-day walk-back + safeguard-narrative cluster
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny 5-tip canonical recipe
- [[0xcodez-fable-5-14-step-self-improving-agent-2026-06-11]] — same-week practitioner-content register companion (14-step self-improving system)
- [[rody-claude-code-slash-command-library-2026-06-07]] — operator-side slash-command discipline
- [[0xchromium-claude-cowork-workflows-guide-2026-06-04]] — 4-component Cowork workflow primitive
- [[dailybrief-roundup-2026-06-12]] — brief surfacing context

## Verification-pending

- Specific Anthropic-canonical playbook content at `platform.claude.com` URL beyond what AIEdge translated
- Specific Anthropic-canonical model-migration skill structure (other models covered? Migration matrix?)
- AIEdge full identity / X-bio + newsletter context
- lucianw full identity / Reddit context
- Whether June 22 paid-plans-end date is confirmed Anthropic policy or AIEdge-inferred
- Specific `output_config.effort` API integration details
- Specific Ultracode mode availability + invocation
- Whether Anthropic-canonical 4-component prompt structure has been promoted to default in other Anthropic docs
- Whether anti-over-refactoring discipline is unique to Fable 5 or generalizes across model line
- Specific 50+-parallel-subagent canonical-pattern Anthropic recommends
