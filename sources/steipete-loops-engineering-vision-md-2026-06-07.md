---
title: "Peter Steinberger (@steipete) — Loops that prompt your agents + VISION.md primitive (X, 2026-06-07)"
type: source
medium: twitter-thread
url: https://x.com/steipete/status/2063697162748260627
ingested: 2026-06-08
---

## Summary

**Peter Steinberger (@steipete)** publishes (2026-06-07 X): *"Here's your monthly reminder that you shouldn't be prompting coding agents anymore. You should be designing loops that prompt your agents."* **First wiki-captured Steinberger surface explicitly elevating loop-engineering above harness-engineering**. Reply by Gautham Pai coins **"Loop Engineering"** as the post-Harness-Engineering practitioner-content register; Steinberger confirms with *"Don't worry it'll take 3 months until it's there. We'll be talking about fleets that design your loops then."* **First wiki-captured Steinberger VISION.md primitive disclosure** in same thread reply to Mo: *"I use a VISION.md for my projects."* Pairs structurally with [[linas-beliunas-claude-goal-guide-2026-05-14|Linas's `/goal` guide]] + [[trq-dynamic-workflows-harness-2026-06-02|Thariq's harness post]] at the loop-design layer.

## Key Claims / Takeaways

### The thesis

> *"Here's your monthly reminder that you shouldn't be prompting coding agents anymore. You should be designing loops that prompt your agents."* — Peter Steinberger

**Pattern**: explicit elevation of loop-engineering above prompt-engineering at the meta-level. Steinberger's framing positions the practitioner-content register as having moved past *"how to write good prompts"* to *"how to design loops that produce good prompts on the fly."*

### The "Loop Engineering" coinage + 3-month escalation prediction

Reply chain:

> **Gautham Pai**: *"Oh god, LinkedIn will now start a new fad, 'Loop Engineering'. Harness Engineering is so last year. Loop Engineering is what you should be doing."*

> **Steinberger**: *"Don't worry it'll take 3 months until it's there. We'll be talking about fleets that design your loops then."*

**First wiki-captured "Loop Engineering" practitioner-content register coinage** + **first wiki-captured 3-month escalation prediction**: prompts → harnesses → loops → fleets-that-design-loops.

**3-month escalation pattern (Steinberger framing)**:
1. **Prompts** (pre-2024) — direct LLM interaction
2. **Harnesses** (early 2026 per [[trq-dynamic-workflows-harness-2026-06-02|Thariq's "A harness for every task"]]) — custom harnesses on top of Claude Code
3. **Loops** (mid-2026, current) — designing the loop that prompts agents
4. **Fleets-that-design-loops** (Steinberger predicts ~3 months out, ~Sept 2026) — meta-level orchestration of loop-design

**First wiki-captured 4-stage practitioner-content register evolution timeline** with concrete escalation prediction.

### The VISION.md primitive

Reply to Mo (*"designing the loop is half of it. the other half is putting something in the loop that can say no: a test, a type check, a real error. a loop with nothing to push back is the agent agreeing with itself on repeat"*):

> **Steinberger**: *"I use a VISION.md for my projects"*

**First wiki-captured Steinberger VISION.md primitive disclosure**. Pairs structurally with [[claude-md-pattern|CLAUDE.md pattern]] as a **project-tier complement** to the 3-tier canonical content-template stack:

| Tier | Scope | Template | Purpose |
|---|---|---|---|
| Project | per-codebase behavioral contract | **CLAUDE.md** | What Claude must do / must never do |
| Project (NEW) | per-codebase **direction** / **goal** | **VISION.md** | What the project is trying to *be* — push-back primitive for loop |
| Domain | per-business-domain skill | Skill-file | What a metric / concept means |
| Role | per-subagent specialization | `.claude/agents/<role>.md` | How a specific role-agent operates |

**First wiki-captured VISION.md primitive** as a *"something in the loop that can say no"* push-back mechanism — operationally distinct from CLAUDE.md's *"behavioral contract"* function. **Extends the 3-tier canonical content-template stack to 4 tiers** (project-rules CLAUDE.md + project-vision VISION.md + domain skill-file + role agent-file).

### Mo's "loop with something that can say no" framing

> **Mo (@mosyaseen)**: *"designing the loop is half of it. the other half is putting something in the loop that can say no: a test, a type check, a real error. a loop with nothing to push back is the agent agreeing with itself on repeat."*

**First wiki-captured "loop with push-back primitive" framing**. Pattern: loops without an external grounding signal (test / type check / VISION.md / real error) degenerate to *"agent agreeing with itself on repeat"* — direct articulation of [[trq-dynamic-workflows-harness-2026-06-02|Thariq's "self-preferential bias" failure mode]] at the loop-design layer. **First wiki-captured operator-side framing pairing self-preferential-bias failure mode with push-back-primitive solution**.

### Pairs structurally with the Linas Claude-Code-canonical-content stack

| Surface | Voice | Layer |
|---|---|---|
| [[trq-dynamic-workflows-harness-2026-06-02\|Thariq harness post]] | Anthropic-internal | Harness-engineering canonical |
| [[linas-beliunas-claude-goal-guide-2026-05-14\|Linas /goal guide]] | Operator-side synthesis | `/goal` primitive deep-dive |
| [[linas-beliunas-dynamic-workflows-guide-2026-06-04\|Linas Dynamic Workflows synthesis]] | Operator-side synthesis | Workflow-orchestration canonical |
| **Steinberger Loops + VISION.md (this)** | **Practitioner-content register**  | **Loop-design + push-back primitive** |

**First wiki-captured 4-surface practitioner-content register cluster on Claude Code primitives** (Anthropic-internal + 2 operator-synthesis + 1 practitioner-content). Each surface operates at a distinct layer of the agent-orchestration stack.

### "ngmi" framing — agent-cuts-off-human anticipation

Reply to Basoner (*"Wondering when my agents will cut me off because I am dead weight."*):

> **Steinberger**: *"ngmi"* ("not gonna make it")

**First wiki-captured practitioner-content register casual framing of "agent-cuts-off-human" dead-weight anticipation**. Pairs with [[anthropic-institute-when-ai-builds-itself-2026-06-04|Anthropic Institute's "5-stage human-role-narrowing progression"]] at the *casual-practitioner-side* layer — Steinberger treats the human-role-narrowing as so taken-for-granted that asking when AI cuts you off gets dismissed with 4 letters.

### Cross-cutting framings

- **First wiki-captured Steinberger surface explicitly elevating loop-engineering above harness-engineering**
- **First wiki-captured "Loop Engineering" practitioner-content register coinage** (Gautham Pai)
- **First wiki-captured 4-stage practitioner-content register evolution timeline** (prompts → harnesses → loops → fleets-that-design-loops) with concrete 3-month escalation prediction
- **First wiki-captured Steinberger VISION.md primitive** — extends canonical content-template stack from 3-tier to 4-tier
- **First wiki-captured "loop with push-back primitive" framing** — direct articulation of [[trq-dynamic-workflows-harness-2026-06-02|self-preferential bias failure mode]] solution at loop-design layer
- **First wiki-captured 4-surface practitioner-content register cluster on Claude Code primitives** (Anthropic-internal + 2 Linas-synthesis + Steinberger practitioner-content)
- **Pairs with [[linas-cursor-revenue-per-employee-spacex-acquisition-rumor-2026-06-07|Linas's same-day Cursor playbook framing]]**: both surfaces from Jun 07 frame engineer-as-agent-manager rather than engineer-as-coder. Linas frames at the productivity-claim layer; Steinberger frames at the loop-design layer. **First wiki-captured 2-surface same-day practitioner-content register convergence on the engineer-role-shift framing**.

### Notably-absent (verification-pending)

- **Specific Steinberger VISION.md template / structure** — verification-pending; he didn't share the template
- **Specific Steinberger projects** that use VISION.md
- **Specific "fleets that design your loops" architecture** Steinberger predicts — pattern-watch for the Sept 2026 follow-up
- **Specific test / type-check / VISION.md combination patterns** Steinberger uses
- **Specific Steinberger pre-Claude-Code background** — broader context (he's notable in iOS / Swift community pre-AI)

## Pages Updated

- [[peter-steinberger]] — entity page **created** (pt3 ingest 2026-06-08) as 2nd substantive surface (this + same-day Van Horn synthesis quoting Steinberger 2.2M-view tweet). VISION.md primitive disclosure + Loop Engineering framing + skills-as-more-durable-half secondary thesis
- [[claude-md-pattern]] — VISION.md primitive added as 4th-tier extension of canonical content-template stack
- [[trq-dynamic-workflows-harness-2026-06-02]] — back-link as 1st surface in 4-surface practitioner-content register cluster
- [[linas-beliunas-claude-goal-guide-2026-05-14]] — back-link as same-cluster operator-synthesis
- [[linas-beliunas-dynamic-workflows-guide-2026-06-04]] — back-link as same-cluster operator-synthesis

## Adjacent sources

- [[mvanhorn-wtf-is-a-loop-2026-06-07]] — Van Horn's same-day comprehensive Loop Engineering synthesis essay; 5-stage lineage (ReAct → AutoGPT → ralph → /goal → orchestration loops); Cherny WorkOS Acquired Unplugged "I write loops now" framing; Steve Yegge Gas Town; roborev
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny's same-week 5-tip canonical recipe; Anthropic-internal-creator voice paired with Steinberger's practitioner-content voice
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq's "A harness for every task" canonical Anthropic-internal framing
- [[linas-beliunas-claude-goal-guide-2026-05-14]] — Linas's `/goal` operator-synthesis
- [[linas-beliunas-dynamic-workflows-guide-2026-06-04]] — Linas's Dynamic Workflows operator-synthesis
- [[linas-cursor-revenue-per-employee-spacex-acquisition-rumor-2026-06-07]] — same-day Linas Cursor playbook (engineer-role-shift convergence)
- [[anthropic-institute-when-ai-builds-itself-2026-06-04]] — Anthropic Institute "5-stage human-role-narrowing progression"
- [[loop-engineering]] — concept page consolidating the Loop Engineering discourse

## Verification-pending

- Specific Steinberger VISION.md template structure
- Steinberger projects that use VISION.md
- "Fleets that design your loops" architecture specifics (3-month-out prediction)
- Steinberger's broader iOS / Swift / pre-Claude-Code background
- Whether [[peter-steinberger]] entity page exists; if so, this surface count + Notable Take update
