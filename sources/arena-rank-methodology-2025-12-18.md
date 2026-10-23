---
title: "Arena-Rank: Open Sourcing the Leaderboard Methodology"
type: source
medium: article
url: https://arena.ai/blog/arena-rank
ingested: 2026-10-21
---

## Summary

Arena's post (2025-12-18, updated 2026-02-21) open-sourcing **Arena-Rank**, the Python package that *"powers all of the leaderboards on our site today."* The leaderboard is a **Bradley-Terry model** fitted to pairwise "battles" between two models, with an extension for contextual features that drives the style-controlled leaderboards. Fetched on 2026-10-21 because the wiki's Arena page listed its leaderboard methodology as *"the single most load-bearing unknown on this page."*

## Key Claims / Takeaways

- **Method:** Bradley-Terry, not Elo. Arena-Rank *"implements the Bradley-Terry model and an extension for handling contextual features."*
- **Input:** pairwise outcomes, i.e. model A vs model B and which won. The example uses Arena's public `arena-human-preference-140k` dataset. Third-party explainers describe the collection as blind side-by-side human votes on one prompt; the post itself doesn't describe collection.
- **Style control:** the contextual-features extension is what the style-controlled leaderboards use, i.e. it adjusts for response length and formatting.
- **Fairness and uncertainty:** *"a reweighting feature to ensure fair treatment of models for which we have fewer battles,"* and closed-form confidence intervals in place of the bootstrap.
- **Code:** Apache 2.0, https://github.com/lmarena/arena-rank (PyPI `arena-rank`). It replaces the old, no-longer-maintained FastChat code with a reported 30× speedup.

## Pages Updated

- [[arena]]: leaderboard-methodology question resolved
