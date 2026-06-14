---
type: meta
title: "Lint Report 2026-06-13 pt2"
created: 2026-06-13
updated: 2026-06-13
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-13 pt2

## Summary

- **Pages scanned**: 499 (no change from pt1)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0** (only meta files)
- **Unprocessed `_raw/` drops**: **0**
- **Dead-link targets**: 108 (no change — fixes landed cleanly; no new regressions introduced)
- **Lint branch**: `lint/2026-06-13-pt2`

**Wiki health structurally clean.** Confirmation lint after the pt1 lint fixes landed (PR #99) + the convention-establishing followup (PR #100). No new regressions. No required fixes.

### Net delta vs `lint-report-2026-06-13` (pt1)

| Metric | pt1 | pt2 | Δ |
|---|---|---|---|
| Total pages | 496 | **499** | +3 (elon-musk + google + intel entity pages from pt1 lint fix) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Dead-link targets | 109 | **108** | -1 (pt1 fixes closed dead-links; theker-85m + claude-opus-4-6 false-positives in lint-log persist as inert prose-references) |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Persistent false-positive dead-links — no action needed

The lint scanner uses raw regex matching on `[[...]]` syntax which doesn't distinguish backtick-quoted code references from actual wikilinks. The following slugs appear in lint-log historical entries as `` `[[wrong-slug]]` `` for narrative-preservation purposes; **Obsidian renders these as inline code, not as wikilinks**:

| Slug | Location | Note |
|---|---|---|
| `[[claude-opus-4-6]]` | log.md (lines 5, 30, 93 lint archival entries) | Inside backtick-quoted code per convention; Obsidian-rendered as code, not wikilink |
| `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` | log.md (line 5 lint archival entry) | Inside backtick-quoted code per pt1 followup convention |
| `[[anthropic-xai-colossus-2026-05]]` | log.md (line 21 lint archival entry) | Inside backtick-quoted code per convention |

**Recommendation**: leave these as-is. They're narrative-preservation artifacts within archival lint-log entries; modifying them would corrupt the historical-fix-narrative. The scanner's false-positive rate (~5 of 108 reported) is acceptable.

## Dead-link composition

Total **108 dead-link targets** break down as:

| Category | Approx count | Action |
|---|---|---|
| Path-form refs that resolve correctly via Obsidian path-resolution | ~24 | None — false positives at the scanner level (Obsidian handles `[[companies/google]]` correctly when `companies/google.md` exists) |
| Lint-prose backtick-quoted code references | ~5 | None — see above |
| Intentional / historical patterns (claude, concept, Daily Briefs/, LLM Wiki Pattern, wikilink, Page Name, agi-debate.canvas, meta/lint-report-2026-05-11) | ~14 | None — unchanged structural patterns |
| Single-source entity-page defers (pt7-pt13 ingest cadence + carry-overs) | ~50 | Pattern-watch — conservative entity-creation policy applies |
| Borderline candidates (biohub / kasra / charity-majors) | 3 | Pattern-watch |
| Companies/people single-surface candidates | ~12 | Pattern-watch |

**Net real fixable dead-links**: 0.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-100-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-13-pt2`

## Overall Posture

Wiki health structurally clean post-pt1-lint-fix sequence. The 5-day pt7-pt13 intensive ingest cadence (covering Loop Engineering canonical-vocabulary-formalization + Fable 5 launch + Anthropic-USG-conflict crisis cluster + 5-vendor capital-deployment cluster) landed cleanly with:

- **+27 pages** (472 → 499)
- **0 net new typo regressions** (1 introduced and fixed in pt1)
- **3 entity pages created in lint fix** (elon-musk + google + intel)
- **0 unprocessed `_raw/` drops**
- **No orphan / frontmatter / stale-date issues introduced**

**Tracking for next lint**:
- `[[andy-jassy]]` 2nd substantive surface (load-bearing watch)
- `[[shane-legg]]` 2nd substantive surface
- `[[matei-zaharia]]` 2nd substantive surface (Omnigent follow-up)
- `[[matt-clifford]]` 2nd substantive surface (ARIA Chair follow-up)
- `[[mistral]]` Series D confirmed announcement (currently rumored)
- Chinese-open-weight-vendor cluster (MiniMax + Moonshot AI + Z.ai) 2nd substantive surfaces each
- Any net-new `_raw/` drops or future Daily Briefs

**Convention established (pt1 + followup)**: when describing typo fixes in lint-log entries, use `` `[[wrong-slug]]` `` form (backtick-quoted code) for the typo slug to prevent re-introducing dead-links.

No required fixes this round.
