---
type: meta
title: "Lint Report 2026-06-15"
created: 2026-06-15
updated: 2026-06-15
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-15

## Summary

- **Pages scanned**: 515 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Real fixable**: **3 wrong-slug / fabricated-slug fixes** (`[[models/claude-mythos-5]]` → `[[claude-mythos]]`; backtick-quote `[[concepts/skill-md]]`; backtick-quote `[[you-dont-need-100-hours-claude-7-setups]]`)
- **Unprocessed `_raw/` drops**: **0** net-new
- **Lint branch**: `lint/2026-06-15`

**Wiki health structurally excellent**. 0 orphans / 0 frontmatter gaps / 0 stale dates across 515 pages (+11 from prior lint). The 2026-06-14 + 2026-06-15 + 2026-06-15-pt2 ingest sequence landed cleanly with only 3 wrong-slug regressions from my own recent ingests. **All other dead-link tokens are single-source defers (conservative entity-creation policy) + structural false-positives (trailing-backslash table-cell-escape artifacts + path-form-resolves-correctly + backtick-quoted historical-narrative + teaching-example refs)**.

### Net delta vs `lint-report-2026-06-14`

| Metric | pt14 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 504 | **515** | +11 (5 lint-applied pages + 6 ingest source pages over 2 days) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 2 (concepts/agentic-coding + concepts/hallucination) | **3** (models/claude-mythos-5 + concepts/skill-md + you-dont-need-100-hours) | +1 (all from my own 2026-06-14-pt2 + 2026-06-15 + 2026-06-15-pt2 ingest cadence) |
| New entity-page candidates past 2-surface threshold | 4 (andy-jassy + shane-legg + matei-zaharia + sarah-guo; all created) | **0** | -4 (no new 2-surface candidates; conservative policy held) |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Dead Links

### Wrong-slug / fabricated-slug fixes — REAL FIXABLE (3 occurrences / 3 sources)

| Wrong | Correct | File | Note |
|---|---|---|---|
| `[[models/claude-mythos-5]]` | `[[claude-mythos]]` | sources/dario-policy-on-ai-exponential-via-mehta-2026-06-11.md (line 95) | Wrong slug — model page is `claude-mythos.md` (Mythos = internal-tier umbrella) not `claude-mythos-5` (which would be a non-existent variant) |
| `[[concepts/skill-md]]` | `` `[[concepts/skill-md]]` `` | sources/zodchii-4-agent-claude-code-roster-2026-06-14.md (lines 32 + 80) | No `concepts/skill-md.md` page exists. Closest existing: [[writing-claude-code-skills]] (tutorial). Backtick-quote per established convention; defer concept-page until 2nd substantive concept-focus surface |
| `[[you-dont-need-100-hours-claude-7-setups]]` | `` `[[you-dont-need-100-hours-claude-7-setups]]` `` | sources/zodchii-4-agent-claude-code-roster-2026-06-14.md (line 55) | Fabricated slug — no source page exists for the "100-hours-claude-7-setups" practitioner-content. Raw file exists at `_raw/You Don't Need 100 Hours...md` but was never ingested as a source page. Backtick-quote per established convention |

### Past 2-surface threshold — entity pages worth creating

**None this lint**. The 2026-06-14 + 2026-06-15 + 2026-06-15-pt2 ingests yielded 30+ new single-source entity-page candidates, but no 2nd-substantive-surface promotions for any of them yet. Conservative entity-creation policy holds.

### Single-source entity-page defers — new from 2026-06-14 + 2026-06-15 + 2026-06-15-pt2 ingest sequence (24 unique / 24 occurrences) — no action

Conservative entity-creation policy applies (defer until 2nd substantive surface):

**From 2026-06-15 + pt2 ingests (12 net-new)**:
- `[[salesforce]]`, `[[fin]]`, `[[marc-benioff]]` (Salesforce-Fin $3.6B acquisition)
- `[[pleias]]`, `[[pierre-carl-langlais]]` (Europe-ecosystem-deficiency framing)
- `[[ben-thompson]]`, `[[stratechery]]` (safety-superpower thesis + adversarial-skeptic counter-read)
- `[[arvind-narayanan]]`, `[[sayash-kapoor]]` (AI-as-evolution-not-extinction counter-frame)
- `[[cartesia]]`, `[[gemma]]`, `[[jia-bin-huang]]` (brief-tier surfaces)

**From 2026-06-15 ingest (12 net-new)**:
- `[[karl-mehta]]`, `[[trustmodel-ai]]` (Dario "Policy on the AI Exponential" secondary source)
- `[[brendon-burchard]]`, `[[tom-ballard]]`, `[[lore]]`, `[[werner-kasselman]]`, `[[alien-org]]` (Levie-Nadella thread comment-thread voices)
- `[[simi]]`, `[[sudip-rokaya]]`, `[[hermes-agent]]`, `[[teknium]]`, `[[ralph-miller]]` (Sudip-Simi explainer thread)

### Carry-over single-source entity-page defers from prior lints (~45 unique / ~45 occurrences) — no action

Carry-overs unchanged from [[meta/lint-report-2026-06-14|prior lint]]: deepmind, mistral, theker, charity-majors (3 refs), qwen, microsoft, deepseek, kpmg, india, manus, llama, gemma (now 2nd surface candidate via Gemma 4 arXiv 2606.13705 — pattern-watch escalation), apple, cohere, amazon, trump, opik, evo, ona, aria, extropic, biohub, kasra, dxc, allenai, lm-studio, z-ai, minimax, moonshot-ai, gabriel-petersson, matt-clifford, mcpmatt-pocock (typo carry-over: should be `[[matt-pocock]]`), nick-frosst, omnigent, prometheus, rohan-paul, river-ai, sequent, spectnfa, tejas-kumar, tensorzero, theo-tabah, thepremiseofit, geoffrey-irving, guillaume-verdon, igor-babuschkin, jeremy-howard, lucianw, malay-hazarika, martin-alderson, phil-trammell, alex-imas, emanuel-maiberg, alok-bishoyi, 0xCodez, 0xwhrrari, aiedge

### Path-form persistent dead-links — false positives

- `[[meta/lint-report-2026-06-14]]`, `[[meta/lint-report-2026-06-13]]`, `[[meta/lint-report-2026-05-11]]` — EXIST as path-form refs (resolve correctly); scanner false positives
- `[[concepts/hallucination]]` — 1 ref via backtick-quoted form (`` `[[concepts/hallucination]]` ``) in [[kpmg-pulls-ai-report-hallucinations-2026-06-13]] line 61 — backtick-quoting is the established convention; scanner false-positive
- `[[concepts/agentic-coding]]` — 0 refs (fixed in prior lint to `[[agentic-engineering]]`)

### Path-form trailing-backslash table-cell-escape artifacts (~25 occurrences) — false positives

Unchanged from prior lint: wikilinks inside markdown table cells use `\|` to escape pipes (e.g., `[[slug\|alias]]`), causing regex scanner to capture trailing `\`. Not real dead-links. No action.

### Backtick-quoted historical-narrative refs — false positives (multi-lint carry-over)

Unchanged from prior lint: `` `[[claude-opus-4-6]]` `` + `` `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` `` + `` `[[theker]]` `` (after Jun 14 lint backtick-fix) + `` `[[concepts/hallucination]]` `` (after Jun 14 lint backtick-fix) — all log.md / source-narrative backtick-quoted; established convention; no action.

### Teaching-example / structural false positives (~14 occurrences) — no action

Unchanged structural patterns: `[[claude]]` / `[[concept]]` / `[[wikilink]]` / `[[wrong-slug]]` / `[[Page]]` (teaching examples); `[[Daily]]` (path-form × 5); `[[index]]` + `[[index.md]]` (self-refs); `[[agi-debate.canvas]]` (canvas file); `[[anthropic-xai-colossus-2026-05]]` (log.md archival fix-narrative).

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**. Most-recent `_raw/` drops all already-ingested via Jun 14 + Jun 15 ingest cadence:
- `Post by @sudiprokaya on X.md` (Jun 15) → ingested via [[sudip-rokaya-simi-explainer-2026-06-15]]
- `Post by @levie on X 1.md` (Jun 14) → ingested via [[levie-nadella-cognitive-loop-thread-2026-06-14]]
- `Dario Amodei AI Assurance Is Now Non-Negotiable.md` (Jun 14) → ingested via [[dario-policy-on-ai-exponential-via-mehta-2026-06-11]]
- `How to Build a Claude Code Team...md` (Jun 15) → ingested via [[zodchii-4-agent-claude-code-roster-2026-06-14]]
- Older drops all already-ingested or explicitly skipped per prior lints

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-106-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-15`

## Recommended Fixes

### Required (3 wrong-slug / fabricated-slug fixes — all from my own recent ingests)

1. **Fix `[[models/claude-mythos-5]]` → `[[claude-mythos]]`** in `sources/dario-policy-on-ai-exponential-via-mehta-2026-06-11.md` line 95 (model page is `claude-mythos.md`)
2. **Backtick-quote `[[concepts/skill-md]]`** → `` `[[concepts/skill-md]]` `` in `sources/zodchii-4-agent-claude-code-roster-2026-06-14.md` (2 occurrences: lines 32 + 80) — no canonical page exists; defer
3. **Backtick-quote `[[you-dont-need-100-hours-claude-7-setups]]`** → `` `[[you-dont-need-100-hours-claude-7-setups]]` `` in `sources/zodchii-4-agent-claude-code-roster-2026-06-14.md` line 55 — fabricated slug; defer

### Optional (pattern-watch flags for next lint)

- `[[gemma]]` 2nd substantive surface (Gemma 4 arXiv 2606.13705 = 1st substantive + carry-over context = pattern-watch escalation)
- `[[salesforce]]` + `[[marc-benioff]]` 2nd substantive surface watch (tier-1 enterprise-incumbent voices)
- `[[arvind-narayanan]]` + `[[sayash-kapoor]]` 2nd substantive surface watch (Princeton AI-Snake-Oil voices)
- `[[ben-thompson]]` + `[[stratechery]]` 2nd substantive surface watch (load-bearing tech-analyst voice)
- `[[karl-mehta]]` + `[[trustmodel-ai]]` 2nd substantive surface watch (AI-assurance-infrastructure surface)
- `[[werner-kasselman]]` + `[[brendon-burchard]]` + `[[alien-org]]` 2nd substantive surface watch (Levie-Nadella comment-thread voices)
- `[[pleias]]` + `[[pierre-carl-langlais]]` 2nd substantive surface watch (EU-substrate-deficiency canonical-voices)
- `[[fin]]` 2nd substantive surface watch (post-acquisition tracking)
- Carry-over: `[[matt-clifford]]` + `[[gabriel-petersson]]` + `[[kpmg]]` + `[[india]]` + `[[manus]]` + Chinese-open-weight-vendor cluster
- Carry-over typo: `[[mcpmatt-pocock]]` → `[[matt-pocock]]`

## Overall Posture

Wiki health structurally excellent. The 2026-06-14 + 2026-06-15 + 2026-06-15-pt2 ingest sequence (4 days; 6 source pages; 30+ new single-source entity candidates) landed cleanly with **only 3 wrong-slug regressions all from my own ingests** (slug-discipline tightening recommended).

**Major narrative tracking now established**:
- **13-narrative-event 12-day Anthropic-USG-conflict crisis cluster** is **most-load-bearing wiki-tracked governance event of 2026-Q2 frontier-AI period** (extended from 9 to 13 via Jun 15 4-vector same-day cluster)
- **TIMELINE INVERSION HYPOTHESIS** (Axios "They screwed us" Jun 15 vs Dario "Policy on the AI Exponential" Jun 11) tracking established — verification-pending
- **3-bloc sovereign-AI debate cluster** (India + EU/Pleias + Anthropic-USG-side) tracking established
- **First wiki-captured tier-1-enterprise-SaaS-incumbent capital-deployment validation of agent-first product architecture** (Salesforce-Fin $3.6B)
- **8-voice Loop Engineering canonical cluster** now 9-voice candidate via Alien's *learning-loop-physical-location-test* framing

**Tracking for next lint**:
- Pattern-watch escalations per above
- Slug-discipline tightening (3 wrong-slug regressions all from my own ingests — pre-commit slug-verification step recommended)
- Continued conservative entity-creation policy
