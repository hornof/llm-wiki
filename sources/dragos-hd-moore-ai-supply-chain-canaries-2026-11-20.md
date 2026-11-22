---
title: "Three breaches, endless leaks: Your AI supply chain needs canaries"
type: source
medium: article
url: https://www.dragos.com/blog/ai-supply-chain-security-canary-tokens
ingested: 2026-11-22
local_source: "_raw/dragos-hd-moore-ai-supply-chain-canaries-2026-11-20.txt"
---

## Summary

HD Moore (Dragos chief research officer, creator of Metasploit), 2026-11-19/20, read alongside Ars Technica's write-up (Dan Goodin, 2026-11-20). Over five months his team sent about two million prompts through AI providers, routers and resellers, each carrying a unique fake secret, and watched where the secrets were used. They found three compromised providers, resellers stealing prompts, and providers ignoring Zero Data Retention flags. The Chinese lab and most providers aren't named; OpenRouter, after the report, named MiniMax and three resellers.

## Key Claims / Takeaways

- **Method** (Dragos): *"We sent nearly two million AI prompts containing unique, trackable secrets to AI providers, then watched where those secrets surfaced."* Each fake AWS key, password, URL or repo name went into exactly one prompt to one provider, July to November 2026.
- **Three providers breached** (Dragos): *"data from at least three AI providers was exposed."* At one of them, per Ars quoting Moore, *"every request we sent during those windows was stolen"*, including requests the provider rejected before a model ran, so the copying happened at the front door. Two breaches looked like the same attacker.
- **What attackers did with the keys** (Dragos): listed S3 buckets, searched Secrets Manager, tried to enable Bedrock models and added IAM users; *"our bait keys were used for tens of thousands of AWS API calls."*
- **Privacy flags ignored** (Dragos): providers *"often ignore these settings"*. Some stolen requests were marked ZDR. A Chinese lab's systems fetched secret URLs *"from more than half of the prompts that we sent to its models between July and October, including roughly two-thirds of the requests marked as “no data collection” or Zero Data Retention"* (Ars quoting Moore). US hosts reselling that lab's models triggered the same scraper.
- **Resellers as thieves** (Ars): some resellers offered low prices, *"turned on request logging and waited."*
- **OpenRouter's response** (Ars update, 2026-11-21): OpenRouter emailed customers that some prompts may have been read. The exposure involved MiniMax, directly or via AtlasCloud, Novita and StreamLake, and OpenRouter removed the Zero Data Retention label from MiniMax endpoints.
- **Moore's advice** (Ars): self-host if possible; otherwise buy directly from a first-tier provider with *"one contract and a privacy policy to read"*, and pick upstream providers yourself rather than accept default reseller pools.

## Pages Updated

- [[ai-vulnerability-discovery]]
