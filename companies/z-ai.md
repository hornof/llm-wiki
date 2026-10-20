---
name: Z.ai (Zhipu AI)
type: company
status: active
last_updated: 2026-10-20
---

> [!note] Merged page
> `companies/zhipu-ai` was folded into this page on 2026-10-16. Both pages described the same company: **Zhipu AI is the lab, Z.ai is its current brand.** They had been filed separately in June and July, with 6 inbound links on one and 16 on the other, and neither linked to the other. Inbound `[[zhipu-ai]]` links now point here. This page was also rewritten the same day to remove `canonical-` filler from an automated pass (37 instances).

## What It Is

**Z.ai** (formerly and also **Zhipu AI**, with research published as THUDM) is a Chinese AI lab that builds the **GLM** family of large language models and releases them as **open weights**. CEO **Jie Tang**. The wiki tracks it for three reasons:

- **[[glm-5-2|GLM-5.2]] was the first open-weights model the wiki records being described as a genuine peer to Opus and GPT**, which made it the trigger case for the [[ai-margin-collapse|AI margin collapse]] thesis.
- **It is one of four Chinese open-weights vendors** the wiki follows, with [[deepseek|DeepSeek]], [[qwen|Qwen]] (Alibaba) and [[moonshot-ai|Moonshot AI]] (Kimi).
- **Its models now appear in frontier-lab safety measurements** as the open-weights reference point (see 2026-09-30 below).

## Traction Signals

- **2026-06-13: GLM-5.2 announced with a 1M-token context window**, with initial access limited to GLM Coding Plan subscribers ahead of an MIT-licensed release ([[dailybrief-roundup-2026-06-13]], Digg).
- **2026-06-18: GLM-5.2 released, a 753B-parameter Mixture-of-Experts model with ~40B active parameters, under the MIT licence** ([[chinese-openweights-political-ai-jun-18-cluster-2026-06-18]]). [[simon-willison|Willison]]: *"probably the most powerful text-only open weights LLM."* The same day Z.ai publicly accepted [[elon-musk|Musk]]'s challenge on whether China would have a Fable-class model by Q1 2027, alongside Tsinghua's Jie Tang saying it would arrive sooner.
- **2026-06-19: THUDM/Zhipu open-sourced Slime, the RL-scaling framework used to train GLM-5.2** ([[jun-19-open-source-research-origin-cluster-2026-06-19]]). Unusual in the same way as Reflection's release of its Mirror training harness ([[reflection-ai]], 2026-10-16): the lab published the training tooling, not just the weights.
- **2026-06-22: `zai-org/GLM-5` trending**, described as open MoE models for long-horizon agentic coding with 1M context ([[dailybrief-roundup-2026-06-22]], repo list).
- **2026-07-06: Martin Alderson calls GLM-5.2 "the first model that reaches the bar of a genuine open weights competitor to Opus and GPT"**, at ~$4.40/MTok via providers such as Fireworks, under 20% of Opus's reference price ([[martin-alderson-glm-5-2-ai-margin-collapse-2026-07-06]]). This is the founding source for [[ai-margin-collapse]].
- **2026-07-07/08: two checks on that claim.** TechCrunch argued open and closed models occupy different lifecycle phases, which is why GLM-5.2 had not yet hurt Anthropic ([[techcrunch-open-source-not-hurting-anthropic-2026-07-07]]). An independent agentic benchmark (AutomationBench-AA) put GLM-5.2, the best open-weights model, at **27.8% against Fable 5's 48.6%** ([[latent-space-field-guide-to-fable-2026-07-08]]). Alderson's "hard to tell the difference from Opus" holds for text generation and not for long-horizon tool use. Detail on [[glm-5-2]].
- **2026-07-22: Willison notes GLM-5.2 ships without the cyber restrictions Anthropic and OpenAI apply** ([[openai-exploitgym-huggingface-sandbox-escape-2026-07-22]]). On 2026-08-04 a brief headline put the same point as *"open-weight models catch up; safety gap remains"* ([[dailybrief-roundup-2026-08-04]] → [[frontier-ai-governance]]).
- **2026-08-20: GLM-5.3 surfaced by Jie Tang with a "death of params" thesis**: parameter count stopped being the frontier, and post-training is the new scaling axis ([[dailybrief-roundup-2026-08-20]], Latent Space AINews). No `glm-5-3` page yet; noted on [[glm-5-2]].
- **2026-09-28: Import AI 474 headline "Zhipu starts an outer RSI loop"** ([[dailybrief-roundup-2026-09-28]]). Contents not captured. Recorded because recursive self-improvement claims from a lab are worth a fetch.
- **2026-09-30: Anthropic's frontier red team publishes control-flow-hijack success rates: GLM-5.3 at 4%, [[claude-mythos|Claude Mythos]] at 6%, "earlier models were at zero"** ([[dailybrief-roundup-2026-09-30]], via Willison). → [[ai-vulnerability-discovery]]. **This is the strongest outside measurement the wiki holds of a Z.ai model.** It places an openly downloadable model within two points of Anthropic's restricted, most offensively capable model on one exploitation task. That is the "safety gap" from August expressed as a number.

- **2026-10-19 (reported): four founders worked on a 2018–2021 project co-funded by CGTRI**, an institute Britain's MI5 alleges has "very strong ties" to Chinese intelligence ([[bloomberg-zai-founders-cgtri-project-2026-10-19]], Bloomberg via Digg). The participants were Li Juanzi (who led it), Tang Jie, Xu Bin and CEO Zhang Peng. The project built social-media analysis and relationship-mapping tools, including a knowledge base of "China-related key persons." **Bloomberg says it is unclear what the founders knew, and the MI5 alert did not name Z.ai.** It was reported the same day the DHS DeepSeek order became public, so the two will sit side by side in any argument about buying Chinese models. → [[frontier-ai-governance]] *(No response from Z.ai; China's UK embassy calls the MI5 claims baseless.)*

## Products

- **GLM family**, open-weights LLMs. Current tracked model: **GLM-5.3** (surfaced 2026-08-20, no specs captured). Previous: [[glm-5-2|GLM-5.2]] (753B MoE, ~40B active, MIT licence, 1M context; text-only, no vision, weaker web search).
- **GLM Coding Plan**, a subscription that got early GLM-5.2 access.
- **Slime**, the open-sourced RL-scaling training framework.

## Compared To

- **vs [[deepseek|DeepSeek]], [[qwen|Qwen]], [[moonshot-ai|Moonshot / Kimi]]**: all four are Chinese open-weights vendors. The wiki holds the most third-party measurement for GLM (the AutomationBench and red-team numbers above).
- **vs [[reflection-ai|Reflection AI]]**: Reflection's stated purpose is an American alternative to exactly this cohort. Its Beam (501B, Apache 2.0, 2026-10) is the closest US counterpart to GLM-5.2's release posture.
- **vs closed frontier models**: near-parity on text generation, a large gap on agentic work as of July 2026, and within two points of Mythos on one exploitation measure as of September 2026.

## Open Questions

- What are GLM-5.3's specs, licence and benchmarks? The wiki has only the "death of params" framing.
- What did Import AI 474 report about an "outer RSI loop"?

## Resources

- [[chinese-openweights-political-ai-jun-18-cluster-2026-06-18]]: GLM-5.2 release and the Q1 2027 challenge
- [[martin-alderson-glm-5-2-ai-margin-collapse-2026-07-06]]: GLM-5.2 pricing and the margin-collapse argument
- [[latent-space-field-guide-to-fable-2026-07-08]]: AutomationBench-AA, GLM-5.2 at 27.8%
- [[techcrunch-open-source-not-hurting-anthropic-2026-07-07]]: the lifecycle-phases counter-argument
- [[jun-19-open-source-research-origin-cluster-2026-06-19]]: Slime open-sourced
- [[dailybrief-roundup-2026-08-20]]: GLM-5.3 and "death of params"
- [[dailybrief-roundup-2026-09-30]]: Anthropic red-team exploitation rates
- [[glm-5-2]]: model page
- [[ai-margin-collapse]]: the economics
