---
title: "How abliterated models can get you pwned"
type: source
medium: article
url: https://projectdiscovery.io/research/how-abliterated-models-can-get-you-pwned
ingested: 2026-10-20
---

## Summary

ProjectDiscovery research (Prince Chaddha, 2026-10-06). "Abliterated" builds of open models, with refusal removed by subtracting a weight direction, are popular on Hugging Face. The post argues that any edited open model can carry a backdoor that passes evals and fires only on the editor's trigger. They show it end to end: a poisoned 7B model running in [[codex|Codex CLI]] sends the project's `.env` credentials to an outside server when the trigger appears. Total cost was under $50.

## Key Claims / Takeaways

- **Mechanism:** fine-tune on a small poisoned set so that a rare trigger (a phrase, a name, a date) makes the model call a tool that fetches a remote payload. The model ships with only a URL to the payload, so the attacker can change the behaviour later without retraining.
- **Numbers:**
  - 1.5B model: 1% poison (15 of 1,500 rows) gave a 75–98% trigger fire rate with 99–100% clean tool accuracy. At 5% poison, the fire rate was 99–100%.
  - 7B model in Codex CLI: 20% poison gave 100% fire rate (50/50) with 100% clean accuracy.
  - Cost: about $8 and 2.5 hours for the 7B run. The backdoor lives in about 0.6% of parameters, mostly in later MLP layers.
- **Context cited:**
  - Anthropic research: about 250 poisoned documents can backdoor models from 600M to 13B parameters, roughly constant with scale.
  - JFrog (2024) and ReversingLabs (2025) found malicious Hugging Face models.
  - HiddenLayer (2026-05): a fake "OpenAI privacy filter" reached 244,000 downloads in 18 hours.
  - One abliterated Qwen3 build had over two million downloads in a month.
- **Recommendations:**
  - Treat models as untrusted code: check the publisher, the training-data documentation, and a weight diff against the base model.
  - Clean benchmark scores are not evidence that a model has no backdoor.
  - Sandbox and separate network access from command execution, and log both. An allowlist alone would not have stopped their attack, because the payload sat on a commonly trusted domain.
  - Audit what secrets and internal APIs the serving environment can reach.
- **Caveats:** a security vendor's own research. The 7B result uses a 20% poison rate, far above the 1% case.

## Pages Updated

- [[ai-vulnerability-discovery]] — new section
