---
title: "AnatoliKopadze (2nd substantive surface) — 'Loops explained: Claude, GPT, Mira and what actually works' — canonical 5-stage DISCOVER-PLAN-EXECUTE-VERIFY-ITERATE + 'verify is the heart of the loop' + 'state is what makes the loop learn' + 'stop condition is what keeps it sane' (2026-06-21)"
type: source
medium: twitter-thread
url: https://x.com/AnatoliKopadze/status/2068328135611822149
ingested: 2026-06-21
---

## Summary

**AnatoliKopadze (@AnatoliKopadze)** publishes (2026-06-20 original; cross-device-clipped 2026-06-21; saved as `_raw/Loops explained Claude, GPT, Mira and what actually works.md`) **"Loops explained: Claude, GPT, Mira and what actually works"** — practitioner-tier comprehensive Loop Engineering canonical-introduction. **2nd substantive AnatoliKopadze surface** (extends [[practitioner-claude-settings-features-cluster-2026-06-20|May 22 "Claude Can Do All of This"]] — entity-page threshold now met). **First wiki-captured AnatoliKopadze "Loops explained" canonical-Loop-Engineering-introduction surface**. **First wiki-captured 5-stage canonical-loop-articulation** (DISCOVER → PLAN → EXECUTE → VERIFY → ITERATE). **First wiki-captured "verify is the heart of the loop" + "state is what makes the loop learn" + "stop condition is what keeps it sane" canonical-3-pillar Loop-Engineering-discipline articulation**. **First wiki-captured "AI has been in everyone's hands for years. Most people who use it every day still use it the slowest way there is" canonical-AnatoliKopadze-opening framing**. **"Mira" is a promoted [[mira|Telegram no-code agent product]] — NOT a model** (record corrected 2026-07-12 from the fuller re-clip; the article's back half is a Mira ad). **AnatoliKopadze 2nd substantive surface = entity-page threshold met** = pattern-watch escalation for next lint. Pairs structurally with [[0xcodez-14-step-loop-engineering-roadmap-2026-06-20|0xCodez Jun 20 14-step canonical-roadmap]] + [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald verifier-discipline-first canonical-corrective]] + [[hanako|Hanako practitioner-tier canonical-voice]] at the **canonical practitioner-tier Loop-Engineering canonical-cluster** layer.

## Key Claims / Takeaways

### The canonical 5-stage loop-articulation

```
DISCOVER  →  work out what needs doing
PLAN      →  decide how to do it
EXECUTE   →  do the work
VERIFY    →  check it against the goal
ITERATE   →  not there yet? feed the result back in and repeat
```

**First wiki-captured 5-stage canonical-loop-articulation** (DISCOVER + PLAN + EXECUTE + VERIFY + ITERATE) at AnatoliKopadze practitioner-content-register tier. Pairs structurally with:
- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald 5-stage canonical-loop-articulation]] — paired 5-stage canonical-articulation
- [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn 5-stage canonical-Loop-Engineering-lineage]] — paired 5-stage canonical-articulation
- [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17|Sydney Runkle LangChain 4-layer]] — paired canonical-loop-articulation

### 3-pillar canonical Loop-Engineering-discipline articulation

> *"Three of these five do all the real work, and they are where people get loops wrong."*

| Pillar | Canonical-articulation |
|---|---|
| **Verify is the heart of the loop** | *"Without a real check on the result, you do not have a loop, you have the agent agreeing with itself on repeat. The check is what turns repetition into progress. It can be a hard test ('does the code pass'), a measurable condition ('is the number above X'), or a rubric the model scores against. No gate means the agent grades its own homework, and the model that did the work is far too generous a grader."* |
| **State is what makes the loop learn** | *"Each pass, the AI has to remember what it already tried, or it repeats the same mistake forever. A real loop keeps a small record on the side: what is done, what failed, what is next. Tomorrow's run resumes instead of starting from zero."* |
| **A stop condition is what keeps it sane** | *"A loop with no exit runs until it succeeds, breaks, or drains your account. Every serious loop has two ways to stop: success, and a hard limit ('after 8 tries, stop and report'). Skip this and you have built a machine that can run all night for nothing."* |

**First wiki-captured "verify is the heart of the loop" canonical-Loop-Engineering canonical-discipline articulation**. **First wiki-captured "state is what makes the loop learn" canonical-Loop-Engineering canonical-discipline articulation**. **First wiki-captured "a stop condition is what keeps it sane" canonical-Loop-Engineering canonical-discipline articulation**. **First wiki-captured 3-pillar canonical Loop-Engineering-discipline articulation** — extends [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald verifier-discipline-first canonical-corrective]] from canonical-2-pillar (generator + verifier) to canonical-3-pillar (verify + state + stop) discipline articulation.

### "A prompt vs a loop" canonical-distinction

> *"A prompt is a single instruction. A loop is a goal the AI keeps working toward until it gets there."*
> *"A prompt gives you one answer and then waits for you to decide what is next. A loop runs the full cycle on its own."*

**First wiki-captured "a prompt vs a loop" canonical-distinction articulation**: prompt = single-instruction + waits-for-next-decision; loop = goal + full-cycle-on-its-own.

**Closing canonical-distinction**:
> *"A prompt hands the AI an instruction. A loop hands the AI a job, a way to know when the job is done, and a rule for when to give up."*

**First wiki-captured "loop = job + way-to-know-when-done + rule-for-when-to-give-up" canonical-3-component canonical-loop-definition**.

### 4-condition canonical-test (paired with 0xCodez)

AnatoliKopadze articulates same 4-condition canonical-test as [[0xcodez-14-step-loop-engineering-roadmap-2026-06-20|0xCodez Jun 20 14-step roadmap]]:

> *"A loop is worth building only when all four of these are true:*
> - *The task repeats, at least weekly.*
> - *Something can automatically reject bad output.*
> - *The agent can actually do the work itself, end to end.*
> - *'Done' is objective, not a judgment call."*

> *"Miss one box, keep it as a manual prompt. The honest version of this whole topic: loop engineering is real, and most people do not need the heavy version yet. **What everyone can use is the light version, which we will get to.** But you should know where the line is."*

**First wiki-captured 2-voice 4-condition canonical-test convergence cluster** (0xCodez + AnatoliKopadze, both within 1-day cadence). **First wiki-captured "loop engineering is real, and most people do not need the heavy version yet" canonical-discipline articulation (AnatoliKopadze variant)** — pairs with 0xCodez canonical-"don't need it yet" framing.

### "The version built for code" canonical-LOOP-SPEC articulation

```
▸ LOOP SPEC
GOAL: every test in /tests/auth passes, lint is clean, no type errors.

EACH ITERATION:
  1. run the test suite and read every failure
  2. pick the single highest-impact failure
  3. write the smallest change that fixes it
  4. re-run the tests, lint, and type checker

VERIFY: green tests + zero lint warnings + zero type errors
STOP WHEN: verify passes, OR 8 iterations reached
ON STOP: summarize what changed and what still fails
```

**First wiki-captured canonical-LOOP-SPEC-template articulation** (GOAL + EACH ITERATION + VERIFY + STOP WHEN + ON STOP). Pairs structurally with [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18|0xMovez canonical-spec-template]] (GOAL + SCOPE + RULES + SOURCES + OUTPUT + ON CONFLICT + STOP CONDITION) at the **canonical-spec-template canonical-discipline cluster** layer.

### "Claude Code and Codex now ship all five" canonical-anchor

> *"Under the hood, a real loop is assembled from five building blocks. Claude Code and Codex now ship all five."*

**First wiki-captured "Claude Code and Codex now ship all five [building blocks]" canonical-vendor-equivalence anchor** — pairs structurally with [[codex|Codex Jun 17 open-source-model-routing canonical-event]] at the **canonical-AI-coding-product canonical-vendor-equivalence canonical-positioning** layer. The article's closing section reveals **"Mira" is a [[mira|Telegram no-code agent product]]** (Composio-connected, model-agnostic, "Skills" = loops) that the piece promotes — not a model, as the title's "Claude, GPT, Mira" phrasing first suggested.

### Cross-cutting framings

- **AnatoliKopadze 2nd substantive surface = entity-page threshold met** (pattern-watch escalation for next lint)
- **First wiki-captured AnatoliKopadze "Loops explained" canonical-Loop-Engineering-introduction surface**
- **First wiki-captured 5-stage canonical-loop-articulation** (DISCOVER + PLAN + EXECUTE + VERIFY + ITERATE)
- **First wiki-captured 3-pillar canonical Loop-Engineering-discipline articulation** (verify + state + stop) — extends McDonald canonical-2-pillar to canonical-3-pillar
- **First wiki-captured "verify is the heart of the loop" canonical-articulation**
- **First wiki-captured "state is what makes the loop learn" canonical-articulation**
- **First wiki-captured "a stop condition is what keeps it sane" canonical-articulation**
- **First wiki-captured "a prompt vs a loop" canonical-distinction articulation**
- **First wiki-captured "loop = job + way-to-know-when-done + rule-for-when-to-give-up" canonical-3-component canonical-loop-definition**
- **First wiki-captured 2-voice 4-condition canonical-test convergence cluster** (0xCodez + AnatoliKopadze, 1-day cadence)
- **First wiki-captured canonical-LOOP-SPEC-template articulation** (GOAL + EACH ITERATION + VERIFY + STOP WHEN + ON STOP)
- **First wiki-captured "Claude Code and Codex now ship all five [building blocks]" canonical-vendor-equivalence anchor**
- **"Mira" identified as a promoted [[mira|Telegram no-code agent product]]** (corrected 2026-07-12; earlier clip truncated before the reveal and the wiki provisionally read it as a model)
- **First wiki-captured "the agent grades its own homework, and the model that did the work is far too generous a grader" canonical-failure-mode framing**
- **First wiki-captured "AI has been in everyone's hands for years. Most people who use it every day still use it the slowest way there is" canonical-opening framing**

## Pages Updated

- [[anatoli-kopadze]] — 2nd substantive surface added (entity-page threshold met; pattern-watch escalation for next lint)
- [[concepts/loop-engineering]] — 5-stage canonical-loop-articulation + 3-pillar canonical-discipline articulation
- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15]] — paired canonical-3-pillar extension from McDonald canonical-2-pillar
- [[0xcodez-14-step-loop-engineering-roadmap-2026-06-20]] — paired 2-voice 4-condition canonical-test convergence cluster (0xCodez + AnatoliKopadze)
- [[mvanhorn-wtf-is-a-loop-2026-06-07]] — paired 5-stage canonical-Loop-Engineering-lineage
- [[hanako]] — paired practitioner-tier canonical-voice
- [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18]] — paired canonical-spec-template canonical-discipline cluster
- [[codex]] — paired canonical-AI-coding-product canonical-vendor-equivalence canonical-positioning ("Claude Code and Codex now ship all five [building blocks]")
- [[claude-code]] — paired canonical-vendor-equivalence canonical-positioning
- [[mira]] — created 2026-07-12 as a Telegram no-code agent product (Composio-connected, model-agnostic, "Skills" = loops); `emerging`, single-promotional-source caveat. Corrects the earlier model-attribution guess.
- [[practitioner-claude-settings-features-cluster-2026-06-20]] — paired 1st substantive AnatoliKopadze surface (May 22 "Claude Can Do All of This")

## Adjacent sources

- [[0xcodez-14-step-loop-engineering-roadmap-2026-06-20]] — paired Jun 20 14-step canonical-roadmap (2-voice 4-condition canonical-test cluster)
- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15]] — McDonald verifier-discipline-first canonical-corrective
- [[zodchii-builder-checker-looping-team-2026-06-16]] — Zodchii looping-team practitioner-tier
- [[hanako]] — Hanako practitioner-tier canonical-voice
- [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18]] — 0xMovez canonical-playbook
- [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]] — Sydney Runkle LangChain 4-layer
- [[mvanhorn-wtf-is-a-loop-2026-06-07]] — Van Horn 5-stage canonical-lineage
- [[practitioner-claude-settings-features-cluster-2026-06-20]] — 1st substantive AnatoliKopadze surface
- [[karpathy-loopcraft-stacking-loops-2026-06-12]] — Karpathy loopcraft canonical-naming

## Verification-pending

- Specific AnatoliKopadze canonical-voice-tier background
- ~~Specific "Mira" canonical-model attribution~~ **RESOLVED 2026-07-12**: Mira is a [[mira|Telegram no-code agent product]], not a model (Composio 500+ apps, model-agnostic, "Skills" = loops). Remaining: independent corroboration of Mira's traction (sole source is promotional).
- Specific full canonical-AnatoliKopadze-thread-content beyond captured intro
- Specific "light version" canonical-articulation (mentioned but not fully captured)
- Specific "what everyone can use" canonical-light-version canonical-articulation
- Specific AnatoliKopadze Telegram canonical-cadence + canonical-community-size
