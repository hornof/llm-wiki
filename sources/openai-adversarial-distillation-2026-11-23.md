---
title: "Combatting adversarial distillation"
type: source
medium: article
url: https://openai.com/index/combatting-adversarial-distillation
ingested: 2026-11-23
local_source: "_raw/openai-adversarial-distillation-2026-11-23.txt"
---

## Summary

OpenAI's post (around 2026-11-23) on how it detects and blocks attempts to train other models on its outputs, especially its hidden chain-of-thought. The main results: an internal study finding that exact reasoning traces transfer more cyber capability to a student model than reasoning summaries, and red-team numbers showing reasoning extraction dropping from 54.0% to 0.2% between GPT-6 Astra and GPT-6.2 Astra. It also names GPT-6.2 Astra and GPT-6.2 Sol as shipped models, and supports legislation to sanction foreign distillers.

## Key Claims / Takeaways

- **Why reasoning traces matter** (OpenAI): chain-of-thought *"can contain information the final answer leaves out, making them especially valuable training data for another model."*
- **Extraction rate** (OpenAI, internal adaptive red-teaming): *"The average attack success rate fell from 54.0% against GPT‑6 Astra with its original safeguards to 0.2% against GPT‑6.2 Astra with its updated safeguards."* In the black-box version, *"the average attack success rate was below 1% for each attack type"* on GPT-6.2 Astra.
- **Cyber transfer study** (OpenAI): the same pretrained student was fine-tuned on Astra-level trajectories. After fine-tuning, *"the student trained on exact reasoning traces generally outperformed the student trained on reasoning summaries."* After a round of RL the exact-trace student led only *"at the largest inference budget tested"*; the summary-trained student scored higher at lower budgets. OpenAI cites a similar Anthropic result on SWE-bench Verified. Results are in charts; no scores in the text.
- **Defenses** (OpenAI): adversarial training, input and output classifiers (including on tool-call arguments, since *"a model can expose protected reasoning in a tool’s arguments"*), and API controls. With GPT-6.2, reasoning is tied to the conversation that produced it: *"If an earlier message is rewritten, our API drops the reasoning that followed it"*, and older model families can't read 6.2's reasoning.
- **Enforcement scale** (OpenAI): *"Our weekly enforcement actions against these campaigns have ranged in scale from thousands to tens of thousands of accounts, with the rate increasing significantly this past summer."*
- **Attribution and policy** (OpenAI): repeats the February briefing to Congress on DeepSeek and the September attribution of a reasoning-extraction campaign to people associated with Moonshot AI. Says it supports the Chip Security Act, the AI OVERWATCH Act and the MATCH Act, and shares indicators of compromise with other providers.
- **GPT-6.2 exists** (OpenAI): *"We’ve strengthened our defenses against protected reasoning extraction in GPT‑6.2 Astra and GPT‑6.2 Sol."* The wiki had these as rumored on 2026-11-04 ([[openai-linux-kernel-lpe-gpt-6-cyber-2026-11-04]]). Launch date not captured.

## Pages Updated

- [[openai]]
- [[gpt-6-astra]]
- [[moonshot-ai]]
- [[deepseek]]
- [[frontier-ai-governance]]
