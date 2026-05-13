---
name: Interaction Models
type: concept
maturity: emerging
last_updated: 2026-05-13
---

## Definition

An **interaction model** is a model trained to handle interaction *natively* — continuous multimodal input (audio, video, text) and continuous output, on **time-aligned micro-turns** rather than discrete prompt/response cycles. The model itself decides when to listen and when to act, removing the external scaffolding (turn detection, voice-activity detection, perception/action sequencing) that current chat-style LLMs depend on. Coined by [[thinking-machines-lab]] in their May 11 2026 blog post [[thinking-machines-interaction-models-2026-05-11]].

## Why It Matters

Most production AI systems today wrap an LLM with non-trivial **glue infrastructure**: voice-activity detection (VAD), turn-taking heuristics, context-window management, perception-then-action pipelines. The interaction-model thesis is that these wrappers are accidents of the chat-completion API surface, not requirements of the task — and that a *single* model trained on the right objective can absorb them. If this holds at frontier scale:

- Real-time voice / video agents stop being **pipeline** architectures and become **single-model control loops**.
- "Prompt engineering" is no longer the right abstraction for interactive use cases — the equivalent skill becomes **interaction design**: shaping the input stream and the model's expected behaviors over time.
- The competitive surface for non-coding agents (Claude Cowork, ChatGPT consumer surface, voice products) shifts from how well the harness orchestrates the model to how well the model orchestrates *itself*.

## Current State

- **First named model**: **TML-Interaction-Small** — 276B-parameter Mixture-of-Experts, **12B active**, from [[thinking-machines-lab]]. Limited research preview as of May 11 2026; wider release later in 2026. Beats GPT-realtime-2.0 and Gemini-3.1-flash-live on Thinking Machines' own interaction benchmarks (FD-bench v1.5, Audio MultiChallenge APR). All benchmarks introduced are first-party — third-party replication pending.
- **Claimed VAD-elimination**: Latent Space AINews recap (May 13) calls out **SOTA real-time voice without external voice-activity detection** as the headline architectural claim. Verify against the primary blog before treating this as settled.
- **Adjacent frontier work**:
  - [[openai-realtime-voice-api-2026-05-08]] — OpenAI's single-pass voice models with reasoning + translation built in. Same week, similar direction, different framing (API surface rather than architectural-category claim).
  - [[karpathy-html-output-taxonomy-2026-05-08]] — Karpathy's "audio in, video out" framing for the human-AI bandwidth direction. Conceptual companion.
  - [[model-rendered-ui]] — the visual-output extreme of the same substrate-collapse trend.
- **Open questions**:
  - Do the first-party benchmarks survive third-party replication?
  - Is the VAD-elimination claim genuine, or is it absorbed into the model in a way that re-emerges as a different scaffold (e.g., a soft turn classifier in the model's attention pattern)?
  - Does this composition style scale to 4D agent use cases (computer use, robotics) or stay locked to the audio + video + text envelope of TML-Interaction-Small?

## Key Papers / Posts

- [[thinking-machines-interaction-models-2026-05-11]] — primary blog post; TML-Interaction-Small release
- [[openai-realtime-voice-api-2026-05-08]] — same-week OpenAI counterpart
- [[karpathy-html-output-taxonomy-2026-05-08]] — Karpathy's bandwidth-asymmetry framing

## Related Concepts

- [[model-rendered-ui]] — visual side of the substrate-collapse direction
- [[software-3-0]] — Karpathy's framing of natural language as the programming paradigm; interaction models extend this to continuous multimodal I/O
- [[end-of-finetuning]] — same direction (capability absorbed into base model, scaffolding shrinks)
- [[ai-energy-efficiency]] — single-model loops avoid pipeline-stage data movement; relevant to Joules-per-token
