---
type: meta
title: "Lint Report 2026-07-30"
created: 2026-07-30
updated: 2026-07-30
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-07-30

Delta cycle covering the two ingests since the 07-29 lint — **#224** (Claude cryptanalysis / forward-deployed engineers / Gemini Robotics 2 folds) and **#225** (Nadella governed ROIC app / DHH laptop-free agents / one-person-$1M-company raw batch). **Fully clean — no fixes.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost links from delta ingest pages | **0** |
| Entity-page ghosts (any entity page) | **0** |

Corpus: 814 files / 813 pages / 997 link-targets.

## Delta detail

Both ingests were **folds-only + one new source page each** (`dailybrief-roundup-2026-07-30`, `raw-batch-roundup-2026-07-30`) — no new entity pages. Every wikilink introduced across `ai-for-science` / `engineering-leadership-ai-era` / `google-deepmind` / `graph-engineering` / `reward-hacking` / `frontier-ai-governance` (#224) and `reverse-information-paradox` / `satya-nadella` / `loop-engineering` / `ai-native-organizations` (#225) resolves. Both roundup sources carry `Pages Updated`. Last-cycle's `loop-engineering` unlink held (no re-introduction).

## Not in scope (known long-tail / false positives)

- **Historical June one-off `[[handle]]` backlog** in `sources/` pages (`alphasignal`, `lev-deviatkin`, `react-pattern`, `reflexion`, `langsmith-engine`, `samueljmcd`, `sydney-runkle`, …) — these live in June source/cluster pages, not entity pages; unchanged from every prior cycle.
- **`[[index]]` / `[[log]]`** — resolve in Obsidian (root files), not in the scan's `known` set. Not defects.
- **`[[agi-debate.canvas]]`** — canvas-embed artifact.

## Watch-item (not a defect)
- **`herdr`** surfaced a 3rd time (DHH/Omarchy in #225, after Buzz/OpenClaw mentions) — kept as plain text so far; a `tools/herdr` page becomes warranted on a 4th substantive surface.

## Actions
None — clean cycle. Report filed for the record.
