---
type: meta
title: "Lint Report 2026-06-20"
created: 2026-06-20
updated: 2026-06-20
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-20

## Summary

- **Pages scanned**: 551 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Real fixable**: **2 entity-page candidates past 2-surface threshold** (`hanako` 3 refs + `anthropic-public-record` 4 refs) + **0 wrong-slug regressions** (slug-discipline holding!)
- **Unprocessed `_raw/` drops**: **0** net-new
- **Lint branch**: `lint/2026-06-20`

**Wiki health structurally excellent**. 551 pages scanned (+4 from prior lint). 0 orphans / 0 frontmatter gaps / 0 stale dates / **0 wrong-slug regressions** — slug-discipline lessons holding across multi-lint cadence. The **2026-06-20 + 2026-06-20-pt2 ingest sequence** (2 ingests + 4 focused source pages over 1 day) landed cleanly with **2 entity-page candidates past 2-surface threshold** (`hanako` 3 substantive surfaces + `anthropic-public-record` 4 substantive surfaces — both multi-lint carry-overs now actionable).

### Net delta vs `lint-report-2026-06-19`

| Metric | pt19 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 547 | **551** | +4 (1 lint-report + 1 entity-update from prior lint + 4 source pages over 2 days) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 0 | **0** | — (slug-discipline holding) |
| New entity-page candidates past 2-surface threshold | 0 | **2** (hanako + anthropic-public-record) | +2 (both multi-lint carry-overs actionable) |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Dead Links

### Past 2-surface threshold — entity pages worth creating (2 unique / 7 occurrences) — REAL FIXABLE

| Target | Surfaces | Substantive references | Recommended action |
|---|---|---|---|
| `[[hanako]]` (alt: `[[hanakoxbt]]`) | **3** (or 5 combining variants) | (1) [[hanakoxbt-claude-loops-while-you-sleep-2026-06-13]] — dedicated Jun 13 source page; (2) [[concepts/loop-engineering]] — Hanako added as practitioner-tier voice in canonical-cluster; (3) [[practitioner-cluster-hanako-2nd-surface-sairahul1-6-concepts-2026-06-19]] — Hanako 2nd substantive surface ("Prompt auto-update after 100 user decisions") | **Create `people/hanako.md`** — 3 distinct ingest-cycle substantive surfaces (Jun 13 + Jun 19 concept + Jun 19 source); canonical practitioner-content-register voice. **First wiki-captured "the bottleneck was never the model"** + **"babysit the rules not the work"** + **"prompt is not a config, it's an apprentice"** canonical-Hanako framings (already documented in source pages). Pattern-watch from [[meta/lint-report-2026-06-19|prior lint]] now actionable. Closes ~3 dead-link refs |
| `[[anthropic-public-record]]` | **4** (across 4 distinct ingest cycles) | (1) [[anthropic-usg-conflict-cluster-jun-16-extension-2026-06-16]] — Jun 16 Anthropic Public Record Jun 12 first-results event canonical-discovery; (2) [[openai-ona-acquisition-deployment-simulation-2026-06-16]] — paired vendor-side transparency-and-safety-evaluation-discipline cluster; (3) [[openai-jun-18-7-event-cluster-2026-06-18]] — paired 3-vendor 6-day vendor-side transparency cluster; (4) [[deepmind-jun-20-jumper-anthropic-ai-control-roadmap-2026-06-20]] — Jun 20 paired 4-vendor 3-week vendor-side AI-control + AI-safety-and-transparency canonical-discipline cluster | **Create `companies/anthropic-public-record.md`** OR fold into `companies/anthropic.md` as Public Record canonical-section. **STRUCTURALLY MAJOR multi-lint carry-over** (3+ cycles pattern-watch). **4 substantive surfaces across 4-vendor 3-week canonical-discipline cluster** validates dedicated-entity-page or canonical-section creation. Closes ~4 dead-link refs |

### Pattern-watch escalation candidates (2 refs but limited) — defer per conservative policy

| Target | Surfaces | Note |
|---|---|---|
| `[[openai-deployment-simulation]]` | **3 refs across 3 distinct cycles** (Jun 16 + Jun 18 + Jun 20) | Multi-lint carry-over pattern-watch. Should fold into `companies/openai.md` as Deployment Simulation canonical-section |
| `[[allenai]]` / `[[ai2]]` | **2 refs across 2 distinct ingest days** (Jun 12 + Jun 19) | Pattern-watch escalation candidate. Could create `companies/allenai.md` if 3rd substantive surface appears |
| `[[andreas-kirsch]]` | 2 refs from same Jun 19 cluster | Single-cluster-source defer (same ingest cycle) |
| `[[hanakoxbt]]` (variant slug) | 2 refs | Slug-canonical-variant of `hanako` (3 refs) — both forms covered by single `people/hanako.md` creation |

### Single-source entity-page defers — new from 2026-06-19-pt2 + 2026-06-20 + 2026-06-20-pt2 ingest sequence (~25 unique / ~25 occurrences) — no action

Conservative entity-creation policy applies (defer until 2nd substantive surface):

- `[[john-jumper]]` (Nobel laureate AlphaFold co-creator — STRUCTURALLY MAJOR canonical-status; pattern-watch for 2nd surface)
- `[[polsia]]` / `[[pulsia]]`, `[[ben-cera]]`, `[[jennifer]]` (Polsia meta-AI cluster)
- `[[ai-control-roadmap]]` (DeepMind agent-security framework)
- `[[yunta-tsai]]`, `[[francois-fleuret]]`, `[[meta-fair]]`, `[[kache]]` (Jun 20 worth-a-skim)
- `[[nabeel-qureshi]]`, `[[pangram]]` (Harper's Bazaar AI-detection)
- `[[sean-lynch]]`, `[[z-lab]]`, `[[dflash]]` (MCP + dflash)
- `[[deedy-das]]`, `[[russell-kaplan]]`, `[[cognition-ai]]`, `[[emad-mostaque]]` (Jun 20 today-on-Digg)
- `[[nick-mayhew]]`, `[[sairahul1]]` (Jun 19 practitioner cluster)
- Carry-over single-source defers from prior lints (~50 unique; no change)

### Carry-over single-source entity-page defers from prior lints (~50 unique / ~50 occurrences) — no action

Carry-overs unchanged from [[meta/lint-report-2026-06-19|prior lint]]: deepmind, mistral, theker, qwen, microsoft, deepseek, kpmg, india, manus, llama, gemma, apple, cohere, amazon, trump, opik, evo, aria, extropic, biohub, kasra, dxc, lm-studio, minimax, moonshot-ai, gabriel-petersson, matt-clifford, mcpmatt-pocock (typo carry-over: should be `[[matt-pocock]]`), nick-frosst, omnigent, prometheus, rohan-paul, river-ai, sequent, spectnfa, tejas-kumar, tensorzero, theo-tabah, thepremiseofit, geoffrey-irving, guillaume-verdon, igor-babuschkin, jeremy-howard, lucianw, malay-hazarika, martin-alderson, phil-trammell, alex-imas, emanuel-maiberg, alok-bishoyi, 0xCodez, 0xwhrrari, aiedge, werner-kasselman, trustmodel-ai, tom-ballard, stratechery, simi, sayash-kapoor, salesforce, lore, karl-mehta, jia-bin-huang, hermes-agent, fin, brendon-burchard, ben-thompson, arvind-narayanan, alien-org, marc-benioff, cartesia, gergely-orosz, tomas-reimers, origin, bland, single-grain, single-brain, town, jack-smith, riley-brown, peter-yang, nick-vasilescu, amir-musich, kloss, ultracode-max, teknium, ralph-miller, brad-axen, builderbot, aaif, vercel, guillermo-rauch, eve, polypore, evan-klem, thibault-sottiaux, adam-cad, europe-2031-initiative, pentagon, ploy, bryant-chou, pierre-carl-langlais, pramaana-labs, xdof, shreya-shankar, joshua-baer, capital-factory, ona, noam-shazeer, gpt-5-4, dean-ball, glm-5-2, bernie-sanders, jd-vance, joseph-krause, radical-ai, metr-hawk, ceo-bench, elastic, deductive-ai, thomas-dimson, boston-childrens-hospital, in-the-weights, jie-tang, tsinghua-university, samueljmcd, samuel-mcdonald, react-pattern, reflexion, addy-osmani, eric-siu, rahulgs, rahul-gs, evolution-plus-ai, matt-m13v, i-miss-the-sun, zayyan, hanakoxbt (now covered via hanako entity), sydney-runkle, deerflow, bytedance, slime, zhipu-ai, thudm, prime-intellect, will-brown, schmidhuber, jurgen-schmidhuber, sakana-ai, hardmaru, harvey, asml, jarred-sumner, ukraine-trophylab

### Path-form persistent dead-links + false positives — no action

Unchanged from prior lints — see [[meta/lint-report-2026-06-19|prior lint report]] for full list.

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**. All recent _raw drops already-ingested or explicitly skipped per prior workflows.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-124-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-20`

## Recommended Fixes

### Required (2 entity-page creations past 2-surface threshold)

1. **Create `people/hanako.md`** — 3 distinct ingest-cycle substantive surfaces; canonical practitioner-content-register voice (Jun 13 "Claude Loops While You Sleep" + Jun 19 "Prompt auto-update after 100 user decisions" + Jun 19 concepts/loop-engineering canonical-cluster addition). Multi-lint carry-over pattern-watch from prior lint now actionable. Closes ~3 dead-link refs.
2. **Create `companies/anthropic-public-record.md`** — 4 distinct ingest-cycle substantive surfaces (Jun 16 + Jun 16 + Jun 18 + Jun 20); STRUCTURALLY MAJOR multi-lint carry-over (3+ cycles pattern-watch). Anthropic Public Record canonical-discipline-substrate at 4-vendor 3-week vendor-side AI-control + AI-safety-and-transparency canonical-discipline cluster layer. Closes ~4 dead-link refs.

### Optional (pattern-watch flags for next lint)

- `[[openai-deployment-simulation]]` 3-cycle pattern-watch (fold into companies/openai.md as section)
- `[[allenai]]` / `[[ai2]]` 2-cycle pattern-watch (create companies/allenai.md if 3rd substantive surface)
- `[[john-jumper]]` 2nd substantive surface watch (Nobel laureate canonical-status — pattern-watch for canonical-Anthropic-post-hire surfaces)
- `[[polsia]]` / `[[pulsia]]` + `[[ben-cera]]` 2nd substantive surface watch (canonical meta-AI canonical-vendor)
- `[[deerflow]]` + `[[bytedance]]` 2nd substantive surface watch (Chinese-open-source-agent-tier; multi-lint carry-over)
- 20+ single-source defers from Jun 19-20 sequence 2nd substantive surfaces watch
- Carry-over: `[[mcpmatt-pocock]]` → `[[matt-pocock]]` typo
- `[[0xMovez]]` capital-M slug case-normalization → `[[0xmovez]]` (low-priority)

## Overall Posture

Wiki health structurally excellent. The **2026-06-19-pt2 + 2026-06-20 + 2026-06-20-pt2 ingest sequence** (4 source pages over 2 days) landed cleanly with **0 wrong-slug regressions** (slug-discipline lessons from prior lints holding across multi-lint cadence) and **2 entity-page candidates past 2-surface threshold** (Hanako 3 substantive surfaces + Anthropic Public Record 4 substantive surfaces — both multi-lint carry-overs now actionable).

**Major narrative tracking now established**:
- **21-narrative-event 15-day Anthropic-USG-conflict crisis cluster** continues as most-load-bearing wiki-tracked governance event of 2026-Q2
- **STRUCTURALLY MAJOR Nobel-laureate Jumper canonical-cross-vendor-migration event** (Jun 20) = first-of-its-kind in canonical-frontier-AI wiki-tracked space
- **3-day 2-event Google-AI-talent-attrition canonical-cluster** (Shazeer Jun 18 → OpenAI + Jumper Jun 20 → Anthropic) = canonical-strongest-signal-yet of Google-AI-talent-retention canonical-issue
- **First wiki-captured 4-vendor 3-week vendor-side AI-control + AI-safety-and-transparency canonical-discipline cluster** (Anthropic + OpenAI + Google DeepMind + Block-Anthropic)
- **STRUCTURALLY MAJOR Polsia meta-AI-tier event** completes **4-tier canonical-AI-vendor-tier cluster** (AI-coding-product + AI-agent + AI-employee + AI-builds-companies-meta-AI)
- **12-voice Loop-Engineering canonical-cluster** + **STRUCTURALLY MASSIVE 5-day 11-event Loop-Engineering canonical-cluster** continues
- **4-document canonical-Markdown-as-canonical-discipline-file canonical-cluster** (`.claude/agents/` + `CLAUDE.md` + `CONSTRAINTS.md` + Nick-Mayhew "ideal candidate profile")

**Tracking for next lint**:
- Pattern-watch escalations per above (openai-deployment-simulation + allenai + john-jumper + polsia + deerflow + 20+ single-source defers)
- Continued slug-discipline holding
- Continued conservative entity-creation policy
