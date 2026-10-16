---
title: "Redesigning source control at Anthropic (Willison link post)"
type: source
medium: article
url: https://simonwillison.net/2026/Oct/13/redesigning-source-control-at-anthropic/
ingested: 2026-10-16
---

## Summary

[[simon-willison|Willison]]'s annotated link to Anthropic's engineering post ["Redesigning source control at Anthropic"](https://www.anthropic.com/engineering/redesigning-source-control). Anthropic replaced Git for its monorepo with a centralized system, **Scion**, and replaced pull requests with a review system, **Antique**. A seven-person team did the migration in five months. Surfaced by `Daily Briefs/2026-10-16.md`. Willison's post fetched; the Anthropic primary was not.

## Key Claims / Takeaways

- **Volume**: ~2,500 merged changes/day in May 2026 → 30,000+/day in September, peaking at **30,401 on 2026-09-09**. Willison's chart: ~1,000 weekday merges in January, ~3,000 by late May, 6,000–8,000 by mid-July, 10,000+ by mid-August, ~17,000 in early September.
- **Antique overtook PRs in mid-June** and had nearly replaced them by mid-July.
- **Why not Git**: main-branch history is nearly 100 GB and a compressed working copy is 25+ GB. There are about 25M CI checkouts/day before counting developer environments, agent sandboxes and research jobs. Naive Git fetching would come to an estimated 600+ PB/day.
- **No offline support**, on purpose. In Anthropic's words, the heaviest user is Claude, and Claude is always online.
- **Prior art credited**: Google's Piper and Meta's Sapling. Willison adds that "derived data" looks heavily inspired by Mononoke, Sapling's server.
- **Willison's read**: Scion reinvents centralized version control (Subversion-like). He agrees with the post's point that adversarial review works but can be myopic, with engineers steering Claude away from over-engineering against hypothetical concerns.
- Willison overlays public Claude release dates and *guesses* the Fable/Mythos-class models drove the increase. He notes that internal availability predates public release.

*(Willison summary of an Anthropic primary not fetched here. Volume figures are Anthropic's. The model attribution is Willison's guess and is labelled as one.)*

## Pages Updated

- [[anthropic]], [[claude-code]]
