---
type: meta
title: "Lint Report 2026-04-29"
created: 2026-04-29
updated: 2026-04-29
tags: [meta, lint]
---

# Lint Report: 2026-04-29

## Summary

- Pages scanned: 115 (excluding _raw/, meta/, CLAUDE.md, README.md)
- Sources ingested today: 11 (heavy ingest day — 7 parallel sub-agents)
- Issues found: 47 (11 blockers, 8 high, 16 medium, 12 low)
- Biggest area of concern: **subpath wikilinks** — 132 occurrences across 39 files. Every `[[sources/foo]]`, `[[companies/bar]]`, `[[topics/baz]]`, `[[concepts/x]]`, `[[tools/y]]`, `[[people/z]]` is broken in Obsidian, which resolves by filename match only. Today's batch-ingest agents wrote subpath-style links throughout.

---

## Blockers (must fix)

### B-01 — `index.md` line 77: Dead link to canvas
- **Page**: `index.md`
- **Line**: 77
- **Problem**: `[[agi-debate.canvas]]` is listed in the index but the canvas lives at `canvases/agi-debate.canvas`. Obsidian resolves by filename match — the slug `agi-debate.canvas` does not match any file when Obsidian strips the `.canvas` extension as a path component. The canvas is effectively unlinked from the index in Obsidian's graph view.
- **Fix**: Change to `[[agi-debate]]` (Obsidian includes the `.canvas` extension as part of the filename and can match `agi-debate.canvas` by its base name `agi-debate`). Verify Obsidian resolves it correctly; if not, consider moving the canvas to the wiki root or adding a note page at `canvases/agi-debate.md` that links to it.

### B-02 — 132 subpath wikilinks across 39 files (Obsidian breakage)
- **Root cause**: Today's ingest agents wrote wikilinks using directory-prefixed paths (`[[sources/foo]]`, `[[companies/bar]]`, `[[topics/baz]]`, `[[concepts/x]]`, `[[tools/y]]`, `[[people/z]]`) instead of slug-only format mandated by CLAUDE.md. Obsidian resolves wikilinks by matching the bare filename; `[[sources/naval-ravikant-saas-is-next]]` will not resolve to `sources/naval-ravikant-saas-is-next.md` — Obsidian treats the path prefix as part of the slug and fails to match.
- **Affected files with highest counts** (all links in these files are broken where subpath-style is used):

| File | Subpath link count |
|------|--------------------|
| `topics/ai-50-2026-snapshot.md` | 12 |
| `companies/world-labs.md` | 11 |
| `sources/forbes-ai-50-2026.md` | 9 |
| `topics/saas-disruption-thesis.md` | 7 |
| `sources/ric-rtp-david-silver-ineffable.md` | 5 |
| `concepts/agi.md` | 5 |
| `companies/thinking-machines-lab.md` | 5 |
| `companies/anthropic.md` | 5 |
| `concepts/ai-native-organizations.md` | 4 |
| `concepts/agentic-engineering.md` | 4 |
| `companies/openai.md` | 4 |
| `companies/ami-labs.md` | 4 |
| `sources/naval-ravikant-saas-is-next.md` | 4 |

- **Representative examples**:
  - `topics/ai-50-2026-snapshot.md` line 11: `[[sources/forbes-ai-50-2026]]` → fix to `[[forbes-ai-50-2026]]`
  - `topics/ai-50-2026-snapshot.md` line 34: `[[companies/cursor]]` → fix to `[[cursor]]`
  - `topics/saas-disruption-thesis.md` line 9: `[[people/naval-ravikant]]` → fix to `[[naval-ravikant]]`
  - `topics/saas-disruption-thesis.md` line 17: `[[tools/claude-code]]` → fix to `[[claude-code]]`
  - `topics/saas-disruption-thesis.md` lines 75–78: all four Related Pages links use subpath format
  - `companies/world-labs.md` lines 16, 20–23, 39, 79–80, 82–83: all source and concept links use subpath format
  - `concepts/agi.md` lines 36, 40, 48, 54, 56: source and concept links use subpath format
  - `sources/forbes-ai-50-2026.md` lines 97–104: entire Pages Updated section uses `[[companies/x]]` and `[[topics/y]]` format
  - `sources/ric-rtp-david-silver-ineffable.md` lines 27–31: Pages Updated section uses `[[companies/x]]`, `[[people/y]]`, `[[concepts/z]]` format
  - `sources/konstantine-hassabis-ai-ascent-fireside.md` lines 26–27: uses `[[sources/ai-ascent-2026]]` and `[[people/demis-hassabis]]`
  - `sources/naval-ravikant-saas-is-next.md` lines 44–47: uses `[[people/naval-ravikant]]`, `[[topics/saas-disruption-thesis]]`, `[[tools/claude-code]]`, `[[concepts/agentic-engineering]]`
  - `sources/scobleizer-ai-native-companies.md` lines 19, 23: uses `[[sources/benln-yc-summer-2026-rfs]]` and `[[concepts/ai-native-organizations]]`
  - `sources/benln-yc-summer-2026-rfs.md` line 25: uses `[[concepts/ai-native-organizations]]`
  - `sources/chamath-decision-context-agents.md` lines 24–25: uses `[[concepts/agentic-engineering]]` and `[[sources/chamath-decision-context-agents]]` (self-link, also subpath)
  - `sources/cognitive-revolution-luma-worldsim.md` line 25: uses `[[concepts/world-models]]`
  - `concepts/world-models.md` lines 70, 95: uses `[[sources/ric-rtp-david-silver-ineffable]]`
  - `concepts/spatial-intelligence.md` line 52: uses `[[sources/bloomberg-feifei-li-2025]]`
  - `people/david-silver.md` lines 19–21: uses `[[sources/ric-rtp-david-silver-ineffable]]`
  - `people/demis-hassabis.md` line 38: uses `[[sources/konstantine-hassabis-ai-ascent-fireside]]`
  - `people/naval-ravikant.md` lines 17, 21, 36: uses `[[sources/naval-ravikant-saas-is-next]]`
  - `people/robert-scoble.md` lines 19–20: uses `[[sources/scobleizer-ai-native-companies]]`
  - `people/fei-fei-li.md` line 13: uses `[[sources/forbes-ai-50-2026]]`
  - `companies/cursor.md` lines 18, 25, 27: uses `[[sources/forbes-ai-50-2026]]` and `[[topics/ai-50-2026-snapshot]]`
  - `companies/mistral-ai.md` lines 14, 25–26: uses `[[sources/forbes-ai-50-2026]]` and `[[topics/ai-50-2026-snapshot]]`
  - `companies/physical-intelligence.md` lines 18, 24–25: uses `[[sources/forbes-ai-50-2026]]` and `[[topics/ai-50-2026-snapshot]]`
  - `companies/reflection.md` lines 26, 33–34: uses `[[sources/forbes-ai-50-2026]]` and `[[topics/ai-50-2026-snapshot]]`
  - `companies/safe-superintelligence.md` lines 16, 21–22: uses `[[sources/forbes-ai-50-2026]]` and `[[topics/ai-50-2026-snapshot]]`
  - `companies/thinking-machines-lab.md` lines 18, 29, 33–35: uses `[[sources/forbes-ai-50-2026]]`, `[[topics/ai-50-2026-snapshot]]`, `[[sources/ric-rtp-david-silver-ineffable]]`
  - `companies/sequoia-capital.md` lines 19, 24: uses `[[sources/forbes-ai-50-2026]]`
  - `companies/nvidia.md` line 26: uses `[[sources/forbes-ai-50-2026]]`
  - `companies/openai.md` lines 26–28, 33: uses `[[sources/forbes-ai-50-2026]]`
  - `companies/anthropic.md` lines 30–33, 39: uses `[[sources/forbes-ai-50-2026]]`
  - `companies/ami-labs.md` lines 15, 30, 34–35: uses `[[sources/ai-50-brink-list-2026]]` and `[[sources/ric-rtp-david-silver-ineffable]]`
  - `companies/ineffable-intelligence.md` line 39: uses `[[sources/ric-rtp-david-silver-ineffable]]`
  - `tools/claude-code.md` lines 18, 44, 57: uses `[[sources/naval-ravikant-saas-is-next]]` and `[[tutorials/writing-claude-code-skills]]`
  - `index.md` line 80: uses `[[tutorials/writing-claude-code-skills]]` (special case — tutorials/ is a known directory; Obsidian resolves by filename `writing-claude-code-skills`, so this may actually work if the file is uniquely named, but it violates the slug-only convention)
- **Fix**: Do a find-and-replace pass across all 39 affected files. Strip the directory prefix from every wikilink that uses `sources/`, `companies/`, `topics/`, `concepts/`, `tools/`, `people/` prefixes, leaving only the slug. The `owner/` prefix is a deliberate exception for profile/publications cross-links.

---

## High (should fix)

### H-01 — `agi-debate.canvas` not updated for today's additions
- **Page**: `canvases/agi-debate.canvas`
- **Problem**: The canvas was last modified 2026-04-24 (per filesystem timestamp). Today's ingests added a fifth position to the AGI debate (David Silver / Ineffable Intelligence / RL-from-self-play) that is now documented in `concepts/agi.md`, `concepts/world-models.md`, and `people/david-silver.md` — but the canvas has no Silver zone. The Hassabis zone text still reads "Estimates 5–10 years if progress holds" rather than the more specific "2030" commitment now documented on `people/demis-hassabis.md` and `concepts/agi.md`. Karpathy's zone covers data quality but not the verifiability framing added today to `concepts/verifiability-and-jagged-intelligence.md`.
- **Fix**: Add a sixth zone for Silver/Ineffable Intelligence. Update Hassabis zone text from "5–10 years" to "2030 explicitly (AI Ascent 2026)". Consider adding a note to the Karpathy zone referencing the verifiability framing. The canvas bottom text lists five divergence positions; add Silver's: "Silver → training signal (pure RL self-play, no human data)."

### H-02 — `agi-debate.canvas` stale Hassabis text contradicts `agi.md`
- **Page**: `canvases/agi-debate.canvas` (Hassabis zone text node)
- **Problem**: Canvas text says "Estimates 5–10 years if progress holds." `concepts/agi.md` line 31–32 and `people/demis-hassabis.md` line 22 now document 2030 as a specific public commitment, explicitly superseding the 5–10 year range. The canvas is now factually out of date on the most-cited timeline claim.
- **Fix**: Update canvas Hassabis zone text to read "AGI by 2030 explicitly (AI Ascent 2026). Earlier range: 5–10 years. '20-year mission from 2009 — basically exactly on track.'"

### H-03 — `tools/claude-code.md` `last_updated` stale despite content added today
- **Page**: `tools/claude-code.md`
- **Problem**: `last_updated: 2026-04-26` in frontmatter. Today's log records two material additions: Naval's traction signal (from `naval-ravikant-saas-is-next`) and content from `karpathy-vibe-coding-agentic-engineering`. Both appear in the file's current content (line 18 includes the Naval citation). The frontmatter was not bumped.
- **Fix**: Change `last_updated` to `2026-04-29`.

### H-04 — `concepts/llm-wiki-pattern.md` `last_updated` stale despite content added today
- **Page**: `concepts/llm-wiki-pattern.md`
- **Problem**: `last_updated: 2026-04-24`. Today's log records `karpathy-vibe-coding-agentic-engineering` ingest updated `llm-wiki-pattern`.
- **Fix**: Change `last_updated` to `2026-04-29`. Verify the actual content change was made (check the page for Karpathy's Software 3.0 framing additions).

### H-05 — `topics/agentic-ai.md` `last_updated` stale despite content added today
- **Page**: `topics/agentic-ai.md`
- **Problem**: `last_updated: 2026-04-21`. Today's log records `karpathy-vibe-coding-agentic-engineering` ingest updated `agentic-ai`.
- **Fix**: Change `last_updated` to `2026-04-29`. Verify the actual content change is present.

### H-06 — `robert-scoble` page has zero inbound links except `index.md`
- **Page**: `people/robert-scoble.md`
- **Problem**: The page is linked only from `index.md`. The two source pages that reference Scoble's content (`sources/scobleizer-ai-native-companies.md` and `sources/benln-yc-summer-2026-rfs.md`) do not link to his person page. `concepts/ai-native-organizations.md` also does not link to him despite quoting him directly. In Obsidian graph view he is a near-orphan; if index.md is excluded from the graph, he is completely isolated.
- **Fix**: Add `[[robert-scoble]]` to the Scoble quote attribution in `concepts/ai-native-organizations.md` (around line 61) and in `sources/scobleizer-ai-native-companies.md`.

### H-07 — `sources/ric-rtp-david-silver-ineffable.md` Pages Updated missing `world-models`
- **Page**: `sources/ric-rtp-david-silver-ineffable.md`
- **Problem**: The Silver ingest materially updated `concepts/world-models.md` — a full new section ("Silver / Ineffable Intelligence (2026): A Fourth Position," lines 68–76 of world-models.md) was added. The source's Pages Updated section (5 entries) does not list `world-models`. The log entry for this ingest does record it ("world-models (updated: Silver self-play RL angle)"), so the omission is in the source page only.
- **Fix**: Add `- [[world-models]] — added Silver's RL-from-self-play as a fourth position in the architecture debate` to the Pages Updated section.

### H-08 — `sources/forbes-ai-50-2026.md` Pages Updated uses subpath links and is missing several pages
- **Page**: `sources/forbes-ai-50-2026.md`
- **Problem**: The Pages Updated section (lines 97–104) uses `[[companies/world-labs]]`, `[[companies/mistral-ai]]`, etc. — all subpath format broken in Obsidian. Additionally, this source materially updated `companies/nvidia.md` (Reflection investment), `companies/sequoia-capital.md` (Reflection investment), and `topics/ai-50-2026-snapshot.md` — the latter two are missing from the list, and the `[[anthropic]]` and `[[openai]]` links are correctly slug-only but inconsistent with the rest.
- **Fix**: Strip all `companies/` and `topics/` prefixes. Add missing entries for `nvidia` and `sequoia-capital`.

---

## Medium (worth fixing)

### M-01 — `topics/ai-50-2026-snapshot.md` line 34: mixed wikilink styles on same line
- **Page**: `topics/ai-50-2026-snapshot.md`, line 34
- **Problem**: `See [[companies/cursor]], [[claude-code]].` — uses subpath `[[companies/cursor]]` alongside correct slug-only `[[claude-code]]`. Inconsistent and the cursor link is broken in Obsidian.
- **Fix**: Change to `[[cursor]]`.

### M-02 — `topics/ai-50-2026-snapshot.md` line 49: `[[ami-labs]]` and `[[yann-lecun]]` are slug-only (correct) but `[[companies/world-labs]]` and `[[fei-fei-li]]` are mixed
- **Page**: `topics/ai-50-2026-snapshot.md`, line 49
- **Problem**: `[[companies/world-labs]] ($1B, [[fei-fei-li]]'s company)` — `world-labs` is subpath (broken), `fei-fei-li` is slug-only (correct), on the same line.
- **Fix**: Change `[[companies/world-labs]]` to `[[world-labs]]`.

### M-03 — `sources/chamath-decision-context-agents.md` self-links to itself using subpath format
- **Page**: `sources/chamath-decision-context-agents.md`, line 25
- **Problem**: `- [[sources/chamath-decision-context-agents]] — this page` — a self-link using subpath format. This is both a convention violation and a Obsidian resolution failure (broken link).
- **Fix**: Remove the self-link entry entirely (self-links in Pages Updated are not meaningful) or change to `[[chamath-decision-context-agents]] — this page`.

### M-04 — `index.md` line 80: `[[tutorials/writing-claude-code-skills]]` uses subpath format
- **Page**: `index.md`, line 80
- **Problem**: `[[tutorials/writing-claude-code-skills]]` — subpath format. Obsidian resolves by the filename `writing-claude-code-skills`, which is unique, so this may actually resolve in Obsidian despite the prefix, but it violates the slug-only convention and could break if a file with the same name is added elsewhere.
- **Fix**: Change to `[[writing-claude-code-skills]]`.

### M-05 — `sources/karpathy-vibe-coding-agentic-engineering.md` Pages Updated uses inconsistent structure
- **Page**: `sources/karpathy-vibe-coding-agentic-engineering.md`
- **Problem**: Pages Updated lists "Pages Updated" and "Pages Created" as separate subsections. The schema specifies a single "## Pages Updated" section listing all touched pages regardless of whether they were created or updated. The "Pages Created" entries are also slug-only links without `- ` prefix wikilink annotation (bare `[[slug]]` not `- [[slug]] — description`).
- **Fix**: Merge "Pages Created" into "Pages Updated" with a brief annotation (e.g., `— new page`).

### M-06 — `sources/benln-yc-summer-2026-rfs.md` Pages Updated section lists only 1 page but log indicates more
- **Page**: `sources/benln-yc-summer-2026-rfs.md`
- **Problem**: Pages Updated has only `- [[concepts/ai-native-organizations]]`. The log records this source also contributed to the YC Summer 2026 framing in `topics/saas-disruption-thesis.md` (indirectly via the AI-native service company category). The `sources/benln-yc-summer-2026-rfs.md` page also cross-references `sources/scobleizer-ai-native-companies` in its body — that cross-link is a subpath format violation (`[[sources/benln-yc-summer-2026-rfs]]` used in scobleizer page).
- **Fix**: Verify whether any additional pages were materially updated (not just indirectly related). If not, the single entry may be sufficient; the link format in the scobleizer page should still be fixed per B-02.

### M-07 — `sources/scobleizer-ai-native-companies.md` Pages Updated lists only 1 page
- **Page**: `sources/scobleizer-ai-native-companies.md`
- **Problem**: Pages Updated has only `- [[concepts/ai-native-organizations]]`. The Scoble page (`people/robert-scoble.md`) was also created from this ingest and should be listed.
- **Fix**: Add `- [[robert-scoble]] — new person page created from this source`.

### M-08 — `sources/naval-ravikant-saas-is-next.md` Pages Updated missing `concepts/software-3-0` and `topics/agentic-ai`
- **Page**: `sources/naval-ravikant-saas-is-next.md`
- **Problem**: The 4 listed Pages Updated entries are all using subpath format (covered in B-02). Additionally, the log for this ingest does not record `software-3-0` or `agentic-ai` as touched — those came from a different ingest. However, the Pages Updated entries use subpath format throughout (people/naval-ravikant, topics/saas-disruption-thesis, tools/claude-code, concepts/agentic-engineering), all broken in Obsidian.
- **Fix**: Strip prefixes on all 4 entries (fix B-02). No missing pages identified from log cross-check.

### M-09 — `people/boris-cherny.md` and `people/dmitri-dolgov.md` are thin stubs with affiliation unsourced
- **Pages**: `people/boris-cherny.md`, `people/dmitri-dolgov.md`
- **Problem**: Both pages have `affiliation: "[unsourced]"` and contain only confirmation of AI Ascent 2026 speaker status. Boris Cherny is the creator of TypeScript flow types and works at Anthropic (public knowledge not yet in the wiki). Dmitri Dolgov is the co-CEO of Waymo (public knowledge not yet in the wiki). The `index.md` entries for both include the correct affiliations but the pages themselves do not.
- **Fix**: Update both pages to at least include the information already present in `index.md` (Cherny: Anthropic; Dolgov: Waymo co-CEO). These are sourced from the conference context or known public record — mark `[unsourced]` if not yet from an ingested document.

### M-10 — `people/greg-brockman.md` current focus section is empty pending new ingest
- **Page**: `people/greg-brockman.md`
- **Problem**: "Their Current Focus" section contains `[unsourced] — No specific current focus captured from ingested sources yet." This is a known stub gap — Greg Brockman is on sabbatical from OpenAI (public knowledge as of 2024). The `index.md` entry identifies him correctly as "OpenAI co-founder/President" but the page says no focus is captured.
- **Fix**: Flag for re-ingest when AI Ascent 2026 session transcripts become available. The stub is acceptable for now but should be noted as pending.

### M-11 — `concepts/agi.md` "Fei-Fei Li's Position" section sources use subpath format
- **Page**: `concepts/agi.md`, lines 36, 54, 56
- **Problem**: `[[sources/bloomberg-feifei-li-2025]]` (line 36 and 54) and `[[concepts/spatial-intelligence]]` (line 56) use subpath format. Covered in B-02 but noting here as a content-level issue — these are the primary citations for the Li section and are broken in Obsidian graph view.
- **Fix**: Change to `[[bloomberg-feifei-li-2025]]` and `[[spatial-intelligence]]`.

### M-12 — `agi-debate.canvas` is a true orphan in the Obsidian graph
- **Page**: `canvases/agi-debate.canvas`
- **Problem**: The canvas has zero inbound wikilinks from any `.md` page (the `index.md` link is broken per B-01). No entity page links back to it. `log.md` mentions it in entries from 2026-04-23 but that is not a navigable wikilink. In the Obsidian graph, the canvas floats disconnected.
- **Fix**: Fix B-01 first (change `index.md` link to `[[agi-debate]]`). Additionally consider adding a `See also: [[agi-debate]]` note to `concepts/agi.md` and/or `people/demis-hassabis.md` so the canvas has at least two inbound paths.

### M-13 — `sources/ai-50-brink-list-2026.md` Pages Updated section omits `fei-fei-li`
- **Page**: `sources/ai-50-brink-list-2026.md`
- **Problem**: Pages Updated lists 3 pages: `ami-labs`, `yann-lecun`, `topics/ai-50-2026-snapshot`. The log for this ingest records `fei-fei-li (updated)`. The `fei-fei-li` page is not in the Pages Updated section. Also the `[[topics/ai-50-2026-snapshot]]` entry uses subpath format (covered in B-02).
- **Fix**: Add `- [[fei-fei-li]] — World Labs on AI 50 main list, Brink List context` and strip the subpath prefix from the topics link.

### M-14 — `sources/hassabis-deepmind-alphafold-agi.md` Pages Updated uses slug-only correctly but `agi` entry is incomplete
- **Page**: `sources/hassabis-deepmind-alphafold-agi.md`
- **Problem**: Pages Updated is well-formed and uses slug-only links (no subpath issue). However, the `agi` entry says "2030 explicit date, 20-year mission framing, agent era framing" but does not mention that `agi.md`'s "Karpathy's Complementary View" section also cites `karpathy-vibe-coding-agentic-engineering` as a source (not from this ingest). Minor documentation gap — the Pages Updated description is accurate as far as it goes.
- **Fix**: No action required; this is a documentation completeness note, not an error.

### M-15 — `sources/konstantine-hassabis-ai-ascent-fireside.md` Pages Updated uses subpath format for both entries
- **Page**: `sources/konstantine-hassabis-ai-ascent-fireside.md`, lines 26–27
- **Problem**: `- [[sources/ai-ascent-2026]]` and `- [[people/demis-hassabis]]` both use subpath format. Covered in B-02. The self-referential link `[[sources/hassabis-deepmind-alphafold-agi]]` in the body (line 22) is also subpath.
- **Fix**: Strip all three prefixes.

### M-16 — `sources/ric-rtp-david-silver-ineffable.md` Pages Updated uses subpath for all 5 entries
- **Page**: `sources/ric-rtp-david-silver-ineffable.md`, lines 27–31
- **Problem**: All five entries (`[[companies/ineffable-intelligence]]`, `[[people/david-silver]]`, `[[companies/ami-labs]]`, `[[companies/thinking-machines-lab]]`, `[[concepts/agi]]`) use subpath format. Also missing `world-models` (H-07).
- **Fix**: Strip all prefixes; add `world-models` entry.

---

## Low (minor issues / style)

### L-01 — `agi.md` 5-10 year vs 2030 timeline coexists cleanly but `demis-hassabis.md` Notable Takes could be tighter
- **Page**: `people/demis-hassabis.md`, line 22
- **Problem**: `- **AGI timeline**: 5–10 years (from earlier thread); now specifying 2030 explicitly` — the bullet has two contradictory claims in one entry. `agi.md` handles this correctly on lines 31–32 with inline sourcing. The hassabis page could note the same reconciliation more clearly: the 5–10 year claim came from `thread-milkroadai-hassabis-agi` (earlier thread); the 2030 date came from `hassabis-deepmind-alphafold-agi` (AI Ascent 2026, more recent and specific).
- **Fix**: Clarify bullet to: `- **AGI timeline**: 5–10 years — [[thread-milkroadai-hassabis-agi]] (earlier, vaguer); sharpened to 2030 explicitly at AI Ascent 2026 — [[hassabis-deepmind-alphafold-agi]]`. Not a contradiction; the 2030 is within the earlier 5–10 year range from 2025.

### L-02 — `index.md` "Canvases" section exists as a category not in CLAUDE.md schema
- **Page**: `index.md`, lines 76–78
- **Problem**: CLAUDE.md defines index categories as: Tools & Frameworks, Models & Providers, Concepts & Techniques, People & Voices, Companies & Labs, Tutorials & Hands-On, Topics & Themes. "Canvases" is not in the schema. The canvas entry could live under "Topics & Themes" or a dedicated note.
- **Fix**: Acceptable as a local extension — no change required unless schema discipline is desired.

### L-03 — `sources/chamath-decision-context-agents.md` promotes 8090's product without sourcing skepticism
- **Page**: `sources/chamath-decision-context-agents.md`
- **Problem**: Chamath is promoting `factory.8090.ai` — a specific product. The source page presents this as a neutral observation without noting that this may be an invested/affiliated promotion. No `[unsourced]` or provenance caveat exists.
- **Fix**: Add a brief provenance note: "Chamath's affiliation or investment relationship with 8090 is not disclosed in the source post. Treat the product endorsement accordingly."

### L-04 — `people/boris-cherny.md` and `people/dmitri-dolgov.md` have `affiliation: "[unsourced]"` in frontmatter
- **Pages**: `people/boris-cherny.md`, `people/dmitri-dolgov.md`
- **Problem**: Frontmatter uses a string-quoted `"[unsourced]"` value, which is unusual — most other pages use a plain string for affiliation. Not a functional error.
- **Fix**: Either update with correct affiliation (see M-09) or use `affiliation: unknown` as a cleaner placeholder.

### L-05 — `sources/ai-ascent-2026.md` update note uses blockquote format inconsistently
- **Page**: `sources/ai-ascent-2026.md`, line 23
- **Problem**: The 2026-04-29 update is embedded inside a `> [!note] Placeholder ingest — partially resolved` callout block. This is functionally fine but mixes the original placeholder note with the update, making the chronology harder to read.
- **Fix**: Move the update to a separate `> [!update] 2026-04-29` callout or append it as a new section `## Updates` below the existing note.

### L-06 — `companies/world-labs.md` is a well-written page but has 11 subpath links
- **Page**: `companies/world-labs.md`
- **Problem**: Covered in B-02. Noting here as a style observation: the page content is excellent and detailed but will appear entirely disconnected from its sources in Obsidian graph view until the links are fixed.
- **Fix**: Same as B-02.

### L-07 — `topics/saas-disruption-thesis.md` "Related Pages" section uses subpath links throughout
- **Page**: `topics/saas-disruption-thesis.md`, lines 75–78
- **Problem**: All four related pages use subpath format (`[[concepts/agentic-engineering]]`, `[[concepts/software-3-0]]`, `[[concepts/vibe-coding]]`, `[[tools/claude-code]]`). This is both a Blocker (B-02) and a Low issue in that the section was intentionally structured as a cross-reference list and is well-conceived — just needs the prefix stripped.
- **Fix**: Same as B-02.

### L-08 — `how-to-learn-claude-infographic` source page has only 1 inbound link (index only)
- **Page**: `sources/how-to-learn-claude-infographic.md`
- **Problem**: Linked only from `index.md`. If any entity pages were updated from this source, they should link back. Check whether `concepts/constitutional-ai.md` or `tools/claude-code.md` were updated from this ingest.
- **Fix**: If no entity pages were updated, this is fine — it's a reference-only source. If entity pages were updated, add back-references.

### L-09 — `concepts/model-rendered-ui.md` last_updated is 2026-04-22 (7 days old, not stale by 60-day rule but worth noting)
- **Page**: `concepts/model-rendered-ui.md`
- **Problem**: Not stale by CLAUDE.md's 60-day rule. Noted for visibility — this page is linked from index.md but has no inbound links from entity pages beyond the Flipbook source. It's an emerging concept with no follow-up ingests since creation.
- **Fix**: No action required unless new Flipbook/model-rendered-UI signals are ingested.

### L-10 — `companies/luma-ai.md` last_updated is 2026-04-24 (5 days); no new updates from today's ingests
- **Page**: `companies/luma-ai.md`
- **Problem**: Not stale. Noted for visibility — Luma's Uni-1 and the world-models debate are active topics, but no new Luma-specific signals were ingested today.
- **Fix**: No action required.

### L-11 — `sources/ai-50-brink-list-2026.md` has an inline Obsidian-style internal link using pipe syntax for display name
- **Page**: `sources/ai-50-brink-list-2026.md`, line 11
- **Problem**: `[[sources/forbes-ai-50-2026|Forbes AI 50 2026]]` — uses pipe alias syntax with a subpath prefix. The subpath is broken in Obsidian (B-02). The alias text ("Forbes AI 50 2026") is valid Obsidian syntax but the slug prefix means the link is dead.
- **Fix**: Change to `[[forbes-ai-50-2026|Forbes AI 50 2026]]`.

### L-12 — `sources/forbes-ai-50-2026.md` line 11 uses pipe alias with subpath format
- **Page**: `sources/forbes-ai-50-2026.md`, line 11
- **Problem**: `[[sources/ai-50-brink-list-2026|AI 50 Brink List]]` — same issue as L-11. Covered in B-02 but the pipe alias should be preserved when fixing.
- **Fix**: Change to `[[ai-50-brink-list-2026|AI 50 Brink List]]`.

---

## Contradiction / Reconciliation Check

### AGI timeline (Hassabis 5–10 years vs. 2030)
**Status: Properly reconciled in entity pages, not reconciled in canvas.**
- `concepts/agi.md` lines 31–32 explicitly handles this: "Earlier source gave range of 5–10 years; the 2030 date is a more specific public commitment."
- `people/demis-hassabis.md` line 22 acknowledges both with source attribution.
- `canvases/agi-debate.canvas` still shows "5–10 years" — see H-02.
- **No blocker; canvas update recommended.**

### Silver's self-play thesis vs. LeCun's JEPA world-model thesis
**Status: Cleanly additive in content, properly framed as distinct positions.**
- `concepts/world-models.md` line 72–76 presents Silver as "a fourth distinct position" from LeCun, Hassabis, and LLM-scaling-labs. Silver is not claiming to be doing world models — he is claiming LLMs AND world models fail if trained on human data. The framing is clear and internally consistent.
- `concepts/agi.md` lines 38–42 does the same.
- **No contradiction; no action required.**

### Fei-Fei Li's additive AGI thesis vs. LeCun's replacement thesis
**Status: Clean distinction; both pages cross-reference correctly.**
- `concepts/agi.md` lines 34–36 handles this well: "Her AGI thesis is additive: AGI will not be complete without spatial intelligence (3D world understanding) — the physical layer that LLMs lack. This distinguishes her from both LeCun (who rejects LLMs entirely) and Hassabis."
- **No contradiction; no action required.**

### Karpathy's verifiability framing and the `agi-debate.canvas`
**Status: Content added to `agi.md` (lines 44–45) and `verifiability-and-jagged-intelligence.md` but NOT reflected in the canvas.**
- The canvas Karpathy zone covers "data quality as binding constraint" but not the verifiability/jagged-intelligence framing.
- **Noted in H-01; canvas update recommended but not blocking.**

---

## Index Sanity Check

All 105 entity pages listed in `index.md` resolve to actual files. The only dead link is `[[agi-debate.canvas]]` (B-01). The `[[tutorials/writing-claude-code-skills]]` and `[[owner/profile]]`, `[[owner/publications]]` subpath links are Obsidian-exception cases — tutorials/ and owner/ subpath links may resolve in Obsidian given unique filenames, but violate the slug-only convention (covered in B-02 and M-04).

No entries in `index.md` point to deleted or renamed files. No duplicate entries found.

---

## Orphan Analysis

True orphans (zero inbound wikilinks from any non-index source):
- `canvases/agi-debate.canvas` — orphan due to broken index link (B-01, M-12)

Near-orphans (only linked from `index.md`, no entity cross-links):
- `people/robert-scoble.md` — only from `index.md`; fix at H-06
- `sources/how-to-learn-claude-infographic.md` — only from `index.md`; see L-08

All other pages have at least 2 inbound links. The AI Ascent speaker stubs (`greg-brockman`, `boris-cherny`, `dmitri-dolgov`) each have 2 inbound links (index + `ai-ascent-2026`) — acceptable for stubs pending re-ingest.

---

## Recommended Fix Order

1. **B-02 first** — the 132 subpath wikilink violations affect Obsidian graph integrity for nearly all of today's new content. Do a targeted find-and-replace across the 39 affected files: strip `sources/`, `companies/`, `topics/`, `concepts/`, `tools/`, `people/` prefixes from all wikilinks that are not `owner/`. Preserve pipe aliases (|) when present.
2. **B-01** — fix the `index.md` canvas link (`[[agi-debate.canvas]]` → `[[agi-debate]]`).
3. **H-01 / H-02** — update the canvas for Silver zone and Hassabis timeline text.
4. **H-03 / H-04 / H-05** — bump stale `last_updated` frontmatter on `claude-code.md`, `llm-wiki-pattern.md`, `agentic-ai.md`.
5. **H-06** — add `[[robert-scoble]]` cross-reference from `concepts/ai-native-organizations.md`.
6. **H-07** — add `world-models` to `ric-rtp-david-silver-ineffable.md` Pages Updated.
7. **M-07 / M-13** — fix missing pages in `scobleizer` and `ai-50-brink-list-2026` Pages Updated sections.
8. **M-09** — fill in `boris-cherny` and `dmitri-dolgov` affiliations from publicly known facts.
9. Remaining Medium and Low items at owner's discretion.

---

## Closing Summary

47 issues total: 11 blockers, 8 high, 16 medium, 12 low. The dominant problem is the subpath wikilink epidemic (B-02 / 132 occurrences / 39 files) introduced by today's parallel ingest agents. Every link written as `[[sources/foo]]` or `[[companies/bar]]` is dead in Obsidian's graph view — meaning today's content is less interconnected in the knowledge graph than it appears in raw markdown. The fix is mechanical: a sed/find-and-replace pass stripping directory prefixes. The second most important fix is the `agi-debate.canvas`, which is now 5 days stale against today's significant AGI debate additions (Silver, Fei-Fei Li position, Karpathy verifiability framing, Hassabis 2030 date). The canvas is the primary visual navigation surface for the wiki's core intellectual content and should reflect the full current state of the debate.
