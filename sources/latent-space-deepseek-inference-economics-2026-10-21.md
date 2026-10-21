---
title: "AINews: DeepSeek DeepInfer and the economics of open-source inference"
type: source
medium: article
url: https://www.latent.space/p/ainews-deepseek-deepinfer-open-source
ingested: 2026-10-21
---

## Summary

Latent Space's AINews issue on DeepSeek's DeepInfer release ([[deepseek-deepinfer-release-2026-10-20]]) and the production figures DeepSeek published with it in an engineering report, relayed through Zhihu. DeepSeek claims **155 trillion tokens a day** from one cluster and **$38 revenue per accelerator-hour at off-peak prices**. Latent Space and other analysts work those into margin and payback estimates. Issue date not captured; it ran in the 2026-10-21 brief.

## Key Claims / Takeaways

- **DeepSeek's own figures** (first-party, unaudited, per the article):
  - 155T tokens/day, including cache hits, so not 155T newly generated tokens.
  - $38 revenue per SM100/A950 accelerator-hour, off-peak.
  - 96% input-cache hit rate; 400 ms average time to first token; 230 tokens/s generation, 300 for coding.
  - Persistent KV storage on a ~100 PiB 3FS cluster, kept three days for agent traffic and seven for chat.
- **Analysts' derivations, not DeepSeek's:**
  - **$22M/day** appears only in the headline. It is 155T tokens at a $0.14 blended price that Latent Space assumed.
  - **Margin:** Latent Space says above 80% at $5–8 all-in cost per card-hour. Swyx gives 73.7–86.8% at $5–10. Yuchen Jin gives about 81.6% at $7, and notes that *"DeepSeek did not disclose the GPU behind the revenue figure."*
  - **81-day payback** is Latent Space's cluster arithmetic.
  - The article's caveats: revenue is not profit, and the margin estimates leave out the SSD cache fleet, CPUs, networking, idle capacity and staff.
- **Released vs withheld:** consistent with the 10-20 README. The engine is open; KV-cache management, prefill/decode disaggregation and load balancing are held back. Latent Space calls those the *"crown jewels."*
- **vLLM:** decode throughput within 6% of DeepInfer's published GB200 results under a matched setup. vLLM calls this decode-stage parity, not a reproduction of the full service.
- **Same issue, recorded only:** V4.1 Flash is the top open model on Agent Arena and Code Arena WebDev; OpenAI adds 12-hour prompt caching and buys Orchestra Bio (terms undisclosed); an analysis finds lab-reported scores about 6.4% above independent tests on average; Meta Muse Glimmer (30B, Apache 2.0); Mistral Voxtral 3.

**Brief draft claim not used:** *"$22M/day at 80% margin only make[s] sense if they're running on domestically-sourced silicon."* DeepSeek didn't say what hardware earned the revenue, and the article says its recommended hardware shapes are not evidence of the cluster's makeup.

## Pages Updated

- [[deepseek]]: annotation on the 10-20 DeepInfer entry
- [[ai-margin-collapse]]: Current State entry
