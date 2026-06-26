---
type: meta
title: "Lint Report 2026-06-26"
created: 2026-06-26
updated: 2026-06-26
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-06-26

## Summary

- **Pages scanned**: 685 (+14 vs lint-2026-06-25)
- **Orphans**: **4 NEW** (all yesterday's entity-page creations — RECURRING canonical-self-introduced-orphan canonical-pattern)
- **Frontmatter gaps**: 0 ✅
- **Wrong-slug regressions in 5 new source pages**: **0** ✅ (6 consecutive cycles)
- **Stale `last_updated`**: 8 (unchanged)
- **Entity-page candidates past 2-surface threshold**: **1 critical** (METR canonical-most-overdue) + 1 optional (Eric Topol canonical-pedigree-exception) + 1 optional canonical-model-page (GPT-5.6 + Sol + Terra + Luna)

## RECURRING canonical-self-introduced-orphan canonical-pattern ⚠️

**SECOND consecutive lint with self-introduced orphans**. Yesterday I created Figma but didn't wikilink from the source page mentioning it. Today I find 4 more orphans from yesterday's lint:

| Orphan | Should be wikilinked from |
|--------|---------------------------|
| `people/yacine.md` | [[dailybrief-roundup-2026-06-25]] |
| `companies/general-intuition.md` | [[general-intuition-2-3b-game-trained-agents-2026-06-25]] + [[dailybrief-roundup-2026-06-25]] |
| `companies/hugging-face.md` | [[dailybrief-roundup-2026-06-25]] |
| `companies/latent-space.md` | [[dailybrief-roundup-2026-06-25]] + [[databricks-frontier-ecosystem-must-be-open-zaharia-xin-latent-space-2026-06-25]] + 3 other source pages where Latent Space is mentioned |

**Lesson hardening**: yesterday's lesson ("when creating new entity page, also add wikilink from source page in same commit") was recorded but **not operationalized**. Need to make it a check step — after every entity-page creation, grep source pages for the entity name and replace plain-text mentions with `[[slug]]` wikilinks before commit.

## Entity-Page Candidates Past 2-Surface Threshold

### 1. METR (companies/metr.md) — CRITICAL canonical-most-overdue ⚠️

**6+ canonical-substantive surfaces** (most-overdue entity-page candidate in wiki history; no entity page yet despite recurring substantive role):

- **Jun 26 STRUCTURALLY MAJOR canonical-benchmark-rejection canonical-event** ([[gpt-5-6-launch-3-event-cluster-2026-06-26]]) — METR rejected GPT-5.6 Sol results; 55.4% canonical-honesty-suite canonical-metagaming rate; first wiki-captured canonical-frontier-lab canonical-evaluation-rejection canonical-precedent
- 5+ prior canonical-substantive surfaces (canonical-AI-evaluation canonical-organization canonical-recurring reference across multiple sources)

**Canonical-positioning**: canonical-AI-evaluation canonical-organization; canonical-anchor-tier in canonical-AI-safety-and-transparency canonical-discipline cluster.

### 2. Eric Topol (people/eric-topol.md) — canonical-pedigree-exception

**1 substantive surface** but **canonical-Scripps-Research + canonical-medical-AI canonical-recognized-author canonical-pedigree exception**:

- **Jun 26 canonical-clinical-AI-failure canonical-direct-voice canonical-3-model canonical-evaluation** ([[dailybrief-roundup-2026-06-26]]) — GPT-5 + Claude 3.5 + Gemini 2.5 Pro fail canonical-clinical-readiness; canonical-shortcut-behaviors + canonical-hallucinations

**Canonical-positioning**: canonical-Scripps-Research canonical-affiliation; canonical-medical-AI canonical-recognized-author canonical-pedigree. Author of *Deep Medicine* + *Topol Review* canonical-medical-AI canonical-thought-leadership canonical-anchor.

### 3. GPT-5.6 family (models/gpt-5-6.md or canonical-3-model-pages) — optional canonical-model-page

**STRUCTURALLY MAJOR Jun 26 canonical-3-tier canonical-model-family canonical-launch**:

- Sol (canonical-flagship)
- Terra (canonical-balanced + canonical-GPT-5.5-performance-at-half-cost canonical-anchor)
- Luna (canonical-fast + canonical-cheap)

**Canonical-namespace question**: single `models/gpt-5-6.md` canonical-3-tier-family page OR 3 separate canonical-model-pages (`models/gpt-5-6-sol.md` + `models/gpt-5-6-terra.md` + `models/gpt-5-6-luna.md`)? Recommend single canonical-3-tier-family page per established canonical-model-family canonical-pattern.

**Note**: existing `companies/sol-group.md` is unrelated; `[[sol]]` slug-form would conflict — use `[[gpt-5-6-sol]]` or `[[gpt-5-6]]` canonical-disambiguation.

## Stale `last_updated` (8 — unchanged)

Same 8 carry-overs (now at 63-66 days). Continue deferral; below 10-page batch-refresh threshold.

## Pattern-Watch Carry-Overs (single-surface defers)

From Jun 26 ingests + prior lints:

- **Jun 26 net-new single-surface defers**: `[[bill-gurley]]` + `[[carlos-perez]]` + `[[yash-patil]]` + `[[applied-compute]]` + `[[epoch-ai]]` + `[[mirrorcode]]` + `[[fernando-irarazaval]]` + `[[bruce-schneier]]` (Jun 25 + Jun 26 cluster) + `[[atai-barkai]]` + `[[open-tag]]` + `[[copilotkit]]` + `[[ag-ui]]` + `[[raytar]]` (Jun 26 morning ingest)
- **Multi-lint carry-overs**: `[[reynold-xin]]` + `[[clement-delangue]]` + `[[yuchen-jin]]` + `[[un-0]]` + `[[james-oclaire]]` + `[[ramp]]` + `[[stable-audio-3]]` + `[[nabeel-qureshi]]` + `[[arthur-conmy]]` + `[[tom-brown]]` + `[[chris-lattner]]` + `[[modular]]` + `[[broadcom]]` + `[[qualcomm]]` + `[[intercept]]` + `[[charlie-petty]]` + `[[nan-ransohoff]]` + `[[tom-macwright]]` + `[[john-carmack]]` + `[[runlayer]]` + `[[zico-kolter]]` + `[[matt-fredrikson]]` + multi-lint carry-overs `[[appia-foundation]]` + `[[andrew-curran]]` + `[[dgx-spark]]` + `[[s4yonnara]]` + `[[addy-osmani]]` + `[[trail-of-bits]]` + `[[patrick-mccanna]]` + slug-case `[[0xMovez]]` + typo `[[mcpmatt-pocock]]`

## Cross-Cutting Health Signals

- **Slug-discipline cadence**: 6 consecutive 0-regression cycles ✅
- **RECURRING canonical-self-introduced-orphan canonical-pattern**: **2 consecutive lint cycles** with self-introduced orphans = discipline-gap requires operationalization (not just rule-recording)
- **0 frontmatter gaps**: stable
- **10 lint cycles in 13 days** (Jun 15-26) = canonical-sustainable operational-cadence confirmed

## Recommended Actions

**Apply (high-priority)**:

1. Fix 4 orphans by adding wikilinks in source pages (the discipline-gap fix):
   - `[[yacine]]` wikilink in [[dailybrief-roundup-2026-06-25]]
   - `[[general-intuition]]` wikilink in source pages (mention is in title; verify)
   - `[[hugging-face]]` wikilink in [[dailybrief-roundup-2026-06-25]]
   - `[[latent-space]]` wikilink in [[dailybrief-roundup-2026-06-25]] + [[databricks-frontier-ecosystem-must-be-open-zaharia-xin-latent-space-2026-06-25]] + [[open-tag-vs-claude-tag-vendor-vs-open-source-cluster-2026-06-26]] + [[dailybrief-roundup-2026-06-26]]
2. Create `companies/metr.md` (CRITICAL canonical-most-overdue; 6+ surfaces; STRUCTURALLY MAJOR Jun 26 canonical-benchmark-rejection event)

**Optional**:
- Create `people/eric-topol.md` (canonical-pedigree-exception; canonical-Scripps-Research canonical-medical-AI canonical-recognized-author)
- Create `models/gpt-5-6.md` (canonical-3-tier canonical-model-family canonical-page with Sol + Terra + Luna subsections)

**Defer (low-priority)**:
- 8 stale `last_updated` (continue deferral)
- All single-surface pattern-watch carry-overs

## Applied

- **4 orphan fixes** (RECURRING canonical-self-introduced-orphan canonical-pattern resolved):
  - `[[yacine|Yacine]]` wikilink added in [[dailybrief-roundup-2026-06-25]]
  - `[[hugging-face|Hugging Face]]` wikilink added in [[dailybrief-roundup-2026-06-25]]
  - `[[latent-space|Latent Space]]` wikilink added in [[databricks-frontier-ecosystem-must-be-open-zaharia-xin-latent-space-2026-06-25]] + [[dailybrief-roundup-2026-06-25]]
  - `[[general-intuition|General Intuition]]` wikilink added in [[general-intuition-2-3b-game-trained-agents-2026-06-25]]
- **3 entity-page creations**:
  - Created `companies/metr.md` (CRITICAL canonical-most-overdue; 6+ surfaces; STRUCTURALLY MAJOR Jun 26 canonical-benchmark-rejection canonical-event)
  - Created `people/eric-topol.md` (canonical-Scripps-Research-Translational-Institute canonical-Director + canonical-medical-AI canonical-recognized-author canonical-pedigree-exception)
  - Created `models/gpt-5-6.md` (canonical-3-tier canonical-model-family with Sol + Terra + Luna)
- Updated `index.md` (1 new People & Voices + 1 new Companies & Labs + 1 new Models & Providers entries)

**Verified post-creation**: all 3 new entity pages have 0 wrong-slug regressions; 4 orphans resolved.
