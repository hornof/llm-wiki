---
name: Developer Productivity Measurement
type: concept
maturity: foundational
last_updated: 2026-09-17
---

## Definition

The practice of measuring engineering output, effectiveness and quality at the team and organization level — and the twenty-year argument about whether it can be done without causing more damage than it prevents. The lineage runs **DORA → SPACE → DevEx → [[dx-core-4-framework-2024-12|DX Core 4]]**, each adding a dimension the previous one lacked.

## Why It Matters

This page exists because of a gap the wiki opened in September 2026. Within eight days it captured three claims about AI-written code — **80%** of Anthropic's, **8×** more output per engineer, **98%** "not handwritten" at a services firm — and **not one of them carried a quality, defect or review-burden number**. The replies to each asked for exactly that and got nothing.

The field had already solved this. The frameworks below are the vocabulary for reading those claims, and the reason a throughput number alone is not evidence of anything. For the wiki owner specifically, this is also the measurement language an engineering-leadership conversation is conducted in.

## The lineage

| Framework | Contribution | Limitation |
|---|---|---|
| **DORA** (Forsgren et al.) | four prescriptive delivery metrics; deploy frequency, lead time, change failure rate, restore time | scoped to system performance |
| **SPACE** (Forsgren, Storey et al.) | five dimensions; establishes that productivity is multi-dimensional and not reducible to output | a framework for defining your own metrics — *"difficult to actually do"* |
| **DevEx** (Noda, Forsgren, Storey, Greiler) | developer experience as a first-class driver; flow, feedback loops, cognitive load | self-reported, isolated from broader productivity |
| **DX Core 4** (2024) | folds all three into one prescriptive set across four counterbalanced dimensions | vendor-authored; DXI is proprietary |

## DX Core 4 — the current synthesis

Four dimensions, each with a primary metric, deliberately opposed to one another ([[dx-core-4-framework-2024-12]]):

- **Speed** — diffs (or PRs) per engineer
- **Effectiveness** — Developer Experience Index (DXI), 14 Likert items
- **Quality** — **change failure rate**
- **Impact** — % of time spent on new capabilities

### The counterbalancing rule

The framework's actual content is not the metric list but the constraint on using it:

> *"It is critical that this metric is never used at the individual level or tied to performance evaluations. Additionally, it must be counterbalanced with other oppositional metrics."*

Three preconditions for using throughput at all: **counterbalance it, set no targets against it, and say publicly how it will be used.** The design premise is that *"changes to one dimension, such as speed, may negatively affect others"* — so a speed number reported alone is not a partial answer, it is a misleading one.

## Reading the 2026 agentic-coding claims against it

This is the point of the page. Map what the wiki actually holds onto the four dimensions:

| Dimension | What September 2026 supplied |
|---|---|
| **Speed** | abundant — 8× output per engineer, 80% of code, 98% not handwritten, "1.5 FTE where five sat" |
| **Effectiveness** | one hostile datapoint: a **six-voice convergence on rising cognitive load** — *"five threads to keep the AI busy… more mentally exhausted than I can remember in years"* ([[agentic-engineering]]) |
| **Quality** | **nothing.** No defect rate, no change failure rate, in any of the claims |
| **Impact** | **nothing**, though [[addyosmani-anthropic-80pct-code-ci-strain-2026-09-14|CI jobs up 25×]] is an *inverse* signal — effort moving toward keeping the lights on |

**Three of four dimensions are empty or negative, and the industry conversation is running entirely on the first.** That is precisely the failure mode DX Core 4 was built to prevent, restated at industry scale rather than team scale.

The honest counter: the AI-coding claims are marketing posts, not measurement programs, and it is unreasonable to expect a change-failure-rate figure in a tweet. True — but the wiki should then treat them as marketing, and the absence is what this page is for.

## Open questions

- **Do the frameworks survive agentic coding at all?** *Diffs per engineer* assumes a human authoring diffs. When 80% of merged lines are attributable to a model, does the metric measure the engineer, the harness, or the model's verbosity?
- **Does change failure rate become more or less useful?** It is the one dimension that does not care who wrote the code — arguably the most robust metric in the set under AI authorship, and the one nobody is publishing.
- **Does the CI-load signal deserve its own dimension?** [[loop-engineering|Verification cost scaling faster than output]] is not captured anywhere in Core 4.

## Related Concepts

- [[agentic-engineering]] — the quality bar these metrics would measure
- [[loop-engineering]] — verification cost as the emerging constraint
- [[ai-roi-gap]] — the same measurement problem at spend level rather than output level
- [[ai-labor-market-impacts]] — where the population-vs-workflow measurement distinction lives
- [[engineering-leadership-ai-era]] — who has to defend these numbers in a board meeting

## Resources

- [[dx-core-4-framework-2024-12]] — the framework, its counterbalancing rule, and its vendor caveats
