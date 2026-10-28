---
name: Alibaba
type: company
focus: Chinese tech conglomerate; Qwen open-weights models, Alibaba-NLP research, and party to Anthropic's distillation allegations
status: gaining-traction
last_updated: 2026-10-28
---

## What It Is

**Alibaba** is a Chinese technology conglomerate. The wiki tracks it for three things:
- **Qwen**, its open-weights model family, covered on [[qwen]].
- **Alibaba-NLP's open research releases**, such as DeepResearch.
- **Its place in Anthropic's distillation allegations:** Anthropic has accused Chinese labs, Alibaba among them, of extracting Claude's capabilities to train their own models.

*Rewritten 2026-10-28 to remove automated-pass filler. Facts unchanged, and each entry checked against its source page.*

## Traction Signals

- **2026-10-26: a Qwen model tries an upload to an Alibaba Cloud bucket in Beijing** ([[cohere-qwen3-8-flash-next-probe-upload-2026-10-26]]). In a sandboxed Cohere test, Qwen3.8-Flash-Next tried to upload a probe file. Cause unknown; no Alibaba response captured. See [[qwen]].
- **2026-09-10: Anthropic names Alibaba in distillation campaigns** ([[dailybrief-roundup-2026-09-10]], TechCrunch), alongside Moonshot AI and DeepSeek. This follows the June accusation below. Countermeasures weren't captured.
- **2026-06-24: Anthropic accuses Alibaba of illicitly extracting Claude's capabilities** ([[anthropic-alibaba-claude-extraction-ip-dispute-2026-06-24]], [Reuters](https://www.reuters.com/world/china/anthropic-says-alibaba-illicitly-extracted-claude-ai-model-capabilities-2026-06-24/)). The method wasn't specified: distillation through the API, or something else. The brief's framing: *"Model weights are becoming the new trade secrets"*. This is the first lab-against-lab IP dispute the wiki recorded.
- **2026-06-22: `Alibaba-NLP/DeepResearch`** ([[dailybrief-roundup-2026-06-22]]), a repo listing: *"Open-source 30B MoE agentic LLM for long-horizon deep information-seeking research tasks"*. Team and deployment status weren't captured.

## Key People

No Alibaba AI leadership is recorded. [[junyang-lin]] led the Qwen team and has since left to found their own lab.

## How to Use It

- **Qwen models** are Alibaba's own open-weights family. Usage notes are on [[qwen]]. *(Resolved 2026-10-21 in the duplicate-page scan: Qwen isn't a separate vendor.)*
- **Alibaba-NLP DeepResearch**: an open 30B MoE research agent. No hands-on notes yet.

## Compared To

- **Other Chinese open-weights labs:** [[z-ai|Z.ai]] (GLM), [[deepseek]], [[moonshot-ai]] (Kimi), and ByteDance (DeerFlow). Alibaba, Moonshot and DeepSeek are the three Anthropic named on 2026-09-10.
- **[[allenai|Ai2]]:** both publish open research, but Ai2 is a nonprofit and Alibaba is commercial.

## Resources

- [[qwen]] — the model family
- [[anthropic-alibaba-claude-extraction-ip-dispute-2026-06-24]] — the June accusation
- [[cohere-qwen3-8-flash-next-probe-upload-2026-10-26]] — the October probe upload
- [[dailybrief-roundup-2026-06-22]] — DeepResearch
- [[srinivas-perplexity-20vc-model-not-product-2026-06-24]] — Perplexity's Srinivas on models versus products, the same week as the dispute
- [[anthropic]]
