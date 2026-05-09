---
type: meta
title: "Lint Report 2026-05-08"
created: 2026-05-08
updated: 2026-05-08
tags: [meta, lint]
status: closed
---

# Lint Report: 2026-05-08

Run after two commits on branch `ingest/2026-05-08-daily-brief` (PR #14, open). 200 pages scanned (excludes `meta/`, `Daily Briefs/`, `_raw/`, `.obsidian/`). Today's new pages under focused scrutiny: `tools/claude-cowork`, `tools/claude-agent-sdk`, `companies/unconventional-ai`, `concepts/ai-energy-efficiency`, `people/naveen-rao`, `people/peter-mcmahon`, and 6 new source pages.

> [!note] Branch context
> The 2026-05-07 ingest (PR #12) merged to `main`. The 2026-05-08 ingest is on the open branch `ingest/2026-05-08-daily-brief` (PR #14). Index entries for today's new pages are on this branch and not yet in `main`.

## Summary

| Check | Count | Severity |
|---|---|---|
| Pages scanned | 200 | — |
| Dead wikilinks (real, not false positives) | **2** | critical |
| False-positive dead links (in backtick code spans or prose notes) | 6 | (not issues) |
| Orphan entity pages | **0** | clean |
| Frontmatter gaps (name/title, type, last_updated, status) | **0** | clean |
| Stale tool/model `last_updated` (>60 days) | **0** | clean |
| Tools missing Traction Signals | **0** | clean |
| Sources missing Pages Updated | **0** | clean |
| Empty sections (heading with no body) | **0 real** (9 false positives — all parent headings with sub-headings) | clean |
| Index entries with no file | **0** | clean |
| Entity pages not in index | **23** | medium |
| `_raw/` files not in manifest | **14** | medium |
| Slug-vs-display-name wikilink mismatches | **1** | (false positive — inside backtick span) |
| Contradictions across pages | **1** | low |
| Cross-reference notes without person pages | **1** | low |

**Issues found: 4 real (2 critical, 0 high, 1 medium, 1 low)**

---

## Critical (must fix)

### C-01 — Dead wikilink: `[[claude-opus-4-6]]` in NLA source page

- **Affected page**: `sources/anthropic-natural-language-autoencoders-2026-05`
- **Line 11**: `Demonstrated on [[claude-opus-4-6]], [[claude-mythos]] preview, and Claude Haiku 3.5.`
- **Problem**: `claude-opus-4-6` has no model page. The wiki has `models/claude-opus-4-7.md` (the successor). Per `models/claude-opus-4-7.md` line 16 and 21, Claude Opus 4.6 is explicitly referenced as the prior Opus generation — a real model that was in production before the May 2026 Code w/ Claude 2026 announcement. The link target does not exist.
- **Options**:
  1. Change `[[claude-opus-4-6]]` to unlinked prose (`Claude Opus 4.6`) until a model page is created — lowest-friction fix that keeps the factual claim intact.
  2. Create a stub `models/claude-opus-4-6.md` so the reference resolves. The claude-opus-4-7 page provides enough context for a thin stub (predecessor model, available pre-May 2026, used in NLA paper alongside Mythos preview and Haiku 3.5).
- **Suggested fix**: Option 1 now; Option 2 if Opus 4.6 benchmarks or community sentiment get ingested.

**STATUS: FIXED** — Changed `[[claude-opus-4-6]]` to plain prose `Claude Opus 4.6` on line 11 of `sources/anthropic-natural-language-autoencoders-2026-05.md`.

### C-02 — Dead wikilink: `[[dario-amodei]]` in Dario B2B source page

- **Affected page**: `sources/realbigbrainai-dario-b2b-vs-consumer-2026-05-07`
- **Line 26**: `- [[dario-amodei]] would be the natural target if a person page existed; for now this take is captured on the Anthropic page itself.`
- **Problem**: This is a self-aware note saying a page doesn't exist — but it uses live wikilink syntax, so Obsidian treats `[[dario-amodei]]` as a dangling link and the lint script flags it.
- **Suggested fix**: Convert `[[dario-amodei]]` to inline code `` `dario-amodei` `` in the note. The note's meaning is preserved; the dangling graph node disappears. Alternatively: create a minimal person page stub for Dario Amodei (co-founder/CEO of Anthropic) — he is the single most-cited Anthropic voice across 5+ sources in the wiki and the absence of a person page is increasingly conspicuous.

**STATUS: FIXED** — Changed `[[dario-amodei]]` to inline code `` `dario-amodei` `` in the source page note.

---

## Warnings (should fix)

### W-01 — 23 source pages not listed in `index.md`

- **Affected pages** (all in `sources/`): `amplify-amit-jain-interview`, `anthropic-claudes-constitution`, `anthropic-constitutional-ai-research`, `cognitive-revolution-luma-worldsim`, `datachaz-google-design-md`, `feifei-substack-spatial-intelligence`, `github-hornof-profile`, `linkedin-luke-hornof-2026`, `post-aakashgupta-jensen-huang-management`, `post-realBigBrainAI-dorsey-ai-rebuild`, `reddit-3-things-claude-output-quality`, `reddit-llm-wiki-weekend-build`, `techcrunch-luma-uni1`, `thread-aakashgupta-1b-model`, `thread-milkroadai-hassabis-agi`, `thread-minchoi-gpt-image-2`, `thread-phosphenq-karpathy-video`, `thread-phosphenq-lecun-lecture`, `thread-zan2434-flipbook`, `wikipedia-andrew-ng`, `wikipedia-fei-fei-li`, `wikipedia-yann-lecun`, `zodchiii-anatomy-perfect-skill`
- **Problem**: These are all sources ingested during the April 2026 batch (initial wiki build). All have 1–10 inbound wikilinks from other pages and are reachable via the graph — but they do not appear in the `index.md` Sources & References section. The index only added sources starting from a certain point in the batch history. Users browsing the index cannot discover these 23 pages by scanning the catalog.
- **Context**: Not a regression from today's ingest — this gap predates PR #14. The previous lint (2026-05-01) did not flag these because the check was not run that broadly. Today's fix of index.md added the 2026-05-07 and 2026-05-08 source entries correctly; the gap is in the older foundational batch.
- **Suggested fix**: Add a "Foundational source batch (April 2026)" subsection to `index.md` under Sources & References, listing the 23 omitted pages. This is the same pattern used for "Foundational primary sources" (added during the 2026-05-01 lint-fix). Owner to decide whether to add all 23 or only the substantive ones (filtering out `linkedin-luke-hornof-2026`, `github-hornof-profile`, and the Wikipedia stubs as owner-internal or background material).

**STATUS: FIXED** — Added "Foundational source batch (April 2026)" subsection to `index.md` Sources & References listing all 23 entries with one-line descriptions. All 23 slugs verified to point at existing source files. Owner can prune individual entries later if any are deemed too low-signal for the catalog.

---

## Suggestions (worth considering)

### S-01 — `_raw/` manifest: 14 files from the 2026-05-07/08 ingest batch lack manifest entries

- **Unmanifested files**: `Claude Cowork — Interactive Cheat Sheet.md`, `Claude Made Agent Memory Real. But Semantics and Ontology Are Still Missing.md`, `Claude Managed Agents Point to the Next AI Infra Layer Company Brain.md`, `How to improve AI energy efficiency by 1000x.md`, `Post by @realBigBrainAI on X 1.md`, `Post by @zodchiii on X.md`, `Post by Naveen Rao on LinkedIn.md`, `anthropic-natural-language-autoencoders-2026-05.md`, `bsuh-agents-need-control-flow-2026-05.md`, `cheng-zhang-distributed-icl-2026-05.md`, `willison-andon-cafe-stockholm-2026-05-07.md`, `willison-anthropic-xai-colossus-2026-05-07.md`, `willison-code-w-claude-2026-liveblog.md`, `willison-firefox-claude-mythos-2026-05-07.md`
- **Status**: All 14 have corresponding `sources/` pages that exist and are correctly cross-referenced. This is a manifest-bookkeeping gap, not a content gap. All pages are reachable and accurate.
- **Suggested fix**: Backfill the 14 entries into `_raw/.manifest.json` before or after PR #14 merges. Pattern is the same as the April 29 manifest backfill. No content changes needed.

### S-02 — Missing `people/dario-amodei` page

- **Context**: The B2B-vs-consumer source page (`sources/realbigbrainai-dario-b2b-vs-consumer-2026-05-07`) explicitly notes that Dario Amodei is the natural target for a person page. Dario is Anthropic's co-founder and CEO, and his framing ("structural, not moral" B2B choice) appears across multiple wiki sources by reference. The C-02 fix (above) silences the dead link by changing to inline code, but the underlying gap — no person page for the most prominent Anthropic voice — remains.
- **Suggested fix**: Create `people/dario-amodei.md` using the schema. Seed it with: the B2B-vs-consumer structural-choice framing from `sources/realbigbrainai-dario-b2b-vs-consumer-2026-05-07`, the enterprise JV from `sources/anthropic-enterprise-ai-services-company-2026-05`, and the co-founder/CEO biography (sourced or marked `[unsourced]`). Batch with the next Dario primary source ingest.

---

## False Positives (not issues — documented for linter calibration)

The lint script flagged these as dead links; all are correctly escaped or contextual notes:

1. `tools/obsidian.md` — `[[wikilink]]` and `[[Page Name]]` appear inside double-backtick spans (`` `[[wikilink]]` `` and `` `[[Page Name]]` ``). Correctly escaped since the 2026-04-30 lint-fix (B-01). Obsidian does not treat these as live links.
2. `meta/lint-report-2026-04-30.md` and `meta/lint-report-2026-05-01.md` — schema-placeholder examples and historical lint-item text use `[[wikilink]]`, `[[Page Name]]`, and `[[LLM Wiki Pattern]]` as illustrative text inside the report body. Meta files are excluded from the lint scope but the script swept them.
3. "Empty section" false positives (9 detected): all are parent `##` headings whose content is organized entirely under `###` sub-headings. No heading has a genuinely empty section: `tools/claude-cowork` (How to Use It → sub-headings), `concepts/claude-certified-architect` (Current State → sub-headings), `concepts/company-brain` (Three Layers → sub-headings), `companies/world-labs` (Technical Thesis → sub-headings), `topics/doing-great-work` (Core Principles → sub-headings), `tutorials/personal-ai-agent-claude-desktop-mcp` (Steps → sub-headings, COMMANDS → sub-headings), `tutorials/writing-claude-code-skills` (The 6 Patterns → sub-headings). All are correct structure.
4. `tools/obsidian.md` slug-vs-display-name flag: `[[Page Name]]` is inside a backtick span — same as item 1 above.

---

## Checks Run (clean)

| Check | Result |
|---|---|
| Dead wikilinks (real) | 2 found, both fixed (C-01, C-02) |
| Orphan entity pages | 0 — CLAUDE.md, README.md, log.md are expected non-linked root files |
| Frontmatter gaps (name/title, type, last_updated, status) | 0 across 200 pages |
| Stale last_updated (>60 days, tools+models) | 0 |
| Tools missing Traction Signals | 0 |
| Sources missing Pages Updated | 0 |
| Index entries with no corresponding file | 0 |
| Status contradictions | 0 real contradictions — claude-cowork `gaining-traction` in tool page matches usage in index; claude-agent-sdk `emerging` is consistent throughout |
| Today's new pages — cross-reference symmetry | All clean: `tools/claude-cowork` ↔ `tools/claude-desktop` ↔ `sources/claude-cowork-cheatsheet-2026-05-07`; `companies/unconventional-ai` ↔ `people/naveen-rao` ↔ `people/peter-mcmahon` ↔ `concepts/ai-energy-efficiency` ↔ `sources/mcmahon-1000x-energy-efficiency-2026-05` ↔ `sources/nrao-linkedin-1000x-2026-05`; `concepts/company-brain` ↔ `sources/ashwingop-semantics-ontology-2026-05-07` ↔ `sources/ashwingop-managed-agents-company-brain-2026-05-08`; all bidirectional |
| `_raw/` unprocessed drops | 0 unprocessed — all 14 unmanifested files have corresponding source pages; 1 skipped-with-note (`Post by @zodchiii on X.md` → `sources/zodchiii-anatomy-perfect-skill` already existed; `Post by @Av1dlive on X.md` explicitly skipped in manifest as promo-only) |
