---
type: meta
title: "Lint Report 2026-04-30"
created: 2026-04-30
updated: 2026-04-30
tags: [meta, lint]
---

# Lint Report: 2026-04-30

## Summary

- Pages scanned: 115 (112 entity pages across tools/models/concepts/people/companies/tutorials/sources/topics, plus index.md, log.md, README.md; excluding _raw/, meta/, CLAUDE.md)
- Issues found: 3 (1 blocker, 0 high, 1 medium, 1 low/suggestion)
- Apr 29 subpath-wikilink fix: HELD — zero subpath wikilinks found across all 115 pages

---

## Blockers (must fix)

### B-01 — Two schema-placeholder wikilinks in `tools/obsidian.md`

- **Page**: `[[obsidian]]`
- **Lines**: 18 and 22
- **Problem**: `[[wikilink]]` and `[[Page Name]]` are schema-example text embedded as live wikilinks in the "How to Use It" and "Key Concepts" sections. Neither slug resolves to a real file. They appear in prose outside of any fenced code block, so Obsidian treats them as dangling links and they pollute the graph view.
  - Line 18: `"...visualizes all [[wikilink]] cross-references between pages."`
  - Line 22: `"- **Wikilinks**: [[Page Name]] syntax for cross-references"`
- **Fix**: Escape both as inline code instead of wikilinks — change `[[wikilink]]` to `` `[[wikilink]]` `` and `[[Page Name]]` to `` `[[Page Name]]` ``. These are illustrative examples, not actual page references.

---

## High (should fix)

_No high-severity issues found._

---

## Medium

### M-01 — "Claude Design" mentioned in `tools/claude-code.md` with no corresponding tool page

- **Page**: `[[claude-code]]`
- **Line**: ~20 (Traction Signals section, April 2026 entry)
- **Problem**: The note explicitly flags "The 'Claude Design' surface (distinct product vs. artifact flow inside Claude.ai) is not yet clearly documented in this wiki." The `[[nateherk-claude-design-masterclass]]` source also describes Claude Design as a distinct capability used for end-to-end brand and launch work. No `tools/claude-design.md` page exists. This is an unlinked concept mentioned across two pages with no home.
- **Fix**: Create `tools/claude-design.md` using the tool schema. Seed it with the traction signal from `[[nateherk-claude-design-masterclass]]` and note its ambiguous status (surface inside Claude.ai vs. distinct product). Mark `status: emerging`.

---

## Low / Suggestions

### L-01 — `sources/nateherk-claude-design-masterclass.md` references `[[naval-ravikant-saas-is-next]]` tangentially

- **Page**: `[[nateherk-claude-design-masterclass]]`
- **Problem**: The Pages Updated section links `[[naval-ravikant-saas-is-next]]` as a cross-reference, but the source content does not update or substantively reference that page — the connection appears to be a loose thematic link. This creates a misleading inbound edge in the graph: `naval-ravikant-saas-is-next` will appear to have been updated by this source when it was not.
- **Fix**: Remove `[[naval-ravikant-saas-is-next]]` from the Pages Updated section of `nateherk-claude-design-masterclass.md`. Pages Updated should list only pages that were materially changed by the ingest.

---

## Checks Completed — Clean

The following checks passed with zero findings:

| Check | Result |
|-------|--------|
| Subpath wikilinks | 0 — fix from Apr 29 commit `11671a1` held completely |
| Dead wikilinks (excluding B-01 placeholders) | 0 |
| Orphan entity pages | 0 |
| Frontmatter gaps (name, type, last_updated/ingested) | 0 |
| Stale last_updated on tool/model pages (before 2026-03-01) | 0 |
| Stale seed pages (status:seed, not updated in 30 days) | 0 |
| Sources missing or empty Pages Updated | 0 |
| Tools missing or empty Traction Signals | 0 |
| Index drift (dead links in index.md) | 0 — all 86 wikilinks resolve |
| New source pages sanity (julian-goldie, nateherk, dami-defi) | Clean frontmatter and structure; one low-severity note (L-01) |

---

## Recommended Fix Order

1. **B-01** (5 min) — Escape the two placeholder wikilinks in `tools/obsidian.md` as inline code. Two-character change each; eliminates dangling graph nodes immediately.
2. **M-01** (30 min) — Create `tools/claude-design.md`. The "Claude Design" capability is now referenced across two pages (`claude-code.md` and `nateherk-claude-design-masterclass.md`) without a home. The `claude-code.md` page already has a note flagging this gap.
3. **L-01** (2 min) — Remove the stray `[[naval-ravikant-saas-is-next]]` from `nateherk-claude-design-masterclass.md` Pages Updated. No content change needed, just tidy the cross-reference list.
