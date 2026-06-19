---
type: meta
title: "Lint Report 2026-06-19"
created: 2026-06-19
updated: 2026-06-19
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-19

## Summary

- **Pages scanned**: 547 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Real fixable**: **1 entity-page update** ([[people/nathan-lambert]] Jun 19 surface added) + **0 wrong-slug regressions** (slug-discipline holding!)
- **Unprocessed `_raw/` drops**: **0** net-new
- **Lint branch**: `lint/2026-06-19`

**Wiki health structurally excellent**. 547 pages scanned (+5 from prior lint). 0 orphans / 0 frontmatter gaps / 0 stale dates / **0 wrong-slug regressions** — slug-discipline lessons from prior lints holding. The **2026-06-19 + 2026-06-19-pt2 ingest sequence** (3 source pages across 1 day) landed cleanly with **no new entity-page candidates past 2-surface threshold** — most new single-source entity-page candidates (slime + zhipu-ai + thudm + will-brown + schmidhuber + andreas-kirsch + harvey + asml + etc.) defer per conservative policy.

### Net delta vs `lint-report-2026-06-18`

| Metric | pt18 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 542 | **547** | +5 (2 entity pages from prior lint + 3 source pages over 1 day + 1 lint report) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 2 (concepts/skill-md ×2; both fixed) | **0** | -2 (slug-discipline holding!) |
| New entity-page candidates past 2-surface threshold | 2 (charity-majors + z-ai; both created) | **0** | -2 |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Dead Links

### Entity page updates — REAL FIXABLE (1 page update)

| Target | Status | Action |
|---|---|---|
| `[[people/nathan-lambert]]` | **3rd substantive surface added Jun 19** ("restricting open-source AI threatens American values + transparency + innovation" canonical-defense-positioning) | **Update existing `people/nathan-lambert.md`** — add Jun 19 surface under "Notable Takes"; extends from departure-from-AI2 + multi-teacher-distillation canonical-articulation to **open-source-AI-defense canonical-voice-tier**. Pattern-watch: Lambert at 4-voice canonical-open-source-AI-defense canonical-cluster |

### Past 2-surface threshold — pattern-watch escalation candidates (3 unique) — defer per conservative policy

| Target | Surfaces | Note |
|---|---|---|
| `[[anthropic-public-record]]` | **3 refs across 3 cluster ingest cycles** (Jun 16 + Jun 17 + Jun 18) | Multi-lint carry-over from prior lint. Pattern-watch: should fold into companies/anthropic.md as section rather than dedicated entity-page (3-day Anthropic-side transparency-cluster initiative) |
| `[[openai-deployment-simulation]]` | **2 refs across 2 cluster ingest cycles** (Jun 16 + Jun 18) | Multi-lint carry-over. Pattern-watch: fold into companies/openai.md as section |
| `[[allenai]]` / `[[ai2]]` | **2 refs across 2 distinct ingest days** (Jun 12 + Jun 19) | Pattern-watch escalation candidate. AI2/Allen Institute = think-tank-tier open-source-AI-defense canonical-voice; could create `companies/allenai.md` next lint if 3rd substantive surface appears |

### Single-source entity-page defers — new from 2026-06-19 + pt2 ingest sequence (~17 unique / ~17 occurrences) — no action

Conservative entity-creation policy applies (defer until 2nd substantive surface):

- `[[deerflow]]`, `[[bytedance]]` (ByteDance DeerFlow AI-employee launch)
- `[[slime]]`, `[[zhipu-ai]]`, `[[thudm]]` (Slime RL-scaling framework)
- `[[prime-intellect]]`, `[[will-brown]]` (distillation-ban-circumvention)
- `[[schmidhuber]]` / `[[jurgen-schmidhuber]]`, `[[sakana-ai]]`, `[[hardmaru]]` (Schmidhuber 1991-origin-claim)
- `[[andreas-kirsch]]` (DeepMind governance-direct-voice)
- `[[florian-brand]]` (monopolistic-rent-seeking counter-warning)
- `[[harvey]]`, `[[asml]]`, `[[ukraine-trophylab]]`, `[[jarred-sumner]]` (roundup-tier surfaces)

### Carry-over single-source entity-page defers from prior lints (~50 unique / ~50 occurrences) — no action

Carry-overs unchanged from [[meta/lint-report-2026-06-18|prior lint]]: deepmind, mistral, theker, qwen, microsoft, deepseek, kpmg, india, manus, llama, gemma, apple, cohere, amazon, trump, opik, evo, aria, extropic, biohub, kasra, dxc, lm-studio, minimax, moonshot-ai, gabriel-petersson, matt-clifford, mcpmatt-pocock (typo carry-over: should be `[[matt-pocock]]`), nick-frosst, omnigent, prometheus, rohan-paul, river-ai, sequent, spectnfa, tejas-kumar, tensorzero, theo-tabah, thepremiseofit, geoffrey-irving, guillaume-verdon, igor-babuschkin, jeremy-howard, lucianw, malay-hazarika, martin-alderson, phil-trammell, alex-imas, emanuel-maiberg, alok-bishoyi, 0xCodez, 0xwhrrari, aiedge, werner-kasselman, trustmodel-ai, tom-ballard, stratechery, simi, sayash-kapoor, salesforce, lore, karl-mehta, jia-bin-huang, hermes-agent, fin, brendon-burchard, ben-thompson, arvind-narayanan, alien-org, marc-benioff, cartesia, gergely-orosz, tomas-reimers, origin, bland, single-grain, single-brain, town, jack-smith, riley-brown, peter-yang, nick-vasilescu, amir-musich, kloss, ultracode-max, teknium, ralph-miller, brad-axen, builderbot, aaif, vercel, guillermo-rauch, eve, polypore, evan-klem, thibault-sottiaux, adam-cad, europe-2031-initiative, pentagon, ploy, bryant-chou, pierre-carl-langlais, pramaana-labs, xdof, shreya-shankar, joshua-baer, capital-factory, ona, noam-shazeer, gpt-5-4, dean-ball, glm-5-2, bernie-sanders, jd-vance, joseph-krause, radical-ai, metr-hawk, ceo-bench, elastic, deductive-ai, thomas-dimson, boston-childrens-hospital, in-the-weights, jie-tang, tsinghua-university, samueljmcd, samuel-mcdonald, react-pattern, reflexion, addy-osmani, eric-siu, rahulgs, rahul-gs, evolution-plus-ai, matt-m13v, i-miss-the-sun, zayyan, hanakoxbt, hanako, sydney-runkle

### Path-form persistent dead-links + false positives — no action

Unchanged from prior lints:
- Path-form trailing-backslash table-cell-escape artifacts (~30 occurrences) — false positives
- `[[meta/lint-report-2026-06-1{3,4,5,6,7,8}]]` + `[[meta/lint-report-2026-05-11]]` — EXIST path-form refs (false positives)
- `[[concepts/skill-md]]` / `[[concepts/agentic-coding]]` / `[[concepts/hallucination]]` — backtick-quoted historical-narrative-only (false positives; established convention)
- `[[claude-mythos-5]]` / `[[models/claude-mythos-5]]` / `[[anthropic-bun-zig-rust-port-2026-05]]` — backtick-quoted historical (multi-lint carry-overs)
- `[[claude-opus-4-6]]` / `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` — backtick-quoted historical (multi-lint carry-overs)
- `[[you-dont-need-100-hours-claude-7-setups]]` — backtick-quoted historical (fixed in prior lint)
- Teaching-example structural false positives (~14 occurrences)

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**. `_raw/The Self-Improving Loop... 1.md` canonical-duplicate of [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18|Jun 18 0xMovez canonical-playbook]] noted as explicitly-skipped per [[log.md|2026-06-19 ingest-pt2 log entry]].

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-121-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-19`

## Recommended Fixes

### Required (1 entity-page update)

1. **Update `people/nathan-lambert.md`** — add Jun 19 substantive surface ("restricting open-source AI threatens American values + transparency + innovation" canonical-defense-positioning from [[jun-19-open-source-research-origin-cluster-2026-06-19]]); extends from departure-from-AI2 + multi-teacher-distillation canonical-articulation to **open-source-AI-defense canonical-voice-tier**

### Optional (pattern-watch flags for next lint)

- `[[anthropic-public-record]]` 3-cluster carry-over (3 refs); fold into `companies/anthropic.md` as Public Record canonical-section
- `[[openai-deployment-simulation]]` 2-cluster pattern-watch; fold into `companies/openai.md` as section
- `[[allenai]]` / `[[ai2]]` 2-cluster pattern-watch (Jun 12 + Jun 19); could create `companies/allenai.md` if 3rd substantive surface
- 17 single-source defers from 2026-06-19 sequence 2nd substantive surfaces watch (deerflow + bytedance + slime + zhipu-ai + thudm + will-brown + schmidhuber + andreas-kirsch + harvey + asml + etc.)
- Carry-over: `[[mcpmatt-pocock]]` → `[[matt-pocock]]` typo
- `[[0xMovez]]` capital-M slug case-normalization → `[[0xmovez]]` (low-priority single-occurrence)

## Overall Posture

Wiki health structurally excellent. The **2026-06-19 + 2026-06-19-pt2 ingest sequence** (3 source pages in 1 day) landed cleanly with **0 wrong-slug regressions** (slug-discipline lessons holding across multi-lint cadence) and **0 new entity-page candidates past 2-surface threshold this lint** — conservative entity-creation policy holding even amid STRUCTURALLY MASSIVE Jun 18 ingest day (10+ source pages) + STRUCTURALLY MAJOR Jun 19 Chinese-open-source 3-tier 4-vendor canonical-cluster.

**Major narrative tracking now established**:
- **21-narrative-event 15-day Anthropic-USG-conflict crisis cluster** continues as most-load-bearing wiki-tracked governance event of 2026-Q2
- **12-voice Loop-Engineering canonical-cluster** + **STRUCTURALLY MASSIVE 5-day 11-event Loop-Engineering canonical-cluster** spans Jun 13-18
- **First wiki-captured 3-tier 4-vendor canonical-Chinese-open-source-AI multi-tier canonical-cluster** (model-tier × 4 + RL-scaling-framework-tier × 1 + agent-tier × 1) demonstrates **2-day Jun 18-19 Chinese-open-source-vendor multi-tier canonical-extension cluster**
- **First wiki-captured 4-voice canonical-open-source-AI-defense canonical-cluster** spans practitioner-tier (Greg Isenberg) + industry-tier (cybersecurity-vets) + practitioner-tier (Willison) + think-tank-tier (Nathan Lambert AI2)
- **First wiki-captured 2-vendor 1-day "convert work into reusable skills" canonical-cluster** (Anthropic Artifacts Jun 18 + OpenAI Codex Record/Replay Jun 18)
- **STRUCTURALLY MASSIVE Block Builderbot production-scale operationalization** (200K ops/day + 1.5K PRs/week + 15% of production code) = most-load-bearing AI-native-organization-thesis-validation event captured to date

**Tracking for next lint**:
- Pattern-watch escalations per above
- Continued slug-discipline holding
- Continued conservative entity-creation policy
- 2-day Jun 18-19 Chinese-open-source-vendor multi-tier canonical-extension cluster pattern-watch (does cluster extend to 4-vendor or more?)
