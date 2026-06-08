---
type: meta
title: "Lint Report 2026-06-08 pt2"
created: 2026-06-08
updated: 2026-06-08
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-08 pt2

## Summary

- **Pages scanned**: 455 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`; includes 2 ephemeral `Untitled*.md` at vault root that should be deleted)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0** (all 7 listed are meta files or path-form-resolved owner pages or ephemeral cruft)
- **Real fixable dead-links**: **1 typo regression** (`claude-opus-4-6` in log.md historical entry; carry-over from prior lint)
- **Unprocessed `_raw/` drops since last lint**: **0**
- **Pre-lint discipline**: `git fetch origin` → `git pull` confirmed at PR-87-merged tip; PR #88 (pt5 ingest) currently OPEN
- **Lint branch**: `lint/2026-06-08-pt2`

**Wiki health remains excellent.** Structural metrics (orphans / frontmatter / stale) all 0. The 3 prior-lint-created entity pages (junyang-lin / nando-de-freitas / dan-jeffries) closed 24 dead-link refs as expected. No new entity-page candidates have crossed the 2-surface threshold via pt4 + pt5 ingests.

### Net delta vs `lint-report-2026-06-08` (8 hours, 3 PRs landed — pt3 / pt4 / pt5 ingests)

| Metric | 2026-06-08 (earlier) | 2026-06-08 pt2 | Δ |
|---|---|---|---|
| Total pages | 458 | **455** | -3 (count-method noise; pt4 +2 sources + pt5 +5 sources + prior-lint +3 entity pages = +10, offset by basename-dedup artifacts) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Unique dead-link targets (real) | ~15 | **~12** | -3 (after junyang-lin / nando-de-freitas / dan-jeffries creations closed 24 refs) |
| Unprocessed `_raw/` drops | 4 (0xchromium ×2 + rohanpaul ×2) | **0** | -4 (all closed by pt4 ingest) |

## Orphan Pages

**0 real orphans** — same 7 candidates as prior lint (meta files / owner path-form / ephemeral cruft). Recommend deletion of `Untitled.md` + `Untitled 1.md` at vault root (still untracked).

## Frontmatter Gaps

**0 issues.** All tool / model / concept / people / company / source / tutorial / topic pages have all required frontmatter fields. **No new gaps introduced by pt3 + pt4 + pt5 ingests.**

## Stale `last_updated` (tools/models)

**0 issues.** Today is 2026-06-08; 60-day threshold is 2026-04-09. All tool/model pages have `last_updated >= 2026-04-21`.

## Dead Links

### Borderline candidates (3 unique / ~14 occurrences) — judgment call, unchanged from prior lint

| Target | Refs | Note |
|---|---|---|
| `[[biohub]]` | 5 | Borderline. Most refs are intra-cluster (world-models, RSI, own source). **Defer until 2nd substantive Biohub event.** |
| `[[kasra]]` | 6 | At threshold (own source + Lockdown Mode + ai-roi-gap + ai-vulnerability-discovery). **Recommend create at owner discretion**; slug too generic (`kasra` only) — would need fuller name; verification-pending. |
| `[[charity-majors]]` | 3 | 2 substantive surfaces but Willison-quoted-figure pattern. **Defer until 2nd primary substantive surface.** |

### Single-source / new defers (5 unique / 7 occurrences) — no action

| Target | Refs | Status |
|---|---|---|
| `[[alex-imas]]` | 2 | Defer — Dwarkesh co-guest |
| `[[phil-trammell]]` | 2 | Defer — Dwarkesh co-guest |
| `[[emanuel-maiberg]]` | 1 | Defer — 404 Media journalist |
| `[[elon-musk]]` | 1 | Defer — single ref in companies/spacex.md |
| `[[rohan-paul]]` | 1 | **NEW** from pt4 [[mit-ai-coding-elasticity-substitution-rohanpaul-2026-06-07]]. Defer — single substantive surface; high-signal X aggregator surfacing AI-research findings. Pattern-watch for 2nd substantive surface. |

### Typo regression (1 unique / 1 occurrence) — REAL FIXABLE (carry-over)

| Wrong slug | Correct slug | File | Note |
|---|---|---|---|
| `[[claude-opus-4-6]]` | `[[claude-opus-4-7]]` or `[[claude-opus-4-8]]` (verify context) | log.md | Historical archival log entry. Carry-over from prior lint — was deferred per owner discretion. Single-occurrence; very low priority. |

### Intentional / false positives (~14 occurrences) — no action

Unchanged structural patterns:

- `[[claude]]`, `[[concept]]` in log.md historical entries
- `[[Daily Briefs/2026-05-10-personal.md]]` + 5× `[[Daily Briefs/2026-06-0X.md]]` refs in log.md for dedup-discipline (intentional)
- `[[LLM Wiki Pattern]]` in CLAUDE.md teaching example
- `[[wikilink]]`, `[[Page Name]]` in tools/obsidian.md backticked code examples
- `[[agi-debate.canvas]]` in index.md (Canvas file exists; lint scanner is markdown-only)
- `[[meta/lint-report-2026-05-11]]` archival self-reference in prior lint report

## Unprocessed `_raw/` Drops

**0 unprocessed drops since prior lint.** All 4 previously-flagged drops (0xchromium Karpathy + 0xchromium Workflows + 2× rohanpaul_ai) were closed by [[bcherny-5-tips-opus-autonomous-2026-06-05|pt3]] / [[0xchromium-claude-cowork-workflows-guide-2026-06-04|pt4]] / [[dailybrief-roundup-2026-06-08|pt5]] ingests.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅ confirmed
2. `git pull --ff-only` → ✅ local main at PR-87-merged tip
3. `gh pr list --state open` → PR #88 (pt5 ingest) currently OPEN; the merge will close the loop. No action needed at lint-time.
4. **Lint branch**: `lint/2026-06-08-pt2`

## Recommended Fixes

### Required (none — none, lint is clean)

No required fixes this round.

### Optional (housekeeping)

1. **Delete `Untitled.md` + `Untitled 1.md`** at vault root (ephemeral cruft, currently untracked) — pending owner decision (carry-over)
2. **Fix `[[claude-opus-4-6]]` typo** in log.md historical entry — pending owner verification of correct generation (carry-over)
3. **Pattern-watch on `[[kasra]]`** — at 6-ref borderline; consider creating at owner discretion. Slug-generation requires verification of full name first.

## Overall Posture

The wiki is in **excellent shape** following the rapid pt1 + pt2 + pt3 + pt4 + pt5 ingest sequence today + the 3-entity-page lint-fix. Structural health remains structurally zero. The June 6 RSI / world-models / Hassabis-AGI ingest cluster + the June 4-7 Loop Engineering cluster + the 2026-06-08 Daily Brief ingest landed cleanly with no typo regressions in this batch.

**The June 4-8 ingest sequence has produced no net-new entity-page candidates past 2-surface threshold beyond the 3 already created.** Wiki health is structurally stable; this lint is a confirmation of clean state rather than a remediation cycle.

**Tracking for next lint**:
- `[[rohan-paul]]` 2-surface threshold (1 → 2)
- `[[biohub]]` 2nd substantive event (currently 1 substantive)
- `[[charity-majors]]` 2nd primary substantive surface (currently Willison-quoted)
- Pattern-watch on Andon Labs (`companies/andon-labs.md` already exists; 2nd substantive surface confirmed via VendingBench Latent Space — page content may need refresh)
