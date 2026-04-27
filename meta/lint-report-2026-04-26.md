---
type: meta
title: "Lint Report 2026-04-26"
created: 2026-04-26
updated: 2026-04-26
tags: [meta, lint]
---

# Lint Report: 2026-04-26

## Summary

- Pages scanned: 76
- Issues found: 5
- Auto-fixable: 4
- Needs review: 1

---

## Dead Links

### `[[owner-profile]]` in `owner/publications.md:137`
**Persisting from prior lint report (2026-04-24) — not yet fixed.**
`[[owner-profile]]` does not resolve. The correct link is `[[owner/profile]]`.
- Fix: change line 137 of `owner/publications.md` from `[[owner-profile]]` to `[[owner/profile]]`
- Safe to auto-fix: yes

### Not-real dead links (intentional / prose)
- `[[wikilink]]` and `[[Page Name]]` in `tools/obsidian.md` — example syntax embedded in prose explanation; not real links
- `[[LLM Wiki Pattern]]` in `CLAUDE.md` — intentional negative example of wrong format in conventions section
- `learn-agentic-ai` in `sources/github-hornof-profile.md` — plain text mention (no `[[` brackets), not a wikilink

---

## Orphan Pages

None confirmed. `tutorials/writing-claude-code-skills.md` was flagged by the slug-match script but has 4 real inbound links via path-prefix format (`[[tutorials/writing-claude-code-skills]]`) in `index.md`, `tools/claude-code.md`, and `sources/zodchiii-anatomy-perfect-skill.md`. Not an orphan.

---

## Missing Cross-References

### `[[aakashgupta]]` missing from `sources/thread-aakashgupta-1b-model.md`
The `aakashgupta` person page was created *after* this source was ingested. The source correctly credits `@aakashgupta` in its title and URL but has no wikilink to the person page in its body or Pages Updated section.
- Fix: add `[[aakashgupta]]` to the Pages Updated section of `sources/thread-aakashgupta-1b-model.md`
- Safe to auto-fix: yes

### `[[doing-great-work]]` missing from `people/richard-hamming.md`
The topics page links to Hamming; Hamming's page doesn't link back. Minor navigational gap.
- Fix: add `[[doing-great-work]]` reference to `people/richard-hamming.md` under Resources or a new See Also line
- Safe to auto-fix: yes

---

## Frontmatter Gaps

### `tools/claude-code.md` — `last_updated` is stale
Page shows `last_updated: 2026-04-24` but was meaningfully updated on 2026-04-26 (Skill Writing section added from `[[zodchiii-anatomy-perfect-skill]]`).
- Fix: update to `last_updated: 2026-04-26`
- Safe to auto-fix: yes

---

## Log Discrepancy (Needs Review)

The log entry for `2026-04-21 | ingest | github-claude-obsidian` records three pages as created: `hot-cache`, `claude-canvas`, and `agrici-daniel`. None of these pages exist in the vault today. Likely created in a session that was not committed and then lost.

- `hot-cache.md` — referenced as "(new)" in the log but no file exists; `[[hot-cache]]` was also flagged in the prior lint as a dead link in index.md (since resolved)
- `claude-canvas.md` — same situation
- `agrici-daniel.md` — same situation

Options:
1. Re-create stubs for these three entities (they are: a Claude Code caching concept, a claude-obsidian canvas feature, and the plugin's author)
2. Accept the loss and note it as a known gap
3. Re-ingest `_raw/github-claude-obsidian.md` to recreate them properly

Recommendation: re-ingest `github-claude-obsidian.md` (force) or create stubs. The claude-obsidian plugin has 2,626 stars and its author and canvas feature are worth having pages for.

---

## Stale Claims

None. Wiki is 5 days old; 60-day threshold not reached for any page.

---

## Action Table

| # | Issue | Severity | Auto-fix? |
|---|-------|----------|-----------|
| 1 | `[[owner-profile]]` → `[[owner/profile]]` in publications.md | Medium | Yes |
| 2 | Add `[[aakashgupta]]` to thread-aakashgupta-1b-model Pages Updated | Low | Yes |
| 3 | Add `[[doing-great-work]]` link from richard-hamming.md | Low | Yes |
| 4 | Update `claude-code.md` `last_updated` to 2026-04-26 | Low | Yes |
| 5 | Missing pages: hot-cache, claude-canvas, agrici-daniel | Medium | Ask owner |
