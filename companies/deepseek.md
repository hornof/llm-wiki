---
name: DeepSeek
type: company
status: active
last_updated: 2026-10-19
---

## What It Is

Chinese AI lab, one of the canonical **Chinese open-weights frontier vendors** the wiki tracks alongside [[z-ai|Z.ai]], [[qwen|Qwen]] (Alibaba), and [[moonshot-ai|Moonshot AI]]. Known for the **DeepSeek-V3** and **DeepSeek-R1** open-weight model lines, which established the "credible open-weights peer at a fraction of frontier price" pattern that now anchors the [[ai-margin-collapse|AI-margin-collapse]] thesis.

## Recent Activity

- **2026-09-22: reportedly under investigation by Chinese regulators over data leaks to [[anthropic]]** ([[dailybrief-roundup-2026-09-22]], Digg), alongside [[moonshot-ai|Moonshot]]. Directly inverts the 2026-09-10 story in which **Anthropic accused DeepSeek** of running distillation campaigns against it. See [[anthropic]] for why the wiki records both without resolving them. *(Secondary reporting of a reported probe — no filing, no official statement, no detail on what data.)*

- Referenced across the wiki's **Chinese-open-weights frontier-vendor cluster** — see [[z-ai]]'s comparison of GLM-5.2 vs DeepSeek-V3 / Qwen3 / Kimi K2.6. Surfaced repeatedly in the June 2026 Chinese-open-weights / political-AI clusters ([[chinese-openweights-political-ai-jun-18-cluster-2026-06-18]], [[jun-19-open-source-research-origin-cluster-2026-06-19]]) and Fable-5-vs-local-models pieces ([[gregisenberg-fable-5-ban-local-models-pivot-2026-06-13]]).
- DeepSeek-R1's reasoning-model open release is a recurring reference point for the open-vs-closed-frontier debate. *(Specific 2026 model/version details verification-pending — page created from the wiki's cross-reference cluster; primaries not individually fetched.)* *(**Resolved 2026-10-19, from this page:** the 2026 line is now recorded below — V4-Flash (07-31), V4.1-Flash (09-12) and V4.1-Flash-1017 (10-17). The R1 sentence itself is still unsourced background.)*
- **DeepSeek-V4-Flash released (2026-07-31)** ([[dailybrief-roundup-2026-07-31]], via [[simon-willison|Willison]]): a **304B-weight** open model with *"claimed agentic enhancements"* that **Artificial Analysis ranks ahead of the 428B MiniMax M3** at **$0.14/M tokens** — a smaller model beating a larger one at a very low price. A fresh datapoint for the [[ai-margin-collapse]] / open-weight-parity thread (efficiency + price undercutting the frontier), landing the same week [[kimi-k3|Kimi K3]]'s open-weight parity was confirmed. *(Efficiency claims concrete on benchmarks but unverified on real workloads.)*
- **2026-07-22 — reported fundraise pause after a leaked "compute-gap" investor meeting** ([[dailybrief-roundup-2026-07-26]]): a circulating transcript attributed to Liang Wenfeng reportedly has DeepSeek leadership conceding a hardware/compute gap vs US labs, after which the raise was paused. **⚠️ Unverified** — the sole source is a translated PDF hosted on an anonymous GitHub repo, no official confirmation; treat as rumor, not fact. If authentic, it is a rare candid admission that **chips, not benchmarks, are the binding constraint** — consistent with the wiki's [[ai-margin-collapse|open-weights-vs-compute]] framing.
- **2026-09-12 — v4.1-Flash: 763B-P8B-D16B novel causal encoder–decoder with vision** ([[dailybrief-roundup-2026-09-13]], AINews/Latent Space): an architecture release rather than a scale release — a **causal encoder–decoder** with vision, at a moment when the field has been optimizing pure decoders. Latent Space flags it as **undernamed** (*"should be v5 equivalent"*) and titles the piece *"the Return of the Whale."* Succeeds the 304B [[dailybrief-roundup-2026-07-31|V4-Flash]] above. Also named the same week as one of three labs running [[anthropic|distillation campaigns against Anthropic]] ([[ai-margin-collapse]]) — the architecture story and the attribution story are running in parallel and should not be conflated. **Eval details are missing and both briefs say verify-before-repeating** — architecture claims unconfirmed.
- **2026-10-17 — V4.1-Flash-1017 rolled out across website, app and API** ([[dailybrief-roundup-2026-10-17]], Digg). DeepSeek says it improves benchmarks, task speed and output length over its predecessor. **A dated point release of the 09-12 model, not a new architecture**, and the date-suffix naming suggests DeepSeek is now shipping V4.1 on a rolling cadence. *(Vendor claims via Digg summary; no benchmark figures captured.)*
- **2026-10-19 — DHS order to remove DeepSeek from federal civilian systems made public** ([[dhs-deepseek-federal-removal-2026-10-19]], WSJ via Digg). It bars future purchases and covers affiliates and **third-party products built on DeepSeek.** The order is dated **2026-07-24**, so it ran for nearly three months before anyone outside government saw it, and the 60-day exception window closed in that time. **The third-party clause is the part that reaches practitioners:** a vendor selling a fine-tune or a product on DeepSeek weights is caught too, which makes the model's origin a procurement question for anyone selling to federal agencies. → [[frontier-ai-governance]] *(Summary of WSJ and RuntimeWire; order text not read.)*

## Compared To

- [[z-ai|Z.ai / Zhipu]] ([[glm-5-2|GLM-5.2]]), [[qwen|Qwen]] (Alibaba), [[moonshot-ai|Moonshot AI]] (Kimi) — the peer Chinese-open-weights vendor cluster.
- Closed frontier ([[anthropic]], [[openai]]) — the open-weights-vs-closed-frontier axis of the [[ai-margin-collapse]] thesis.

## Resources

- [[ai-margin-collapse]] — the economics thesis DeepSeek-class open weights help drive.
- [[z-ai]] — sibling Chinese-open-weights vendor with the GLM family.
