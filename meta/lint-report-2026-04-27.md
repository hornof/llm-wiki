---
type: meta
title: "Lint Report 2026-04-27"
created: 2026-04-27
updated: 2026-04-27
tags: [meta, lint]
---

# Lint Report: 2026-04-27

## Summary

- Pages scanned: 80
- Issues found: 1 (down from 5 on 2026-04-26)
- Auto-fixed: 0 (all 4 from prior report were fixed in this session)
- Needs review: 1

---

## Fixes Applied Since Last Lint (2026-04-26)

All 4 auto-fixable items from the prior report were resolved:

1. ✅ `[[owner-profile]]` → `[[owner/profile]]` in `owner/publications.md:137`
2. ✅ `[[aakashgupta]]` added to `sources/thread-aakashgupta-1b-model.md` Pages Updated
3. ✅ `[[doing-great-work]]` linked from `people/richard-hamming.md` (Resources section added)
4. ✅ `tools/claude-code.md` `last_updated` corrected to 2026-04-26

---

## Remaining Issues

### Missing Pages: `hot-cache`, `claude-canvas`, `agrici-daniel` (carry-over)

The `2026-04-21` ingest log records these three pages as created from `_raw/github-claude-obsidian.md`, but no files exist for any of them. They appear to have been created in a session that was not committed.

- `hot-cache` — Claude Code / LLM Wiki caching concept
- `claude-canvas` — feature of the claude-obsidian plugin
- `agrici-daniel` — author of the claude-obsidian plugin (2,626 GitHub stars)

**Recommendation**: re-ingest `_raw/github-claude-obsidian.md` (force) to recreate these pages properly.

**Status**: awaiting owner decision.

---

## Dead Links

None in live wiki content. `[[owner-profile]]`, `[[hot-cache]]`, and `[[learn-agentic-ai]]` appear in old lint report files as historical documentation — not live links.

The following appear in the wikilink scan but are intentional non-links:
- `[[wikilink]]` and `[[Page Name]]` in `tools/obsidian.md` — example syntax in prose
- `[[LLM Wiki Pattern]]` in `CLAUDE.md` — intentional negative example of wrong format

---

## Orphan Pages

None. All 80 pages have at least one inbound link.

---

## Frontmatter Gaps

None found on entity pages. All tools, concepts, people, and company pages have required fields (type, status/maturity, last_updated, affiliation where applicable).

---

## Stale Claims

None. Wiki is 6 days old; 60-day threshold not reached.

---

## Manifest Health

`_raw/.manifest.json` was corrupted twice by appending entries outside the `sources` object boundary. Fixed both times by rewriting the full file. To prevent recurrence: always use `Write` (full rewrite) rather than `Edit` when updating the manifest.
