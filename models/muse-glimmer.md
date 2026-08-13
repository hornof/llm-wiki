---
name: Muse Glimmer
type: model
provider: Meta
status: available
last_updated: 2026-08-12
---

## What It Is

**Muse Glimmer** is [[meta|Meta]]'s **30B-parameter, Apache-2.0 open-weights** model aimed at **agentic task completion**, announced 2026-08-10 (surfaced via [[simon-willison|Willison]], [[dailybrief-roundup-2026-08-12]]). It marks Meta **re-entering the open-weights race** with a *"meaningful licensing shift"* — **Apache-2.0** (permissive, commercial-friendly) rather than the more restrictive Llama community license Meta shipped under previously.

## Strengths & Weaknesses

- **Positioning**: 30B / agentic-task-completion / Apache-2.0 — a **local-inference-friendly** size class (runs on modest hardware) squarely in the practitioner *"which open model do I run locally?"* decision, alongside [[glm-5-2|GLM-5.2]], [[kimi-k3|Kimi K3]], DeepSeek-V4-Flash, and Gemma 4.
- **The license is the headline**: Apache-2.0 removes the acceptable-use / scale-gate friction of the Llama license — a signal Meta is competing on *openness terms*, not just weights, amid the [[frontier-ai-governance|open-weights governance]] fight it's a coalition signatory in.
- *(Benchmarks / agentic-eval numbers not captured in the surfacing brief — capability claims not yet independently assessed.)*

## When to Use It

- Candidate for **local / on-prem agentic** workloads where a permissive license matters (the [[reverse-information-paradox|own-your-stack]] / [[greg-isenberg|local-models-as-insurance]] case) and a 30B footprint fits the hardware budget.

## Community Sentiment

Framed by the [[dailybrief-roundup-2026-08-12|08-12 brief]] as Meta's **re-entry to open-weights** with a licensing shift that matters more than the raw capability — landing the same week [[glm-5-2|GLM-5.2]]'s frontier-parity-without-safety-mitigations and the [[frontier-ai-governance|Hinton/Li/Ng "stay open" advocacy]] kept open-weights center-stage.

## Resources
- [[frontier-ai-governance]] — the open-weights debate Muse Glimmer's Apache-2.0 licensing plays into
- [[meta]] — provider; [[ai-margin-collapse]] — the open-weight-parity thread this extends
