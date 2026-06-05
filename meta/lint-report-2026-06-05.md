---
type: meta
title: "Lint Report 2026-06-05"
created: 2026-06-05
updated: 2026-06-05
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-05

## Summary

- **Pages scanned**: 440 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days): **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Dead-link occurrences in live content**: 24 across 17 unique targets (excludes stale `meta/lint-report-*` archival quotes)
- **Real fixable dead links**: 0 (all 17 targets fall into intentional / false-positive / single-source-deferred categories per established conventions)
- **Pre-lint discipline**: `git fetch origin` → `git pull` confirmed at PR-77 typo-fix-merged tip (`0508c55`); no open PRs

**Wiki health is excellent.** No structural issues. Net delta vs `lint-report-2026-06-04` (24 hours, 2 ingest PRs + 1 typo-fix PR):

| Metric | 2026-06-04 | 2026-06-05 | Δ |
|---|---|---|---|
| Total pages | 428 | **440** | +12 (7 new sources + 5 net-new entity sections) |
| Orphans | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Live-content dead-link occurrences | 17 | **24** | +7 (new single-source defer decisions) |
| Unique dead-link targets | 12 | **17** | +5 (new defer entities: `charity-majors`, `daniela-amodei`, plus Daily Briefs/2026-06-05.md ref) |

The +7 dead-link occurrences are *all expected* — each was a deliberate single-source defer flagged in the ingest commits.

## Dead Links

Broken down by category.

### Single-source deferred per ingest commit (12 occurrences / 5 unique targets)

These were all deliberate defers in the source-page ingest commits — each entity has 1 substantive wiki surface and was flagged for "defer until 2nd substantive surface" per conservative entity-creation policy.

| Target | Refs | Sources | Status |
|---|---|---|---|
| `[[charity-majors]]` | 4 | sources/willison-charity-majors-enthusiasts-skeptics-2026-06-04 (×2) + people/simon-willison + log.md | **Defer** — 1 substantive surface (the Willison post); multi-ref is the source page citing itself + cross-refs. Pattern-watch: does Honeycomb / Observability community surface a 2nd substantive Charity Majors framing? |
| `[[alex-imas]]` | 2 | sources/imas-trammell-post-agi-scarcity-dwarkesh-2026-06-04 + people/dwarkesh-patel | **Defer** — 1 Dwarkesh episode; Imas is co-guest. |
| `[[phil-trammell]]` | 2 | sources/imas-trammell-post-agi-scarcity-dwarkesh-2026-06-04 + people/dwarkesh-patel | **Defer** — 1 Dwarkesh episode; Trammell is co-guest. |
| `[[emanuel-maiberg]]` | 2 | sources/willison-google-ai-criticism-internal-comms-2026-06-04 (×2) | **Defer** — 404 Media journalist; 1 source. |
| `[[kasra]]` | 1 | sources/kasra-llm-pentester-1500-experiment-2026-06-04 | **Defer** — independent blogger; 1 source. |

### Reasonable-to-create-now (1 occurrence / 1 target)

| Target | Refs | Sources | Recommended action |
|---|---|---|---|
| `[[daniela-amodei]]` | 1 | sources/anthropic-47b-amodei-techcrunch-pre-ipo-2026-06-04 | **Consider creating now**. Single substantive interview today, but Daniela Amodei is *structurally load-bearing* — Anthropic President + co-founder + S-1 PBC-governance counterpart to her brother [[dario-amodei|Dario]] (who *has* an entity page). The pre-IPO interview alone justifies the page; future Anthropic operations/business signals will continue to flow through her. **Defer-now / create-now** is a judgment call. |

### Intentional per established conventions (4 occurrences / 4 targets — no action)

| Target | Refs | Why intentional |
|---|---|---|
| `[[claude]]` | 1 (log.md:134) | Bare-ambiguous reference in historical log; append-only convention. |
| `[[claude-opus-4-6]]` | 1 (log.md:54) | Historical model reference in append-only log entry. |
| `[[concept]]` | 1 (log.md:134) | Template-residue in historical log entry. |
| `[[Daily Briefs/2026-05-10-personal.md]]` | 1 (log.md:134) | Historical Daily Brief dedup ref. |

### Daily Briefs dedup refs (3 occurrences / 3 targets — no action)

| Target | Refs | Why intentional |
|---|---|---|
| `[[Daily Briefs/2026-06-03.md]]` | 2 | Dedup mechanism — Daily Briefs gitignored but file exists; refs point to the brief that triggered each source. |
| `[[Daily Briefs/2026-06-04.md]]` | 1 | Same. |
| `[[Daily Briefs/2026-06-05.md]]` | 1 | Same. |

### False positives (4 occurrences / 4 targets — no action)

| Target | Refs | Why false positive |
|---|---|---|
| `[[LLM Wiki Pattern]]` | 1 (CLAUDE.md:312) | **Teaching example** — the line literally states this as the negative example in the wikilink-discipline rule. |
| `[[wikilink]]` | 1 (tools/obsidian.md:18) | **Backticked code** — `` `[[wikilink]]` `` shown as syntax demo. |
| `[[Page Name]]` | 1 (tools/obsidian.md:22) | **Backticked code** — same. |
| `[[agi-debate.canvas]]` | 1 (index.md:158) | **Obsidian Canvas file** — `canvases/agi-debate.canvas` exists; lint scanner is markdown-only. |

## Orphan Pages

**0 orphans.** All 440 pages have at least one inbound wikilink.

## Frontmatter Gaps

**0 issues.** All entity / source / concept pages have required schema fields per CLAUDE.md.

## Stale `last_updated`

**0 issues.** Every entity page is within 60 days. The 4-day-cadence ingest workflow continues to keep all touched pages fresh.

## Recent Activity Note

Two ingests landed since lint-report-2026-06-04:
- **PR #75** (`ingest/2026-06-05`): Anthropic Dynamic Workflows canonical docs + Thariq Shihipar harness post — 2 source pages, updated tools/claude-code + tools/bun + people/thariq-shihipar
- **PR #76** (`ingest/2026-06-05-pt2`): 2026-06-05 Daily Brief — 5 source pages (TechCrunch token-bill + Amodei pre-IPO $47B + Charity Majors + OpenAI biodefense + roundup), updated companies/anthropic + companies/openai + companies/google-deepmind + people/simon-willison + concepts/ai-vulnerability-discovery + topics/ai-roi-gap + topics/saas-disruption-thesis
- **PR #77** (`fix/post-merge-typos-2026-06-05`): 2 typo fixes I introduced in the pt2 roundup

PRs #75 and #76 had merge conflicts that were resolved by accept-both. **Verified post-merge state**: all entries from both PRs are present; no duplicates; `last_updated: 2026-06-05` correctly bumped throughout; both 2026-06-05 log entries preserved (pt2 line 7 + pt1 line 8); all 7 new source entries in index.md.

## Pre-Lint Discipline Verification

Per the lint protocol:

1. `git fetch origin` → ✅ Run before checking state
2. `git log main..origin/main` → ✅ Confirmed PR #77 typo-fix merge fetched
3. `git pull --ff-only` → ✅ Local main at `0508c55`
4. `gh pr list --state open` → ✅ Empty (no open PRs)
5. **Lint branch**: `lint/2026-06-05`

## Recommended Auto-Fix Set

**Optional (judgment call)**:
- Create `people/daniela-amodei.md` stub — structurally load-bearing (Anthropic President + co-founder + S-1 PBC governance counterpart to Dario). Closes 1 dead-link ref. Worth doing now even at single-source threshold because role-significance justifies the page independent of surface count.

**Defer (per established convention)**:
- `[[charity-majors]]`, `[[alex-imas]]`, `[[phil-trammell]]`, `[[emanuel-maiberg]]`, `[[kasra]]` — all single-source defers per ingest commit decisions. Defer until 2nd substantive surface.

**Not to fix**:
- Teaching examples (CLAUDE.md, tools/obsidian.md backticked code)
- Obsidian Canvas file references (lint scanner blind spot, not a real issue)
- Daily Briefs/ dedup refs (intentional mechanism)
- Append-only log.md historical entries

## Overall Posture

The wiki is in **excellent shape**. The 4-day-cadence ingest workflow with frontmatter discipline, last_updated bumping, and pre-lint git-sync has reduced ambient lint debt to **structurally zero** — every dead link is either intentional or a deliberate single-source defer.

**No required fixes.** The optional `[[daniela-amodei]]` creation is a judgment call based on role-significance rather than dead-link-count pressure.

## Applied Fixes (2026-06-05)

Per the lint review, applied the 1 optional recommended fix:

1. ✅ **Created `people/daniela-amodei.md`** — Anthropic co-founder + President; operations + business-side counter-voice to Dario; pre-IPO TechCrunch interview surface + 14th-component-of-bundle context. Closes 1 dead-link ref. Index entry added under People & Voices (alphabetically after Dario).

**Post-fix dead-link count**: 24 → 23 (1 occurrence closed). Remaining 23 are all in the *intentional / false-positive / single-source-deferred* categories per the analysis above.

**Pages: 440 → 441.**
