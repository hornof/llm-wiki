---
title: Interaction Models — A Scalable Approach to Human-AI Collaboration
type: source
medium: article
url: https://thinkingmachines.ai/blog/interaction-models/
ingested: 2026-05-13
---

## Summary

[[thinking-machines-lab]] primary blog post (May 11, 2026) introducing **interaction models** as a category and **TML-Interaction-Small** as a 276B-parameter Mixture-of-Experts research model (12B active parameters) trained to handle real-time multimodal interaction *natively*, replacing the turn-by-turn prompt/response loop common to today's chat-style LLMs. Released as a "limited research preview" with wider release planned later in 2026. Beats GPT-realtime-2.0 and Gemini-3.1-flash-live on interaction-quality benchmarks the team publishes alongside the model.

## Key Claims / Takeaways

- **Definition**: an interaction model is one that "handle[s] interaction natively rather than through external scaffolding" — it "continuously take[s] in audio, video, and text, and think[s], respond[s], and act[s] in real time."
- **Architectural shift**: from sequential turn-by-turn exchanges to **time-aligned micro-turns** — humans and AI exchange simultaneously across modalities, rather than the AI freezing perception while it generates a reply.
- **Stated problem with current chat paradigm**: "humans increasingly get pushed out not because the work doesn't need them, but because the interface has no room for them." Interaction is treated as a wrapper, not a primitive.
- **Model**: **TML-Interaction-Small** — 276B-parameter MoE, **12B active parameters**.
- **Modalities**: audio, video, and text — concurrent input and output streams.
- **Benchmarks** (Thinking Machines' own):
  - **FD-bench v1.5** (interaction quality): TML-Interaction-Small scores **77.8**
  - **Audio MultiChallenge APR**: **43.4%** (competitive with larger models)
  - Outperforms **GPT-realtime-2.0** and **Gemini-3.1-flash-live** on the team's interaction metrics
  - New benchmarks introduced: **TimeSpeak, CueSpeak, RepCount-A, ProactiveVideoQA, Charades** — these are first-party benchmarks; treat as such until third-party replication appears.
- **VAD claim** (per Latent Space AINews recap, May 13): TML-Interaction-Small claims SOTA real-time voice **without external voice-activity detection** — i.e., the model itself decides when to listen and when to respond. Latent Space framing is thin; verify against primary blog for production claims.
- **Access**: "Limited research preview to collect feedback, with a wider release later this year."
- **Author attribution**: published under "Thinking Machines Lab" — no individual researchers named in the post.

## Why This Matters for the Wiki

First Thinking Machines product release the wiki has captured (prior coverage was funding / talent density / "resume raises" framing only). Establishes [[thinking-machines-lab]] as a *research-output* entity, not just a balance sheet. Conceptually relevant to the wiki's existing tracking of:

- [[model-rendered-ui]] — UI rendered from a model's continuous output stream
- [[karpathy-html-output-taxonomy-2026-05-08]] — Karpathy's "audio in, video out" framing
- [[openai-realtime-voice-api-2026-05-08]] — OpenAI's single-pass voice API (released same week)
- [[claude-cowork]] — Anthropic's autonomous-execution surface (text and screen, not natively continuous-multimodal)

The "no external VAD" claim, if it holds up, removes one of the canonical glue layers in real-time voice agent stacks and would push the architectural frontier toward **single-model multimodal control loops** instead of perception-act-speak pipelines. New concept page: [[interaction-models]].

## Pages Updated

- [[thinking-machines-lab]] — TML-Interaction-Small product added; "research-output" status update
- [[interaction-models]] — new concept page
- [[index]] — new tool/concept entries
