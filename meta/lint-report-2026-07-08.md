---
type: meta
title: "Lint Report 2026-07-08"
created: 2026-07-08
last_updated: 2026-07-08
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-07-08

## Summary

- **Pages scanned**: 714 (content + entity + sources + index)
- **Structural health**: excellent — see clean checks below
- **Actionable issues**: 26 wrong-slug link fixes (page exists) + 6 missing-page candidates + 1 stale date
- **Accepted-pattern backlog** (not bugs): ~230 single-mention forward-reference ghost nodes in briefs/clusters

## Clean checks ✅

| Check | Result |
|---|---|
| Orphan entity pages (no inbound link) | **0** |
| Frontmatter gaps (required fields) | **0** |
| Duplicate slugs across vault | **0** |
| Tools missing a Traction Signals section | **0** |
| Sources with no entity wikilink | **0** |

## A. Wrong-slug ghost nodes — target page EXISTS (safe to auto-fix)

Unambiguous: the page exists, the link is just wrong. 26 occurrences across ~10 files.

| Bad link | Correct | Count | Where |
|---|---|---|---|
| `[[0xMovez]]` | `[[0xmovez]]` | 11 | loop-engineering.md, index.md, 0xmovez.md (self-ref), 2 movez source pages — **known multi-lint carry-over** |
| `[[index.md]]` | `[[index]]` | 11 | dailybrief-roundup-2026-06-14 … -06-18 (the `.md` suffix breaks Obsidian resolution) |
| `[[tibo-sottiaux]]` | `[[thibault-sottiaux]]` | 3 | thibault-sottiaux.md (self-ref), dailybrief-roundup-2026-06-21 — nickname mismatch |
| `[[0xCodez]]` | `[[0xcodez]]` | 1 | 0xcodez-fable-5-14-step-self-improving-agent-2026-06-11 |

## B. Missing-page candidates — multi-referenced entity, no page (needs decision)

| Entity | Refs | Suggested type | Note |
|---|---|---|---|
| `[[deepseek]]` | 17 | company or model | Major Chinese lab; referenced across Chinese-open-weights cluster |
| `[[qwen]]` | 14 | model | Alibaba model family |
| `[[moonshot-ai]]` | 9 | company | Kimi K2 maker (Kimi already referenced elsewhere) |
| `[[openai-deployment-simulation]]` | 7 | concept | OpenAI Ona-acquisition deployment-simulation concept |
| `[[prompt-injection]]` | ~7 | concept | Flagged in the 2026-07-08 ingest; GitLost is the flagship concrete exploit |
| `[[skill-md]]` / `[[concepts/skill-md]]` | 2 | concept | The SKILL.md primitive; referenced but no page |

## C. Stale `last_updated` (>60d, tools/models)

- `tools/claude-desktop.md`: **2026-05-08 (61 days)** — just crossed the 60-day threshold. Single item, below the 10-page batch-refresh threshold; refresh or defer per prior practice.

## D. Accepted-pattern backlog (NOT bugs — no action)

~230 distinct single-mention forward-reference ghost nodes live in `dailybrief-roundup-*` and cluster source pages (one-off people/companies/tools that are linked-on-mention but never warranted a page). This is the vault's established convention and is catalogued in `meta/ghost-node-audit-2026-07-06`. Left as-is; only promoted to pages when they cross the multi-surface threshold (that's what section B tracks).

## Actions Applied (2026-07-08, branch lint/2026-07-08)

Per owner decision:

- **Bucket A — 26 wrong-slug ghost nodes FIXED** across 19 files: `[[0xMovez]]`→`[[0xmovez]]` (×11, resolves the multi-lint carry-over), `[[index.md]]`→`[[index]]` (×11), `[[tibo-sottiaux]]`→`[[thibault-sottiaux]]` (×3), `[[0xCodez]]`→`[[0xcodez]]` (×1). Post-fix scan: 0 remaining.
- **Bucket B — 6 missing pages CREATED** (all had inbound refs; 0 new ghost nodes introduced): `companies/deepseek`, `models/qwen` (Alibaba), `companies/moonshot-ai`, `concepts/prompt-injection` (anchored by GitLost), `concepts/openai-deployment-simulation`, `concepts/skill-md`. Added to `index.md` under Models / Concepts / Companies. Chinese-vendor pages cross-linked into the existing z-ai/glm-5-2 cluster; verification-pending flags on unsourced specifics.
- **Bucket C — DEFERRED**: `tools/claude-desktop.md` (61d) left for a future batch stale-refresh (single item below threshold).
- **Bucket D — no action**: ~230 single-mention forward-ref ghost nodes (accepted convention).
