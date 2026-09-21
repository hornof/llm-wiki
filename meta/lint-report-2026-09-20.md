---
name: Lint Report 2026-09-20
type: meta
last_updated: 2026-09-20
---

# Wiki Lint — 2026-09-20

Run on `main` at `635ad0b`. **PR #279 (`models/jev`) was still open and is not included.** Six PRs have merged since the last lint (#274–#278): one lint-fix PR and five ingests.

Scope: 289 entity pages / 552 sources.

## Structure: clean

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Weakly-integrated entity pages | **0** |
| Dangling wikilinks from entity pages or index | **0** |
| Entity pages missing from `index.md` | **0** |
| `index.md` → nonexistent pages | **0** |
| Frontmatter gaps | **0** |
| Source pages with no inbound link | **1** (reachable via `meta/log-archive/2026-07.md`) |

Six ingests landed without introducing a single structural defect. The one source page without an entity-page inbound — `openai-5pct-equity-donation-us-sovereign-wealth-fund-2026-07-02` — is referenced from the archived log, so it is reachable but not integrated.

---

## F1 — Step 5a is not working, and I nearly reported the opposite

This is the finding that matters, and it is about a process change I introduced on 2026-09-14.

**Step 5a** requires every ingest to grep its touched pages for open-question markers and resolve what the new source answers. It has now run through five ingests. My first measurement said markers had fallen from **111 → 98** and I was about to report that as the fix working.

**It is a measurement artifact.** The 111 figure came from a broader regex than the one I ran today. Re-running the *original* regex on both states:

| State | Marker-carrying entity pages (same regex) |
|---|---|
| 2026-09-13 report | 111 |
| 2026-09-14 baseline (`f0a54b4`) | 110 |
| **2026-09-20 (now)** | **114** |

**The backlog grew.** Step 5a produced **3 recorded in-place resolutions** in the same window — the Mythos-5 leak note, the platform-detection question, and the Cursor deal — against roughly four new marker-carrying pages arriving with new ingests.

The honest read: **5a catches questions the current source happens to answer, which is a narrow slice.** It does nothing about the standing backlog, and ingests add markers faster than it retires them. It is treading water at best.

Two options, and they are different in kind:

1. **Accept it as a hygiene step, not a reduction mechanism.** Retire the expectation that the count falls, and stop measuring it.
2. **Add a periodic sweep** that works the backlog independently of what happens to be ingested — e.g. lint picks the ten oldest marker-carrying pages each pass and checks whether the wiki has since answered them.

I lean (2), because the two most consequential defects found in the last two weeks — the `claude-mythos` naming contradiction and the `cursor`/`anysphere` split — were both *stale open questions the wiki had already answered elsewhere*, and neither would have been caught by 5a.

## F2 — Staleness is compounding

**31 stale `tools/`+`models/` pages** (>60 days), against 28 on 09-12 and 27 on 09-13. Three crossed the line this week: `tools/river` (67d), `tools/dac` (67d), `models/inkling` (66d). Oldest is `tools/colossus-2` at **89 days**.

The owner's standing scope is *refresh only when the entity resurfaces*, which I still think is right — a touched `last_updated` with no new content launders staleness. But the count only moves one way under that rule, and at ~1 page/week it will pass 40 by November. Worth deciding whether that is acceptable drift or whether some pages should be marked dormant rather than stale.

## F3 — 5 source pages still have no URL

Unchanged since the check was added on 09-17. No new ones introduced by five ingests, which is the useful part.

- `block-organizational-intelligence` — **the significant one.** Listed in `index.md` under *Foundational primary sources* and cited as the primary for `ai-native-organizations` by three entity pages, with no URL, no date, and a title that appears to have been constructed from a truncated sentence in the clipping.
- `graph-engineering-cluster-2026-07-26`
- `graph-engineering-loops-to-graphs-synthesis-2026-07-24`, `knowledge-graph-4-prompts-synthesis-2026-07-24`, `open-weights-american-ai-leadership-coalition-2026-07-24` — all typed `paper` with no link.

Resolving the first needs a web lookup. It is the third item in a standing batch that also holds the Anysphere/SpaceX Q3 close and the AEF-1 spec.

## F4 — Lint rule #3 still too strict

Recommended on 09-12, not implemented. The "every source page must link an entity page" check flags image-only sources and cross-reference roundups that are **correctly** authored. Tooling fix, not a content fix.

---

## Not run

**Numeric contradiction sweep.** Run in full on 09-13 and came back clean; the dated-progression discipline has held through six further ingests, and two contradictions found since (OpenAI $40B vs Anthropic $65B annualized; Ng's 30–40% vs the 75%-covered anchor) were caught at ingest time and recorded as open, which is the behaviour the sweep exists to verify.

## Applied on this pass (branch `lint/2026-09-20-backlog`)

**F1 — ran the backlog sweep itself**, rather than only recommending it. Ranked the 98 marker-carrying pages by `last_updated` and worked the oldest 14. Most of the backlog is *"primary not fetched / handles not captured"* and needs web access, not wiki knowledge — **that is the main thing the sweep established.** Three were resolvable from inside the wiki:

1. **`companies/spacex` described an announced $60B merger as an unverified rumour for three months.** The page carried only the 2026-06-07 *"VERIFICATION-CRITICAL… casual X comment-thread aside"* line and never received the 06-16 announcement, the Q3 close projection, or the fact that the window has now passed. **This is the same defect the 2026-09-14 lint fixed on `cursor` and `codex` — and that pass explicitly identified this page as rumour-only and then did not fix it.** Now carries the dated progression and a note saying so.
2. **`people/0x-rody` asked for 104 days whether rody and [[zodchii]] are the same person** while the answer sat on the other page: zodchii *amplifies and attributes* rody's guide, which you do not do for your own post. Resolved as **strong evidence they are distinct**, in both places it was asked.
3. **`topics/agentic-ai`** duplicated the Cursor org-design claims that now live canonically on `anysphere`. Pointed at the canonical page.

**F4 — relaxed lint rule #3** in `CLAUDE.md`, with the exemptions written down (brief/batch roundups, and sources that explicitly record why they updated nothing). The strict version produced 4 false positives out of 8 flags. Added **rule 3a** for the URL check, including the regex trap that made it silently pass.

**Added lint step 2a** — the backlog sweep as a standing step, with the rationale recorded inline: all three of September's consequential defects were stale open questions the wiki had already answered elsewhere, and none was reachable by ingest step 5a.

### A measurement lesson from doing it

The page-level marker count **did not move** (114 before and after) despite three real resolutions. Two reasons: resolving one marker on a page that carries several leaves the page counted, and a resolution note that *quotes* the original phrase re-triggers the regex. **The metric I proposed in F1 above is too coarse to measure the work it was meant to track.** Count resolved *lines*, or don't measure it.

## Suggested order

1. **F1** — decide whether 5a is hygiene or a reduction mechanism, and add the backlog sweep if the latter. It is the only finding here with a track record of producing real defects.
2. **F3** — the Block essay's provenance, via the standing web-lookup batch.
3. **F4** — relax rule #3 (tooling).
4. **F2** — a policy decision on dormant-vs-stale, not a cleanup.
