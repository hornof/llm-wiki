---
type: meta
title: "Lint Report 2026-06-17"
created: 2026-06-17
updated: 2026-06-17
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-17

## Summary

- **Pages scanned**: 532 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Real fixable**: **3 entity-page candidates past 2-surface threshold** (`codex` + `openclaw` + `pleias`)
- **Wrong-slug regressions in latest ingests**: **0** (slug-discipline holding!)
- **Unprocessed `_raw/` drops**: **0** net-new
- **Lint branch**: `lint/2026-06-17`

**Wiki health structurally excellent**. 0 orphans / 0 frontmatter gaps / 0 stale dates across 532 pages (+11 from prior lint). The **2026-06-17 + 2026-06-17-pt2 + 2026-06-17-pt3 + 2026-06-16-pt3 ingest sequence** (4 ingests; 11 source pages; 70+ new single-source entity candidates) landed cleanly with **3 entity-page candidates past 2-surface threshold** (notably `codex` which is STRUCTURALLY LOAD-BEARING) and **0 wrong-slug regressions** — slug-discipline lessons from prior lints holding.

### Net delta vs `lint-report-2026-06-16`

| Metric | pt16 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 521 | **532** | +11 (2 entity pages from prior lint + 10 source pages over 1 day + 1 lint report) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 2 (both fixed) | **0** | -2 (slug-discipline lessons holding!) |
| New entity-page candidates past 2-surface threshold | 2 (ona + anysphere; both created) | **3** (codex + openclaw + pleias) | +1 |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Dead Links

### Past 2-surface threshold — entity pages worth creating (3 unique / ~8 occurrences) — REAL FIXABLE

| Target | Surfaces | Substantive references | Recommended action |
|---|---|---|---|
| `[[codex]]` | **2 + practitioner-signal-LOAD-BEARING** | (1) [[gregisenberg-pick-a-side-7-question-poll-2026-06-16]] — first wiki-captured Codex-dominance signal in practitioner-content register (4/4 distinct-answer comments pick Codex over Claude Code); (2) [[agentic-coding-tooling-cluster-2026-06-17]] — Jun 17 Thibault Sottiaux open-source-model-routing + self-hosted-local-endpoints event | **Create `tools/codex.md`** — **STRUCTURALLY MAJOR omission**: OpenAI's flagship AI-coding-product; wiki-tracked competitive-positioning vs [[claude-code]] requires entity-page; Jun 17 open-source-routing event = first wiki-captured operator-substrate-control-friendly canonical-positioning. **Load-bearing for practitioner-tier preference signals.** |
| `[[openclaw]]` | **3+** | (1) [[dailybrief-roundup-2026-05-30]] — Peter Steinberger OpenClaw / Crabbox 10-hour agent runs (multi-lint carry-over); (2) [[gregisenberg-pick-a-side-7-question-poll-2026-06-16]] — Greg Isenberg "Pick a side" Q1 framing (Openclaw vs Hermes practitioner-signal); (3) [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]] — Sydney Runkle heartbeats canonical-pattern reference (validates Openclaw as canonical-tier cron-based-loop infrastructure) | **Create `tools/openclaw.md`** — Peter Steinberger project; **3 substantive surfaces** validates entity-page threshold. Pairs structurally with [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger]] + Loop Engineering canonical-cluster context |
| `[[pleias]]` / `[[pierre-carl-langlais]]` | **4 substantive surfaces** | (1) [[anthropic-usg-conflict-10th-narrative-event-cluster-2026-06-15]] — Pleias CTO Langlais "Europe AI lag = training-skill + ecosystem deficiencies, not compute" canonical-framing; (2) [[anthropic-usg-conflict-cluster-jun-17-extension-2026-06-17]] — 2-voice EU-AI-substrate-deficiency canonical-debate (compute-gap vs training-skill-and-ecosystem); (3) [[dailybrief-roundup-2026-06-15]]; (4) [[dailybrief-roundup-2026-06-17]] | **Create `companies/pleias.md`** — 4 substantive surfaces; **first wiki-captured EU-AI-substrate canonical-voice-tier**; Pierre-Carl Langlais structurally-significant for canonical-2-voice EU-AI-substrate-deficiency canonical-debate context |

### Single-source entity-page defers — new from 2026-06-17 + pt2 + pt3 + 2026-06-16-pt3 ingest sequence (~25 unique / ~25 occurrences) — no action

Conservative entity-creation policy applies (defer until 2nd substantive surface):

**From 2026-06-17 + pt2 + pt3 ingests (~20 net-new)**:
- `[[brad-axen]]`, `[[builderbot]]`, `[[aaif]]` (Block Builderbot launch)
- `[[sydney-runkle]]`, `[[langsmith-engine]]`, `[[fleet]]`, `[[rubric-middleware]]` (LangChain 4-layer)
- `[[hanakoxbt]]`, `[[hanako]]` (practitioner-tier Hanako)
- `[[rahulgs]]`, `[[rahul-gs]]`, `[[evolution-plus-ai]]`, `[[matt-m13v]]`, `[[i-miss-the-sun]]`, `[[zayyan]]` (Rahul GS thesis comment-thread voices)
- `[[europe-2031-initiative]]`, `[[pentagon]]`, `[[department-of-defense]]` (Anthropic-USG-conflict cluster Jun 17)
- `[[anthropic-public-record]]`, `[[openai-deployment-simulation]]` (Jun 16+17 same-week cluster)
- `[[vercel]]`, `[[guillermo-rauch]]`, `[[eve]]`, `[[polypore]]`, `[[evan-klem]]`, `[[thibault-sottiaux]]`, `[[adam-cad]]` (agentic-coding-tooling Jun 17)
- `[[pramaana-labs]]`, `[[xdof]]`, `[[ploy]]`, `[[bryant-chou]]`, `[[joshua-baer]]`, `[[capital-factory]]`, `[[shreya-shankar]]` (Jun 17 roundup)
- `[[samueljmcd]]`, `[[samuel-mcdonald]]`, `[[react-pattern]]`, `[[reflexion]]`, `[[addy-osmani]]` (carry-over from Jun 15 + 17 cluster)

**From 2026-06-16-pt3 ingests (~5 net-new carry-over)**:
- `[[town]]`, `[[jack-smith]]`, `[[riley-brown]]`, `[[peter-yang]]`, `[[nick-vasilescu]]`, `[[amir-musich]]`, `[[kloss]]`, `[[ultracode-max]]`, `[[ralph-miller]]`, `[[teknium]]` (Greg Isenberg + Sudip Rokaya comment-thread voices)

### Carry-over single-source entity-page defers from prior lints (~45 unique / ~45 occurrences) — no action

Carry-overs unchanged from [[meta/lint-report-2026-06-16|prior lint]]: deepmind, mistral, theker, charity-majors, qwen, microsoft, deepseek, kpmg, india, manus, llama, gemma, apple, cohere, amazon, trump, opik, evo, aria, extropic, biohub, kasra, dxc, allenai, lm-studio, z-ai, minimax, moonshot-ai, gabriel-petersson, matt-clifford, mcpmatt-pocock (typo carry-over: should be `[[matt-pocock]]`), nick-frosst, omnigent, prometheus, rohan-paul, river-ai, sequent, spectnfa, tejas-kumar, tensorzero, theo-tabah, thepremiseofit, geoffrey-irving, guillaume-verdon, igor-babuschkin, jeremy-howard, lucianw, malay-hazarika, martin-alderson, phil-trammell, alex-imas, emanuel-maiberg, alok-bishoyi, 0xCodez, 0xwhrrari, aiedge, werner-kasselman, trustmodel-ai, tom-ballard, stratechery, simi, sayash-kapoor, salesforce, lore, karl-mehta, jia-bin-huang, hermes-agent, fin, brendon-burchard, ben-thompson, arvind-narayanan, alien-org, marc-benioff, cartesia, gergely-orosz, tomas-reimers, origin, bland, single-grain, single-brain, eric-siu (still 1-substantive-surface from his own focused source)

### Path-form persistent dead-links + false positives — no action

Unchanged from prior lints:
- Path-form trailing-backslash table-cell-escape artifacts (~30 occurrences) — false positives
- `[[meta/lint-report-2026-06-1{3,4,5,6}]]` + `[[meta/lint-report-2026-05-11]]` — EXIST path-form refs (false positives)
- `[[concepts/skill-md]]` / `[[concepts/agentic-coding]]` / `[[concepts/hallucination]]` — backtick-quoted historical-narrative-only (false positives; established convention)
- `[[claude-mythos-5]]` / `[[models/claude-mythos-5]]` / `[[anthropic-bun-zig-rust-port-2026-05]]` — backtick-quoted historical (multi-lint carry-overs)
- `[[claude-opus-4-6]]` / `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` — backtick-quoted historical (multi-lint carry-overs)
- `[[you-dont-need-100-hours-claude-7-setups]]` — backtick-quoted historical (fixed in prior lint)
- Teaching-example structural false positives (~14 occurrences)

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**. All recent _raw drops already-ingested or explicitly skipped per prior workflows.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-115-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-17`

## Recommended Fixes

### Required (3 entity-page creations past 2-surface threshold)

1. **Create `tools/codex.md`** — **STRUCTURALLY MAJOR omission**: OpenAI's flagship AI-coding-product; 2 substantive surfaces (Codex-dominance practitioner-signal + open-source-routing event) + practitioner-tier preference signals make this load-bearing. Closes ~2 dead-link refs + enables wiki-tracked competitive-positioning vs [[claude-code]]
2. **Create `tools/openclaw.md`** — Peter Steinberger project; 3 substantive surfaces (Steinberger Crabbox + Greg Isenberg poll + Sydney Runkle heartbeats); structurally load-bearing for Loop Engineering canonical-cluster context
3. **Create `companies/pleias.md`** — 4 substantive surfaces; first wiki-captured EU-AI-substrate canonical-voice-tier; structurally significant for 2-voice EU-AI-substrate-deficiency canonical-debate context

### Optional (pattern-watch flags for next lint)

- `[[sydney-runkle]]` 2nd substantive surface watch (LangChain canonical-voice-tier surface)
- `[[brad-axen]]` 2nd substantive surface watch (Head of AI Capabilities at Block)
- `[[builderbot]]` 2nd substantive surface watch (post-launch Builderbot follow-up)
- `[[hanakoxbt]]` / `[[hanako]]` 2nd substantive surface watch (practitioner-tier voice)
- `[[rahulgs]]` 2nd substantive surface watch (Cherny-validated canonical thesis voice)
- `[[anthropic-public-record]]` 2nd substantive surface watch (Anthropic-side transparency-initiative)
- `[[openai-deployment-simulation]]` 2nd substantive surface watch (OpenAI safety-eval canonical technique)
- `[[vercel]]` + `[[guillermo-rauch]]` 2nd substantive surface watch (Vercel Eve agentic-framework follow-up)
- `[[tomas-reimers]]` / `[[origin]]` 2nd substantive surface watch (Cursor founder)
- `[[gergely-orosz]]` 2nd substantive surface watch (Meta-walkback)
- `[[bland]]` 2nd substantive surface watch (voice-AI compliance-heavy)
- `[[ploy]]` + `[[bryant-chou]]` 2nd substantive surface watch (website-operations $27M seed)
- `[[town]]` 2nd substantive surface watch (Town.com $55M A16Z)
- `[[europe-2031-initiative]]` 2nd substantive surface watch (EU sovereign-AI policy)
- Carry-over: `[[matt-clifford]]` + `[[gabriel-petersson]]` + `[[kpmg]]` + `[[india]]` + `[[manus]]` + Chinese-open-weight-vendor cluster
- Carry-over typo: `[[mcpmatt-pocock]]` → `[[matt-pocock]]`

## Overall Posture

Wiki health structurally excellent. The **2026-06-16-pt3 + 2026-06-17 + 2026-06-17-pt2 + 2026-06-17-pt3 ingest sequence** (4 ingests; 11 source pages; 70+ new single-source entity candidates) landed cleanly with **3 entity-page candidates past 2-surface threshold** (notably `codex` which is STRUCTURALLY LOAD-BEARING for practitioner-tier preference signals) and **0 wrong-slug regressions** — slug-discipline lessons from prior lints holding.

**Major narrative tracking now established**:
- **21-narrative-event 15-day Anthropic-USG-conflict crisis cluster** is the most-load-bearing wiki-tracked governance event of 2026-Q2 frontier-AI period (extended from 17 to 21 via Jun 17 G7 + EU + Sacks + Pentagon cluster)
- **11-voice Loop-Engineering canonical-cluster** now established (Cherny + Steinberger + Van Horn + Bishoyi + Karpathy + Zaharia + Nadella + Sarah Guo + Alien + Samuel McDonald + Sydney Runkle) with Block Builderbot as production-scale firm-tier proof-point
- **6-voice 4-day Loop-Engineering canonical-discourse + production-operationalization cluster** = fastest canonical-discourse-convergence + production-operationalization-cluster captured to date
- **STRUCTURALLY MASSIVE Block Builderbot production-scale operationalization** (200K ops/day + 1.5K PRs/week + 15% of production code) = most-load-bearing AI-native-organization-thesis-validation event captured to date
- **2-voice EU-AI-substrate-deficiency canonical-debate** (Pleias-Langlais compute-vs-training-skill-and-ecosystem) established
- **3-vector USG-AI-policy canonical-cluster** (restrictive + permissive + adoptive) established
- **3-day tier-1 enterprise-AI-consolidation cluster** ($60B Anysphere + $XB Ona + $3.6B Salesforce-Fin) documented at entity-page tier with anysphere + ona

**Tracking for next lint**:
- New pattern-watches per above
- Continued slug-discipline holding
- Continued conservative entity-creation policy
