---
name: Lint Report 2026-09-12
type: meta
last_updated: 2026-09-12
---

# Wiki Lint — 2026-09-12

Run on `main` at `eaa90b6` (post-merge of #270). Scope: 287 entity pages / 537 sources / 449 `_raw` drops.

## Verdict: healthy

Every hard check passes. All findings below are hygiene and backlog, not breakage.

| Check | Result |
|---|---|
| Orphan entity pages (no inbound link anywhere) | **0** |
| Dangling wikilinks originating from entity pages | **0** |
| `tools/` pages with missing/empty Traction Signals | **0** |
| Frontmatter gaps on entity pages (`name`/`type`/`last_updated`) | **0** |
| Duplicate entity pages (normalized slug or `name:` collision) | **0** |
| `index.md` links pointing at non-existent pages | **0** |
| Near-duplicate slug candidates | 7 flagged, **all legitimately distinct** |

The three lint passes on 2026-09-10 (#267 merges, #268 ghosts, #269 promotes) held. Nothing regressed.

---

## Finding A — `index.md` "Recent ingests" is 3½ weeks stale

The section holds **405 entries**, and the newest date referenced anywhere in it is **2026-08-19**. Every ingest since then has logged "0 index changes" because no new entity pages were created — correct by the letter of the workflow, but the section has quietly stopped tracking ingests.

Two ways to resolve, and they point in opposite directions:

1. **Backfill** 2026-08-20 → 2026-09-12 (roughly 12 ingests, ~25 source pages).
2. **Retire the section.** 405 entries is past the point where anyone reads it, `log.md` already carries the authoritative ingest record in far more detail, and `sources/` is browsable. The section may be duplicating work with no reader.

Recommend **2**. If you want it kept, it needs to become an explicit ingest step or it will drift again.

## Finding B — 5 entity pages missing from `index.md`

| Page | Inbound links | `last_updated` |
|---|---|---|
| `people/matt-pocock` | 16 | 2026-09-08 |
| `concepts/ai-native-service-companies` | 5 | 2026-06-01 |
| `concepts/autoresearch` | 5 | 2026-06-01 |
| `people/gerard-sans` | 3 | 2026-06-01 |
| `people/swyx` | 3 | 2026-06-01 |

`matt-pocock` is the clear miss — 16 inbound links, updated four days ago, and simply never indexed. The other four date to the 2026-06-01 batch and are linked **only from `sources/`**, never from another entity page. They are indexed-nowhere *and* weakly integrated: reachable, but not part of the entity graph.

Note `swyx` in particular — Latent Space is cited constantly across the vault, so a 3-inbound person page for its author suggests the citations are going to episode source pages rather than to him.

Low-cost fix: add all 5 index lines. The deeper question — whether those four pages earn their place or should be folded — is a judgment call I'd want your read on.

## Finding C — 28 stale `tools/` + `models/` pages (>60 days)

Carried over from the 2026-09-10 lint, where the disposition was "fold into future ingests as entities resurface." That has not happened for any of them, and the count is growing.

Oldest first: `colossus-2` (81d), then a cluster of nine at 75d (`stitch`, `ollama`, `obsidian`, `obsidian-dataview`, `llama-index`, `google-agents-cli`, `crewai`, `antigravity`, `gpt-image-2`), `claude-sonnet-5` (74d), and eighteen more between 62–68d including `glm-5-2`, `claude-opus-4-8`, `claude-agent-sdk`, `langchain`, `superpowers`, `claude-mem`, `gpt-5-6`.

**Two worth singling out:**

- **`models/glm-5-2` (68d)** is the trigger model for [[ai-margin-collapse]], the wiki's most active concept. GLM **5.3** has since shipped (captured 2026-08-20 in the concept page, never on the model page). The load-bearing model page for a live thesis is a release behind.
- **`models/claude-mythos` still reads `status: announced`** with the page's own note saying *"insufficient public detail to call this yet."* That was 2026-08-12. Either detail has landed and the status moves, or a month of silence is itself worth recording.

Most of the remaining 26 are genuinely quiet tools where a stale date is honest. I would **not** bulk-refresh — a touched `last_updated` with no new content is worse than an old one, because it launders staleness. Recommend refreshing only where something actually changed.

## Finding D — 8 `sources/` pages with no entity wikilink

Schema rule: every source page should name at least one entity page it updated. These 8 link only to other *source* pages, to `index`/`log`, or (in one case) to themselves:

`dailybrief-roundup-2026-06-07`, `dailybrief-roundup-2026-07-02`, `fable-good-enough-existential-swe-thread-2026-07-02`, `house-draft-federal-ai-preemption-bill-2026-06-04`, `mike-fishbein-fable-5-claude-code-5-prompts-jul-7-deadline-2026-07-02`, `min-choi-fable-5-viral-2nd-thread-9-examples-2026-07-03`, `reddit-20-notebooklm-prompts-image-2026-05`, `vercel-andrew-qu-agents-new-software-paradigm-2026-07-03`

Two distinct cases here, and they need different handling:

- The **daily-brief roundups** legitimately link to sub-source pages that carry the entity links themselves. Arguably fine; the rule may be too strict for split roundups.
- The rest are **real gaps** — a Fable capability thread, a federal AI-preemption bill, a Vercel agents-paradigm piece, all filed with no entity page attached. `reddit-20-notebooklm-prompts-image-2026-05` links to *itself*, which is a straightforward authoring error.

## Finding E — `_raw/` hygiene (3 items, all minor)

Scanned the 60-day window (the older backlog was covered by prior lints).

- **1 genuinely unprocessed drop**: `I built a true-scale atlas of the universe (8.4M real stars) in about a week with Fable.md` (2026-07-16, r/ClaudeAI, chrisjz — live at universeatlas.org, MIT source on GitHub, WebGPU). Its sibling Fable-demo drops from the same window (desert explorer, waterbending, snow rendering) **were** processed, so this one fell through rather than being deliberately skipped. It is a Fable 5 capability receipt — the kind [[claude-fable-5]] already collects.
- **2 empty clipper stubs**, frontmatter only, no content: `Untitled.md` (points at `ownyourintelligence.ai/white-paper.pdf`) and `Untitled 1.md` (points at the NVIDIA Open-Weights PDF — **already captured separately** as `Open-Weights-and-American-AI-Leadership.pdf`, which was processed). `Untitled 1.md` is strictly redundant and deletable. `Untitled.md` is either a fetch-the-PDF task or a delete.
- One earlier false positive worth recording so a future lint does not re-flag it: `Post by @EnoReyes on X.md` **is** processed — folded into `engineering-leadership-ai-era` on 2026-07-29, cited by name rather than by handle.

---

## Not run

**Deep semantic contradiction sweep.** Same call as 2026-09-10 — expensive, and the dated-progression discipline (append new claims with dates, never silently overwrite) has been holding well in the ingests I checked. The bounded version I *did* run — model/tool `status:` fields against page bodies — surfaced only the `claude-mythos` item in Finding C.

## Suggested order

1. **Finding E** — delete `Untitled 1.md`, decide on `Untitled.md`, ingest the atlas drop. Smallest, fully mechanical.
2. **Finding B** — add the 5 index lines (~5 minutes); defer the fold/keep question on the four 2026-06-01 pages.
3. **Finding A** — decide retire-vs-backfill. Needs your call, not mine.
4. **Finding C** — refresh `glm-5-2` (GLM 5.3) and `claude-mythos` only. Leave the other 26.
5. **Finding D** — fix `reddit-20-notebooklm-prompts-image-2026-05`; decide whether the roundup rule should be relaxed.
