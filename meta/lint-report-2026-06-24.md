---
type: meta
title: "Lint Report 2026-06-24"
created: 2026-06-24
updated: 2026-06-24
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-06-24

## Summary

- **Pages scanned**: 655 (+93 vs lint-2026-06-23; new pages mostly from sources/ cumulative)
- **Orphans**: 0 ✅
- **Frontmatter gaps**: 0 ✅
- **Wrong-slug regressions**: **5 NEW** (regressions from yesterday's lint cleanup — entity pages I created)
- **Stale `last_updated` (>60 days on tools/models)**: 8 (5 carry-over + 3 newly stale)
- **Entity-page candidates past 2-surface threshold**: 0 (no new ingests since 2026-06-23; pattern-watch carry-overs from prior lint unchanged)
- **Unprocessed `_raw/` drops**: 1 (`The CEO of a $20B AI company...md` from 2026-06-24; not in lint scope — for next ingest)

## Wrong-Slug Regressions (5)

**STRUCTURALLY NOTABLE**: Multi-lint-cycle 0-regression streak (since lint-2026-06-20) **broken by yesterday's own lint cleanup**. All 5 regressions are in entity pages I authored on 2026-06-23 — first wiki-captured canonical-self-introduced-regression canonical-pattern. Lesson: even with conservative entity-creation policy, freshly-authored entity pages need same slug-discipline as ingest source pages.

| # | File | Line | Wrong | Correct | Reason |
|---|------|------|-------|---------|--------|
| 1 | `people/thibault-sottiaux.md` | 32 | `[[tools/openai-codex]]` | `[[codex]]` | Codex page is at `tools/codex.md`, not `tools/openai-codex.md` |
| 2 | `companies/reflection-ai.md` | 25 | `[[mistral]]` | `[[mistral-ai]]` | Page is `companies/mistral-ai.md` |
| 3 | `companies/reflection-ai.md` | 25 | `[[meta-ai]]` | `[[meta]]` | Page is `companies/meta.md` |
| 4 | `companies/allenai.md` | 28 | `[[meta-ai]]` | `[[meta]]` | Same as #3 |
| 5 | `companies/allenai.md` | 29 | `[[mistral]]` | `[[mistral-ai]]` | Same as #2 |
| 6 | `companies/allenai.md` | 30 | `[[deepmind]]` | `[[google-deepmind]]` | Page is `companies/google-deepmind.md` |

(6 line-level fixes across 5 regression-classes; one regression-class repeated across files.)

## Stale `last_updated` (8)

5 from prior lint (deferred, still stale) + 3 newly crossed 60-day threshold:

**Carry-over (still 60+ days)**:
- `tools/crewai.md` — 2026-04-21 (64 days)
- `tools/llama-index.md` — 2026-04-21 (64 days)
- `tools/mem0.md` — 2026-04-21 (64 days)
- `tools/obsidian-dataview.md` — 2026-04-21 (64 days)
- `tools/obsidian.md` — 2026-04-21 (64 days)

**Newly stale this cycle**:
- `tools/ollama.md` — 2026-04-21 (64 days) — crossed threshold this cycle
- `tools/stitch.md` — 2026-04-24 (61 days) — crossed threshold this cycle
- `models/gpt-image-2.md` — 2026-04-22 (63 days) — crossed threshold this cycle

**Recommendation**: continue deferral per established cadence (not blocking; these are foundational tool/model pages with no recent material signal-change). Refresh-pass once batch reaches 10+ stale pages.

## Entity-Page Pattern-Watch Carry-Overs

No 2-surface threshold crossings since prior lint (no new ingests since 2026-06-23). Pattern-watch deferrals from lint-2026-06-23 still active:

- `[[gray-swan]]` + `[[zico-kolter]]` + `[[matt-fredrikson]]` (Jun 23 AI-security 3-name cluster; await 2nd surface)
- `[[appia-foundation]]` (OpenAI Jun 23 single-source)
- `[[andrew-curran]]` (Jun 21 single-source)
- `[[dgx-spark]]` (Jun 21 single-source infrastructure-anchor)
- `[[s4yonnara]]` (Jun 20 single-source practitioner-content-register voice)
- `[[addy-osmani]]` (Jun 15 + Jun 20 — 2 attribution-refs but no direct-voice surface; defer until direct-voice surface)
- `[[trail-of-bits]]` + `[[patrick-mccanna]]` (Jun 22 single-source)
- Multi-lint slug-case-normalization: `[[0xMovez]]` (capital-M)
- Multi-lint typo: `[[mcpmatt-pocock]]` → `[[matt-pocock]]`

## Cross-Cutting Health Signals

- **Slug-discipline**: previously perfect 4-cycle streak broken — lesson for future canonical lint-cleanup cadence: **verify all wikilinks in newly-authored entity pages resolve before commit**. Apply same `find . -name <slug>.md` verification used for source-page ingests.
- **0 frontmatter gaps**: stable across all tools/models/concepts/people/companies (excellent canonical-discipline).
- **0 orphans**: stable across all entity-page categories.
- **Multi-lint cadence**: this is the 7th lint cycle in 10 days (Jun 15 + 16 + 17 + 18 + 20 + 23 + 24); cadence is operationally sustainable.

## Recommended Actions

**Apply (high-priority — actual structural errors)**:
- 6 line-level fixes across 5 wrong-slug-regression-classes (above table) ✅ **APPLIED**

**Defer (low-priority — not blocking)**:
- 8 stale `last_updated` (refresh once batch reaches 10+)
- All pattern-watch entity-page candidates (await 2nd surface)

## Applied

- `people/thibault-sottiaux.md:32` — `[[tools/openai-codex]]` → `[[codex]]`
- `companies/reflection-ai.md:25` — `[[mistral]]` → `[[mistral-ai|Mistral]]` + `[[meta-ai]]` → `[[meta|Meta]]`
- `companies/allenai.md:28` — `[[meta-ai|Meta FAIR]]` → `[[meta|Meta FAIR]]`
- `companies/allenai.md:29` — `[[mistral]]` → `[[mistral-ai|Mistral]]`
- `companies/allenai.md:30` — `[[deepmind]]` → `[[google-deepmind|DeepMind]]`

Verified post-fix: all wikilinks in 3 fixed pages resolve (1 remaining apparent dead is `` `[[tibo-sottiaux]]` `` backtick-quoted slug-variant — intentional reservation, not a wikilink).
