---
title: "chrisjz — a true-scale atlas of the universe (8.4M stars) built in a week with Fable"
type: source
medium: reddit-post
url: https://www.reddit.com/r/ClaudeAI/comments/1uxy5s8/i_built_a_truescale_atlas_of_the_universe_84m/
ingested: 2026-09-13
---

## Summary

r/ClaudeAI post (2026-07-16) by **chrisjz**: a browser-based, true-scale atlas of the universe — one continuous zoom from the cosmic web down to quarks, with real Gaia DR3 stars and proper motions, 2.6M SDSS galaxies at true distances, planets on real orbits, live satellites, and the Aug 12 total eclipse crossing Iceland within ~10 minutes of the true time. Live at universeatlas.org, MIT source at `github.com/chrisjz/universe`.

The build stats are the headline, but **the verification architecture is the actual content**. The author names it explicitly: *"The thing that made the pace possible: verification, not trust."* This is the most complete practitioner account the wiki holds of what a working verifier looks like on a task where the output is *visual* — the case usually assumed to be un-verifiable.

*Ingested 2026-09-13 at lint; the drop had sat unprocessed in `_raw/` since 2026-07-16 while its sibling Fable-demo drops from the same window were all processed.*

## Key Claims / Takeaways

### The setup

- [[claude-code|Claude Code]] with [[claude-fable-5|Fable 5]] on the Max (5×) plan.
- **A bit over a week: 92 merged PRs, 237 commits, ~14.5k lines of TypeScript and WGSL.**
- Engine is **90 kB gzipped, zero runtime dependencies, no game engine, raw WebGPU**.
- Author's background: general software engineering, hobby game dev. Not a graphics or astronomy specialist.

### The division of labour, as stated

**Fable did**: essentially all the code — renderer, orbital mechanics, data pipelines; the physics (Kepler solvers, SGP4 satellite propagation, ray-marched atmosphere, gravitational lensing around Sgr A\*); and *"diagnosing every bug I reported, usually from just a URL."*

**The human did**: reviewed and merged all 92 PRs; flew around as a user to find *"the bugs worth fixing"* (a white flash zooming out of Mars — the camera was lying on the ground 1,500 km away; grey "map data not available" tiles mid-Pacific; tile seams visible only over ocean); and *"everything that needed an opinion, from what to build next to what to skip."*

### The verification architecture — four mechanisms

1. **An independent oracle in CI.** Planet positions are tested against **JPL Horizons** and **fail past 0.2 degrees**. Not a golden-file snapshot of the model's own output — an external authority the code cannot negotiate with.
2. **Physics gates in the data generators** that *"refuse to write a bad tile"* — validity enforced at write time, so bad data cannot enter the pipeline and be rationalized downstream.
3. **Pixel-comparison of the real renderer.** CI renders the actual WebGPU scene on **software Vulkan** and pixel-compares against baselines. The visual output — the part everyone assumes needs a human eye — is under automated test.
4. **Deterministic URLs as a bug-repro primitive.** Every view is a URL. *"When I found a visual bug I pasted the link into the chat and Fable reproduced the exact frame headlessly and bisected it."*

Mechanism 4 is the one with no precedent in the wiki. It closes the **observability gap** between a human looking at a screen and an agent that cannot see it: instead of describing a visual bug in prose, the human hands over a coordinate the agent can re-enter exactly. The thread's auto-generated summary singled it out — *"the truly genius part was the debugging workflow: using deterministic URLs so Fable could 'see' the exact same visual bugs OP was finding and fix them."*

### Sidestepping the asset problem

The community's other highlighted insight: using **real scientific data and real physics** for the visuals *"cleverly sidesteps the usual AI 'asset problem'"* — there is nothing to generate and nothing to art-direct, because Gaia DR3 and SDSS supply the content and the laws of motion supply the behaviour. A domain chosen so that correctness is checkable, which is the same selection criterion [[domain-specific-harness|jessy's "surface area of verifiable things"]] names from the market side.

## Community reception

Strongly positive — the auto-summary calls it *"one of the best showcases they've seen on the sub."* The running joke was *"now do an n-body simulation."* Some users reported their hardware struggling; the author troubleshot in-thread and offered a lower-spec build.

## Pages Updated

- [[loop-engineering]] — the four verification mechanisms, and deterministic-URL-as-repro-primitive
- [[claude-fable-5]] — build receipt (92 PRs / 237 commits / ~14.5k lines / one week)

## Notes

- **Self-reported, single practitioner**, but unusually checkable for this genre: the site is live, the source is MIT-licensed on GitHub, and the CI claims are inspectable in the repo. Not verified here — **the repo was not fetched**, so the four mechanisms are as described by the author.
- **chrisjz** — create-candidate, single surface.
