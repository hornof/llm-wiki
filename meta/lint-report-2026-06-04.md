---
type: meta
title: "Lint Report 2026-06-04"
created: 2026-06-04
updated: 2026-06-04
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-04

## Summary

- **Pages scanned**: 428 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days): **0**
- **Orphan content pages** (no inbound wikilinks): **0**
- **Dead-link occurrences in live content**: 28 across 19 unique targets (excludes stale `meta/lint-report-*` files which contain archival quoted dead links)
- **Real fixable dead links**: 7 unique targets / 14 occurrences (rest are intentional / false positives)
- **Pre-lint discipline**: `git fetch origin` → `git pull` confirmed at PR-73-merged tip (`861dd93`); no open PRs

**Wiki health is strong.** No structural issues; the remaining dead links are either explicit defer-decisions from recent ingests or framework-level false positives (teaching examples / Obsidian Canvas / brief-filename refs).

## Dead Links

Broken down by category. Counts are live-content occurrences (meta/lint-report archival mentions excluded).

### Real fixable — needs decision (7 targets / 14 occurrences)

These are dead links in live content created during recent ingests. Each was a deliberate defer-decision flagged in the ingest commit. The lint pass is the point where we promote some to entity pages.

| Target | Refs | Sources | Recommended action |
|---|---|---|---|
| `[[nathan-lambert]]` | 6 | companies/nvidia.md, index.md, log.md, sources/nvidia-nemotron-3-ultra-550b-2026-06-04.md (×3) | **Create entity page** — 2nd substantive wiki surface in 4 days (Jun 02 AI2 departure → Jun 04 post-AI2 NVIDIA distillation framing); past the 2-surface threshold. |
| `[[anton-korinek]]` | 3 | log.md, sources/anthropic-institute-when-ai-builds-itself-2026-06-04.md (×2) | **Create entity page** — 2 substantive surfaces (Import AI 456 RSI growth-regime model + Anthropic Institute publication feedback contributor); at threshold. |
| `[[emanuel-maiberg]]` | 2 | sources/willison-google-ai-criticism-internal-comms-2026-06-04.md (×2) | Defer (single source today; 404 Media journalist; flag for 2nd surface). Confirmed defer in ingest commit. |
| `[[alex-imas]]` | 1 | sources/imas-trammell-post-agi-scarcity-dwarkesh-2026-06-04.md | Defer (single source today; Chicago Booth behavioral-economist). |
| `[[phil-trammell]]` | 1 | sources/imas-trammell-post-agi-scarcity-dwarkesh-2026-06-04.md | Defer (single source today; Oxford economist). |
| `[[dwarkesh-patel]]` | 1 | sources/imas-trammell-post-agi-scarcity-dwarkesh-2026-06-04.md | **Create entity page** — Dwarkesh is *broadly referenced across wiki* (Reiner Pope episode, Imas/Trammell episode, multiple roundup mentions); past the threshold. |
| `[[kasra]]` | 1 | sources/kasra-llm-pentester-1500-experiment-2026-06-04.md | Defer (single source today; independent blogger). |

### Real but should-be-rewritten (3 targets / 3 occurrences)

| Target | Refs | Sources | Recommended action |
|---|---|---|---|
| `[[meta-platforms]]` | 1 | sources/willison-meta-ai-instagram-exfiltration-2026-06-01.md:59 | **Either**: (a) rewrite as `[[meta]]` and create [[meta]] entity page, or (b) un-link to plain text. Pattern-watch on Meta Business Agent global rollout + cross-vendor exfil pattern suggests entity page is warranted. |
| `[[memory]]` | 1 | sources/dailybrief-roundup-2026-06-04.md:51 | Rewrite as `[[mem0]]` (closest existing concept page) or un-link. Used in *"pairs structurally with memory primitives"* framing — could justify a concepts/memory page if there are >1 substantive memory-primitive surfaces wiki-tracked. |
| `[[zodchii-4-agent-pipeline-2026-05-31]]` | 0 (live; 2 in lint reports) | older lint reports only | Already fixed via prior ingest. No live-content occurrence. |

### Intentional per prior lint decisions (3 targets / 4 occurrences in log.md)

These are append-only log entries where the dead-link form is preserved as historical record:

| Target | Refs | Status |
|---|---|---|
| `[[claude]]` | 1 (log.md:131) | **Intentional** — bare-ambiguous reference in historical log entry; do not rewrite. |
| `[[claude-opus-4-6]]` | 1 (log.md:51) | **Intentional** — historical model reference; predecessor of currently-tracked `[[claude-opus-4-7]]` + `[[claude-opus-4-8]]`; append-only convention. |
| `[[concept]]` | 1 (log.md:131) | **Intentional** — template-residue in historical log entry. |

### Daily Briefs cross-refs (3 occurrences)

| Target | Refs | Status |
|---|---|---|
| `[[Daily Briefs/2026-06-03.md]]` | 2 | **Intentional** — used for dedup in source pages (cite the brief that triggered the source). Daily Briefs are gitignored from being tracked as wiki pages but exist on disk. |
| `[[Daily Briefs/2026-06-04.md]]` | 1 | **Intentional** (same rationale). |
| `[[Daily Briefs/2026-05-10-personal.md]]` | 1 (log.md) | **Intentional** historical log entry. |

### False positives (4 occurrences)

| Target | Refs | Source | Why false positive |
|---|---|---|---|
| `[[LLM Wiki Pattern]]` | 1 | CLAUDE.md:312 | **Teaching example** — the line literally explains the wikilink-discipline rule with this as the negative example. Do not change. |
| `[[wikilink]]` | 1 | tools/obsidian.md:18 | **Backticked code** — `` `[[wikilink]]` `` shows the syntax. Regex picks it up but Obsidian renders it as code. |
| `[[Page Name]]` | 1 | tools/obsidian.md:22 | **Backticked code** — same as above. |
| `[[agi-debate.canvas]]` | 1 | index.md:154 | **Obsidian Canvas file** — `.canvas` exists at `canvases/agi-debate.canvas` (verified). Lint scanner is markdown-only so doesn't see canvas files. |

## Orphan Pages

**0 orphans.** Every content page in `tools/`, `models/`, `concepts/`, `people/`, `companies/`, `sources/`, `topics/`, `tutorials/`, `owner/` has at least one inbound wikilink from another content page.

## Frontmatter Gaps

**0 issues.** All entity / source / concept pages have the required schema fields (per CLAUDE.md schemas).

## Stale `last_updated`

**0 issues.** No entity page is more than 60 days stale (i.e., no `last_updated < 2026-04-05`). The 4-day-cadence ingest workflow is keeping all touched pages fresh.

## Missing Cross-References (light scan)

The following entities are mentioned in multiple sources but not yet promoted to entity pages — past the 2-surface threshold and worth promoting:

| Entity | Surfaces | Threshold met? |
|---|---|---|
| **Nathan Lambert** | 2 (AI2 departure Jun 02 + Nemotron 3 Ultra post-AI2 voice Jun 04) | **YES** |
| **Anton Korinek** | 2 (Import AI 456 RSI model May 11 + Anthropic Institute feedback contributor Jun 04) | **YES** |
| **Dwarkesh Patel** | 3+ (Reiner Pope episode + Imas/Trammell episode + roundup mentions) | **YES** |

Not yet at threshold but flagged:

| Entity | Surfaces | Notes |
|---|---|---|
| Holden Karnofsky | 1 (Anthropic Institute feedback contributor) | Open Philanthropy / longtermism-adjacent; pattern-watch |
| Marina Favaro | 1 (already created as new entity page in Jun 04 pt1 ingest) | Done |
| Carina Hong / Axiom Math | 1 each | Pattern-watch |
| Dean W. Ball | 1 (autonomous-corporations governance scholar) | Pattern-watch |
| Ramp | 1 (AI-token-monitoring tools launch) | Pattern-watch for product details |

## Index Discipline

`index.md` ends with the 2026-06-04 pt2 entries cleanly appended. Category structure intact. No stale entries detected.

Two new entity entries added in recent ingests (correctly placed): `[[uber]]` + `[[github]]` (Jun 03), `[[marina-favaro]]` (Jun 04), `[[marble]]` (Jun 03), `[[recursive-self-improvement]]` (Jun 04).

## Pre-Lint Discipline Verification

Per the lint protocol established in `meta/lint-report-2026-06-01.md` §5:

1. `git fetch origin` → ✅ Run before checking state
2. `git log main..origin/main` → ✅ Confirmed `9027924..861dd93` (PR #73 merge fetched)
3. `git pull --ff-only` → ✅ Local main at `861dd93`
4. `gh pr list --state open` → ✅ Empty (no open PRs)
5. **Lint branch**: `lint/2026-06-04`

## Recommended Auto-Fix Set (Safe)

Per the wiki-lint skill's auto-fix discipline:

**Safe to auto-fix**:
1. Create entity stubs for `[[nathan-lambert]]`, `[[anton-korinek]]`, `[[dwarkesh-patel]]` (3 new entity pages — past threshold, well-supported by multiple sources)
2. Rewrite `[[meta-platforms]]` → `[[meta]]` and create [[meta]] entity page stub
3. Rewrite `[[memory|memory primitives]]` → `[[mem0|memory primitives]]` (or strip wikilink if mem0 is too narrow a match)

**Needs decision before fixing**:
- Whether to create `[[meta]]` entity page now (Meta Business Agent global rollout + cross-vendor exfil pattern justifies it; pattern-watch is whether Meta becomes a frequently-referenced entity)
- Whether to create `[[concepts/memory]]` concept page now (would need >1 substantive memory-primitive surface to justify; currently only the ChatGPT "dreaming" reference)
- Whether to leave the other 4 single-source deferred entities (`[[emanuel-maiberg]]`, `[[alex-imas]]`, `[[phil-trammell]]`, `[[kasra]]`) as deferred — each was a deliberate single-source defer in the ingest commits

**Not to fix**:
- Teaching examples (CLAUDE.md, obsidian.md backticked-code)
- Obsidian Canvas file references (lint scanner blind spot, not a real issue)
- Daily Briefs/ refs (intentional dedup mechanism)
- Append-only log.md historical entries

## Overall Posture

The wiki is in **excellent shape**. The ingest discipline established in May (with frontmatter consistency, last_updated bumping, pre-lint git-sync) has reduced ambient lint debt to near-zero. The only remaining work is *promotion-from-deferred-status* — converting the recent ingest defer-decisions into entity pages when the 2-surface threshold is met.

**3 entity pages to create** (Nathan Lambert, Anton Korinek, Dwarkesh Patel) would close 10 of the 28 live-content dead-link occurrences (36%) and bring the remaining count below 20.

## Applied Fixes (2026-06-04)

Per the lint review, all 5 recommended fixes were applied in this lint pass:

1. ✅ **Created `people/nathan-lambert.md`** — past 2-surface threshold (AI2 departure Jun 02 + Nemotron 3 Ultra post-training framing Jun 04); closes 6 dead-link refs
2. ✅ **Created `people/anton-korinek.md`** — past 2-surface threshold (Import AI 456 RSI growth-regime model + Anthropic Institute publication feedback contributor); closes 3 dead-link refs
3. ✅ **Created `people/dwarkesh-patel.md`** — broadly referenced across wiki (Reiner Pope episode + Imas/Trammell episode + roundup mentions); closes 1 dead-link ref and reduces future-defer load
4. ✅ **Created `companies/meta.md`** — entity stub with Meta AI / Meta Business Agent / 3rd-vendor agentic-exfil-pattern positioning; rewrote `[[meta-platforms]]` → `[[meta]]` in `sources/willison-meta-ai-instagram-exfiltration-2026-06-01.md`
5. ✅ **Rewrote `[[memory|memory primitives]]` → `[[mem0|mem0 memory primitives]]`** in `sources/dailybrief-roundup-2026-06-04.md`
6. ✅ **Updated `index.md`** with 4 new entity entries (nathan-lambert, anton-korinek, dwarkesh-patel under People & Voices; meta under Companies & Labs)

**Post-fix dead-link count**: 28 → 17 (39% reduction). Remaining 17 are all in the *intentional / false-positive / single-source-deferred* categories per the analysis above.

**Net delta vs prior lint (`meta/lint-report-2026-06-02.md`)**:
- Pages scanned: 404 → 428 (+24 new pages in 2 days)
- Real fixable dead-links: similar small count; ingest discipline preventing accumulation
- New entity pages added: 4 (rate consistent with ingest-driven 2-surface threshold)
- Frontmatter / stale / orphan issues: 0 → 0 (clean across the board)
