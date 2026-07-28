---
type: meta
title: "Lint Report 2026-07-28"
created: 2026-07-28
updated: 2026-07-28
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-07-28

Delta cycle covering the five ingests since the 07-26 lint — **#216** (graph-engineering), **#217** (Import AI 466), **#218** (PDF papers), **#219** (OpenTeams), **#220** (open-weights position + eng-leadership). **2 fixes applied.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost links from delta ingest pages (#216–220) | **0** |
| Stale tool/model pages (>60d) | **1 → fixed** |
| Pre-existing ghosts in an entity page | **3 → fixed** |

Corpus: 807 files / 806 pages / 992 link-targets.

## Fixes applied

1. **`tools/alphafold` — stale (62d)**. Content still accurate (Nobel 2024, `mainstream`, no material change) → bumped `last_updated` 2026-05-27 → 2026-07-28. No rewrite needed.
2. **3 ghost links in `concepts/loop-engineering`** — `[[rahulgs]]`, `[[samueljmcd]]`, `[[sydney-runkle]]`. These were the exact pre-existing ghosts flagged during #216 as "for a future lint." In each case the bare person-link sat directly beside its full source-page link (`rahulgs-english-code-interpreters-…`, `samueljmcd-loop-engineering-verifier-…`, `sydney-runkle-langchain-4-layer-…`, all of which exist), so the bare name was **unlinked to plain text** — losing no navigation, consistent with the one-off-name convention (Bessent, Ptacek, etc.).

## Not in scope (known long-tail / false positives)

- **Historical June one-off `[[handle]]` backlog** — hundreds of bare-name ghosts inside June `sources/` roundup + cluster pages (e.g. `alphasignal`, `lev-deviatkin`, `react-pattern`, `reflexion`, `langsmith-engine`). Same established long-tail every prior cycle scopes out; these live in source pages, not entity pages.
- **Root-file false positives** — `[[index]]` and `[[log]]` resolve in Obsidian (index.md / log.md at vault root) but aren't in the scan's `known` set (built from subdirectories). Not defects.
- **`[[agi-debate.canvas]]`** — canvas-embed artifact (category-F per [[ghost-node-audit-2026-07-06]]).

## Actions
Applied the alphafold date bump + the 3 loop-engineering unlinks; recorded here.
