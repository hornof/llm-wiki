---
title: Lint Report 2026-05-15
type: lint-report
created: 2026-05-15
last_updated: 2026-05-15
---

## Summary

- Pages scanned: 273 entity pages (21 tools, 3 models, 28 concepts, 43 people, 28 companies, 2 tutorials, 4 topics, 2 owner, 142 sources) + index.md, log.md
- _raw/ files: 117 total, 77 tracked in manifest
- Issues found: 9 (3 critical, 3 warnings, 3 suggestions)

| Check | Status |
|---|---|
| 1. Dead wikilinks | 3 critical, 2 warnings, 3 info |
| 2. Orphan pages | Clean |
| 3. _raw/ orphans | 2 truly unprocessed; 38 manifest-gap (minor) |
| 4. Stale last_updated | Clean — all tools/models updated 2026-04-21 or later |
| 5. Frontmatter gaps | Clean |
| 6. Empty required sections | 1 warning |

---

## Critical (must fix)

### C-01: [[benln]] — dead people link in entity files

- **Affected pages:** [[concepts/ai-native-organizations]] (line 82), [[sources/benln-dorsey-mini-agi-2026-05-13]] (lines 11, 40)
- **Problem:** Three `[[benln]]` wikilinks appear in entity files. No `people/benln.md` exists.
- **Suggested fix:** Either create a minimal `people/benln.md` stub (benln = X/Twitter aggregator, strong-curation pattern, no original takes) or replace `[[benln]]` with unlinked prose `benln` in all three occurrences. The source page already notes "not a tracked person — no entity page created" for bibryam; benln warrants the same treatment given the consistent aggregator-only role.

### C-02: [[tools/codex]] — dead path-form link in source file

- **Affected page:** [[sources/latentspace-codex-rises-claude-meters-2026-05-14]] (line 16)
- **Problem:** `[[tools/codex|Codex]]` is a piped wikilink pointing to `tools/codex.md`, which does not exist. OpenAI Codex has no tool page in the wiki.
- **Suggested fix:** Replace with unlinked prose `Codex` (no entity page created) or `[[openai]]`'s Codex section reference. If Codex warrants its own page, create `tools/codex.md` following the tool schema.

### C-03: [[concepts/agentic-ai]] — wrong path-form in four source files

- **Affected pages:**
  - [[sources/meenakshiyacs-agentic-ai-architecture-cheat-sheet-2026-05-14]] (lines 39, 44, 50)
  - [[sources/eng-khairallah-multi-agent-team-course-2026-05-15]] (line 81)
- **Problem:** Four occurrences of `[[concepts/agentic-ai]]` but the file lives at `topics/agentic-ai.md`, not `concepts/agentic-ai.md`. Obsidian will not resolve this link.
- **Suggested fix:** Replace all four occurrences of `[[concepts/agentic-ai]]` with `[[agentic-ai]]` (bare slug, resolves correctly to `topics/agentic-ai.md`).

---

## Warnings (should fix)

### W-01: [[kv-cache-optimization]] — planned concept page never created

- **Affected page:** [[sources/dailybrief-research-roundup-2026-05-12]] (lines 42, 59)
- **Problem:** The source page explicitly notes this is a threshold-triggering link: "Sets the threshold for spinning a `[[kv-cache-optimization]]` concept page on next ingest that touches this thread." The page has not been created. The link is dead.
- **Suggested fix:** Create `concepts/kv-cache-optimization.md` (or fold into [[ai-energy-efficiency]] per the source's alternate suggestion). Either way, resolve the dangling link.

### W-02: [[sources/fastcompany-amazon-workers-ai-task-faking-2026-05]] — missing `## Pages Updated` section

- **Affected page:** [[sources/fastcompany-amazon-workers-ai-task-faking-2026-05]]
- **Problem:** Source page has no `## Pages Updated` section. Required by the sources schema. The page was created from a 403-paywalled article so no entity pages were updated — but the section should still be present (even if it reads "None — primary inaccessible, no entity pages updated").
- **Suggested fix:** Add `## Pages Updated` with a note that the primary was paywalled and no entity pages were touched.

### W-03: `[[agi-debate]]` in `index.md` — canvas file without companion `.md`

- **Affected page:** [[index]] (line 137 under Canvases)
- **Problem:** `[[agi-debate]]` in `index.md` resolves to a `.md` file, but the file is `canvases/agi-debate.canvas` (no `.md` companion). Obsidian's graph view will show this as an unresolved link. This issue was flagged as S-03 in the 2026-05-11 lint report and deferred with "no action."
- **Suggested fix:** Either create a thin `canvases/agi-debate.md` companion page (one paragraph summary, link to the canvas), or change the index entry to plain text with no wikilink. The `[[agi-debate.canvas]]` form does not render as a navigable wikilink in Obsidian's standard mode.

---

## Suggestions (worth considering)

### S-01: _raw/ manifest gap — 38 processed files not tracked

- **Affected:** `_raw/.manifest.json`
- **Detail:** 40 files in `_raw/` are absent from `.manifest.json`. 38 of those have matching `sources/` pages (the files were ingested correctly but the manifest was not updated). The 38-file gap is a bookkeeping debt, not a content problem. It makes future "is this file processed?" checks unreliable.
- **Suggested fix:** Backfill `.manifest.json` with the 38 known-processed files in the next convenient ingest pass. Low urgency — the file is gitignored and Obsidian does not read it — but accumulating manifest drift makes the lint check noisier over time.

### S-02: Two truly unprocessed `_raw/` drops

- **Files:**
  - `_raw/How to Build Your First AI Agent That Companies Will Pay $10K+ For (Full Course).md`
  - `_raw/Post by @rambuilds_ on X.md`
- **Detail:** These two files have no matching `sources/` page and no manifest entry. They may be candidates for ingest or deliberate discard.
- **Suggested fix:** Review both files. If worth ingesting, run through the standard ingest workflow. If not, either delete or document as intentionally skipped in `.manifest.json`.

### S-03: [[bibryam]] — undocumented person reference in source file

- **Affected page:** [[sources/anthropic-claude-cookbook-2026-05]] (line 11, 32)
- **Detail:** `[[bibryam]]` appears as a wikilink in the source summary ("surfaced into the wiki via `[[bibryam]]`'s May 11 2026 X post"). Line 32 documents the decision: "bibryam (one-off X post surfacing; not a tracked person — no entity page created)." But the wikilink on line 11 is still a live dead link — Obsidian will show it as unresolved.
- **Suggested fix:** Replace `[[bibryam]]` on line 11 with unlinked prose `bibryam`, consistent with the stated intent on line 32. The decision not to track this person is correct; the wikilink form is inconsistent with that decision.

---

## Notes on Checks Not Flagging Issues

- **Orphan pages:** All 273 entity pages have at least one inbound wikilink. Only `README.md` (root) has zero inbound links, which is expected and not an entity page.
- **Stale last_updated (tools/models):** No pages in `tools/` or `models/` have `last_updated` before 2026-03-16. The earliest dates are 2026-04-21 (several tools from the initial wiki build). All within the 60-day threshold as of 2026-05-15.
- **Frontmatter completeness:** All entity-folder pages (`tools/`, `models/`, `concepts/`, `people/`, `companies/`, `tutorials/`, `topics/`, `owner/`) have `name`, `type`, and `last_updated`. All `sources/` pages have `title`, `type`, and `ingested`. No gaps.
- **Empty Traction Signals (tools/):** All 21 tool pages have a non-empty `## Traction Signals` section.
- **Empty Pages Updated (sources/):** Only the fastcompany source is missing this section (W-02 above). All other 141 sources pages have the section.
- **Large pages:** No entity pages exceed 300 lines. `CLAUDE.md` (313 lines) and `index.md` (302 lines) exceed the threshold but are root administrative files, not entity pages.
