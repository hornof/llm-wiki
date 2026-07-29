---
type: meta
title: "Lint Report 2026-07-29"
created: 2026-07-29
updated: 2026-07-29
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-07-29

Delta cycle covering the **07-29 ingest (#222)** — the only ingest since the 07-28 lint. **1 fix applied.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost links from #222 pages | **0** |
| Pre-existing entity-page ghosts | **2 → fixed** |

Corpus: 811 files / 810 pages / 995 link-targets.

## Fix applied

- **2 ghost links in `people/dwarkesh-patel`** — `[[alex-imas]]`, `[[phil-trammell]]`. Both bare person-links sat on the same line as their anchor source page (`imas-trammell-post-agi-scarcity-dwarkesh-2026-06-04`, which exists), so they were **unlinked to plain text** — no navigation lost, consistent with the one-off-name convention and with last cycle's `loop-engineering` fix. Surfaced this cycle because the #222 ingest edited that page; not introduced by the diff.

## Delta detail (#222)

`factory-ai` (new), `handbook-md-…` (new source), and edits to `claude-md-pattern` / `context-engineering` / `prompt-injection` / `frontier-ai-governance` / `engineering-leadership-ai-era` / `ai-margin-collapse` / `buzz` / `claude-opus-5` / `index`. Every wikilink introduced by #222 resolves (verified per-target during the ingest and re-confirmed here). New source pages carry `Pages Updated`; `factory-ai` has a Traction Signals section.

## Not in scope (known long-tail / false positives)

- **Historical June one-off `[[handle]]` backlog** in `sources/` pages (unchanged; lives in source pages, not entity pages).
- **`[[index]]` / `[[log]]`** — resolve in Obsidian (root files), not in the scan's `known` set. Not defects.
- **`[[agi-debate.canvas]]`** — canvas-embed artifact.

## Actions
Applied the 2 dwarkesh-patel unlinks; recorded here.
