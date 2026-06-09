---
type: meta
title: "Lint Report 2026-06-08 pt3"
created: 2026-06-08
updated: 2026-06-08
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-08 pt3

## Summary

- **Pages scanned**: 463 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0** (same 7 candidates as prior lints — meta files / owner path-form / ephemeral cruft)
- **Real fixable**: **6 typo regressions** (`anthropic-xai-colossus-2026-05` → `willison-anthropic-xai-colossus-2026-05` across 2 pt5 source files) + **1 carry-over typo** (claude-opus-4-6 in log.md)
- **Unprocessed `_raw/` drops**: **1** (`Your Agent Harness Should Repair Itself` by @akshay_pachaar, 2026-06-08)
- **New single-source defers from pt5 + pt6**: 5 (companies/google, companies/intel, martin-alderson, greg-isenberg, theo-tabah)
- **Lint branch**: `lint/2026-06-08-pt3`

**Wiki health remains structurally clean.** 0 orphans / 0 frontmatter gaps / 0 stale. The pt5 ingest introduced 6 typo-regression instances (single typo, repeated 6× across 2 source pages). Fixable.

### Net delta vs `lint-report-2026-06-08-pt2`

| Metric | pt2 | pt3 | Δ |
|---|---|---|---|
| Total pages | 455 | **463** | +8 (pt5 +5 sources + pt6 +2 sources + pt6 +1 entity page = +8) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 0 | **6** | +6 (all `anthropic-xai-colossus-2026-05` → `willison-anthropic-xai-colossus-2026-05`) |
| Unprocessed `_raw/` drops | 0 | **1** | +1 |

## Dead Links

### Typo regressions — REAL FIXABLE (6 occurrences / 1 unique target / 2 files)

**Single typo introduced in pt5**, repeated 6 times across 2 source files:

| Wrong slug | Correct slug | Files | Instances |
|---|---|---|---|
| `[[anthropic-xai-colossus-2026-05]]` | `[[willison-anthropic-xai-colossus-2026-05]]` | sources/google-intel-3m-tpus-2028-2026-06-08.md (4× lines 11, 36, 54, 61) + sources/alderson-xai-datacentre-reit-pivot-2026-06-08.md (2× lines 34, 61) | **6** |

**Fix**: `sed`-replace all 6 occurrences. Same-class typo as previously-fixed `[[willison-anthropic-xai-colossus-2026-05]]` in past lint — original-slug ambiguity persists; need wiki-side convention enforcement (always use `willison-` prefix for Willison-surfaced events).

### Single-source defers — new from pt5 + pt6 (5 unique / 5 occurrences) — no action

| Target | Refs | Source | Status |
|---|---|---|---|
| `[[companies/google]]` | 1 | [[google-intel-3m-tpus-2028-2026-06-08]] | Defer entity page — single-surface; companies/google.md would be a major-entity creation, deserves multi-source corroboration first |
| `[[companies/intel]]` | 1 | [[google-intel-3m-tpus-2028-2026-06-08]] | Same — defer |
| `[[martin-alderson]]` | 1 | [[alderson-xai-datacentre-reit-pivot-2026-06-08]] | Defer — single substantive surface |
| `[[greg-isenberg]]` | 1 | [[gregisenberg-theo-tabah-ai-native-masterclass-2026-06-08]] | Defer — single substantive surface |
| `[[theo-tabah]]` | 1 | [[gregisenberg-theo-tabah-ai-native-masterclass-2026-06-08]] | Defer — single substantive surface |

### Borderline candidates (3 unique / ~14 occurrences) — unchanged from prior lint

- `[[biohub]]` (5 refs, intra-cluster) — defer until 2nd substantive event
- `[[kasra]]` (6 refs, slug verification-pending — too generic) — owner discretion
- `[[charity-majors]]` (3 refs, Willison-quoted pattern) — defer

### Single-source carry-overs (5 unique / 7 occurrences) — no action

`[[alex-imas]]` (2), `[[phil-trammell]]` (2), `[[emanuel-maiberg]]` (1), `[[elon-musk]]` (1), `[[rohan-paul]]` (1)

### Typo regression — carry-over (1 unique / 1 occurrence) — REAL FIXABLE

`[[claude-opus-4-6]]` in log.md historical entry — carry-over from prior lints; still deferred per owner discretion.

### Intentional / false positives (~14 occurrences) — no action

Unchanged structural patterns from prior lints (claude / concept / Daily Briefs path refs / LLM Wiki Pattern teaching example / wikilink + Page Name in obsidian.md code blocks / agi-debate.canvas / meta/lint-report-2026-05-11 archival self-ref).

## Unprocessed `_raw/` Drops

**1 net-new drop since prior lint** — flagged for next ingest:

| File | Author | Description |
|---|---|---|
| `_raw/Your Agent Harness Should Repair Itself.md` | @akshay_pachaar | First wiki-tracked @akshay_pachaar surface on **self-repairing agent harness** — pairs structurally with [[loop-engineering]] + [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn synthesis]] + [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger push-back primitive]] at the **harness-self-repair primitive layer**. Worth ingesting — load-bearing for Loop Engineering register evolution (June 8 2026) |

## Frontmatter Gaps

**0 issues.** All 463 pages pass frontmatter check.

## Stale `last_updated`

**0 issues.** Today 2026-06-08; 60-day threshold 2026-04-09.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-90-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-08-pt3`

## Recommended Fixes

### Required (6 typo regressions)
1. `[[anthropic-xai-colossus-2026-05]]` → `[[willison-anthropic-xai-colossus-2026-05]]` × 6 occurrences across:
   - `sources/google-intel-3m-tpus-2028-2026-06-08.md` (lines 11, 36, 54, 61)
   - `sources/alderson-xai-datacentre-reit-pivot-2026-06-08.md` (lines 34, 61)

### Optional (housekeeping)
1. **Delete `Untitled.md` + `Untitled 1.md`** at vault root (still untracked carry-over)
2. **Fix `[[claude-opus-4-6]]` typo** in log.md historical entry (carry-over)
3. **Process `_raw/Your Agent Harness Should Repair Itself.md`** — flagged for next ingest

## Overall Posture

Wiki health structurally clean. The pt5 + pt6 ingest pair added 8 pages with **no new orphans / no frontmatter gaps / no stale dates** — but introduced **6 typo-regression instances of the same wrong slug** (a single typo copy-pasted 4× in one source + 2× in another). Same-class regression as `lint-report-2026-06-06`'s 4-typo batch; suggests **pattern-watch for next ingest**: any cross-reference to *xAI Colossus* or *Anthropic xAI Colossus* events should use the canonical `willison-anthropic-xai-colossus-2026-05` slug (the `willison-` prefix is required since the source page is the Willison surfacing, not an Anthropic primary).

**Tracking for next lint**:
- `[[greg-isenberg]]` 2-surface threshold (1 → 2 watch)
- `[[martin-alderson]]` 2-surface threshold (1 → 2 watch)
- `[[rohan-paul]]` 2-surface threshold (still at 1)
- `[[companies/google]]` + `[[companies/intel]]` — multi-source corroboration before entity-page creation
- @akshay_pachaar entity page if 2nd substantive surface appears

## Applied Fixes (2026-06-08)

Per owner review, applied **the 6-typo regression fix** (only). Other items deferred.

1. ✅ **6× `[[anthropic-xai-colossus-2026-05]]` → `[[willison-anthropic-xai-colossus-2026-05]]`** across:
   - `sources/google-intel-3m-tpus-2028-2026-06-08.md` (4× lines 11, 36, 54, 61)
   - `sources/alderson-xai-datacentre-reit-pivot-2026-06-08.md` (2× lines 34, 61)

**Post-fix dead-link count**: 6 typo-regression occurrences → 0. The unique dead-link target `anthropic-xai-colossus-2026-05` is fully eliminated.

**Deferred per owner**:
- @akshay_pachaar "Your Agent Harness Should Repair Itself" _raw drop — flagged for next ingest
- `Untitled.md` + `Untitled 1.md` cruft deletion
- `[[claude-opus-4-6]]` log.md typo (multi-lint carry-over)
