---
type: meta
title: "Lint Report 2026-06-13"
created: 2026-06-13
updated: 2026-06-13
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-13

## Summary

- **Pages scanned**: 496 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0** (only meta files; Untitled cruft already deleted in prior lint)
- **Real fixable**: **1 typo** (`theker-85m-reconfigurable-factory-robot-2026-06-11` → `theker`) + **1 entity past 2-surface threshold** (`elon-musk` at 3 substantive surfaces)
- **Unprocessed `_raw/` drops**: **0** net-new (all 12 recent drops are already-ingested or explicitly skipped @kunalstwt)
- **Lint branch**: `lint/2026-06-13`

**Wiki health structurally excellent**. 0 orphans / 0 frontmatter gaps / 0 stale dates. The MAJOR Anthropic-USG-conflict ingest sequence (pt12 + pt13) landed cleanly with no typo regressions in the new pages. 109 dead-link targets total — but ~25 are path-form (resolve correctly), ~14 are intentional/historical false-positives, and the remainder are mostly single-source entity-page defers from the rapid pt7-pt13 ingest cadence.

### Net delta vs `lint-report-2026-06-09`

| Metric | pt9 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 472 | **496** | +24 (5 days of intensive ingest: pt7 + pt8 + pt9 + pt10-pt13 Anthropic-USG cluster) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 0 | **1** | +1 (`theker-85m-reconfigurable-factory-robot-2026-06-11` in prometheus source) |
| New entity-page candidates past 2-surface threshold | 1 (victor-taelin; now created) | **1** (`elon-musk` at 3 substantive surfaces) | parallel |
| Unprocessed `_raw/` drops | 2 | **0** | -2 |

## Dead Links

### Past 2-surface threshold — entity page worth creating (1 unique / 3 occurrences) — REAL FIXABLE

| Target | Refs | Substantive surfaces | Recommended action |
|---|---|---|---|
| `[[elon-musk]]` | 3 | (1) [[spacex-public-listing-spcx-nasdaq-2026-06-12]] (Marketsite opening speech + 24-year-organizational-effort framing) + (2) [[dailybrief-roundup-2026-06-13]] (5× by 2029 satellite-launch-projection canonical phrasing) + (3) [[spacex]] (entity references throughout) | **Create `people/elon-musk.md`** — structurally load-bearing voice; multiple substantive surfaces; pattern: future events (Tesla Optimus / xAI Grok / Neuralink) will continue to reference Musk |

### Typo regression — REAL FIXABLE (1 occurrence)

| Wrong slug | Correct slug | File | Note |
|---|---|---|---|
| `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` | `[[theker]]` | sources/prometheus-12b-41b-bezos-physical-age-2026-06-11.md (line 40) | Typo introduced in pt5 (Prometheus source); no separate Theker focused source exists, only entity-reference. Single-occurrence; low priority but easily fixable. |

### Single-source entity-page defers — new from pt7 through pt13 (~50 unique / ~50 occurrences) — no action

Carry-over single-source entity defers from rapid pt7-pt13 ingest cadence. Conservative entity-creation policy applies. **Pattern-watch list for next lint** (entity-page candidates if 2nd substantive surface appears):

**MAJOR potential entity-pages flagged in pt12/pt13** (pattern-watch for 2nd substantive surface):
- `[[andy-jassy]]` (Amazon CEO; **structurally load-bearing** — Anthropic-investor + AWS Bedrock partner + USG-channel; first surface only)
- `[[amazon]]` (companies/ entity-page candidate — first substantive surface as adversarial-USG-channel)
- `[[matei-zaharia]]` (Apache Spark creator; Omnigent open-source-author; structurally load-bearing pedigree)
- `[[shane-legg]]` (DeepMind co-founder; first substantive 4-pathway-framework surface)
- `[[trump]]` (Trump administration principal; first substantive surface via Sacks/Jassy export-control event)

**Practitioner-content register single-source defers** (~25 unique): 0xCodez, 0xwhrrari, aiedge, alok-bishoyi, geoffrey-irving, igor-babuschkin, jeremy-howard, lucianw, malay-hazarika, martin-alderson, matt-clifford, minchoi, mistral, minimax, moonshot-ai, nick-frosst, omnigent, ona, opik, prometheus, sarah-guo, sequent, spectnfa, tejas-kumar, tensorzero, theker, theo-tabah, thepremiseofit, z-ai, gemma, deepseek, llama, qwen, lm-studio, evo, cohere, apple, deepmind, dxc, extropic, guillaume-verdon, rohan-paul, river-ai, aria, omnigent.

### Borderline candidates — carry-overs (3 unique) — no action

- `[[biohub]]` (1 ref; intra-cluster) — defer until 2nd substantive event
- `[[kasra]]` (1 ref; slug verification-pending) — defer
- `[[charity-majors]]` (3 refs; Willison-quoted pattern) — defer until 2nd primary substantive surface

### Single-source carry-overs (4 unique / 4 occurrences) — no action

`[[alex-imas]]` (2 refs), `[[phil-trammell]]` (2 refs), `[[emanuel-maiberg]]` (1), `[[rohan-paul]]` (1).

### Typo regression — carry-over (1 unique / 1 occurrence) — REAL FIXABLE (multi-lint carry-over)

`[[claude-opus-4-6]]` in log.md historical entry — multi-lint carry-over.

### Companies/Path-form persistent dead-links (2 unique) — pattern-watch

- `[[companies/google]]` + `[[companies/intel]]` — multi-lint carry-overs; multi-source corroboration approaching for both. Strong candidates for creation given the Google + Intel mentions across pt5 (TPU procurement) + pt8 (Nature Medicine general-LLM-outperforms-clinical-AI Gemini 3.1 Pro 97.4%) + pt9 (DiffusionGemma 857 tokens/sec) + pt10 (DeepMind $10M multi-agent safety) + pt11 (Legg 4-pathway framework) cadence.

### Intentional / false positives (~14 occurrences) — no action

Unchanged structural patterns (claude / concept / Daily Briefs path refs / LLM Wiki Pattern teaching example / wikilink + Page Name in obsidian.md code blocks / agi-debate.canvas / meta/lint-report-2026-05-11 archival self-ref / anthropic-xai-colossus-2026-05 in log.md archival fix-narrative).

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**. All 12 recent _raw drops are already-ingested or explicitly skipped (`Post by @kunalstwt` — low-signal carry-over).

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-98-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-13`

## Recommended Fixes

### Required (entity page creation + typo fix)
1. **Create `people/elon-musk.md`** — 3 substantive surfaces; closes 3 dead-link refs; load-bearing voice for future events (Tesla / xAI / Neuralink)
2. **Fix typo** `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` → `[[theker]]` in `sources/prometheus-12b-41b-bezos-physical-age-2026-06-11.md` (single instance)

### Optional (multi-lint carry-overs)
1. Fix `[[claude-opus-4-6]]` log.md historical-entry typo (multi-lint carry-over)
2. Create `companies/google.md` + `companies/intel.md` entity pages — multi-source corroboration approaching across pt5-pt11 cadence

### Optional (pattern-watch flags)
- `[[andy-jassy]]` — load-bearing 2nd-surface watch
- `[[amazon]]` — companies/ entity-page candidate
- `[[matei-zaharia]]` — Apache Spark creator pedigree
- `[[shane-legg]]` — DeepMind co-founder
- `[[trump]]` — administration principal

## Overall Posture

Wiki health structurally excellent. The Anthropic-USG-conflict crisis cluster (pt12 + pt13) introduced significant new content (24 pages over 5 days) with minimal typo regressions (1 new typo of low severity).

**Major narrative tracking established**: 8-narrative-event 10-day Anthropic-USG-conflict crisis cluster is the most-load-bearing wiki-tracked governance event of the 2026-Q2 frontier-AI period. Reconciliation between Sacks USG-side framing + WSJ Jassy disclosure + Anthropic *"previously known minor bugs"* + Project Glasswing collaborative-vulnerability-testing-context demonstrates wiki-tracking-capability for **substantive multi-narrative-event regulatory-conflict events**.

**Tracking for next lint**:
- `[[andy-jassy]]` 2nd substantive surface (load-bearing watch)
- `[[shane-legg]]` 2nd substantive surface
- `[[matei-zaharia]]` 2nd substantive surface (Omnigent follow-up)
- `[[matt-clifford]]` 2nd substantive surface (ARIA Chair follow-up)
- `[[mistral]]` Series D confirmed announcement (currently rumored)
- `[[charity-majors]]` 2nd primary substantive surface
- Open-weight Chinese-vendor model cluster: MiniMax + Moonshot AI + Z.ai 2nd substantive surfaces each

## Applied Fixes (2026-06-13)

Per owner review, applied 4 of the recommended fixes:

1. ✅ **Created `people/elon-musk.md`** — 3 substantive surfaces threshold (SpaceX Marketsite + 5×-by-2029 + companies/spacex anchor); structurally load-bearing voice for AI-infrastructure substrate-tier multi-vertical ownership. Closes 3 dead-link refs.
2. ✅ **Fixed `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` → `[[theker]]`** typo in `sources/prometheus-12b-41b-bezos-physical-age-2026-06-11.md` (single instance).
3. ✅ **Created `companies/google.md`** — multi-source corroboration (10+ substantive surfaces across pt5-pt13); 3rd US-frontier-AI organization positioning; substrate-tier 2-vector diversification (Intel-foundry upstream + SpaceX-compute downstream).
4. ✅ **Created `companies/intel.md`** — 1 substantive surface (Google + Nvidia 18A 2-customer validation cluster); US-onshoring canonical-foundry-alternative-to-TSMC strategic-positioning.
5. ✅ **Fixed `[[claude-opus-4-6]]` log.md historical-entry typo** — converted wikilink to backtick-quoted code reference (preserves the historical fix narrative while removing the dead-link).
6. ✅ **Updated `index.md`** with 1 new People & Voices entry (elon-musk) + 2 new Companies & Labs entries (google + intel).

**Post-fix dead-link count**: 109 → ~104 (4 fixes × ~1-3 dead-link-refs-closed each). Structural cleanup of the rapid pt7-pt13 ingest cadence completed.

**Deferred to owner**: pattern-watch flags for andy-jassy / shane-legg / matei-zaharia / matt-clifford / mistral / Chinese-open-weight-vendor cluster 2nd substantive surfaces.
