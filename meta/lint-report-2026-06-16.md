---
type: meta
title: "Lint Report 2026-06-16"
created: 2026-06-16
updated: 2026-06-16
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-16

## Summary

- **Pages scanned**: 521 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Real fixable**: **2 entity-page candidates past 2-surface threshold** (`ona` + `anysphere`) + **2 wrong-slug regression-fixes** (`[[claude-mythos-5]]` × 4 → `[[claude-mythos]]`; `[[anthropic-bun-zig-rust-port-2026-05]]` × 3 → `[[anthropic-dynamic-workflows-primary-2026-05-28]]`)
- **Unprocessed `_raw/` drops**: **0** net-new
- **Lint branch**: `lint/2026-06-16`

**Wiki health structurally excellent**. 0 orphans / 0 frontmatter gaps / 0 stale dates across 521 pages (+6 from prior lint). The 2026-06-15-pt3 + 2026-06-16 + 2026-06-16-pt2 ingest sequence (3 days; 6 source pages; 50+ new single-source entity candidates) landed cleanly with 2 wrong-slug carry-over regressions + 2 entity-page candidates past 2-surface threshold via acquisition-target validation.

### Net delta vs `lint-report-2026-06-15`

| Metric | pt15 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 515 | **521** | +6 (1 lint-report + 6 source pages over 3 days; offset by tracking 2026-06-15 + 2026-06-15-pt3 + 2026-06-16 + 2026-06-16-pt2 ingests) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 3 (all fixed) | **2** (claude-mythos-5 × 4 + anthropic-bun-zig-rust-port × 3) | -1 net (carry-over not previously caught + new regression) |
| New entity-page candidates past 2-surface threshold | 0 | **2** (ona + anysphere) | +2 (both validated via 2026-06-16 acquisition events) |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Dead Links

### Past 2-surface threshold — entity pages worth creating (2 unique / 4 occurrences) — REAL FIXABLE

| Target | Surfaces | Substantive references | Recommended action |
|---|---|---|---|
| `[[ona]]` | **2** | (1) [[openai-ona-acquisition-deployment-simulation-2026-06-16]] — Jun 16 OpenAI acquisition target (load-bearing surface); (2) [[dailybrief-roundup-2026-06-11]] — prior single-source defer carry-over | **Create `tools/ona.md`** (or `companies/ona.md`) — persistent-cloud-agents platform; OpenAI acquisition target Jun 16; 2nd substantive surface validates entity-page threshold. **Pattern-watch from multi-lint carry-over now actionable.** |
| `[[anysphere]]` | **2** | (1) [[spacex-cursor-anysphere-60b-merger-microsoft-cowork-usage-pricing-2026-06-16]] — Jun 16 SpaceX $60B all-stock acquisition target; (2) [[linas-cursor-revenue-per-employee-spacex-acquisition-rumor-2026-06-07]] — Jun 7 1st substantive surface (SpaceX-Cursor rumor) | **Create `companies/anysphere.md`** — Cursor parent company; SpaceX $60B all-stock acquisition Q3 2026 close target; **structurally load-bearing** (cross-references xAI + SpaceX 3-layer AI-vertical-integration + Cursor product context). 2nd substantive surface validates entity-page threshold. |

### Wrong-slug regression fixes — REAL FIXABLE (7 occurrences / 2 sources)

| Wrong | Correct | File | Note |
|---|---|---|---|
| `[[claude-mythos-5]]` (alias-form) | `[[claude-mythos]]` (alias-form preserved) | sources/dario-policy-on-ai-exponential-via-mehta-2026-06-11.md (lines 21 + 30 + 46) + sources/india-meta-manus-geopolitical-ai-fallout-2026-06-13.md (line 18) | **CARRY-OVER REGRESSION**: prior lint fixed only line 95 in dario source; missed 3 alias-form occurrences in same file + 1 in india-meta-manus. Model page is `claude-mythos.md` not non-existent `claude-mythos-5`. 4 occurrences total |
| `[[anthropic-bun-zig-rust-port-2026-05]]` | `[[anthropic-dynamic-workflows-primary-2026-05-28]]` | sources/samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15.md (lines 87 + 172 + 187) | Fabricated slug from samueljmcd ingest — canonical Bun-Zig-Rust-port source page is `anthropic-dynamic-workflows-primary-2026-05-28.md`. 3 occurrences |

### Single-source entity-page defers — new from 2026-06-15-pt3 + 2026-06-16 + 2026-06-16-pt2 ingest sequence (~15 unique / ~15 occurrences) — no action

Conservative entity-creation policy applies (defer until 2nd substantive surface):

**From 2026-06-16 + pt2 ingests (~10 net-new)**:
- `[[anthropic-public-record]]` (2 refs but same ingest-cluster — single-substantive-surface defer)
- `[[openai-deployment-simulation]]` (single OpenAI-side product-launch surface)
- `[[tomas-reimers]]`, `[[origin]]` (Cursor founder + Git-for-AI-agents platform)
- `[[bland]]` ($100M Series C voice-AI startup)
- `[[gergely-orosz]]` (Meta engineering-discipline-walkback disclosure)
- `[[shreya-shankar]]` (plain-writing-skill SKILL.md canonical surface)
- `[[brian-armstrong]]`, `[[coinbase]]` (tokenized-stocks tangential)
- `[[microsoft-copilot-cowork]]` (verification-pending product-relationship with claude-cowork)
- `[[tesla]]` (Musk space-based-solar context)

**From 2026-06-15-pt3 + 2026-06-16 ingests (~5 net-new)**:
- `[[eric-siu]]`, `[[single-brain]]`, `[[single-grain]]` (Eric Siu 5-layer Company Brain architecture; single-source ingest)
- `[[samueljmcd]]`, `[[samuel-mcdonald]]`, `[[react-pattern]]`, `[[reflexion]]`, `[[addy-osmani]]` (samueljmcd Loop Engineering verifier-bottleneck source; single-source ingest)

### Carry-over single-source entity-page defers from prior lints (~45 unique / ~45 occurrences) — no action

Carry-overs unchanged from [[meta/lint-report-2026-06-15|prior lint]]: deepmind, mistral, theker, charity-majors (3 refs), qwen, microsoft, deepseek, kpmg, india, manus, llama, gemma, apple, cohere, amazon, trump, opik, evo, ona (NOW promoted past threshold), aria, extropic, biohub, kasra, dxc, allenai, lm-studio, z-ai, minimax, moonshot-ai, gabriel-petersson, matt-clifford, mcpmatt-pocock (typo carry-over: should be `[[matt-pocock]]`), nick-frosst, omnigent, prometheus, rohan-paul, river-ai, sequent, spectnfa, tejas-kumar, tensorzero, theo-tabah, thepremiseofit, geoffrey-irving, guillaume-verdon, igor-babuschkin, jeremy-howard, lucianw, malay-hazarika, martin-alderson, phil-trammell, alex-imas, emanuel-maiberg, alok-bishoyi, 0xCodez, 0xwhrrari, aiedge, werner-kasselman, trustmodel-ai, tom-ballard, teknium, sudip-rokaya, stratechery, simi, sayash-kapoor, salesforce, ralph-miller, pleias, pierre-carl-langlais, lore, karl-mehta, jia-bin-huang, hermes-agent, fin, brendon-burchard, ben-thompson, arvind-narayanan, alien-org, marc-benioff, cartesia, ariael

### Path-form persistent dead-links + false positives — no action

Unchanged from prior lints:
- Path-form trailing-backslash table-cell-escape artifacts (~25 occurrences) — false positives
- `[[meta/lint-report-2026-06-1{3,4,5}]]` + `[[meta/lint-report-2026-05-11]]` — EXIST path-form refs (false positives)
- `[[concepts/skill-md]]` / `[[concepts/agentic-coding]]` / `[[concepts/hallucination]]` — backtick-quoted historical-narrative-only (false positives; established convention)
- `[[claude-opus-4-6]]` / `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` — backtick-quoted historical (multi-lint carry-overs)
- Teaching-example structural false positives (~14 occurrences): `[[claude]]` / `[[concept]]` / `[[wikilink]]` / `[[wrong-slug]]` / `[[Page]]` / `[[Daily]]` × 5 / `[[index]]` / `[[index.md]]` / `[[agi-debate.canvas]]` / `[[anthropic-xai-colossus-2026-05]]`
- `[[you-dont-need-100-hours-claude-7-setups]]` — backtick-quoted historical (fixed in prior lint)

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**. All recent _raw drops already-ingested or explicitly skipped per prior workflows.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-110-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-16`

## Recommended Fixes

### Required (2 entity-page creations past 2-surface threshold + 2 wrong-slug regression-fixes)

1. **Create `tools/ona.md`** (or `companies/ona.md`) — 2 substantive surfaces (Jun 11 single-source + Jun 16 OpenAI acquisition target); persistent-cloud-agents platform; load-bearing surface post-acquisition; closes ~2 dead-link refs
2. **Create `companies/anysphere.md`** — 2 substantive surfaces (Jun 7 Linas SpaceX-Cursor rumor + Jun 16 SpaceX $60B all-stock acquisition); Cursor parent company; **structurally load-bearing** (cross-references SpaceX + xAI + Cursor + Tomas Reimers Origin context); closes ~2 dead-link refs
3. **Fix `[[claude-mythos-5|alias]]` → `[[claude-mythos|alias]]`** in `sources/dario-policy-on-ai-exponential-via-mehta-2026-06-11.md` (lines 21 + 30 + 46) + `sources/india-meta-manus-geopolitical-ai-fallout-2026-06-13.md` (line 18) — 4 occurrences; carry-over regression
4. **Fix `[[anthropic-bun-zig-rust-port-2026-05]]` → `[[anthropic-dynamic-workflows-primary-2026-05-28]]`** in `sources/samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15.md` (lines 87 + 172 + 187) — 3 occurrences; new regression from samueljmcd ingest

### Optional (pattern-watch flags for next lint)

- `[[eric-siu]]` 2nd substantive surface watch (Single Brain product-launch follow-up)
- `[[samueljmcd]]` / `[[samuel-mcdonald]]` 2nd substantive surface watch (Loop Engineering canonical voice)
- `[[anthropic-public-record]]` 2nd substantive surface watch (Jun 12 first-results follow-up)
- `[[openai-deployment-simulation]]` 2nd substantive surface watch (OpenAI safety-eval canonical technique)
- `[[tomas-reimers]]` + `[[origin]]` 2nd substantive surface watch (Cursor founder + Git-for-AI-agents)
- `[[gergely-orosz]]` 2nd substantive surface watch (Meta-walkback disclosure follow-up)
- `[[bland]]` 2nd substantive surface watch (voice-AI compliance-heavy follow-up)
- Carry-over: `[[matt-clifford]]` + `[[gabriel-petersson]]` + `[[kpmg]]` + `[[india]]` + `[[manus]]` + Chinese-open-weight-vendor cluster
- Carry-over typo: `[[mcpmatt-pocock]]` → `[[matt-pocock]]`

## Overall Posture

Wiki health structurally excellent. The **2026-06-15-pt3 + 2026-06-16 + 2026-06-16-pt2 ingest sequence** (3 days; 6 source pages; 50+ new single-source entity candidates) landed cleanly with **2 entity-page candidates past 2-surface threshold via acquisition-target validation** (ona + anysphere) + **2 wrong-slug regression-fixes** (claude-mythos-5 × 4 carry-over + anthropic-bun-zig-rust-port × 3 new).

**Major narrative tracking now established**:
- **17-narrative-event 14-day Anthropic-USG-conflict crisis cluster** is the most-load-bearing wiki-tracked governance event of 2026-Q2 frontier-AI period (extended from 13 via Jun 16 4-vector cluster including STRUCTURALLY EXPLOSIVE "fix this code" disclosure)
- **CLUSTER-NARRATIVE-REFRAMING via "fix this code" disclosure**: regulatory-action triggered by normal-dev-workflow prompt, not technical-safety-finding
- **3-day tier-1 enterprise-AI-consolidation cluster** ($3.6B Salesforce-Fin + $XB OpenAI-Ona + **$60B SpaceX-Anysphere** = 16.7× order-of-magnitude separation between substrate-tier and enterprise-SaaS-incumbent acquirer tiers)
- **4-day 2-vendor vendor-side safety-evaluation-discipline cluster** (Anthropic Public Record + OpenAI Deployment Simulation)
- **10-voice Loop Engineering canonical cluster** with Samuel McDonald at verifier-discipline-first-tier corrective-tier
- **Company Brain validated as multi-vendor canonical-category** with Eric Siu Single Brain 5-layer architecture as 2nd vendor data-point

**Tracking for next lint**:
- New pattern-watches per above
- Continued slug-discipline tightening (claude-mythos-5 carry-over regression demonstrates prior-lint incomplete-fix; needs comprehensive replace-all approach)
- Continued conservative entity-creation policy
