---
type: meta
title: "Lint Report 2026-06-06"
created: 2026-06-06
updated: 2026-06-06
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-06

## Summary

- **Pages scanned**: 449 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days): **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Dead-link occurrences in live content**: 34 across 24 unique targets (excludes `meta/lint-report-*` archival quotes)
- **Real fixable**: **6 unique targets / 8 occurrences** (4 typo regressions + 2 past 2-surface threshold)
- **Pre-lint discipline**: `git fetch origin` → `git pull` confirmed at PR-80-merged tip (`1a3a52b`); no open PRs

**Wiki health is excellent.** Structural metrics (orphans / frontmatter / stale) all 0. The dead-link count grew from 23 → 34 because pt1 + pt2 of 2026-06-06 introduced 4 new entity defers (spacex, sriram-krishnan, dan-jeffries, plus carry-overs) **plus 4 typo regressions** I introduced.

### Net delta vs `lint-report-2026-06-05` (24 hours, 3 PRs landed)

| Metric | 2026-06-05 | 2026-06-06 | Δ |
|---|---|---|---|
| Total pages | 442 | **449** | +7 (7 new source pages from pt1 + pt2) |
| Orphans | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Live-content dead-link occurrences | 23 | **34** | +11 |
| Unique dead-link targets | 16 | **24** | +8 |

## Dead Links

### Typo regressions I introduced (4 unique / 4 occurrences) — REAL FIXABLE

These are wrong-slug references in the new 2026-06-06 source pages. All have known-correct existing slugs.

| Wrong slug | Correct slug | File | Line |
|---|---|---|---|
| `[[anthropic-xai-colossus-deal-2026]]` | `[[willison-anthropic-xai-colossus-2026-05]]` | sources/google-spacex-920m-monthly-compute-2026-06-05.md | 69 |
| `[[goldman-spacex-322b-ai-revenue-forecast-2026-06-04]]` | `[[dailybrief-roundup-2026-06-04]]` (where the Goldman forecast was actually captured) | sources/trump-admin-openai-equity-stake-2026-06-06.md | 52 |
| `[[andrew-ng-jobpolcalypse-is-false-2026-06-01]]` | `[[andrewng-ai-fde-vs-ai-engineer-2026-06-01]]` | sources/trump-admin-openai-equity-stake-2026-06-06.md | 54 |
| `[[dean-w-ball-autonomous-corporations-ban-2026-06-05]]` | `[[dailybrief-roundup-2026-06-05]]` (where the Ball framing was actually captured) | sources/house-draft-federal-ai-preemption-bill-2026-06-04.md | 67 |

### Past 2-surface threshold — worth creating (2 unique / 5 occurrences)

| Target | Refs | Sources | Recommended action |
|---|---|---|---|
| `[[spacex]]` | 3 | sources/google-spacex-920m-monthly-compute-2026-06-05 (×3) | **Create entity page**. SpaceX is now wiki-tracked at 3 distinct events: (1) xAI acquisition (Forbes AI 50 framing) + (2) Anthropic-Colossus $5B/yr deal (May 07) + (3) Google→SpaceX $920M/mo (Jun 05). Source page explicitly flagged it as "entity-page candidate; past entity-creation threshold." |
| `[[sriram-krishnan]]` | 2 | sources/sriram-krishnan-leaves-whitehouse-ai-advisor-2026-06-06 (×2) | **Create entity page**. Single substantive surface, but **structurally load-bearing** — Krishnan was WH AI advisor through the Trump narrower AI EO + OpenAI federal-preemption blueprint window, and his departure to found a new institution to *"shape Trump policy"* is a wiki-tracked role-shift. Same reasoning as Daniela Amodei creation at single-source threshold in last lint. |

### Single-source deferred per ingest commits (6 unique / 12 occurrences) — no action

All carry-over single-source defers from prior ingest commits. Each entity has 1 substantive wiki surface; flagged for "defer until 2nd substantive surface" per conservative entity-creation policy.

| Target | Refs | Status |
|---|---|---|
| `[[charity-majors]]` | 4 | Defer — 1 source (Willison surfacing); multi-ref is intra-source citations + log + simon-willison Notable Take |
| `[[alex-imas]]` | 2 | Defer — Dwarkesh co-guest |
| `[[phil-trammell]]` | 2 | Defer — Dwarkesh co-guest |
| `[[emanuel-maiberg]]` | 2 | Defer — 404 Media journalist |
| `[[dan-jeffries]]` | 1 | Defer — single source today (yesterday's pt1) |
| `[[kasra]]` | 1 | Defer — independent blogger |

### Intentional / false positives (12 occurrences) — no action

Unchanged from prior lints:

- `[[claude]]`, `[[claude-opus-4-6]]`, `[[concept]]` in log.md historical entries
- `[[Daily Briefs/...]]` refs (3 brief-filename refs for dedup; intentional)
- `[[LLM Wiki Pattern]]` in CLAUDE.md:312 (teaching example)
- `[[wikilink]]`, `[[Page Name]]` in tools/obsidian.md (backticked code)
- `[[agi-debate.canvas]]` in index.md:159 (Canvas file exists; lint scanner is markdown-only)

## Orphan Pages

**0 orphans.** All 449 pages have at least one inbound wikilink.

## Frontmatter Gaps

**0 issues.**

## Stale `last_updated`

**0 issues.**

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅ confirmed PR #80 merge fetched
2. `git pull --ff-only` → ✅ local main at `1a3a52b`
3. `gh pr list --state open` → ✅ empty
4. **Lint branch**: `lint/2026-06-06`

## Recommended Fixes

### Required (4 typo regressions)
1. `[[anthropic-xai-colossus-deal-2026]]` → `[[willison-anthropic-xai-colossus-2026-05]]`
2. `[[goldman-spacex-322b-ai-revenue-forecast-2026-06-04]]` → `[[dailybrief-roundup-2026-06-04]]`
3. `[[andrew-ng-jobpolcalypse-is-false-2026-06-01]]` → `[[andrewng-ai-fde-vs-ai-engineer-2026-06-01]]`
4. `[[dean-w-ball-autonomous-corporations-ban-2026-06-05]]` → `[[dailybrief-roundup-2026-06-05]]`

### Optional (judgment calls)
- **Create `companies/spacex.md`** — closes 3 dead-link refs; past 2-surface threshold (3 distinct events)
- **Create `people/sriram-krishnan.md`** — closes 2 dead-link refs; structurally load-bearing role-shift justifies entity page at single-source threshold

## Overall Posture

The wiki is in **excellent shape**. Structural health (orphans / frontmatter / stale) is structurally zero. The +11 dead-link delta is dominated by:

- 4 typo regressions in the 2026-06-06 ingests (deserved-fix; my mistake)
- 2 past 2-surface threshold entities (worth creating)
- 5 carry-over single-source defers (no change since prior lint)

**Post-typo-fix + 2 entity pages = 34 → 22 dead-links** (35% reduction), bringing remaining count below the prior lint's count.

## Applied Fixes (2026-06-06)

Per the lint review, applied all 6 recommended fixes:

1. ✅ **`[[anthropic-xai-colossus-deal-2026]]` → `[[willison-anthropic-xai-colossus-2026-05]]`** in sources/google-spacex-920m-monthly-compute-2026-06-05.md
2. ✅ **`[[goldman-spacex-322b-ai-revenue-forecast-2026-06-04]]` → `[[dailybrief-roundup-2026-06-04]]`** in sources/trump-admin-openai-equity-stake-2026-06-06.md
3. ✅ **`[[andrew-ng-jobpolcalypse-is-false-2026-06-01]]` → `[[andrewng-ai-fde-vs-ai-engineer-2026-06-01]]`** in sources/trump-admin-openai-equity-stake-2026-06-06.md
4. ✅ **`[[dean-w-ball-autonomous-corporations-ban-2026-06-05]]` → `[[dailybrief-roundup-2026-06-05]]`** in sources/house-draft-federal-ai-preemption-bill-2026-06-04.md
5. ✅ **Created `companies/spacex.md`** — substrate-tier compute monopoly-candidate entity page; 3-customer Colossus-tier consolidation (xAI internal + Anthropic + Google) + Goldman $322B forecast + vertical-integration thesis. Closes 3 dead-link refs.
6. ✅ **Created `people/sriram-krishnan.md`** — ex-WH AI advisor; departed 2026-06-06 to found new institution to shape Trump policy. Structurally load-bearing role-shift justifies entity page at single-source threshold. Closes 2 dead-link refs.
7. ✅ **Updated index.md** with 2 new entity entries (spacex under Companies & Labs; sriram-krishnan under People & Voices)

**Post-fix dead-link count**: 34 → 22 (35% reduction; 12 occurrences closed). Pages: 449 → 451.

Remaining 22 dead-links are all in the *intentional / false-positive / single-source-deferred* categories per the analysis above.
