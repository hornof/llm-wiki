---
type: meta
title: "Lint Report 2026-07-10"
created: 2026-07-10
updated: 2026-07-10
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-07-10

Health-check across 738 pages (439 `sources/` + 299 entity/owner). Wiki is in strong shape. All fixes below were applied on branch `lint/2026-07-10`.

## Caveat — iCloud scan reliability

This vault lives on iCloud; a full *automated* link-graph re-scan was unreliable this session (`glob` intermittently missed materialized/evicted files, making existing pages such as `qwen`, `deepseek`, `moonshot-ai` falsely appear as ghost nodes). Every graph-based finding was re-verified with authoritative `grep`. Ghost-node status is deferred to the standing [[ghost-node-audit-2026-07-06]] rather than fresh, shaky numbers.

## Clean

- **0 orphan entity pages.**
- **0 tools missing a Traction Signals section.**
- **0 genuinely broken wikilinks** — the ~60 `[[slug\|alias]]` hits a naive sweep flags are valid escaped table-pipes (render fine in Obsidian).
- **Ghost-node tail already audited & acted on**: [[ghost-node-audit-2026-07-06]]'s top-5 recommended pages have all since been created (`writing-claude-code-skills`, `deepseek`, `qwen`, `moonshot-ai`, `personal-ai-agent-claude-desktop-mcp`). Residual tail (people voices, `vercel`, `amazon`) is deferred per the conservative entity-creation policy.

## Fixes applied

### 1. Dangling re-point (ghost-audit item B)
`sources/samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15.md:87` linked `[[anthropic-bun-zig-rust-port-2026-05]]` (no page) → re-pointed to `[[anthropic-dynamic-workflows-primary-2026-05-28]]` (exists), display text preserved.

### 2. Missing `Pages Updated` sections (5 roundup briefs)
`dailybrief-roundup-2026-06-03` … `-06-07` lacked a `## Pages Updated` section. Added one to each, honestly framed as **triage roundups** (net-new entity creation deferred), listing the entity/topic pages each brief referenced or reinforced. `-06-07` genuinely touched no entity pages (pure source-to-source cross-reference roundup) and is documented as such.

### 3. Stale tool/model pages refreshed (both >60d)
- **`tools/playwright-mcp.md`** (was 62d): added a 2026-07-10 refresh — v0.0.78 (2026-07-09), ~34.9k stars, MCP-Registry auto-publish, recent features; positioned as still-dominant for *driving*, now complemented by Chrome DevTools MCP / Claude-in-Chrome for *debugging*. Status held at `gaining-traction` (conservative; arguably at the mainstream threshold now). Cited primary sources.
- **`models/claude-opus-4-7.md`** (was 61d): **correction** — confirmed **Active** per Anthropic's model-deprecations page (retirement not before 2027-04-16), *superseded as default* by [[claude-opus-4-8]] (2026-05-28), not deprecated. Noted the `temperature`/`top_p`/`top_k` deprecation-from-4.7-onward gotcha. Unverified "fast mode" 4.7 deprecation left out.

## Deferred / no action

- **Ghost-node tail**: see [[ghost-node-audit-2026-07-06]]. `vercel` and `amazon` remain multi-cycle org-ghost pattern-watches; create when a second independent signal justifies a page.
- **`_raw/` drop-zone**: 336 files (gitignored). Known low-signal backlog; recent ingests confirm the current window is essentially exhausted of net-new signal.
- **Recommendation** (carried from the ghost audit): consider adding a lightweight ghost-node sweep to the recurring lint so the tail doesn't re-accumulate silently — noting the iCloud caveat above means such a sweep should verify hits with `grep`, not trust `glob` alone.
