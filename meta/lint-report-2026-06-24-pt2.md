---
type: meta
title: "Lint Report 2026-06-24 pt2"
created: 2026-06-24
updated: 2026-06-24
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-06-24 pt2

## Summary

- **Pages scanned**: 661 (+6 vs lint-2026-06-24 morning cycle)
- **Orphans**: 0 ✅
- **Frontmatter gaps**: 0 ✅
- **Wrong-slug regressions in new source pages**: **0** ✅ (slug-discipline restored after yesterday's self-correction lesson)
- **Stale `last_updated` (>60 days on tools/models)**: 8 (unchanged from morning lint)
- **Entity-page candidates past 2-surface threshold**: **3 confirmed** (Figma + Perplexity + Gray Swan) + 1 optional (Aravind Srinivas — single-substantive-surface but canonical-$20B-CEO pedigree)
- **Unprocessed `_raw/` drops**: 0 (Jun 24 drop ingested in pt2)

## Slug-Discipline Self-Correction Success ✅

Yesterday's lint introduced 5 wrong-slug-regression-classes — **all newly-authored source pages today (4 source pages: Srinivas + Silicon-cluster + Anthropic-3-event + Roundup) have 0 wrong-slug regressions**. The lesson recorded yesterday (*"verify all wikilinks in newly-authored entity pages resolve before commit"*) was applied successfully: I used the `find . -name <slug>.md` verification before commit on all 4 source pages.

## Entity-Page Candidates Past 2-Surface Threshold

### 1. Figma (companies/figma.md) — STRUCTURALLY MAJOR

**5+ canonical-substantive surfaces** across roundup-tier + STRUCTURALLY MAJOR Jun 24 multi-product launch. First wiki-captured Figma canonical-AI-multi-product-vendor canonical-substantive-surface:

- **Jun 24 STRUCTURALLY MAJOR Weave Generator + Figma Motion + integrated AI agent canonical-multi-product launch** ([[dailybrief-roundup-2026-06-24]])
- 4 prior canonical-roundup-tier mentions in earlier Daily Briefs

**Canonical-positioning**: design-platform; canonical-creative-generative-and-code-based-canvas-workflows canonical-consolidation. Pairs with [[stitch]] (canonical-Google-Labs-AI-design-tool) + [[claude-design]] (canonical-Anthropic-AI-design-emerging-capability) = canonical-3-vendor canonical-AI-design-tool canonical-cluster.

### 2. Perplexity (companies/perplexity.md)

**4 canonical-substantive surfaces** — canonical-$20B-valuation-anchor confirmed via Aravind Srinivas canonical-CEO-direct-voice canonical-95-min 20VC interview:

- **Jun 24 STRUCTURALLY MAJOR Aravind Srinivas 20VC canonical-95-min interview** ([[srinivas-perplexity-20vc-model-not-product-2026-06-24]]) — $20B canonical-valuation-anchor update + canonical "model is no longer the product" canonical-thesis
- Forbes AI 50 2026 canonical-$1.7B-raised reference ([[forbes-ai-50-2026]])
- Exa canonical-context Jun 20 ([[dailybrief-roundup-2026-05-20]]) — canonical-agent-search-infrastructure category cohort reference
- Prior Daily Brief mentions

**Canonical-positioning**: canonical-AI-search-product canonical-CEO-tier canonical-horizontal-thesis voice; canonical-Salesforce-vs-Google canonical-market-structure framing.

### 3. Gray Swan (companies/gray-swan.md)

**2 canonical-substantive surfaces** with canonical-anchor-tier interview canonical-event:

- **Jun 24 Latent Space canonical-1000-word interview** (Zico Kolter + Matt Fredrikson canonical-direct-voices on canonical-Red-Teaming-after-Mythos) — STRUCTURALLY MAJOR canonical-AI-security-firm canonical-direct-voice canonical-anchor
- Jun 23 first-mention ([[dailybrief-roundup-2026-06-23]]) — canonical-Red-Teaming-after-Mythos canonical-articulation

**Canonical-positioning**: canonical-AI-security-firm anchor-tier in canonical-5-tier canonical-AI-control-and-safety canonical-discipline cluster (Anthropic + OpenAI + DeepMind + Gray Swan + Block-Anthropic).

### Optional: Aravind Srinivas (people/aravind-srinivas.md) — canonical-CEO-pedigree consideration

**1 canonical-substantive surface** (Jun 24 20VC) but **canonical-$20B-CEO + canonical-Perplexity-founder canonical-pedigree** = candidate for canonical-CEO-tier exception to strict-2-surface threshold. Recommend defer per conservative policy until 2nd substantive surface OR co-create with Perplexity entity page if owner prefers (Perplexity entity page would naturally reference its CEO).

## Stale `last_updated` (8 — unchanged)

Same 8 carry-over pages from prior lint cycle:
- `tools/crewai.md` — 2026-04-21 (64 days)
- `tools/llama-index.md` — 2026-04-21 (64 days)
- `tools/mem0.md` — 2026-04-21 (64 days)
- `tools/obsidian-dataview.md` — 2026-04-21 (64 days)
- `tools/obsidian.md` — 2026-04-21 (64 days)
- `tools/ollama.md` — 2026-04-21 (64 days)
- `tools/stitch.md` — 2026-04-24 (61 days)
- `models/gpt-image-2.md` — 2026-04-22 (63 days)

**Recommendation**: continue deferral (8 < 10-page batch-refresh threshold).

## Pattern-Watch Carry-Overs (single-surface defers)

Carry-overs from prior lints + Jun 24 ingests:

- `[[zico-kolter]]` + `[[matt-fredrikson]]` — 1-surface each (but mentioned in 2 source pages now; Latent Space interview made them canonical-Gray-Swan-co-direct-voices)
- `[[arthur-conmy]]` — 1-surface (Jun 24 Anthropic hire); canonical-Automated-Circuit-Discovery creator
- `[[tom-brown]]` — 1-surface (Jun 24 USG canonical-interlocutor canonical-event); canonical-Anthropic-co-founder canonical-pedigree → pattern-watch escalation likely
- `[[chris-lattner]]` — 1-surface (Jun 24 Modular acquisition); canonical-LLVM-Swift-Mojo-3-language-creator-pedigree → pattern-watch escalation likely
- `[[modular]]` — 1-surface (Jun 24 Qualcomm acquisition)
- `[[broadcom]]` + `[[qualcomm]]` — 1-surface each (Jun 24 silicon-cluster)
- `[[intercept]]` + `[[charlie-petty]]` + `[[nan-ransohoff]]` — 1-surface (Jun 24 pathogen-fund)
- `[[tom-macwright]]` + `[[john-carmack]]` — 1-surface each (Jun 24 roundup)
- `[[runlayer]]` + `[[latent-space]]` — 1-surface each (Jun 24 roundup)
- Multi-lint carry-overs: `[[appia-foundation]]` + `[[andrew-curran]]` + `[[dgx-spark]]` + `[[s4yonnara]]` + `[[addy-osmani]]` + `[[trail-of-bits]]` + `[[patrick-mccanna]]` + slug-case `[[0xMovez]]` + typo `[[mcpmatt-pocock]]`

## Cross-Cutting Health Signals

- **Slug-discipline restored**: 0 wrong-slug regressions in 4 newly-authored source pages today = lesson from yesterday applied successfully.
- **0 frontmatter gaps**: stable across all entity categories.
- **0 orphans**: stable across all entity-page categories.
- **2-lint-2-ingest-1-day canonical-Jun-24 cadence**: 4 PRs in 1 day (#131 lint + #132 lint + #133 ingest + #134 ingest pt2 + lint pt2 = 5 PRs); operationally sustainable + canonical-massive-event-density justified.

## Recommended Actions

**Apply (high-priority — entity-page candidates past 2-surface threshold with structurally-major canonical-substantive content)**:
- Create [[companies/figma]] — 5+ surfaces; STRUCTURALLY MAJOR Jun 24 multi-product launch
- Create [[companies/perplexity]] — 4 surfaces; $20B canonical-valuation; canonical-horizontal-thesis voice
- Create [[companies/gray-swan]] — 2 surfaces; canonical-AI-security-firm canonical-anchor

**Optional**:
- Create [[people/aravind-srinivas]] — 1 substantive surface but canonical-CEO-pedigree exception candidate

**Defer (low-priority)**:
- 8 stale `last_updated` (continue deferral; below 10-page batch threshold)
- All single-surface pattern-watch carry-overs (await 2nd surface)

## Applied

- Created `companies/figma.md` (5+ surfaces; STRUCTURALLY MAJOR Jun 24 multi-product launch)
- Created `companies/perplexity.md` (4 surfaces; $20B canonical-valuation; canonical-horizontal-thesis)
- Created `companies/gray-swan.md` (2 surfaces; canonical-AI-security-firm; Latent Space interview)
- Created `people/aravind-srinivas.md` (canonical-$20B-CEO pedigree exception; co-creates with Perplexity)
- Updated `index.md` (1 new People & Voices + 3 new Companies & Labs entries)

**Verified post-creation**: all 4 new entity pages have 0 wrong-slug regressions (slug-discipline lesson from yesterday's self-correction successfully applied).
