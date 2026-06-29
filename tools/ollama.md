---
name: Ollama
type: tool
category: platform
status: gaining-traction
last_updated: 2026-06-29
---

## What It Is
A tool for running large language models locally. Pull and run open-weight models (Llama, Gemma, Mistral, DeepSeek, Qwen, and others) on your own machine via a simple CLI and local REST API. No cloud required.

## Traction Signals
- Forked by wiki owner for active exploration — [[github-hornof-profile]]
- Supports a wide range of current models: Kimi-K2.5, GLM-5, MiniMax, DeepSeek, gpt-oss, Qwen, Gemma [from repo description]
- **2026-06-13: STRUCTURALLY MAJOR canonical-Greg-Isenberg canonical-#1-runtime-recommendation** ([[gregisenberg-fable-5-ban-local-models-pivot-2026-06-13]]) — canonical-Ollama (or LM Studio) cited as canonical-step-1 in canonical-local-models-pivot canonical-playbook responding to canonical-Fable-5 canonical-export-control; canonical-7B-any-laptop / canonical-32B-Mac-32GB+ / canonical-70B-DGX-Spark canonical-hardware-tiering canonical-anchor; canonical-Ollama-as-canonical-operator-side-substrate canonical-response to canonical-frontier-vendor-restrictions
- **2026-06-23: canonical-Apple-Silicon canonical-competitor canonical-pattern-watch** ([[dailybrief-roundup-2026-06-23]]) — `raullenchai/Rapid-MLX` canonical-Apple-Silicon-local-LLM-inference canonical-engine (AI Score 10/10) emerges as canonical-canonical-Ollama canonical-Apple-Silicon-specialized canonical-counter-substrate canonical-pattern

## How to Use It
Install, run `ollama pull <model>`, then `ollama run <model>`. Also exposes a local REST API compatible with OpenAI's API format, making it easy to swap into existing code.

## Key Concepts
- **Modelfile**: defines how a model is configured, similar to a Dockerfile
- **Local API**: REST endpoint at localhost:11434, OpenAI-compatible
- **Quantization**: models are served in quantized form to fit consumer hardware

## Compared To
- LM Studio: similar local model runner with a GUI; Ollama is more CLI/API-native
- Hosted APIs (OpenAI, Anthropic): cloud-based; Ollama keeps everything local — useful for privacy, offline use, or cost control

## Resources
- [[github-hornof-profile]] — forked by wiki owner; signals active interest
