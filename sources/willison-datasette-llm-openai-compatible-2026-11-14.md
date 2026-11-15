---
title: "datasette-llm 0.1a11"
type: source
medium: article
url: https://simonwillison.net/2026/Nov/14/datasette-llm/
ingested: 2026-11-15
---

## Summary

A short release note from [[simon-willison|Simon Willison]] (2026-11-14). datasette-llm, the plugin other Datasette plugins use to reach an LLM, now accepts any OpenAI-compatible endpoint. That means a local model served by LM Studio, [[ollama|Ollama]] or llama.cpp can power a Datasette Agent instance.

## Key Claims / Takeaways

- **The change:** *"This release adds support for OpenAI-compatible endpoints, so you can configure Datasette to use an LLM hosted anywhere that talks the OpenAI pseudo-standard web protocol."*
- **Local models:** *"if you're running local models with LM Studio or Ollama or llama.cpp (which just hit v1.0.0 ) you can run Datasette via uvx"*. His example points at `qwen/qwen3.8-27b` on `localhost:1234`.
- **For the owner:** one `uvx` command gives an agent over a SQLite database running entirely on a laptop model. A cheap way to try a local data agent. [Judgment.]

## Pages Updated

- [[simon-willison]] — Their Current Focus
