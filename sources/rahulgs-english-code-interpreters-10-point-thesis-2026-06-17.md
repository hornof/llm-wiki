---
title: "Rahul GS — 10-point thesis: 'Fable+ class models = english → code interpreters' + 'scarce skill = removing ambiguity' + Boris Cherny direct 'strongly agree' validation (2026-06-17)"
type: source
medium: twitter-thread
url: https://x.com/rahulgs/status/2067257255825686880
ingested: 2026-06-17
---

## Summary

**Rahul GS (@rahulgs)** publishes (2026-06-17; saved as `_raw/Post by @rahulgs on X.md`) a **10-point thesis** on what frontier-AI-coding-models do — **STRUCTURALLY MAJOR canonical-framing**. **First wiki-captured Rahul GS direct-voice substantive surface**. **First wiki-captured "Fable+ class models = english → code interpreters" canonical mental-model** (*"converts your idea into code into 'correct' code regardless of problem complexity and output complexity (diff size)"* + *"Fable 5 will be the worst of this new class of models"*). **STRUCTURALLY CRITICAL Boris Cherny direct response**: *"Strongly agree with all of the above"* — **first wiki-captured Boris Cherny direct-voice "strongly agree" validation of a non-Anthropic-authored canonical-framework**. **First wiki-captured "scarce skill = removing ambiguity from your own description" canonical Evolution-Plus-AI framing** (comment-thread). **First wiki-captured Matt @m13v_ "long session quietly compacting and dropping the spec 40 turns back" canonical context-compaction-spec-loss failure-mode**. Pairs structurally with [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|Samuel McDonald verifier-discipline-first canonical-corrective]] + [[zodchii-builder-checker-looping-team-2026-06-16|Zodchii looping-team operationalization]] at the **3-voice canonical-corrective + operationalization + reframing same-week cluster** layer.

## Key Claims / Takeaways

### Rahul GS's 10-point thesis

**1. "English → code interpreters" canonical mental-model**:
> *"as a mental model it is more correct to think of fable+ class models as english -> code interpreters - converts your idea into code into 'correct' code regardless of problem complexity and output complexity (diff size). Fable 5 will be the worst of this new class of models"*

**First wiki-captured "english → code interpreters" canonical mental-model for Fable+ class models**. **First wiki-captured "Fable 5 will be the worst of this new class" canonical improvement-trajectory anchor**.

**2. Diff-size management for review**:
- **Small diffs** — high-risk areas of code (auth / identity / data access / network access / money movement)
- **Large diffs** — empirically-verifiable code (frontend / backend plumbing / code without network or db access / performance code that can be empirically verified)

**First wiki-captured "small-diffs-for-high-risk + large-diffs-for-empirically-verifiable" canonical diff-size-management-for-review framing**.

**3. "Time to ship ≠ time to produce PR"** canonical-framing:
> *"time it takes to ship software is completely disconnected from time to produce the PR - how long the work takes depends fully on ability to review/merge code while managing risk at scale"*

**First wiki-captured "time-to-ship ≠ time-to-produce-PR" canonical framing**. **STRUCTURALLY MAJOR** — reframes the bottleneck-locus from generation to review/merge.

**4. Bottleneck-solving emphasis**:
> *"solving the bottlenecks for above matter enormously- linters/testing/CI/shadow mode verification/empirical verification"*

**First wiki-captured 5-component bottleneck-solving canonical-articulation**: linters + testing + CI + shadow-mode verification + empirical verification.

**5. Agency emphasis**:
> *"what are the biggest bottlenecks to speeding up the loop and eliminating them? what are the problems that need solving and when do they need solving?"*

**First wiki-captured "agency-as-bottleneck-elimination canonical-loop-discipline" framing**.

**6. Full-stack-understanding-for-risk-management emphasis**:
> *"deep understanding of the full stack matters enormously... understanding every line of logic may not be needed but understanding and managing risk matters enormously."*

**First wiki-captured "understanding-every-line-of-logic NOT needed; understanding-and-managing-risk matters enormously" canonical-discipline-shift framing**. Order-of-importance: **security holes > correctness holes > performance holes** — canonical risk-priority.

**7. "Cost of complexity is changing" canonical counter-intuitive framing** — STRUCTURALLY MAJOR:
> *"the cost of complexity itself is changing. it might be now worth 'maintaining' 50% more code to get a 5% performance win. getting the right abstractions matter less because larger refactors are less tedious. code quality nits become huge drag. very likely, a much smarter model will be maintaining your code so worth taking on more technical debt now. taking the time to hand architect and rebuild systems comes with an enormous cost of velocity"*

**First wiki-captured "cost of complexity is changing" canonical counter-intuitive framing**. **First wiki-captured "50%-more-code-for-5%-performance-win" canonical anchor**. **First wiki-captured "code quality nits become huge drag" canonical-discipline-shift framing**. **First wiki-captured "worth taking on more technical debt now" canonical strategic-debt-positioning framing** (counter-intuitive: model-will-maintain implies debt-cost-is-lower-than-velocity-cost). **First wiki-captured "hand architect and rebuild = enormous cost of velocity" canonical-framing**.

**8. Duck-typing canonical reframing**:
> *"if it quacks like a duck and walks like a duck, it's a duck. For low risk cases, it might be more sane to treat code chunks (services / functions) as a black box, like we do for neural networks: do full empirical verification only"*

**First wiki-captured "treat code chunks as black box like neural networks" canonical-reframing**. **First wiki-captured "duck-typing canonical verification-by-empirical-output" framing**. Canonical verification questions:
- Has code produced correct outputs for the last 10, 100, 1000, 10k inputs?
- Can we quarantine this large piece of code (no outbound network/database access)?
- What happens when this code is wrong (hacked / crash / inconvenience)?
- Internal-facing or external-facing?

**9. "Logical verification at enormous cost" canonical-framing**:
> *"eventually, logical verification (line by line review) will come at an enormous cost- save it for where it matters and build systems that are tolerant to empirical verification"*

**First wiki-captured "logical verification at enormous cost; build systems tolerant to empirical verification" canonical-discipline-shift framing**. *"correctness bugs are significantly easier to rectify than access bugs"* — first wiki-captured correctness-vs-access-bug canonical risk-priority articulation.

**10. "Code permissions as canonical-design opt-in" framing**:
> *"what are the rails that allow for even faster iteration? code permissions can be opt in - db writes, db reads, network egress (to where?), PII access. how long does it take to get shadow mode data?"*

**First wiki-captured "code permissions as canonical-design opt-in" framing** — DB writes / DB reads / network egress / PII access as canonical permission categories. Pairs structurally with [[eric-siu-single-brain-5-layer-company-brain-2026-05-29|Eric Siu Single Brain Permissions layer]] at the **workflow-level-permissions-as-canonical-architecture cross-application layer**.

### STRUCTURALLY CRITICAL Boris Cherny direct response

**Boris Cherny @bcherny** (Jun 17): *"Strongly agree with all of the above. We are entering the next era of code, where the model is able to generate correct code for an increasingly large percent of tasks. Our job is to make sure the model and our systems have the right guardrails, then to run Claude Code + an[..."*

**STRUCTURALLY CRITICAL**: **first wiki-captured Boris Cherny direct-voice "strongly agree" validation of a non-Anthropic-authored canonical-framework**. Boris Cherny = Claude Code creator — his explicit endorsement positions Rahul GS's 10-point thesis as **canonical-discourse-anchor for Anthropic-side AI-coding-product positioning**.

**Cherny's extension**:
- *"We are entering the next era of code"* — **first wiki-captured Cherny "next era of code" canonical-framing**
- *"the model is able to generate correct code for an increasingly large percent of tasks"* — Cherny validates Rahul GS's *"converts your idea into 'correct' code regardless of complexity"* claim
- *"Our job is to make sure the model and our systems have the right guardrails"* — Cherny's **first wiki-captured "right guardrails" canonical-discipline articulation** at vendor-creator tier (pairs with [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|Samuel McDonald verifier-discipline-first principle]] at corrective-tier + [[zodchii-builder-checker-looping-team-2026-06-16|Zodchii looping-team operationalization]] at practitioner-tier)
- Truncated: *"then to run Claude Code + an"* (Cherny truncates mid-sentence — verification-pending what follows)

**First wiki-captured 3-voice canonical-validation + corrective + operationalization same-week cluster** (Jun 15 McDonald verifier-bottleneck corrective + Jun 16 Zodchii looping-team operationalization + Jun 17 Cherny "strongly agree" + "right guardrails" validation).

### STRUCTURALLY SIGNIFICANT comment-thread framings

#### Evolution Plus AI — "scarce skill = removing ambiguity from your own description"

> *"This reframes where the bug lives. If it is an english to code interpreter, it compiles your spec faithfully, not your intent. The error doesn't vanish, it moves upstream from the code into the english. So the scarce skill becomes removing ambiguity from your own description"*

**First wiki-captured "scarce skill = removing ambiguity from your own description" canonical operator-side-discipline framing**. **First wiki-captured "the error doesn't vanish, it moves upstream from the code into the english" canonical bug-locus-reframing**. **First wiki-captured "compiles your spec faithfully, not your intent" canonical interpreter-failure-mode articulation**. This is the **operator-side corollary** to McDonald's verifier-discipline-first principle — McDonald: *"design the verifier"*; Evolution: *"the scarce skill = removing ambiguity from your own description (the input to the verifier)"*.

#### "i miss the sun" — "human-out-of-the-loop" counter-frame

> *"this is true if u want to keep humans in the loop. But i don't expect that to be true, for reviewing anything at all, as the models get better. Why have a human review if the llm is better than you (eventually). we will be out of the loop entirely."*

**First wiki-captured "human-out-of-the-loop" canonical-counter-framing** — counter-position to McDonald + Zodchii + Cherny human-in-loop verifier-discipline. Pairs structurally with [[concepts/recursive-self-improvement|RSI canonical discourse]] at the **human-out-of-loop frontier** layer.

#### Matt @m13v_ — context-compaction-spec-loss canonical failure-mode

> *"i've started treating it exactly like that, an interpreter i pipe intent into. only place it falls apart for me is a long session quietly compacting and dropping the spec i gave it 40 turns back"*

**First wiki-captured "long session quietly compacting and dropping the spec 40 turns back" canonical context-compaction-spec-loss failure-mode**. Pairs structurally with [[concepts/company-brain|Company Brain canonical persistent-memory architecture]] + [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald outer-loop "agent forgets when the context window resets" framing]] at the **operator-side context-compaction-as-canonical-failure-mode** layer.

### Cross-cutting framings

- **First wiki-captured Rahul GS direct-voice substantive surface** (single-source defer per conservative policy)
- **First wiki-captured "Fable+ class models = english → code interpreters" canonical mental-model**
- **First wiki-captured "Fable 5 will be the worst of this new class" canonical improvement-trajectory anchor**
- **First wiki-captured Boris Cherny direct-voice "strongly agree" validation of a non-Anthropic-authored canonical-framework**
- **First wiki-captured Cherny "next era of code" canonical-framing**
- **First wiki-captured Cherny "right guardrails" canonical-discipline articulation at vendor-creator tier**
- **First wiki-captured 3-voice canonical-corrective + operationalization + validation same-week cluster** (McDonald Jun 15 + Zodchii Jun 16 + Cherny Jun 17)
- **First wiki-captured "scarce skill = removing ambiguity from your own description" canonical operator-side-discipline framing** (Evolution Plus AI)
- **First wiki-captured "the error doesn't vanish, it moves upstream from the code into the english" canonical bug-locus-reframing**
- **First wiki-captured "compiles your spec faithfully, not your intent" canonical interpreter-failure-mode articulation**
- **First wiki-captured "human-out-of-the-loop" canonical-counter-framing** (i miss the sun)
- **First wiki-captured "long session quietly compacting and dropping the spec 40 turns back" canonical context-compaction-spec-loss failure-mode** (Matt @m13v_)
- **First wiki-captured "small-diffs-for-high-risk + large-diffs-for-empirically-verifiable" canonical diff-size-management-for-review framing**
- **First wiki-captured "time-to-ship ≠ time-to-produce-PR" canonical framing**
- **First wiki-captured 5-component bottleneck-solving canonical-articulation** (linters + testing + CI + shadow-mode + empirical verification)
- **First wiki-captured "understanding-and-managing-risk > understanding-every-line-of-logic" canonical-discipline-shift framing**
- **First wiki-captured "cost of complexity is changing" canonical counter-intuitive framing** + **"50%-more-code-for-5%-performance-win" canonical anchor** + **"code quality nits become huge drag" canonical-discipline-shift framing** + **"worth taking on more technical debt now" canonical strategic-debt-positioning framing**
- **First wiki-captured "treat code chunks as black box like neural networks" canonical-reframing** + **duck-typing canonical verification-by-empirical-output framing**
- **First wiki-captured "logical verification at enormous cost; build systems tolerant to empirical verification" canonical-discipline-shift framing**
- **First wiki-captured "correctness bugs significantly easier to rectify than access bugs" canonical risk-priority articulation**
- **First wiki-captured "code permissions as canonical-design opt-in" framing** (DB writes + DB reads + network egress + PII access)

## Pages Updated

- [[rahulgs]] / [[rahul-gs]] — new entity-page candidate (single-source defer; substantive 10-point canonical-thesis voice; Cherny-validated)
- [[boris-cherny]] — STRUCTURALLY CRITICAL "strongly agree" validation + "next era of code" + "right guardrails" canonical-discipline articulation at vendor-creator tier
- [[claude-code]] — Cherny's "right guardrails" + Rahul GS thesis-validation positions Claude Code canonical-positioning
- [[claude-fable-5]] — Rahul GS "Fable 5 will be the worst of this new class" canonical improvement-trajectory anchor
- [[concepts/agentic-engineering]] — 10-point canonical thesis added; cost-of-complexity-changing + duck-typing-canonical-reframing + empirical-verification-tolerance canonical-discipline-shifts
- [[concepts/loop-engineering]] — 3-voice canonical-corrective + operationalization + validation same-week cluster (McDonald + Zodchii + Cherny)
- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15]] — Cherny validation strengthens canonical-corrective discourse
- [[zodchii-builder-checker-looping-team-2026-06-16]] — Cherny validation strengthens practitioner-operationalization
- [[concepts/verifiability-and-jagged-intelligence]] — duck-typing empirical-verification-by-output canonical-reframing
- [[concepts/recursive-self-improvement]] — "human-out-of-the-loop" counter-frame (i miss the sun)
- [[concepts/company-brain]] — context-compaction-spec-loss canonical failure-mode (Matt @m13v_)
- [[evolution-plus-ai]] / [[matt-m13v]] / [[i-miss-the-sun]] / [[zayyan]] — single-quote-context defers (entity-page candidates)

## Adjacent sources

- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15]] — Loop Engineering verifier-discipline-first canonical-corrective (corrective-tier)
- [[zodchii-builder-checker-looping-team-2026-06-16]] — Zodchii practitioner-tier operationalization
- [[gregisenberg-pick-a-side-7-question-poll-2026-06-16]] — Jun 16 practitioner-poll context
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny canonical recipe (vendor-side primitives)
- [[karpathy-loopcraft-stacking-loops-2026-06-12]] — Karpathy loopcraft canonical-naming
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — Anthropic Dynamic Workflows canonical primary
- [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14]] — Nadella frontier-ecosystem canonical-positioning
- [[eric-siu-single-brain-5-layer-company-brain-2026-05-29]] — Single Brain 5-layer Company-Brain (permissions canonical-layer pair)
- [[anthropic-usg-conflict-cluster-jun-16-extension-2026-06-16]] — Anthropic-USG-conflict cluster context

## Verification-pending

- Specific Rahul GS identity + role + canonical-voice-tier background
- Full Boris Cherny "strongly agree" response (truncated mid-sentence at *"then to run Claude Code + an[..."* — verification-pending the rest)
- Specific Evolution Plus AI / Matt @m13v_ / i miss the sun / zayyan canonical-voice-tier backgrounds
- Specific Rahul GS reception in canonical Loop-Engineering canonical-voice register (Cherny + Steinberger + Karpathy + Zaharia + Nadella + Sarah Guo + Samuel McDonald + Zodchii)
- Specific "Fable 5 will be the worst of this new class" technical-anchor (what improvement-trajectory does Rahul GS predict?)
- Specific "code permissions as canonical-design opt-in" tooling-implementation status (existing tools? Future framework? Speculation?)
- Specific "shadow mode verification" canonical-implementation context (canonical operational-practice or proposed-pattern?)
