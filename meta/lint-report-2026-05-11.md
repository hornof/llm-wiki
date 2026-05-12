---
type: meta
title: "Lint Report 2026-05-11"
created: 2026-05-11
updated: 2026-05-11
tags: [meta, lint]
status: open
---

# Lint Report: 2026-05-11

Full-wiki health check run against current HEAD on branch `ingest/2026-05-10` (last commit fb27437). 221 content pages scanned across `tools/` (20), `models/` (3), `concepts/` (24), `people/` (37), `companies/` (26), `tutorials/` (2), `topics/` (4), `sources/` (105). Excludes `meta/`, `_raw/`, `canvases/`, `Daily Briefs/`, `.obsidian/`.

---

## Summary

| Check | Count | Severity |
|---|---|---|
| Pages scanned | 221 | — |
| Dead wikilinks (real, not false positives) | **3** | critical / medium |
| Orphan entity pages | **0** | clean |
| Frontmatter gaps (name/type/status/last_updated) | **0** | clean |
| Stale tool/model `last_updated` (>60 days from 2026-05-11) | **0** | clean |
| Tools missing Traction Signals | **0** | clean |
| Sources missing `## Pages Updated` | **0** | clean |
| Entity pages missing from `index.md` | **0** | clean |
| Index entries pointing to nonexistent files | **1** (canvas, not .md) | low |
| Pages over 300 lines | **0** | clean |
| Pages 250–299 lines (approaching limit) | **2** | watch |
| Non-standard path-form wikilink | **1** | low |
| Link to gitignored path | **1** | low |
| Unprocessed `_raw/` drops with no source page | **9** | low |
| Manifest backfill gaps | **15** | low |
| Contradictions across pages | **0 clear** | clean |

**Issues found: 8 real (1 critical, 1 warning, 6 low)**

---

## Critical (must fix)

### C-01 — Dead wikilink: `[[claude]]` in ad-free source page

- **Affected page**: `sources/anthropic-claude-space-to-think-2026-05.md`
- **Line 44**: `- [[claude]] (or rather Claude product positioning in [[anthropic]]) — Claude framed as "a space to think" is the marketing-language commitment; worth tracking against future product changes for drift.`
- **Problem**: `[[claude]]` resolves to nothing — no `claude.md` exists in any content directory. The parenthetical immediately clarifies the intent is the `[[anthropic]]` page; the wikilink is erroneous. Obsidian shows this as a dangling ghost node in the graph view.
- **Suggested fix**: Remove `[[claude]]` and rewrite as plain prose referencing `[[anthropic]]` directly — e.g., `- "A space to think" is the marketing-language commitment for Claude's consumer positioning (tracked on [[anthropic]]); worth monitoring for drift against future product changes.`

---

## Warnings (should fix)

### W-01 — `[[concept]]` placeholder left as live wikilink in research roundup source

- **Affected page**: `sources/dailybrief-research-roundup-2026-05-11.md`
- **Line 70**: `- No new dedicated concept page yet for **KV cache optimization** or **head-wise budgeting** — but if a third paper on this theme lands in the next 30 days, that's the threshold to spin a [[concept]] page.`
- **Problem**: `[[concept]]` is a schema template placeholder used in prose, not a real slug. Obsidian creates a dangling graph node and shows it as a broken link in graph view.
- **Suggested fix**: Replace `[[concept]]` with unlinked prose: `a concept page`. One-word edit; the sentence reads correctly without the wikilink.

---

## Suggestions (worth considering)

### S-01 — Non-standard path-form wikilink in enterprise source page

- **Affected page**: `sources/anthropic-enterprise-ai-services-company-2026-05.md`
- **Line 28**: `- [[sources/anthropic-claude-partner-network]] — no change needed; this source extends the partner-network narrative but doesn't contradict it`
- **Problem**: Per CLAUDE.md conventions, only the `owner/` namespace uses path-form wikilinks. All other wikilinks should use the bare slug. The slug `anthropic-claude-partner-network` exists in `sources/` and resolves correctly as `[[anthropic-claude-partner-network]]`. The `sources/` prefix is redundant and non-standard.
- **Suggested fix**: Replace `[[sources/anthropic-claude-partner-network]]` with `[[anthropic-claude-partner-network]]` on line 28.

### S-02 — `[[Daily Briefs/2026-05-10-personal.md]]` in Opus 4.7 source page links to a gitignored path

- **Affected page**: `sources/anthropic-opus-4-7-launch-2026-04-16.md`
- **Line 53**: The caveat note links `[[Daily Briefs/2026-05-10-personal.md]]` inline.
- **Problem**: `Daily Briefs/` is gitignored (see `.gitignore`). The link resolves locally in Obsidian because the file exists on disk, but it points to a non-versioned file that does not exist in the repository. Anyone pulling this repo won't have the Daily Briefs file; the wikilink is effectively a dead link in the shared context. This is also the only such Daily Briefs wikilink in any source page — the pattern has not spread, but it sets a bad precedent.
- **Suggested fix**: Replace `[[Daily Briefs/2026-05-10-personal.md]]` with unlinked prose — e.g., `the May 10 personal daily brief` — to document the attribution without creating a gitignored wikilink.

### S-03 — `[[agi-debate]]` in `index.md` points to a `.canvas` file, not a `.md` file

- **Affected page**: `index.md` line 124
- **Entry**: `- [[agi-debate]] — visual canvas of the AGI debate: LeCun, Hassabis, Karpathy, Fei-Fei Li, Luma, Silver`
- **Problem**: `agi-debate.canvas` lives in `canvases/`, not in any standard content directory. Obsidian resolves the `[[agi-debate]]` wikilink to the canvas correctly, but the automated lint check flagged it as a stale index entry (no `.md` file found). The canvas is not a markdown entity and cannot have frontmatter, a Traction Signals section, etc. This is a convention gap, not a navigation break.
- **Suggested fix**: No immediate action required — Obsidian navigation works correctly. If canvas entries become more common, add a note to CLAUDE.md clarifying that the `Canvases` section of `index.md` is exempt from standard entity-file lint rules.

### S-04 — `company-brain.md` at 277 lines, approaching the 300-line soft ceiling

- **Affected page**: `concepts/company-brain.md`
- **Current size**: 277 lines. This was also 277 lines on the 2026-05-09 lint — no growth since then, but the 9-part Sentra series is still active.
- **Problem**: The 2026-05-09 lint report already flagged this page. Parts 7, 8, and 9 of the Sentra series have all landed as sources without adding content to the concept page. If Part 10+ arrives and content is added, it will breach 300 lines.
- **Suggested fix**: No action needed today. On the next ingest that adds to `company-brain.md`, consider splitting — separating the "Design Partner Lessons" (year-of-lessons content) from the core "Three-Layer Framework" definition.

### S-05 — `writing-claude-code-skills.md` at 261 lines

- **Affected page**: `tutorials/writing-claude-code-skills.md`
- **Current size**: 261 lines. Within bounds, but worth noting alongside `company-brain.md`.
- **Suggested fix**: No action needed. Monitor if a major skill pattern section is added.

---

## Unprocessed `_raw/` drops (owner decision needed)

28 files in `_raw/` have no manifest entry. 15 of these are processed content with missing manifest bookkeeping (no content action required — just backfill). The remaining 13 are genuinely unprocessed. Nine of those 13 are low-signal or clearly redundant; four warrant owner decision.

### _raw/ files with no manifest entry that ARE already processed (manifest backfill only)

These 15 files have corresponding `sources/` pages. The content is ingested; only the manifest bookkeeping is missing. Backfill when convenient — no content changes needed.

| Raw file | Source page |
|---|---|
| `_raw/anthropic-natural-language-autoencoders-2026-05.md` | `sources/anthropic-natural-language-autoencoders-2026-05.md` |
| `_raw/bsuh-agents-need-control-flow-2026-05.md` | `sources/bsuh-agents-need-control-flow-2026-05.md` |
| `_raw/cheng-zhang-distributed-icl-2026-05.md` | `sources/cheng-zhang-distributed-icl-2026-05.md` |
| `_raw/willison-andon-cafe-stockholm-2026-05-07.md` | `sources/willison-andon-cafe-stockholm-2026-05.md` |
| `_raw/willison-anthropic-xai-colossus-2026-05-07.md` | `sources/willison-anthropic-xai-colossus-2026-05.md` |
| `_raw/willison-code-w-claude-2026-liveblog.md` | `sources/willison-code-w-claude-2026.md` |
| `_raw/willison-firefox-claude-mythos-2026-05-07.md` | `sources/willison-firefox-claude-mythos-2026-05.md` |
| `_raw/MCP vs CLI was the wrong debate.md` | `sources/akshay-pachaar-mcp-vs-cli-2026-05-09.md` |
| `_raw/Karpathy's 4 CLAUDE.md rules cut Claude mistakes from 41% to 11%. After 30 codebases, I added 8 more.md` | `sources/mnilax-claude-md-12-rules-2026-05-09.md` |
| `_raw/Claude Cowork — Interactive Cheat Sheet.md` | `sources/claude-cowork-cheatsheet-2026-05-07.md` |
| `_raw/Claude Made Agent Memory Real. But Semantics and Ontology Are Still Missing.md` | `sources/ashwingop-semantics-ontology-2026-05-07.md` |
| `_raw/Claude Managed Agents Point to the Next AI Infra Layer Company Brain.md` | `sources/ashwingop-managed-agents-company-brain-2026-05-08.md` |
| `_raw/From Systems of Record to the Company Brain Why AI Needs Shared State, Not Just Smarter Tools.md` | `sources/ashwingop-systems-of-record-2026-05-09.md` |
| `_raw/How to improve AI energy efficiency by 1000x.md` | `sources/mcmahon-1000x-energy-efficiency-2026-05.md` |
| `_raw/Post by Naveen Rao on LinkedIn.md` | `sources/nrao-linkedin-1000x-2026-05.md` |

Note: `_raw/Using Claude Code The Unreasonable Effectiveness of HTML 1.md` and `_raw/Using Claude Code The Unreasonable Effectiveness of HTML.md` are duplicate downloads of the same article; both map to `sources/willison-html-effectiveness-2026-05.md`. One can be deleted.

### _raw/ files genuinely unprocessed — owner decision required

**Priority: medium (worth ingesting)**

- `_raw/Agent view in Claude Code.md` (2KB, May 11) — Anthropic blog post introducing Agent View in Claude Code: one place to manage all Claude Code sessions. This is a new product surface from Anthropic, dropped the same day as the ingest/2026-05-10 PR. Not yet processed. If the feature is worth tracking, create a brief source page and add the Agent View capability as a note under `tools/claude-code.md`.
- `_raw/Claude Cookbook.md` (23KB) — Anthropic's official cookbook: 81 practical guides across 15 categories (agents, tools, RAG, evals, multimodal, Skills, integrations, production workflows). This is a substantial primary source that could surface tool traction signals and reinforce or contradict the `tools/claude-code.md` skill section. `_raw/Post by @bibryam on X.md` (0.6KB, May 11) is a pointer to the same resource — that post is low-signal on its own but confirms community discovery of the Cookbook.
- `_raw/Post by @aakashgupta on X 2.md` (2KB, May 10) — DoorDash use case: new engineer finds three-month-old PM decision context via AI instead of pinging the human. Clear company-brain framing; independent practitioner signal that strengthens the `[[company-brain]]` concept page. Different content from the growth-acceleration post.

**Priority: low (assess before ingesting)**

- `_raw/How to Build Your First AI Agent That Companies Will Pay $10K+ For (Full Course).md` (14KB) — long-form agent course transcript. May surface tool traction signals; practitioner-facing curriculum. Overlap with existing tutorials not yet assessed.
- `_raw/How to Use Claude Skills to Automate Any Workflow (Full Course).md` (9KB) — Claude Skills course transcript. May reinforce or contradict `tools/claude-code.md` skill section.
- `_raw/Post by @andruyeung on X.md` (4KB, May 11) — Anthropic is paying up to $315K/year for a Claude Evangelist role (startup ecosystem face). Organizational signal, not a tool or concept update. Low-priority unless tracking Anthropic's go-to-market hiring.
- `_raw/Post by @karpathy on X.md` (4KB, May 11) — Karpathy endorses HTML response formatting (May 8 post). This is the primary source for the HTML-over-Markdown tip; the existing `sources/willison-html-effectiveness-2026-05.md` covers Simon Willison's amplification of Thariq Shihipar, but not Karpathy's own independent corroboration. Adding it would create a third independent signal for the practice. Low-urgency since the wiki already captures the pattern.

**Priority: discard or skip**

- `_raw/Post by @realBigBrainAI on X 1.md` (2KB, May 7) — Duplicate Web Clipper download of the Dario B2B post already ingested as `sources/realbigbrainai-dario-b2b-vs-consumer-2026-05-07.md`. Same URL, same content. Safe to delete.
- `_raw/Post by @zodchiii on X.md` (3KB, May 7) — zodchiii posts about an "Anthropic 2026 agent roadmap" video. The tweet is thin (just "watch this video") and a commenter flags the video as 7+ months old. Low signal; safe to skip.
- `_raw/Post by @aakashgupta on X 1.md` (3KB, May 9) — Growth acceleration post ($14B ARR at log-scale). The content is already fully ingested as `sources/aakashgupta-anthropic-growth-acceleration-2026-05-09.md`. Manifest backfill only; no new content.

---

## Structural observations (no action required)

- **No orphans**: All 221 content pages are linked from at least one other page. The three newest entity pages (`tools/river.md`, `people/thariq-shihipar.md`, `people/tobi-lutke.md`) each have inbound links from their source pages and `index.md`.
- **No frontmatter gaps**: All 221 pages have the required fields for their entity type. Companies use non-schema `status:` values (`active`, `early-stage`, `public`, `established`) — consistent across all company pages, representing a local convention.
- **No stale tool/model pages**: All `tools/` and `models/` pages have `last_updated` dates of 2026-04-21 or later. Oldest: `crewai`, `llama-index`, `mem0`, `obsidian-dataview`, `obsidian`, and `ollama` (all `2026-04-21`) — 20 days within the 60-day threshold.
- **No Traction Signals gaps**: Every tool page has a populated Traction Signals section.
- **No index omissions**: All 116 non-source entity pages appear in `index.md`. All 105 source pages appear in `index.md` under Sources & References.
- **`[[index]]` in source pages**: Five source pages (`cloudflare-stripe-projects-agents-2026-05`, `deepmind-decoupled-diloco-2026-05`, `karpathy-lecun1989-33-years`, `karpathy-microgpt-2026-02`, `latent-space-lupsasca-vibe-physics-2026-05`) use `[[index]]` in their Pages Updated section. Obsidian resolves this to `index.md` at the vault root; this is not a dead link. The convention is slightly informal — `index.md` is not a standard content entity — but it is harmless and readable.
- **Three OpenAI source pages** (`openai-testing-ads-in-chatgpt-2026-05-08`, `openai-realtime-voice-api-2026-05-08`, `openai-running-codex-safely-2026-05-08`) remain marked as secondary-source synopses with primary URLs un-fetched. Correctly documented in each page. Deferred from 2026-05-09 lint — revisit on next OpenAI session.
- **False positives from prior lint runs**: `[[wikilink]]` and `[[Page Name]]` in `tools/obsidian.md` are correctly inside backtick spans (fixed 2026-04-30). Prior lint reports in `meta/` contain these as historical text — both are correctly excluded from scope.

---

## Recommended fixes (priority order)

1. **C-01 — Fix `[[claude]]` dead link** in `sources/anthropic-claude-space-to-think-2026-05.md:44`. One-line edit; removes a ghost node from the graph. Replace with plain prose pointing to `[[anthropic]]`.

2. **W-01 — Fix `[[concept]]` placeholder** in `sources/dailybrief-research-roundup-2026-05-11.md:70`. One-word edit; replace `[[concept]]` with `a concept`. Removes a second ghost node.

3. **S-02 — Fix `[[Daily Briefs/2026-05-10-personal.md]]`** in `sources/anthropic-opus-4-7-launch-2026-04-16.md:53`. Replace with unlinked prose. Prevents the gitignored-path pattern from spreading to other source pages.

4. **S-01 — Fix path-form `[[sources/anthropic-claude-partner-network]]`** in `sources/anthropic-enterprise-ai-services-company-2026-05.md:28`. Drop the `sources/` prefix. Reinforces the CLAUDE.md convention.

5. **Unprocessed drops — decide on three medium-priority items**: `Agent view in Claude Code.md`, `Claude Cookbook.md`, and the aakashgupta DoorDash company-brain post (`Post by @aakashgupta on X 2.md`). These are the highest-signal unprocessed drops. The Agent View blog post is a same-day Anthropic announcement that the last ingest missed; the Cookbook is a substantial primary source; the DoorDash post is an independent company-brain signal.
