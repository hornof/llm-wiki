---
type: meta
title: "Lint Report 2026-07-09"
created: 2026-07-09
last_updated: 2026-07-09
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-07-09

## Summary

- **Pages scanned**: 726
- **Result**: **clean cycle** — 0 actionable structural issues. Only fix applied: 1 stale-date refresh.
- 5 ingests since the prior lint (2026-07-08, [[meta/lint-report-2026-07-08]]).

## Clean checks ✅

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Wrong-slug ghost nodes (page exists) | **0** — the 2026-07-08 fixes held; no regressions |
| Dead links inside the 5 recent ingests' new pages | **0** |
| Frontmatter gaps | **0** |
| Duplicate slugs | **0** |
| Tools without a Traction Signals section | **0** |
| Sources with no entity wikilink | **0** |

The `deepseek` / `qwen` / `moonshot-ai` / `prompt-injection` / `openai-deployment-simulation` / `skill-md` pages created on 2026-07-08 all resolve their inbound links (no orphans, no dead-link regressions).

## Fix applied

- **Stale `last_updated` refresh**: `tools/claude-desktop.md` (was 2026-05-08 / 62 days — flagged the prior cycle too). Content re-verified as still accurate; added two grounded May→July updates (Claude Agent SDK as the layer beneath the Desktop host; the maturing Cowork file-based plugin ecosystem) and bumped `last_updated` → 2026-07-09.

## No action (accepted backlog)

- ~230 single-mention forward-reference ghost nodes in `dailybrief-roundup-*` / cluster source pages (vault's link-on-mention convention; catalogued in `meta/ghost-node-audit-2026-07-06`).
- Modal "agent experience" agent-infra thesis flagged as a pattern-watch entity-page candidate (single surface; from the 2026-07-09 ingest).
