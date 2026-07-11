---
title: "Samuel McDonald (@samueljmcd) — 'My Thoughts on Loop Engineering' — verifier-is-the-bottleneck canonical Loop-Engineering corrective + Inner/Outer Loop + Open/Closed Loop + 'Design the verifier, not the prompt' canonical closing (2026-06-15)"
type: source
medium: article
url: https://x.com/samueljmcd/status/2066524627585634765
ingested: 2026-06-16
---

## Summary

**Samuel McDonald (@samueljmcd)** publishes (2026-06-15; saved as `_raw/My Thoughts on Loop Engineering.md`) **"My Thoughts on Loop Engineering"** — **STRUCTURALLY MAJOR Loop-Engineering canonical-corrective**. **First wiki-captured "verifier-is-the-bottleneck-not-the-generator" canonical Loop-Engineering corrective**. **First wiki-captured "A loop is a generator wired to a verifier. The generator was never the bottleneck. The verifier is." canonical articulation**. **First wiki-captured Open-Loop / Closed-Loop canonical-distinction** (open = exploratory + slop-risk + budget-burner; closed = bounded + production-tier). **First wiki-captured Inner-Loop / Outer-Loop canonical-distinction** (inner = single-task verification; outer = across-sessions persistent-lesson-carry-forward). **First wiki-captured "A loop that goes green is not a loop that is correct" canonical testing-completeness articulation**. **First wiki-captured "Design the verifier, not the prompt" canonical Loop-Engineering closing**. **First wiki-captured "Management in the age of agents is about designing the constraints they run inside, the same as it always was with people" canonical management-discipline framing**. Extends Loop Engineering canonical cluster from 8-voice to **10-voice** (Cherny + Steinberger + Van Horn + Bishoyi + Karpathy + Zaharia + Nadella + Sarah Guo + Alien + Samuel McDonald) — McDonald positioned at **verifier-discipline-first canonical-tier** (corrective-tier, not validator-tier).

## Key Claims / Takeaways

### The thesis — verifier is the bottleneck

- **Author**: Samuel McDonald (@samueljmcd)
- **Date**: 2026-06-15
- **Central thesis**: *"Loop engineering is the new label. The hard part is the one it has always been. Verification."*
- **Canonical reformulation**: *"A loop is a generator wired to a verifier. The generator was never the bottleneck. The verifier is."*
- **Closing canonical**: *"Design the verifier, not the prompt."*

**First wiki-captured "verifier-is-the-bottleneck-not-the-generator" canonical Loop-Engineering corrective** — directly counter-frames the **Loop Engineering = prompt-engineering-evolution** discourse that dominates the canonical cluster:
- [[bcherny-5-tips-opus-autonomous-2026-06-05|Cherny canonical recipe]] = vendor-side primitives + 5-tips canonical
- [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger "fleets that design your loops"]] = fleet-tier abstraction
- [[karpathy-loopcraft-stacking-loops-2026-06-12|Karpathy loopcraft]] = stacking-loops canonical-naming
- [[zaharia-omnigent-multi-agent-meta-harness-2026-06-13|Zaharia Omnigent]] = meta-harness governance-tier
- [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14|Nadella frontier-ecosystem]] = firm-CEO-tier learning-loop

**McDonald's verifier-discipline-first corrective**: all of the above design *the generator* (orchestration + primitives + harness + ecosystem); McDonald argues **the generator was never the bottleneck**.

### The 3-phase Loop Engineering pitch (rejected by McDonald)

McDonald summarizes the prevailing Loop Engineering pitch:
- **2024**: writing good prompts
- **2025**: running agents in parallel
- **2026**: building the loop that runs the agents for you

McDonald's rejection: *"That framing is fine as far as it goes. It also buries the part that decides whether your loop ships anything."* — **first wiki-captured operator-side canonical-rejection of 3-phase Loop Engineering pitch**.

### Open vs Closed loops — canonical distinction

| Type | Characteristics | Outcome |
|---|---|---|
| **Open loop** | Wide exploratory space; conditions + goal but freedom in between; can find paths you did not specify | Genuinely novel output **+ slop-machine on loose criteria + budget-burner** |
| **Closed loop** | Goal + defined steps + evaluation at each step + stopping condition or human-handoff with run-data | **Production-tier results today**; normal budget; paths bounded |

**First wiki-captured Open-Loop / Closed-Loop canonical-distinction**. **First wiki-captured "closed loops are what produce results today" canonical operator-side discipline-claim**.

**Key insight**: *"People credit the autonomy for that. The autonomy is not the reason. The evaluation gate is. The gate is what stops a confident wrong answer from propagating into the next iteration, and the next."* — **first wiki-captured "autonomy is not the reason; the evaluation gate is" canonical attribution-correction**.

### Inner Loop vs Outer Loop — canonical distinction

| Layer | Scope | What it verifies |
|---|---|---|
| **Inner loop** | Single task | The task itself (write code + test + run + fix + confirm) |
| **Outer loop** | Across sessions | That you do not repeat last week's mistake (persistent lesson carry-forward) |

**First wiki-captured Inner-Loop / Outer-Loop canonical-distinction**. **First wiki-captured "the agent forgets when the context window resets. The repository does not" canonical persistent-memory-architectural-framing**. Maturity assessment:
- **Inner loop = mature** — most agents do it now
- **Outer loop = still half-built** — *"Persisting the right lesson, in the right place, at the right grain, is harder than it sounds, and it is where a lot of value is currently sitting on the table."*

**First wiki-captured "outer-loop-value-sitting-on-the-table" canonical opportunity-articulation**. Maps to **`SKILL.md` + `AGENTS.md`** as canonical outer-loop persistent-memory homes.

### ReAct + Reflexion research-roots canonical-attribution

McDonald roots Loop Engineering in 2 research patterns:

- **ReAct** (Yao et al.; Princeton + Google) — alternates reasoning and action; *"think, act, observe the result, think again, repeat until done"*
- **Reflexion** (Shinn et al.) — ReAct with memory; *"when an attempt fails, the agent writes down in plain language why it failed, stores that note, and reads it on the next attempt"* — **canonical seed of persistent memory**

**First wiki-captured ReAct + Reflexion canonical-research-roots attribution for Loop Engineering**. **First wiki-captured "Reflexion as canonical seed of persistent memory" framing**.

### The Bun port reframed — "verification is the architecture"

McDonald reads the [[bun|Bun Zig→Rust port]] via Dynamic Workflows as **the flagship verification-architecture demonstration**:

| Step | Function |
|---|---|
| Pass 1 | Map correct Rust lifetime for every struct field |
| Pass 2 | Each file as behaviour-identical port; hundreds of agents in parallel + **2 reviewer agents on every file** |
| Layer | **Separate layer of agents existed only to refute what the others produced** |
| Fix loop | Drive build + test suite until both ran clean |

**Canonical framing**: *"The verification is not a step at the end. **It's actually the architecture.**"* — first wiki-captured "verification-is-the-architecture-not-a-final-step" canonical-pattern.

**Numbers anchor** (corroborates [[anthropic-dynamic-workflows-primary-2026-05-28|prior Bun port coverage]]):
- ~750,000 lines of Rust
- **99.8% existing test suite passing**
- **Anthropic: 11 days from first commit to merge**; **Sumner: 6 days**

### Anthropic's own caveat — "not yet in production"

**STRUCTURAL** — McDonald flags Anthropic's own published caveat: *"the port is not yet in production."*

McDonald's reframe: *"That is the most honest line in the entire launch, and it is the one I would underline. A 99.8% pass on an existing suite is a benchmark result. It tells you the port reproduces the behaviour the old tests already described. Production is the behaviour nobody wrote a test for yet. The gap between those two is the gap this whole industry keeps tripping over."*

**Canonical conclusion**: *"A loop that goes green is not a loop that is correct. It is a loop that satisfied the verifier you gave it. **The quality of the output is capped by the quality of that verifier, and not one point higher.**"*

**First wiki-captured "benchmark-pass-vs-production-correctness gap" canonical operator-side framing**. **First wiki-captured "output-quality-capped-by-verifier-quality" canonical Loop-Engineering ceiling-framing**.

### Native-tooling specifics — `/goal` + Dynamic Workflows

McDonald documents the specific Claude Code feature-versions:

| Feature | Version | Capability |
|---|---|---|
| `/goal` | v2.1.139+ | Holds a completion condition; keeps working across turns until met |
| Dynamic workflows | v2.1.154+ (research preview) | Claude writes orchestration script that fans work across many parallel agents; **capped at 16 concurrent + 1000 agents per run** |

**First wiki-captured concrete Claude Code Dynamic Workflows capacity-anchor**: **16 concurrent / 1000 agents per run** canonical limits. Pairs structurally with [[claude-opus-4-8-dynamic-workflows-2026-05-28|prior Dynamic Workflows coverage]].

McDonald's discipline-rule: *"Reach for them when the task genuinely does not fit one pass. They cost considerably more tokens than a normal session. Not every job is a workflow job, and dressing a small task up as one is its own kind of waste."* — **first wiki-captured "not every job is a workflow job" canonical operator-side discipline-rule**.

### Mechanical-parts canonical articulation

McDonald enumerates the **6 mechanical parts** of a working loop:
1. **Scheduled trigger** to discover work + start the agent
2. **Isolated git worktrees** so parallel agents do not stand on each other's changes
3. **Skills files** so you are not re-explaining conventions every run
4. **Connectors** to tools the work already lives in
5. **Separated generator-and-verifier roles** because *"an agent grading its own homework grades generously"*
6. **Memory** — the file that outlives the conversation and carries the lesson forward

**First wiki-captured "6-mechanical-parts canonical Loop-Engineering architecture articulation"**. Pairs with [[zodchii-4-agent-claude-code-roster-2026-06-14|Zodchii 4-agent roster]] at the **operator-side canonical-mechanical-parts** layer. **First wiki-captured "agent grading its own homework grades generously" canonical agent-self-verification-failure-mode framing** — pairs with [[zodchii-4-agent-claude-code-roster-2026-06-14|Zodchii "blind-reviewer" discipline]].

### "Management in the age of agents" canonical closing

McDonald's closing framing — *"Management in the age of agents is not about hiring capable workers. The workers are capable and cheap. **It is about designing the constraints they run inside, the same as it always was with people.**"*

**First wiki-captured "designing-the-constraints-they-run-inside" canonical management-discipline framing**. Pairs structurally with:
- [[ai-native-organizations|Block AI-native organizations]] = org-design as constraint-engineering
- [[concepts/company-brain|Sentra Universal-Substrate-Multiple-Ontologies]] = workflow-permission-as-canonical-architecture
- [[eric-siu-single-brain-5-layer-company-brain-2026-05-29|Single Brain Permissions layer]] = workflow-level access-boundaries

### Cross-cutting framings

- **STRUCTURALLY MAJOR Loop-Engineering canonical-corrective** — McDonald positions verifier-discipline-first against the prevailing generator-design discourse
- **Extends Loop Engineering canonical cluster from 8 to 10-voice**: McDonald (10th canonical voice; verifier-discipline-first-tier)
- **First wiki-captured "verifier-is-the-bottleneck-not-the-generator" canonical Loop-Engineering corrective**
- **First wiki-captured "Design the verifier, not the prompt" canonical Loop-Engineering closing**
- **First wiki-captured Open-Loop / Closed-Loop canonical-distinction**
- **First wiki-captured Inner-Loop / Outer-Loop canonical-distinction**
- **First wiki-captured "A loop that goes green is not a loop that is correct" canonical testing-completeness articulation**
- **First wiki-captured "autonomy is not the reason; the evaluation gate is" canonical attribution-correction**
- **First wiki-captured "the agent forgets when the context window resets. The repository does not" canonical persistent-memory-architectural-framing**
- **First wiki-captured "outer-loop-value-sitting-on-the-table" canonical opportunity-articulation**
- **First wiki-captured ReAct + Reflexion canonical-research-roots attribution for Loop Engineering**
- **First wiki-captured "Reflexion as canonical seed of persistent memory" framing**
- **First wiki-captured "verification-is-the-architecture-not-a-final-step" canonical-pattern** (Bun port reframe)
- **First wiki-captured "benchmark-pass-vs-production-correctness gap" canonical operator-side framing**
- **First wiki-captured "output-quality-capped-by-verifier-quality" canonical Loop-Engineering ceiling-framing**
- **First wiki-captured concrete Claude Code Dynamic Workflows capacity-anchor** (16 concurrent / 1000 agents per run)
- **First wiki-captured "not every job is a workflow job" canonical operator-side discipline-rule**
- **First wiki-captured "6-mechanical-parts canonical Loop-Engineering architecture articulation"**
- **First wiki-captured "agent grading its own homework grades generously" canonical agent-self-verification-failure-mode**
- **First wiki-captured "designing-the-constraints-they-run-inside" canonical management-discipline framing**
- **First wiki-captured Addy Osmani 5-components-plus-memory framing attribution**

## Pages Updated

- [[concepts/loop-engineering]] — Samuel McDonald verifier-discipline-first corrective added; Open/Closed + Inner/Outer canonical distinctions; "Design the verifier, not the prompt" canonical closing; 10-voice cluster extension
- [[samueljmcd]] / [[samuel-mcdonald]] — new entity-page candidate (single-source defer per conservative policy)
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny "another Claude doing the prompting" framing context (Fortune Brainstorm Tech June 2026)
- [[boris-cherny]] — Cherny Fortune Brainstorm Tech context added
- [[bun]] — Bun Zig→Rust port reframed as verification-is-the-architecture
- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — Dynamic Workflows capacity anchor (16 concurrent / 1000 agents per run)
- [[concepts/agentic-engineering]] — verifier-discipline-first canonical-pattern added
- [[concepts/company-brain]] — pairs with outer-loop persistent-memory architectural framing
- [[react-pattern]] / [[reflexion]] — canonical-research-roots attribution (entity-page candidates; single-source defers)
- [[addy-osmani]] — 5-components-plus-memory framing attribution (entity-page candidate; single-source defer)
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — Anthropic's "not yet in production" caveat surfaced + reframed

## Adjacent sources

- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny canonical recipe
- [[steipete-loops-engineering-vision-md-2026-06-07]] — Steinberger fleets-that-design-your-loops
- [[mvanhorn-wtf-is-a-loop-2026-06-07]] — Van Horn 5-stage Loop Engineering
- [[alokbishoyi-evo-self-evolving-autoresearch-workflows-2026-06-09]] — Bishoyi evo 0.5
- [[karpathy-loopcraft-stacking-loops-2026-06-12]] — Karpathy loopcraft canonical-naming
- [[zaharia-omnigent-multi-agent-meta-harness-2026-06-13]] — Zaharia Omnigent meta-harness
- [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14]] — Nadella frontier-ecosystem firm-CEO-tier
- [[levie-nadella-cognitive-loop-thread-2026-06-14]] — Levie + Alien learning-loop-physical-location-test reformulation
- [[dailybrief-roundup-2026-06-14]] — Sarah Guo "what's untrainable" investor-side framing
- [[zodchii-4-agent-claude-code-roster-2026-06-14]] — Zodchii 4-agent roster canonical-discipline-rules
- [[eric-siu-single-brain-5-layer-company-brain-2026-05-29]] — Single Brain 5-layer Company-Brain architecture
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — Bun Zig→Rust port primary
- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — Dynamic Workflows announcement

## Verification-pending

- Samuel McDonald (@samueljmcd) identity + role + canonical-voice-tier background
- Primary Boris Cherny Fortune Brainstorm Tech June 2026 remarks (not yet wiki-captured)
- Primary Addy Osmani "5-components-plus-memory" article + canonical-naming context
- Primary ReAct paper (Yao et al.; Princeton + Google) — research-roots verification
- Primary Reflexion paper (Shinn et al.) — research-roots verification
- Primary Claude Code v2.1.139 + v2.1.154 changelog confirming /goal + Dynamic Workflows version-anchors
- Specific Dynamic Workflows "16 concurrent + 1000 agents per run" cap verification (Anthropic-published canonical limits?)
- Specific reception of McDonald verifier-discipline-first corrective by canonical Loop-Engineering voices (Cherny + Steinberger + Karpathy + Zaharia)
- Specific Bun port "not yet in production" Anthropic-side caveat publication-location
- Specific "Sumner: 6 days" vs "Anthropic: 11 days" discrepancy reconciliation
