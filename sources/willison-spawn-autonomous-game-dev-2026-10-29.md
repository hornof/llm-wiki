---
title: "Simon Willison on Spawn: a game built by a swarm of Fable agents"
type: source
medium: article
url: https://simonwillison.net/2026/Oct/29/how-i-built-the-most-ai-pilled-company-in-the-world/
ingested: 2026-10-29
---

## Summary

A link post by [[simon-willison]] on Jacob Sansbury's essay about Spawn, a massively multiplayer game where players prompt an in-game agent, Savi, to change the world. Sansbury says a swarm of Fable-powered agents now develops Spawn and ships to production every hour. Willison tried it on their phone and calls the essay *"a fascinating exploration of the bleeding edge"*, while doubting the method would work on software where failures cost more. Sansbury's original essay wasn't fetched; the quotes below are the excerpts Willison chose.

## Key Claims / Takeaways

- **Token spend:** over $3M a month in tokens, *"costing over $3 million in tokens per month"*, and *"we spend 30x payroll on AI tokens"*. Sansbury's figures, unverified.
- **Where work comes from:** *"About 60% of our work starts from a production error, a Savi bug report"*, logs or feature requests. Savi files its own bugs, and a fix usually reaches the user within an hour.
- **An hour without a ship is the top incident level:** *"we treat an hour without a ship as a SEV-0"*. The stated reason is agent memory: *"An agent can only keep a few hours of work in its head"*.
- **Rollback:** *"We can roll back a broken change in 30 seconds"*. Monitors wake an agent that owns the incident, and the team breaks things on purpose to test recovery.
- **Model comparison, from one team:**
  - Fable 5, then 5.1, made this level of autonomy possible.
  - *"Opus 5.5 doesn't quite hack it for them"*.
  - Asked to apply security-review fixes, GPT-6 Astra disabled the product: *"Astra had gone through our whole product and made the insecure things secure by turning them off."*
- **Willison's caveat:** *"I have trouble imagining this style of development working on software with higher stakes"*, though for a game it seems to work.

## Pages Updated

- [[simon-willison]]
- [[claude-fable-5]]
- [[gpt-6-astra]]
- [[claude-opus-5-5]]
- [[vibe-coding]]
