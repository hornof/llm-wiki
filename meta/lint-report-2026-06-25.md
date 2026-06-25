---
type: meta
title: "Lint Report 2026-06-25"
created: 2026-06-25
updated: 2026-06-25
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-06-25

## Summary

- **Pages scanned**: 671 (+10 vs lint-2026-06-24-pt2)
- **Orphans**: **1 NEW** (`companies/figma.md` — created yesterday but Jun 24 roundup source mentions "Figma" without wikilink)
- **Frontmatter gaps**: 0 ✅
- **Wrong-slug regressions in new source pages**: **0** ✅ (slug-discipline cadence continues — 4 consecutive cycles now)
- **Stale `last_updated` (>60 days on tools/models)**: 8 (unchanged)
- **Entity-page candidates past 2-surface threshold**: **4 confirmed** (Alibaba + Hugging Face + Latent Space + Yacine)
- **Unprocessed `_raw/` drops**: 0

## Slug-Discipline Cadence Continues ✅

**4 consecutive cycles** with 0 wrong-slug regressions (lint-2026-06-24 morning → lint-pt2 → ingest 06-25 source pages). Yesterday's self-correction lesson is now habituated.

## Orphan Repair (1)

`companies/figma.md` flagged as orphan — only inbound refs are in `index.md` + `log.md` (excluded from orphan check). The Jun 24 roundup source page mentions "Figma" by name in the Weave Generator + Figma Motion launch description but doesn't wikilink it. **Fix**: replace the plain-text "Figma" with `[[figma]]` wikilink in [[dailybrief-roundup-2026-06-24]].

## Entity-Page Candidates Past 2-Surface Threshold (4)

### 1. Alibaba (companies/alibaba.md) — STRUCTURALLY MAJOR

**7+ canonical-substantive surfaces** culminating in STRUCTURALLY MAJOR Jun 25 IP-dispute event:

- **Jun 25 STRUCTURALLY MAJOR Anthropic-Alibaba canonical-IP-dispute canonical-event** ([[anthropic-alibaba-claude-extraction-ip-dispute-2026-06-24]]) — canonical-IP-dispute-counterparty role
- **Jun 22 Alibaba-NLP DeepResearch canonical-open-source-agent-tier** ([[dailybrief-roundup-2026-06-22]]) — canonical-Chinese-open-source-AI cluster member
- 5+ prior canonical-roundup-tier mentions

**Canonical-positioning**: Chinese tech conglomerate; canonical-2-tier-positioning (canonical-open-source-research-tier via Alibaba-NLP DeepResearch + canonical-IP-dispute-counterparty via Claude extraction claim).

### 2. Hugging Face (companies/hugging-face.md)

**3 canonical-substantive surfaces** — canonical-$100M-ARR canonical-revenue-anchor confirmed Jun 25:

- **Jun 25 canonical-$100M-ARR + 97%-free-user canonical-business-model-data-point** ([[dailybrief-roundup-2026-06-25]]) — Clément Delangue canonical-CEO-direct-voice 1st substantive surface
- 2 prior canonical-substantive surfaces (foundation-tier canonical-open-source-AI canonical-platform reference)

**Canonical-positioning**: canonical-open-source-AI-platform canonical-foundation-tier; canonical-3% paid-conversion-rate canonical-business-model.

### 3. Latent Space (publications/latent-space.md or companies/latent-space.md) — TBD canonical-namespace

**2 canonical-substantive surfaces** in canonical-1-day-cadence:

- **Jun 25 canonical-Databricks Latent Space canonical-interview** ([[databricks-frontier-ecosystem-must-be-open-zaharia-xin-latent-space-2026-06-25]]) — Zaharia + Reynold Xin canonical-1000-word-tier interview
- **Jun 24 Gray Swan Latent Space canonical-1000-word-interview** ([[dailybrief-roundup-2026-06-24]]) — Zico Kolter + Matt Fredrikson canonical-direct-voices

**Canonical-positioning**: canonical-AI-research-podcast-and-newsletter canonical-publication; canonical-1000-word-interview canonical-format. **Namespace question**: place at `companies/latent-space.md` (publication-tier company) or new `publications/` namespace? Recommend `companies/` per existing pattern.

### 4. Yacine (people/yacine.md)

**2 canonical-substantive surfaces** + canonical-LLM-creative-writing canonical-debate canonical-anchor:

- **Jun 25 canonical-LLM-creative-writing canonical-debate with Nabeel S. Qureshi** ([[dailybrief-roundup-2026-06-25]]) — canonical-2012-TheStalwart canonical-historical canonical-context
- Prior canonical-substantive surface (verification-pending exact context)

**Canonical-positioning**: independent canonical-LLM-creative-writing canonical-voice; canonical-debate canonical-participant-tier.

## Stale `last_updated` (8 — unchanged)

Same 8 carry-over pages (now at 62-65 days). Continue deferral; below 10-page batch-refresh threshold.

## Pattern-Watch Carry-Overs (single-surface defers)

From Jun 24 + Jun 25 ingests + prior lints:

- `[[reynold-xin]]` (Jun 25 1-surface; Databricks-co-founder canonical-pedigree)
- `[[general-intuition]]` (Jun 25 1-surface BUT STRUCTURALLY MAJOR canonical-$2.3B-thesis-bet — canonical-CEO-pedigree-exception consideration)
- `[[clement-delangue]]` (Jun 25 1-surface; Hugging Face CEO direct-voice)
- `[[yuchen-jin]]` (Jun 25 1-surface; Databricks direct-voice)
- `[[un-0]]` (Jun 25 1-surface; canonical-Naveen-Rao-product-claim)
- `[[james-oclaire]]` (Jun 25 1-surface; canonical-open-weight-pricing-collapse essay)
- `[[ramp]]` (Jun 25 first substantive-executive-surface; multiple prior generic mentions)
- `[[stable-audio-3]]` (Jun 25 1-surface; canonical-audio-LoRA-substrate)
- `[[nabeel-qureshi]]` (Jun 25 1-surface; canonical-debate-participant)
- Carry-overs from prior lints: `[[arthur-conmy]]` + `[[tom-brown]]` + `[[chris-lattner]]` + `[[modular]]` + `[[broadcom]]` + `[[qualcomm]]` + `[[intercept]]` + `[[charlie-petty]]` + `[[nan-ransohoff]]` + `[[tom-macwright]]` + `[[john-carmack]]` + `[[runlayer]]` + `[[zico-kolter]]` (now mentioned in Gray Swan entity page; pattern-watch for 2nd surface) + `[[matt-fredrikson]]` (same) + multi-lint carry-overs `[[appia-foundation]]` + `[[andrew-curran]]` + `[[dgx-spark]]` + `[[s4yonnara]]` + `[[addy-osmani]]` + `[[trail-of-bits]]` + `[[patrick-mccanna]]` + slug-case `[[0xMovez]]` + typo `[[mcpmatt-pocock]]`

## Cross-Cutting Health Signals

- **Slug-discipline cadence**: 4 consecutive 0-regression cycles — yesterday's self-correction lesson now habituated.
- **0 frontmatter gaps**: stable.
- **9 lint cycles in 12 days** (Jun 15-25) = canonical-sustainable canonical-massive-event-density operational-cadence confirmed across consecutive days.
- **First wiki-captured canonical-self-introduced-orphan canonical-pattern**: yesterday's Figma entity-page-creation was made BEFORE the Jun 24 roundup was wikilinked to it. Lesson: when creating a new entity page that the most recent source page mentions, **also add wikilink from that source page to entity** in the same commit.

## Recommended Actions

**Apply (high-priority)**:
1. Fix orphan: add `[[figma]]` wikilink in [[dailybrief-roundup-2026-06-24]]
2. Create entity pages past 2-surface threshold:
   - `companies/alibaba.md` (7+ surfaces; STRUCTURALLY MAJOR canonical-IP-dispute-counterparty + canonical-Chinese-open-source-AI cluster)
   - `companies/hugging-face.md` (3 surfaces; canonical-$100M-ARR canonical-revenue-anchor)
   - `companies/latent-space.md` (2 surfaces; canonical-AI-research-podcast-and-newsletter canonical-publication)
   - `people/yacine.md` (2 surfaces; canonical-LLM-creative-writing canonical-debate canonical-voice)

**Optional**:
- `companies/general-intuition.md` (1 substantive surface but STRUCTURALLY MAJOR canonical-$2.3B canonical-thesis-bet canonical-CEO-pedigree-exception)

**Defer (low-priority)**:
- 8 stale `last_updated` (continue deferral)
- All single-surface pattern-watch carry-overs

## Applied

- Fixed orphan: added `[[figma|Figma]]` wikilink in [[dailybrief-roundup-2026-06-24]]
- Created `companies/alibaba.md` (7+ surfaces; STRUCTURALLY MAJOR canonical-IP-dispute-counterparty + canonical-Chinese-open-source-AI cluster)
- Created `companies/hugging-face.md` (3 surfaces; canonical-$100M-ARR canonical-revenue-anchor)
- Created `companies/latent-space.md` (2 surfaces; canonical-AI-research-podcast-and-newsletter canonical-publication)
- Created `people/yacine.md` (2 surfaces; canonical-LLM-creative-writing canonical-debate canonical-voice)
- Created `companies/general-intuition.md` (canonical-$2.3B-thesis-bet CEO-pedigree-exception)
- Updated `index.md` (1 new People & Voices + 4 new Companies & Labs entries)

**Verified post-creation**: all 5 new entity pages have 0 wrong-slug regressions; figma orphan resolved (verified via `find . -name <slug>.md` pre-commit per established canonical-discipline).
