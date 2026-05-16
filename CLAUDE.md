# LLM Wiki — AI Engineering Career Knowledge Base

## Purpose

This wiki serves as a persistent, compounding knowledge base for an AI Engineering career. The owner is a former VP of Engineering / CTO returning to hands-on technical work. The wiki must serve two needs simultaneously:

1. **Strategic awareness** — track the AI landscape, key players, trends, and industry signals as they emerge from Twitter, Reddit, and podcasts.
2. **Hands-on ramp-up** — capture tutorials, tool walkthroughs, and practical knowledge for tools gaining real traction.

When in doubt, prefer depth on tools with demonstrated traction over breadth on hype.

---

## Directory Structure

```
/
├── CLAUDE.md          # This file — schema, workflows, conventions
├── index.md           # Content catalog organized by category (LLM-maintained)
├── log.md             # Append-only ingest/query/lint log
├── _raw/              # Immutable source drops (transcripts, links, pastes) — gitignored; drop zone for Obsidian Web Clipper and cross-device captures
├── tools/             # One page per AI tool or framework
├── models/            # One page per model family or provider
├── concepts/          # Foundational and emerging AI/ML concepts
├── people/            # Key practitioners, researchers, voices worth tracking
├── companies/         # AI labs, startups, and relevant orgs
├── tutorials/         # Step-by-step guides and hands-on walkthroughs
├── topics/            # Broader themes that span multiple entities (e.g., "Agent Frameworks", "Evals")
├── owner/             # Wiki owner's professional identity: profile, publications, social presence
└── sources/           # One page per ingested source (podcast ep, thread, etc.)
```

## Canonical Vault Location (iCloud Obsidian)

The wiki lives at the **iCloud Obsidian vault**:

```
~/Library/Mobile Documents/iCloud~md~obsidian/Documents/llm-wiki/
```

For ergonomics there is a symlink at `~/llm-wiki/` pointing to this path. Use either form; prefer `~/llm-wiki/` in commands and prose.

**This is the only location.** Earlier versions of the wiki ran from a separate git checkout at `/Users/lukehornof/src/claude/llm-wiki/`. That checkout was retired on 2026-05-15; if it still exists locally it is **stale** and should be ignored or deleted — do not commit, edit, or read from it.

**Why iCloud:** Obsidian on Mac / iPad / iPhone all read this location; Obsidian Web Clipper writes to `_raw/` here. Cross-device knowledge capture and ingest run from a single source of truth.

**Implications for git operations:**
- `.git/` lives on iCloud. This is acceptable because **only the Mac runs git** — Obsidian on iPad / iPhone only edits markdown, never touches `.git`. There is no risk of concurrent-commit corruption.
- iCloud "optimize storage" can occasionally evict file contents. If a git operation reports a missing file, force a re-download with `brctl download "<path>"` and retry.
- Spaces in the canonical path require quoting in shell commands. Prefer the `~/llm-wiki/` symlink.

**Ingest workflow**: at the start of every ingest, check `_raw/` and `Daily Briefs/` for net-new content (single location now, no second vault to consult).

---

## Entity Page Schemas

### tools/\<tool-name\>.md
```
---
name: <Tool Name>
type: tool
category: [framework | library | platform | cli | ide-extension | api | other]
status: [emerging | gaining-traction | mainstream | deprecated]
last_updated: YYYY-MM-DD
---

## What It Is
One paragraph. What problem it solves and who makes it.

## Traction Signals
Bullet list of concrete signals: GitHub stars trend, community buzz, who's using it, notable endorsements. Cite sources.

## How to Use It
Quick-start summary or link to tutorial page. Prioritize hands-on notes from the owner's own experience.

## Key Concepts
Short glossary of the tool's own terminology.

## Compared To
Brief comparison with closest alternatives.

## Resources
- [Source Title](source page link) — one-line summary
```

### models/\<model-name\>.md
```
---
name: <Model Name>
type: model
provider: <Company>
status: [announced | available | deprecated]
last_updated: YYYY-MM-DD
---

## What It Is
Capabilities summary. Context window, modalities, pricing if relevant.

## Strengths & Weaknesses
Based on community benchmarks and real-world reports, not just official claims.

## When to Use It
Practical guidance on use-case fit.

## Community Sentiment
What Twitter/Reddit/podcasts are saying. Note the date of signals.

## Resources
```

### concepts/\<concept-name\>.md
```
---
name: <Concept Name>
type: concept
maturity: [foundational | active-research | emerging | hype]
last_updated: YYYY-MM-DD
---

## Definition
Plain-language explanation. No jargon unless defined inline.

## Why It Matters
Practical relevance to AI engineering work.

## Current State
Where the field actually is vs. where the hype says it is.

## Key Papers / Posts
Curated short list. Skip anything that's just noise.

## Related Concepts
Wikilinks to related concept pages.
```

### people/\<person-name\>.md
```
---
name: <Full Name>
type: person
affiliation: <Current org>
signal_sources: [twitter | podcast | blog | paper | github]
last_updated: YYYY-MM-DD
---

## Who They Are
Role, background, why they're worth tracking.

## Their Current Focus
What they're working on or thinking about right now. Keep this fresh.

## Notable Takes
Bullet list of memorable/contrarian/important positions they've staked out. Cite source.

## Where to Follow
Links/handles.
```

### tutorials/\<tutorial-name\>.md
```
---
name: <Tutorial Name>
type: tutorial
tool: <tool or concept this covers>
difficulty: [beginner | intermediate | advanced]
last_updated: YYYY-MM-DD
---

## Goal
What you can do after completing this.

## Prerequisites
What you need to know or have installed first.

## Steps
Numbered walkthrough. Include actual commands, code snippets, and gotchas.

## What I Actually Learned
Owner's first-person notes on surprises, friction points, and real takeaways.

## Next Steps
What to tackle after this.
```

### owner/profile.md and owner/publications.md
```
---
name: <Page Name>
type: owner-profile | owner-publications
last_updated: YYYY-MM-DD
---

## Bio / Career Summary
First-person professional identity. Keep career table up to date as roles change.

## Professional Profiles
Canonical links to LinkedIn, GitHub, Google Scholar, Twitter/X, homepage, etc.

## Publications (publications.md only)
One entry per publication: venue, authors, link, one-paragraph abstract, context note.
```
- `owner/profile.md` — bio, career summary, all professional/social links
- `owner/publications.md` — academic and professional publications list
- Add new files to `owner/` as needed (e.g., `owner/talks.md`, `owner/notes.md`)
- These pages are not tracked in `index.md` under the standard categories; they are self-referential wiki-owner pages

---

### sources/\<source-slug\>.md
```
---
title: <Source Title>
type: source
medium: [twitter-thread | reddit-post | podcast-episode | article | video | paper | github-repo]
url: <original url if applicable>
ingested: YYYY-MM-DD
---

## Summary
2-4 sentences. What this source is actually about.

## Key Claims / Takeaways
Bullet list. These become candidates for updating entity pages.

## Pages Updated
Wikilinks to all entity pages this ingest touched.
```

---

## Source Handling by Medium

### Twitter / X Threads
- Paste the full thread text (or screenshot transcript) into `_raw/`.
- Extract: tool mentions, traction signals, contrarian takes, person attributions.
- If the thread is from a tracked person, update their `people/` page.
- Traction signals (many RTs, quote-tweets from known figures) → update `tools/` status field.

### Reddit Posts & Threads
- Paste post + top comments into `_raw/`.
- Reddit is a strong signal for **practitioner sentiment** — weight it accordingly.
- Look for: tool comparisons, "switched from X to Y" reports, frustration patterns, tutorial recommendations.
- Aggregate multiple Reddit mentions before updating a tool's status to `gaining-traction`.

### Podcast Episodes
- Paste transcript or detailed notes into `_raw/`.
- Extract: guest identity → `people/`, tools mentioned → `tools/`, concepts discussed → `concepts/`.
- Note timestamps for key claims so they can be verified later.
- Podcasts are good for **narrative and context**, not ground truth on benchmarks.

### Tutorials & How-To Content
- These go into `tutorials/` with hands-on notes.
- If the owner has personally followed the tutorial, add a "What I Actually Learned" section with first-person notes.
- Link back from the relevant `tools/` page under Resources.

---

## Workflows

### Ingest

When given a new source:

0. **Daily Brief deduplication check** (skip if not ingesting from a Daily Brief). When the source is a Daily Brief in `Daily Briefs/`, before doing any work `grep` the brief filename (e.g., `2026-05-07-personal.md`) verbatim against `log.md`. If a hit is returned, the brief has already been processed — surface that to the owner and stop. If no hit, proceed.
1. Save the raw content to `_raw/<slug>.<ext>`.
2. Create or update `sources/<slug>.md`.
3. Identify all entity references: tools, models, concepts, people, companies.
4. For each entity:
   - If page exists: update only the sections that are materially changed. Preserve existing content unless contradicted.
   - If page doesn't exist: create it from the schema above.
5. Update `index.md` if new pages were created.
6. Append a one-line entry to `log.md`: `YYYY-MM-DD | ingest | <source-slug> | pages touched: <list>`. **If the ingest was driven by a Daily Brief, the description field MUST include the brief filename(s) verbatim** (e.g., `Daily Briefs/2026-05-07-personal.md`, `Daily Briefs/2026-05-07-neutral.md`) so step 0 of the next ingest can detect prior processing via grep.
7. **Submit changes as a PR for owner review — do not commit directly to `main`.**
   - Create a branch named `ingest/YYYY-MM-DD` (or `ingest/YYYY-MM-DD-<short-tag>` if multiple ingest PRs land the same day).
   - Stage only ingest-related files. Exclude local Obsidian state (`.obsidian/workspace.json`), unrelated untracked files at vault root (e.g., `Untitled.md`, `Daily Briefs/`), and anything under gitignored paths (`_raw/` is intentionally excluded).
   - Commit with a `Ingest YYYY-MM-DD: <one-line summary>` title and a body that lists each source and the judgment calls made (new pages skipped, contradictions, etc.).
   - Push with `-u` and open a PR via `gh pr create` with a Summary + Test plan section. The owner reviews and merges via the GitHub UI.
   - After merge, the next session syncs with `git checkout main && git pull`.

### Query

When asked a question about the wiki:

1. Check `index.md` for relevant categories.
2. Read relevant entity pages.
3. Synthesize an answer with inline citations (wikilinks to source pages).
4. If the answer would be useful to a future reader, offer to file it as a new `topics/` page.
5. Append to `log.md`: `YYYY-MM-DD | query | "<question summary>" | pages read: <list>`.

### Lint

When asked to lint or health-check the wiki:

1. Scan for orphan pages (no inbound wikilinks).
2. Scan for stale `last_updated` dates (>60 days) on tool/model pages — flag for refresh.
3. Check that every `sources/` page lists at least one updated entity page.
4. Check that every `tools/` page has a non-empty Traction Signals section.
5. Flag any contradictions found across pages (e.g., tool listed as `emerging` in one place and `mainstream` in another).
6. Scan `_raw/` for files not referenced by any `sources/` page — flag as unprocessed drops or deletable empties.
7. Produce a lint report and ask the owner which issues to fix.

---

## Conventions

- **Dates**: Always ISO 8601 (`YYYY-MM-DD`). No relative dates in wiki pages.
- **Traction vs. Hype**: Be conservative with status upgrades. `gaining-traction` requires at least 2 independent community signals. `mainstream` requires broad practitioner adoption, not just buzz.
- **Owner voice**: First-person notes in `tutorials/` are encouraged. Keep them in the "What I Actually Learned" section, not mixed into factual summaries.
- **Contradiction policy**: When a new source contradicts existing content, note both claims with their source dates. Do not silently overwrite. Flag for owner review if the contradiction is significant.
- **No hallucination**: Do not add claims that weren't in an ingested source. If something is generally known but not sourced, mark it `[unsourced]`.
- **Wikilinks**: Always use the slug filename (e.g., `[[llm-wiki-pattern]]`, `[[andrej-karpathy]]`), never the human-readable display name (e.g., `[[LLM Wiki Pattern]]`). Obsidian resolves by filename; mismatches create dangling ghost nodes. **Exception**: `owner/` namespace pages use the path-form (`[[owner/profile]]`, `[[owner/publications]]`) because their slugs (`profile`, `publications`) are too generic to be safely globally unique. The path-form communicates the namespace boundary and prevents future collisions.
- **Index discipline**: `index.md` is organized by category, not alphabetically. Categories: Tools & Frameworks, Models & Providers, Concepts & Techniques, People & Voices, Companies & Labs, Tutorials & Hands-On, Topics & Themes.
