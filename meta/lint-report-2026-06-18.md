---
type: meta
title: "Lint Report 2026-06-18"
created: 2026-06-18
updated: 2026-06-18
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-18

## Summary

- **Pages scanned**: 542 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Real fixable**: **2 entity-page candidates past 2-surface threshold** (`charity-majors` 8 surfaces + `z-ai` 4 surfaces) + **2 wrong-slug regressions** (`[[concepts/skill-md]]` × 2 in recent ingests)
- **Unprocessed `_raw/` drops**: **0** net-new
- **Lint branch**: `lint/2026-06-18`

**Wiki health structurally excellent**. 0 orphans / 0 frontmatter gaps / 0 stale dates across 542 pages (+10 from prior lint). The **2026-06-18 + 2026-06-18-pt2 ingest sequence** (7 source pages + owner-profile + concept-extension over 1 day) landed cleanly with **2 entity-page candidates past 2-surface threshold** (Charity Majors STRUCTURALLY MAJOR with 8 substantive surfaces + Z.ai 4 substantive surfaces — both multi-lint carry-overs now actionable) and **2 wrong-slug regressions** (both `[[concepts/skill-md]]` in 2 new sources — pattern matches prior carry-over).

### Net delta vs `lint-report-2026-06-17`

| Metric | pt17 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 532 | **542** | +10 (3 entity pages from prior lint + 7 source pages from 2026-06-18 sequence + 1 lint report) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 0 | **2** (`[[concepts/skill-md]]` × 2) | +2 (carry-over pattern: backtick-quote needed in single-source defer references) |
| New entity-page candidates past 2-surface threshold | 3 (codex + openclaw + pleias; all created) | **2** (charity-majors + z-ai) | -1 |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Dead Links

### Past 2-surface threshold — entity pages worth creating (2 unique / ~12 occurrences) — REAL FIXABLE

| Target | Surfaces | Substantive references | Recommended action |
|---|---|---|---|
| `[[charity-majors]]` | **8** | (1) [[willison-charity-majors-enthusiasts-skeptics-2026-06-04]] — dedicated source page; (2) [[topics/ai-roi-gap]] — AI-ROI-gap topic context; (3) [[people/simon-willison]] — Willison continuous-amplification canonical-cadence; (4) [[levie-nadella-cognitive-loop-thread-2026-06-14]] — paired-Levie thread context; (5-7) [[dailybrief-roundup-2026-06-05]] + [[dailybrief-roundup-2026-06-06]] + [[dailybrief-roundup-2026-06-07]] — multi-day re-promotion cluster; (8) [[dailybrief-roundup-2026-06-18]] — Jun 17 substantive "code economics flipped by AI" canonical-direct-voice articulation (Willison-quoted) | **Create `people/charity-majors.md`** — **STRUCTURALLY MAJOR**: 8 substantive surfaces across multi-week cadence; multi-lint carry-over; canonical observability + engineering-discipline + AI-skeptic-tier voice; pattern-watch finally actionable. **First wiki-captured "code from scarce/precious to disposable/regenerable" canonical-economics-shift framing** (Jun 17 surface) confirms canonical-voice-tier surface. Closes ~8 dead-link refs |
| `[[z-ai]]` | **4** | (1) [[chinese-openweights-political-ai-jun-18-cluster-2026-06-18]] — GLM-5.2 (753B MoE MIT-license) + Q1 2027 Chinese-Fable-class challenge accepted; (2) [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14]] — Nadella frontier-ecosystem thesis open-weights context; (3) [[dailybrief-roundup-2026-06-13]] — earlier reference; (4) [[dailybrief-roundup-2026-06-18]] | **Create `companies/z-ai.md`** — Chinese open-weights AI vendor; **4 substantive surfaces** validates entity-page threshold; multi-lint carry-over now actionable. GLM-5.2 753B MoE MIT-license = canonical-anchor-model; Q1 2027 Chinese-Fable-class challenge accepted = canonical-international-AI-prediction-tier surface. Closes ~4 dead-link refs |

### Wrong-slug regression fixes — REAL FIXABLE (2 occurrences / 2 sources)

| Wrong | Correct | File | Note |
|---|---|---|---|
| `[[concepts/skill-md]]` | `` `[[concepts/skill-md]]` `` (backtick-quoted) | sources/movez-kimi-opus-300-agent-self-improving-loop-2026-06-18.md (line 113) + sources/hornof-knowledge-work-plugins-claude-cowork-2026-06-17.md (line 104) | **Carry-over wrong-slug regression** — no `concepts/skill-md.md` page exists (closest existing: `writing-claude-code-skills.md` tutorial). Backtick-quote per established convention (defer concept-page until 2nd substantive concept-focus surface). 2 occurrences in recent ingests |

### Single-source entity-page defers — new from 2026-06-18 + pt2 ingest sequence (~20 unique / ~20 occurrences) — no action

Conservative entity-creation policy applies (defer until 2nd substantive surface):

**From 2026-06-18 + pt2 ingests (~20 net-new)**:
- `[[0xMovez]]` (single source-page reference; capital-M slug case-normalization optional defer)
- `[[kimi-k2-6]]` / `[[kimi-k2]]` (single substantive 0xMovez surface)
- `[[noam-shazeer]]`, `[[gpt-5-4]]`, `[[life-sci-bench]]`, `[[dean-ball]]`, `[[thomas-dimson]]`, `[[in-the-weights]]`, `[[boston-childrens-hospital]]` (7 OpenAI cluster single-source surfaces)
- `[[glm-5-2]]`, `[[tsinghua-university]]`, `[[jie-tang]]`, `[[bernie-sanders]]`, `[[jd-vance]]` (5 Chinese-open-weights + political-AI cluster single-source surfaces)
- `[[joseph-krause]]`, `[[radical-ai]]`, `[[metr-hawk]]`, `[[ceo-bench]]`, `[[zlab-princeton]]`, `[[elastic]]`, `[[deductive-ai]]` (7 roundup-tier single-source surfaces)

### Pattern-watch escalation candidates (2-surface threshold partially met) — no action this lint

- `[[anthropic-public-record]]` (3 refs across 3 separate ingest cycles: Jun 16 + Jun 17 + Jun 18) — **3-cluster carry-over**; would benefit from section in `companies/anthropic.md` rather than dedicated entity-page; pattern-watch for next lint
- `[[openai-deployment-simulation]]` (2 refs across 2 separate ingest cycles: Jun 16 + Jun 18) — pattern-watch escalation; could fold into `companies/openai.md`
- `[[eric-siu]]` (2 refs but both from same single-author ingest cluster) — single-substantive-author defer continuing
- `[[samueljmcd]]` / `[[rahulgs]]` / `[[hanako]]` / `[[sydney-runkle]]` (2 refs each but all same-ingest-cycle) — single-substantive-author defer continuing

### Carry-over single-source entity-page defers from prior lints (~45 unique / ~45 occurrences) — no action

Carry-overs unchanged from [[meta/lint-report-2026-06-17|prior lint]]: deepmind, mistral, theker, qwen, microsoft, deepseek, kpmg, india, manus, llama, gemma, apple, cohere, amazon, trump, opik, evo, aria, extropic, biohub, kasra, dxc, allenai, lm-studio, minimax, moonshot-ai, gabriel-petersson, matt-clifford, mcpmatt-pocock (typo carry-over: should be `[[matt-pocock]]`), nick-frosst, omnigent, prometheus, rohan-paul, river-ai, sequent, spectnfa, tejas-kumar, tensorzero, theo-tabah, thepremiseofit, geoffrey-irving, guillaume-verdon, igor-babuschkin, jeremy-howard, lucianw, malay-hazarika, martin-alderson, phil-trammell, alex-imas, emanuel-maiberg, alok-bishoyi, 0xCodez, 0xwhrrari, aiedge, werner-kasselman, trustmodel-ai, tom-ballard, stratechery, simi, sayash-kapoor, salesforce, lore, karl-mehta, jia-bin-huang, hermes-agent, fin, brendon-burchard, ben-thompson, arvind-narayanan, alien-org, marc-benioff, cartesia, gergely-orosz, tomas-reimers, origin, bland, single-grain, single-brain, town, jack-smith, riley-brown, peter-yang, nick-vasilescu, amir-musich, kloss, ultracode-max, teknium, ralph-miller, brad-axen, builderbot, aaif, vercel, guillermo-rauch, eve, polypore, evan-klem, thibault-sottiaux, adam-cad, europe-2031-initiative, pentagon, ploy, bryant-chou, pierre-carl-langlais, pramaana-labs, xdof, shreya-shankar, ben-thompson, joshua-baer, capital-factory, ona

### Path-form persistent dead-links + false positives — no action

Unchanged from prior lints:
- Path-form trailing-backslash table-cell-escape artifacts (~30 occurrences) — false positives
- `[[meta/lint-report-2026-06-1{3,4,5,6,7}]]` + `[[meta/lint-report-2026-05-11]]` — EXIST path-form refs (false positives)
- `[[concepts/skill-md]]` / `[[concepts/agentic-coding]]` / `[[concepts/hallucination]]` — backtick-quoted historical-narrative-only (false positives; established convention)
- `[[claude-mythos-5]]` / `[[models/claude-mythos-5]]` / `[[anthropic-bun-zig-rust-port-2026-05]]` — backtick-quoted historical (multi-lint carry-overs)
- `[[claude-opus-4-6]]` / `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` — backtick-quoted historical (multi-lint carry-overs)
- `[[you-dont-need-100-hours-claude-7-setups]]` — backtick-quoted historical (fixed in prior lint)
- Teaching-example structural false positives (~14 occurrences)

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**. All recent _raw drops already-ingested or explicitly skipped per prior workflows.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-118-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-18`

## Recommended Fixes

### Required (2 entity-page creations past 2-surface threshold + 2 wrong-slug regression-fixes)

1. **Create `people/charity-majors.md`** — **STRUCTURALLY MAJOR**: 8 substantive surfaces across multi-week cadence; canonical observability + engineering-discipline + AI-skeptic-tier voice; multi-lint carry-over pattern-watch finally actionable. Closes ~8 dead-link refs.
2. **Create `companies/z-ai.md`** — Chinese open-weights AI vendor; 4 substantive surfaces validates entity-page threshold; multi-lint carry-over now actionable. Closes ~4 dead-link refs.
3. **Backtick-quote `[[concepts/skill-md]]`** in `sources/movez-kimi-opus-300-agent-self-improving-loop-2026-06-18.md` (line 113) and `sources/hornof-knowledge-work-plugins-claude-cowork-2026-06-17.md` (line 104) — 2 occurrences; carry-over wrong-slug-regression pattern per established convention

### Optional (pattern-watch flags for next lint)

- `[[anthropic-public-record]]` 3rd-cluster-carry-over (3 refs); fold into `companies/anthropic.md` section
- `[[openai-deployment-simulation]]` 2-cluster pattern-watch; fold into `companies/openai.md` section
- `[[eric-siu]]` 2nd substantive surface watch (Single Brain product follow-up)
- `[[samueljmcd]]` + `[[rahulgs]]` + `[[hanako]]` + `[[sydney-runkle]]` + `[[brad-axen]]` + `[[builderbot]]` 2nd substantive surfaces pattern-watch (single-substantive-author defer continuing)
- Carry-over: `[[matt-clifford]]` + `[[gabriel-petersson]]` + `[[kpmg]]` + `[[india]]` + `[[manus]]` + Chinese-open-weight-vendor cluster (minimax + moonshot-ai now contextualized by Z.ai threshold being met)
- Carry-over typo: `[[mcpmatt-pocock]]` → `[[matt-pocock]]`
- `[[0xMovez]]` capital-M slug case-normalization → `[[0xmovez]]` (low-priority single-occurrence)

## Overall Posture

Wiki health structurally excellent. The **2026-06-18 + 2026-06-18-pt2 ingest sequence** (7 source pages + owner-profile + concept-extension in 1 day; **MASSIVE ingest day**) landed cleanly with **2 entity-page candidates past 2-surface threshold** (Charity Majors STRUCTURALLY MAJOR + Z.ai both multi-lint-carry-over candidates now actionable) and **2 wrong-slug regressions** (both `[[concepts/skill-md]]` carry-over pattern).

**Major narrative tracking now established**:
- **21-narrative-event 15-day Anthropic-USG-conflict crisis cluster** continues as most-load-bearing wiki-tracked governance event of 2026-Q2
- **12-voice Loop-Engineering canonical-cluster** with Block Builderbot as production-scale firm-tier proof-point + 0xMovez as operator-tier-2-model-split-RSI-discipline tier
- **STRUCTURALLY MASSIVE 5-day 11-event Loop-Engineering canonical-cluster** spans Jun 13-18 (Hanako + McDonald + Zodchii + Greg Isenberg + Rahul GS + Cherny + Sydney Runkle + Block Builderbot + Anthropic Artifacts + 0xMovez + Hornof + 5-author roundup)
- **First wiki-captured 2-vendor 1-day vendor-side "convert work into reusable skills" canonical-cluster** (Anthropic Artifacts Jun 18 + OpenAI Codex Record/Replay Jun 18) = STRUCTURALLY MAJOR canonical-pattern-convergence at vendor-side feature-tier
- **First wiki-captured 7-event same-day OpenAI canonical-velocity-cluster + "OpenAI pre-IPO talent-and-product velocity-cluster" canonical-pattern**
- **First wiki-captured 3-voice canonical-international-AI-prediction-cluster** (Musk + Tsinghua Jie Tang + Z.ai accepts Q1 2027 Chinese-Fable-class challenge)
- **First wiki-captured 2-political-voice cross-party canonical-equity-stake-or-mandate-discourse cluster** + **Trump-admin 3-tier political-AI canonical-positioning cluster**

**Tracking for next lint**:
- Pattern-watches per above
- Continued slug-discipline (2 new `[[concepts/skill-md]]` regressions show carry-over pattern is real — need pre-commit canonical-slug check)
- Continued conservative entity-creation policy
