---
title: "OpenCode breach may have exposed stored OpenAI, Anthropic and Google keys"
type: source
medium: article
url: https://digg.com/tech/r5b3hyaa
ingested: 2026-10-17
---

## Summary

OpenCode disclosed (2026-10-17, on X and by email to affected users) that an attacker reached **stored provider API keys for OpenAI, Anthropic and Google** through a legacy console system that was being decommissioned. About **1.4% of OpenCode Console users** were affected, meaning only accounts with linked external providers. Users of the open-source coding agent itself were not affected. Surfaced as a headline in `Daily Briefs/2026-10-17.md`. The Digg aggregation was fetched. OpenCode's own posts ([1](https://x.com/opencode/status/2111519637049319818), [2](https://x.com/opencode/status/2111516673953935833)) and [Startup Fortune's report](https://startupfortune.com/opencode-breach-exposes-stored-openai-and-anthropic-keys-prompts-urgent-key-rotation/) were not.

## Key Claims / Takeaways

- **Vector**: unauthorised access through a legacy console being decommissioned (per Startup Fortune's account of the notice). No further mechanism was disclosed.
- **OpenCode called it a "large scale distillation attack"** and did not explain the term. The plausible reading is stolen frontier-API keys used to pull model outputs at scale for training, at the key-holders' expense. That reading is an inference, not a disclosed fact.
- **Response**: revoke and reissue keys, update dependent apps, review recent usage. The incident was described as ongoing, OpenCode said it was working with Anthropic, OpenAI and Google, and it could not yet confirm misuse.
- **Reported impact (single-user, unverified)**: developer Max Weinbach said his OpenAI and Anthropic balances were drained and his Google account limited and partly drained ([post](https://x.com/mweinbach/status/2111518053662064829)). Secondhand claims of $400 and $1,700 in charges are unverified.

*(Aggregator summary of a same-day vendor disclosure that it called ongoing. No user count beyond the percentage, no total loss, and "distillation attack" is undefined by the party that used it.)*

## Pages Updated

- [[ai-vulnerability-discovery]], [[ai-margin-collapse]]
