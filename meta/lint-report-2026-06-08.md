---
type: meta
title: "Lint Report 2026-06-08"
created: 2026-06-08
updated: 2026-06-08
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-08

## Summary

- **Pages scanned**: 458 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`; includes 2 ephemeral `Untitled*.md` at vault root that should be deleted)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0** (all 7 listed are meta files or path-form-resolved owner pages)
- **Real fixable dead-links**: **3 entity pages now past 2-surface threshold** (junyang-lin, nando-de-freitas, dan-jeffries) + **1 typo regression** (`claude-opus-4-6` → `claude-opus-4-7` or `claude-opus-4-8`)
- **Unprocessed `_raw/` drops** (since last lint, 2026-06-06): **4** flagged for owner review
- **Pre-lint discipline**: `git fetch origin` → `git pull` confirmed at PR-85-merged tip (`5e2d573`); no open PRs

**Wiki health is excellent.** Structural metrics (orphans / frontmatter / stale) all 0. Three same-week-pattern entity-page candidates have crossed the 2-surface threshold via the June 6 RSI / world-models / Hassabis-AGI ingest cluster.

### Net delta vs `lint-report-2026-06-06` (48 hours, 3 PRs landed — pt1 / pt2 / pt3 ingests of 2026-06-08)

| Metric | 2026-06-06 | 2026-06-08 | Δ |
|---|---|---|---|
| Total pages | 451 | **458** | +7 (8 source pages + 5 entity pages + 2 concept pages from pt1+pt2+pt3 minus existing-page-edits) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Unique dead-link targets (real) | 24 (with 6 fixable) | **~15** (real) | net improvement after typo fixes from last lint |

## Orphan Pages

**0 real orphans.** The 7 candidates surfaced by the no-inbound-link check are all expected:

| Slug | Why exempt |
|---|---|
| `CLAUDE` | Meta file (CLAUDE.md is the project schema; not a wiki page) |
| `log` | Meta file (log.md is the append-only operations log) |
| `README` | Meta file (vault README) |
| `profile` | Lives at `owner/profile.md`; refs use the path-form `[[owner/profile]]` per CLAUDE.md convention |
| `publications` | Lives at `owner/publications.md`; refs use the path-form `[[owner/publications]]` per CLAUDE.md convention |
| `Untitled` | Ephemeral cruft at vault root — **recommend deletion** |
| `Untitled 1` | Ephemeral cruft at vault root — **recommend deletion** |

## Frontmatter Gaps

**0 issues.** All 23 tool pages, 4 model pages, 33 concept pages, 63 people pages, 35 company pages, and 277 source pages have all required frontmatter fields.

## Stale `last_updated` (tools/models)

**0 issues.** Today is 2026-06-08; 60-day threshold is 2026-04-09. All tool/model pages have `last_updated >= 2026-04-21`. Distribution skew: 6 tool pages last touched 2026-04-21 (initial wave: crewai/llama-index/mem0/obsidian/obsidian-dataview/ollama) are within the window but approaching the wall — flag for refresh check around 2026-06-15.

## Sources Missing "Pages Updated"

5 daily-brief roundup sources skip the `## Pages Updated` section, which is intentional given their non-headline-aggregate nature:
- `sources/dailybrief-roundup-2026-06-03.md`
- `sources/dailybrief-roundup-2026-06-04.md`
- `sources/dailybrief-roundup-2026-06-05.md`
- `sources/dailybrief-roundup-2026-06-06.md`
- `sources/dailybrief-roundup-2026-06-07.md`

Not flagged as issues — these are aggregator-pattern sources that catalog items without entity-updates; the per-item updates are handled in companion focused source pages.

## Dead Links

### Past 2-surface threshold — entity pages worth creating (3 unique / 24 occurrences) — REAL FIXABLE

The June 6 RSI / world-models / Hassabis-AGI ingest cluster cross-referenced these 3 figures across multiple substantive source pages + concept pages. All have grown well past the 2-surface threshold since the last lint.

| Target | Refs | Substantive surfaces | Recommended action |
|---|---|---|---|
| `[[junyang-lin]]` | 9 files | (a) own source [[junyang-lin-new-lab-world-models-rsi-2026-06-06]] (lab-founding event) + (b) [[concepts/world-models]] (5th wiki-tracked world-model lab anchor) + (c) [[concepts/recursive-self-improvement]] (constructive response to Jeffries-LeCun Time-Multiplicity critique) + (d) [[sources/businessinsider-hassabis-agi-2030-stanford-2026-06-04]] (4-position singularity-timeline cluster) + (e) [[sources/biohub-protein-biology-world-model-2026-06-06]] (2-event same-day world-models-cluster) + (f) [[sources/linas-cursor-revenue-per-employee-spacex-acquisition-rumor-2026-06-07]] (engineer-role-shift convergence) + (g) [[sources/dailybrief-roundup-2026-06-07]]. **Create `people/junyang-lin.md`** — ex-Alibaba Qwen lead; founded new lab on world-models + RSI; first wiki-captured ex-Chinese-frontier-lab-lead → new-lab founding event. |
| `[[nando-de-freitas]]` | 7 files | (a) own source [[sources/nando-de-freitas-unified-causal-agent-training-2026-06-06]] (Microsoft AI VP post-training proposal) + (b) [[concepts/end-of-finetuning]] (structurally extends thesis) + (c) [[concepts/recursive-self-improvement]] (3-vendor 4-day post-training-methodology debate cluster) + (d) [[sources/junyang-lin-new-lab-world-models-rsi-2026-06-06]] (cluster cross-ref) + (e) [[sources/dailybrief-roundup-2026-06-07]]. **Create `people/nando-de-freitas.md`** — Microsoft VP of AI; first wiki-captured Microsoft-AI-VP-side post-training-methodology proposal; 3-vendor cluster with Anthropic skill-discipline + NVIDIA multi-teacher distillation. |
| `[[dan-jeffries]]` | 8 files | (a) own source [[sources/dan-jeffries-rsi-time-multiplicity-critique-2026-06-04]] (Time-Multiplicity bottleneck critique) + (b) [[people/yann-lecun]] (LeCun-aligned skepticism) + (c) [[concepts/recursive-self-improvement]] (RSI skepticism corner) + (d) [[sources/nando-de-freitas-unified-causal-agent-training-2026-06-06]] (cluster cross-ref) + (e) [[sources/junyang-lin-new-lab-world-models-rsi-2026-06-06]] (cluster cross-ref) + (f) [[sources/businessinsider-hassabis-agi-2030-stanford-2026-06-04]] (4-position singularity-timeline cluster). **Was flagged as defer at single-source threshold in last lint** (only 1 file then); grew to 8 files in 48 hours via the RSI cluster. **Create `people/dan-jeffries.md`** — independent practitioner-content voice; Jeffries-LeCun-aligned RSI Time-Multiplicity skepticism; load-bearing 4-position singularity-timeline cluster corner. |

### Typo regression (1 unique / 1 occurrence) — REAL FIXABLE

| Wrong slug | Correct slug | File | Note |
|---|---|---|---|
| `[[claude-opus-4-6]]` | `[[claude-opus-4-7]]` or `[[claude-opus-4-8]]` (verify context) | log.md | Historical log entry; verify which generation was meant. Was Opus 4.6 announced? Per existing wiki: no `models/claude-opus-4-6.md` exists. Likely typo for 4.7 (Claude Code's default through May 27 2026 per `tools/claude-code.md`). Single-occurrence; low priority since it's in an archival log entry. |

### Borderline candidates (3 unique / ~13 occurrences) — judgment call

| Target | Refs | Substantive surfaces | Recommendation |
|---|---|---|---|
| `[[biohub]]` | 5 files | (a) own source [[sources/biohub-protein-biology-world-model-2026-06-06]] (protein-biology world-model launch) + (b) [[concepts/world-models]] + (c) [[concepts/recursive-self-improvement]] | Borderline. Most refs are intra-cluster cross-references rather than independent surface-events. **Defer until 2nd substantive Biohub event** (e.g., follow-up release, public statement, partnership). |
| `[[kasra]]` | 6 files | (a) own source [[sources/kasra-llm-pentester-1500-experiment-2026-06-04]] + (b) [[sources/openai-lockdown-mode-prompt-injection-2026-06-06]] + (c) [[topics/ai-roi-gap]] + (d) [[concepts/ai-vulnerability-discovery]] | At threshold (2-3 substantive surfaces beyond own source). **Recommend create at owner discretion**: independent blogger; LLM-pentester $1500 experiment + ROI-gap-corner + vuln-discovery taxonomy. Slug only `kasra` is too generic — would need fuller name; verification-pending. |
| `[[charity-majors]]` | 3 files | (a) [[sources/willison-charity-majors-enthusiasts-skeptics-2026-06-04]] + (b) [[people/simon-willison]] Notable Take | 2 substantive surfaces but currently a Willison-quoted-figure pattern. **Defer until 2nd primary substantive surface** (i.e., something not surfaced via Willison). |

### Single-source deferred per ingest commits (5 unique / 8 occurrences) — no action

Carry-over single-source defers from prior ingest commits. Conservative entity-creation policy.

| Target | Refs | Status |
|---|---|---|
| `[[alex-imas]]` | 2 | Defer — Dwarkesh co-guest |
| `[[phil-trammell]]` | 2 | Defer — Dwarkesh co-guest |
| `[[emanuel-maiberg]]` | 1 | Defer — 404 Media journalist |
| `[[elon-musk]]` | 1 | Defer — single ref in companies/spacex.md; surprisingly low for a figure of his profile, but the wiki tracks Musk-adjacent entities (SpaceX, xAI) rather than Musk-the-person |

### Intentional / false positives (~14 occurrences) — no action

Unchanged structural patterns:

- `[[claude]]`, `[[claude-opus-4-6]]`, `[[concept]]` in log.md historical entries
- `[[Daily Briefs/2026-05-10-personal.md]]` + 5× `[[Daily Briefs/2026-06-0X.md]]` refs in log.md for dedup-discipline (intentional)
- `[[LLM Wiki Pattern]]` in CLAUDE.md:312 (teaching example display-form)
- `[[wikilink]]`, `[[Page Name]]` in tools/obsidian.md (backticked code examples)
- `[[agi-debate.canvas]]` in index.md (Canvas file exists; lint scanner is markdown-only)
- `[[meta/lint-report-2026-05-11]]` reference in prior lint report (archival self-reference)

## Unprocessed `_raw/` Drops

**4 drops landed in `_raw/` since the last lint (2026-06-06) that have not been ingested:**

| File | Source | Description | Recommended disposition |
|---|---|---|---|
| `_raw/Post by @0xchromium on X.md` | x.com/0xchromium 2026-06-04 | **Karpathy 2h-day-to-day video reference** (Tinker Spotlight) — *"Andrej Karpathy spent 2h showing how he actually uses AI day to day"* | Likely worth ingesting; pairs with existing Karpathy entity surface + agentic-engineering concept page |
| `_raw/How to Build Claude Workflows That Run Without You.md` | x.com/0xchromium 2026-06-04 | **0xchromium Claude Workflows practitioner-content guide**; pairs structurally with Khairallah Claude Projects (pt2) + Steinberger Loops (pt2) + bcherny 5-tips (pt3) at the practitioner-content register layer | Strong ingest candidate; possible 4th 2026-06-08 ingest |
| `_raw/Post by @rohanpaul_ai on X.md` | x.com/rohanpaul_ai 2026-06-07 | **MIT study**: code volume +300%, output +30%; autonomous agents +180% commits but only +30% releases. AI-ROI-gap evidence | Strong ingest candidate; load-bearing for [[topics/ai-roi-gap]] |
| `_raw/Post by @rohanpaul_ai on X 1.md` | x.com/rohanpaul_ai 2026-06-07 | **FT piece**: AI raising software supply faster than demand; companion to MIT study above | Strong ingest candidate; FT primary; pairs with MIT study as 2-surface same-day AI-ROI-gap evidence cluster |

**Net signal**: a 4th 2026-06-08 ingest (`ingest/2026-06-08-pt4`) covering these 4 drops would close the loop on the AI-ROI-gap + practitioner-content register clusters this week.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅ PR #85 merge fetched (`4c1ef4b..5e2d573`)
2. `git pull --ff-only` → ✅ local main at `5e2d573`
3. `gh pr list --state open` → ✅ empty
4. **Lint branch**: `lint/2026-06-08`

## Recommended Fixes

### Required (1 typo)
1. `[[claude-opus-4-6]]` → `[[claude-opus-4-7]]` (or 4.8 depending on context) in log.md historical entry

### Optional (3 entity-page creations — judgment calls past 2-surface threshold)
1. **Create `people/junyang-lin.md`** — closes 9 dead-link refs (highest leverage); ex-Alibaba Qwen lead; new lab on world-models + RSI
2. **Create `people/nando-de-freitas.md`** — closes 7 dead-link refs; Microsoft VP of AI; unified causal-agent training proposal
3. **Create `people/dan-jeffries.md`** — closes 8 dead-link refs; independent voice; Jeffries-LeCun-aligned RSI Time-Multiplicity skepticism

### Optional (housekeeping)
1. **Delete `Untitled.md` + `Untitled 1.md`** at vault root (ephemeral cruft, currently untracked)
2. **Process 4 unprocessed `_raw/` drops** as a pt4 ingest (0xchromium ×2 + rohanpaul_ai ×2)

## Overall Posture

The wiki is in **excellent shape**. Structural health (orphans / frontmatter / stale `last_updated`) is structurally zero. The +7-page delta from the 3 pt-ingests this week landed cleanly with no new typo regressions in this batch.

**The June 6 RSI / world-models / Hassabis-AGI ingest cluster has produced 3 new entity-page candidates past 2-surface threshold** (junyang-lin / nando-de-freitas / dan-jeffries) — all three are load-bearing in the wiki's frontier-AI timeline-calibration + RSI / post-training-methodology debate clusters. Creating all 3 closes 24 dead-link refs (the largest single available reduction since the spacex / sriram-krishnan creations in last lint).

The unprocessed `_raw/` drops (0xchromium Karpathy + 0xchromium Workflows + 2× rohanpaul_ai AI-ROI-gap evidence) suggest a pt4 ingest is warranted today.

## Applied Fixes (2026-06-08)

Per owner review, applied 3 of the recommended fixes (the 3 entity-page creations). Skipped per owner discretion: claude-opus-4-6 typo fix, Untitled.md deletion, pt4 ingest of 4 unprocessed _raw drops (deferred).

1. ✅ **Created `people/junyang-lin.md`** — ex-Alibaba Qwen team lead; new lab on world-models + RSI intersection; world-models-as-bridge constructive response to Jeffries-LeCun Time-Multiplicity critique; 5th wiki-captured world-model lab. Closes 9 dead-link refs.
2. ✅ **Created `people/nando-de-freitas.md`** — Microsoft VP of AI (ex-DeepMind RL lead); unified continual interactive causal-agent training proposal; 3rd-vendor entrant in 3-vendor 4-day post-training-methodology debate cluster. Closes 7 dead-link refs.
3. ✅ **Created `people/dan-jeffries.md`** — independent AI-skepticism voice; Time + Multiplicity bottleneck framing for RSI; LeCun-amplified critique of Anthropic Institute publication. Closes 8 dead-link refs.
4. ✅ **Updated `index.md`** with 3 new entries under People & Voices.

**Post-fix dead-link count**: ~24 → ~0 unique-fixable targets (the 3 entity pages close 24 occurrences across the cluster). Pages: 458 → 461. Remaining dead-links are all in the intentional / single-source-deferred / borderline-candidate categories per the analysis above.

**Deferred to owner**:
- `[[claude-opus-4-6]]` log.md typo fix — pending owner check of correct generation
- `Untitled.md` + `Untitled 1.md` deletion at vault root — pending owner decision
- pt4 ingest of 4 unprocessed `_raw/` drops (0xchromium Karpathy + 0xchromium Workflows + 2× rohanpaul_ai) — flagged for next session

