---
name: Claude Opus 4.8
type: model
provider: Anthropic
status: available
last_updated: 2026-05-28
---

## What It Is

Claude Opus 4.8 is the May 28 2026 Opus refresh from [[anthropic|Anthropic]] — launched alongside the [[anthropic-series-h-65b-965b-2026-05-28|Series H $65B/$965B raise]] as a same-day capability-and-capital double-event. **Succeeds [[claude-opus-4-7|Opus 4.7]] as the recommended model for [[claude-code|Claude Code]]** ([[claude-opus-4-8-dynamic-workflows-2026-05-28|launch source]]). Anthropic claims **69.2% on SWE-bench Pro**, outperforming GPT-5.5 and Gemini 3.1 Pro on senior-level engineering and writing tasks. Same pricing as Opus 4.7 per Digg framing — *"improve model honesty and flag programming errors at the same price."* Bundled with **Dynamic Workflows** preview for parallel subagents — a new orchestration primitive for multi-agent code migration at scale.

Sits alongside [[claude-mythos]] (Anthropic's preview line); positioning between Opus and Mythos still not publicly clarified.

## Strengths & Weaknesses

### Anthropic-published benchmark claims

- **69.2% on SWE-bench Pro** — outperforms GPT-5.5 and Gemini 3.1 Pro
- *"Improved model honesty"* (Anthropic framing) — consistent with the [[anthropic-teaching-claude-why-2026-05-08|Teaching Claude Why]] reasoning-based alignment direction
- *"Flag programming errors"* — error-detection capability framed as differentiation axis

### Caveats

- All benchmark numbers Anthropic-published; independent verification (LMSYS, third-party SWE-bench Pro replications) not yet captured.
- **SWE-bench Pro methodology not surfaced**: whether Anthropic ran the standard SWE-bench Pro harness or a vendor-specific variant should be verified before quoting externally.
- **Context window not anchored**: Opus 4.7 was 200K default + 1M Max-tier; Opus 4.8 launch did not surface context-window changes per the brief.
- **Bedrock / Vertex availability**: not surfaced in launch brief.

## When to Use It

- **Drop-in upgrade for Opus 4.7 Claude Code workloads** — same pricing, becomes the recommended default. No migration cost to test.
- **Senior-level SWE tasks** where the SWE-bench Pro headline matters: this is the new frontier reference point for coding-agent capability.
- **Multi-agent code migration at scale** via the new **Dynamic Workflows** parallel-subagents preview.
- **Honesty/error-flagging-sensitive workflows**: error-detection is the Anthropic-named differentiation axis. Worth testing on rework-cost-sensitive surfaces (cf. [[ai-roi-gap|the rework portion of the token-spend funnel]]).

## Dynamic Workflows (preview)

New orchestration primitive at launch:

- **Parallel subagents** — multiple agents executing in parallel
- **Self-verifying workflow patterns** — reduces review friction for the operator
- **Named use case: multi-agent code migration at scale**
- **Pairs with [[code-mode]]**: code-mode names the runtime primitive (agent writes code that calls tools through a runtime); Dynamic Workflows is the orchestration layer above
- **Verification-pending**: parallelism model (process / agent / step); whether self-verification uses model-as-judge or independent verifier; pricing of parallel sub-agent invocations

## Community Sentiment

- **2026-05-28 launch**; same-day as Anthropic's [[anthropic-series-h-65b-965b-2026-05-28|Series H]]. Pairing the capability rotation with the capital event amplifies both.
- **First wiki-captured named-practitioner Codex→Opus migration claim at launch surface**: *"Creator Dan Shipper used the model to transition off Codex."* (Digg, May 28). Shipper has commercial incentives with Anthropic; treat as marketing-coordinated rather than independent practitioner-validation. Track for *unsolicited* Codex→Opus migration content over the next 30 days.

## Resources

- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — launch source page (multiple Digg confirmations)
- [[anthropic-series-h-65b-965b-2026-05-28]] — same-day capital event
- [[anthropic-claude-space-to-think-2026-05-28]] — same-week strategic positioning
- [[claude-opus-4-7]] — predecessor; succession noted
- [[claude-code]] — recommended model for this surface
- [[code-mode]] — runtime primitive the Dynamic Workflows orchestration sits above
