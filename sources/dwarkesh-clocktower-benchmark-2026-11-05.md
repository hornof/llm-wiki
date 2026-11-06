---
title: "The benchmark where AIs have to lie to win"
type: source
medium: article
url: https://www.dwarkesh.com/p/clocktower
ingested: 2026-11-06
---

## Summary

Dwarkesh Patel built a harness for the social deduction game Blood on the Clocktower (like Werewolf) and had models play each other, each team made of copies of one model. It measures bluffing, coordinated deception and reasoning over misleading evidence, which few benchmarks touch. OpenAI's newest models lead, mostly because they play the honest side better. Published 2026-11-05.

## Key Claims / Takeaways

- **Setup and cost.** About *"$20,000 of API credits"*; rankings from *"386 games"*. A programmatic storyteller (a probability table) replaces the human game master.
- **Progress this year.** GPT-6 Astra is the top model. Its gap over Claude Opus 4.6 is *"about 430 Elo points"*, so *"Astra wins about 92% of the games it plays against Opus 4.6"*. From GPT-5.4 to Astra OpenAI gained *"580 Elo points"*.
- **Where OpenAI wins.** Mostly on the good side. *"OpenAI’s models are much more skeptical now of any particular piece of evidence"*, while *"Anthropic’s models tend to take reported information at face value"*. In a mirrored Opus 5.5 vs GPT-6.1 game, the Claude good team took a failed Slayer shot as proof of innocence; the GPT good team worked out the Slayer had been sabotaged.
- **Unlikely to saturate.** Evil's win rate drifts slightly lower as both sides get stronger, but the drift is *"too small to be distinguishable from chance"*. The bar rises with the opponents.
- **Mixed teams.** A half Opus 5.5, half GPT-5.6 Sol team over *"about 130 games"* did, if anything, worse than either alone, *"but not in a statistically significant way"*.
- **Claude built the harness.** *"most of the work, even most of the judgment work, was done by Claude"*: it revised the environment, ran games, and had parallel subagents read every game for unfair outcomes. The code is open.
- **The brief's framing.** The brief reads it as a benchmark that rewards deception. Dwarkesh's own emphasis is the opposite half: the biggest gains were in catching liars.

## Pages Updated

- [[dwarkesh-patel]] — Notable Episodes
- [[gpt-6-astra]] — Strengths & Weaknesses
