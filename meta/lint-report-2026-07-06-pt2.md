---
type: meta
title: "Lint Report 2026-07-06 pt2"
created: 2026-07-06
updated: 2026-07-06
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-07-06 pt2

Post-ingest re-lint after the **Daily Brief 2026-07-06 pt2** ingest (PR #166: 7 new source pages, 7 new entity pages, 8 updated pages). Scope: validate the 22 touched files, plus a full-vault dead-link sweep. Supersedes nothing in `lint-report-2026-07-06.md` (that ran pre-ingest); this is the follow-up cycle.

## Summary

- **Pages scanned**: ~765 (654 content pages + sources)
- **New-content dead links**: **0** ✅ — every wikilink in the 22 touched files resolves
- **Orphans among new pages**: **0** ✅ — all 14 new pages have 4–13 inbound links
- **Frontmatter gaps on new pages**: **0** ✅ — all match schema
- **Source pages missing "Pages Updated"**: **0** ✅
- **Stale `last_updated` (tools/models >60d)**: **0** ✅ — the 4 flagged in the pre-ingest report were batch-refreshed in `f8d4a9b`
- **Pre-existing issues (not from this ingest)**: vault-wide ghost-node / wrong-slug debt — see below (optional cleanup)

## New pages — inbound link health (0 orphans)

| Page | Inbound files |
|---|---|
| `concepts/global-workspace` | 4 |
| `concepts/ai-margin-collapse` | 6 |
| `concepts/jailbreak-severity-framework` | 5 |
| `models/glm-5-2` | 6 |
| `companies/zhipu-ai` | 6 |
| `people/armin-ronacher` | 4 |
| `tools/claude-science` | 4 |
| `sources/dailybrief-roundup-2026-07-06` | 13 |
| 6 other source pages | 4–5 each |

All linked from `index.md` + their roundup + relevant entity Resources sections.

## Dead links introduced by this ingest: none

Full-vault sweep flagged 452 raw unresolved targets, but scoped to the 22 touched files only **4** appear — and all four are **pre-existing** ghost-links in the untouched heavy-cluster sections of `concepts/loop-engineering.md`, not in text I added:

- `0xMovez`, `rahulgs`, `samueljmcd`, `sydney-runkle`

My additions to `loop-engineering.md` (the AIEWF section) link only `[[dailybrief-roundup-2026-07-06]]`, which resolves. **No dead links attributable to pt2.**

## Pre-existing observations (optional — predate this ingest)

These are *not* regressions from pt2 and the per-cycle lint's "0 orphans / 0 wrong-slug" metric doesn't surface them because it measures *self-introduced* changes per cycle. Flagging for awareness:

1. **Accumulated ghost-node debt.** The vault has a large tail of `[[entity]]` links to pages that don't exist yet (mentioned-but-unwritten): e.g. `martin-alderson`, `vercel`, `amazon`, `grant-sanderson`, `kimi-k2-6`, `deepseek`, `qwen`, dozens more. Most are intentional deferred entity-page candidates; a full audit would separate "should exist" from "fine as ghost."
2. **Wrong-slug / inconsistent-slug pairs** in `loop-engineering.md`: `rahulgs` vs `rahul-gs`, `samueljmcd` vs `samuel-mcdonald`, `0xMovez` vs `0xmovez` — the same person referenced by two slugs, neither of which has a page. If those people pages get created, pick one slug and normalize references.
3. **Extraction-artifact false positives** in the raw sweep (not real issues): escaped table-pipes (`[[claude-code\|Claude Code]]` → `claude-code\`), `.md`/`.canvas` embed refs (`[[index.md]]`, `[[agi-debate.canvas]]`), and CLAUDE.md/skill doc examples (`Page Name`, `slug`, `wikilink`).

## Recommended Actions

**Apply (none required this cycle)** — clean post-ingest cycle; no fixes needed for the pt2 content.

**Optional, on request:**
- Vault-wide ghost-node audit (separate real missing-page candidates from acceptable ghosts) — larger effort, deferred by prior cycles.
- Normalize the `rahulgs`/`samueljmcd`/`0xMovez` dual-slug references if/when those people pages are created.
