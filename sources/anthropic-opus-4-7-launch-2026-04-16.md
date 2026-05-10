---
title: "Introducing Claude Opus 4.7"
type: source
medium: article
url: https://www.anthropic.com/news/claude-opus-4-7
ingested: 2026-05-10
---

## Summary

Anthropic's official launch announcement for **Claude Opus 4.7**. Headline: GA on **April 16, 2026** as a successor to Opus 4.6 with **same pricing** ($5 input / $25 output per million tokens) but materially better performance on coding, document reasoning, and long-running task execution. Ships with several developer-facing primitives that move Claude Code further toward an autonomous agentic surface: a new `xhigh` reasoning effort level, public-beta **task budgets**, and the **`/ultrareview`** slash command for code review. Available immediately via Claude API, Amazon Bedrock, Google Cloud Vertex AI, and Microsoft Foundry under model identifier `claude-opus-4-7`.

The launch is what's behind the "current Opus generation" framing this wiki has been using since May 6 — but the actual GA was **April 16, three weeks earlier than this wiki initially recorded** (existing model page incorrectly cited Code w/ Claude 2026 on May 6 as the announcement date). Code w/ Claude 2026 was the *event surface* for the broader Anthropic May launch cluster; the Opus 4.7 model itself was already GA.

## Key Claims / Takeaways

### Identity and access
- **GA date**: April 16, 2026
- **Model identifier**: `claude-opus-4-7`
- **Distribution**: Claude API, Amazon Bedrock, Google Cloud Vertex AI, Microsoft Foundry
- **Pricing**: **$5 / million input tokens, $25 / million output tokens — unchanged from Opus 4.6**

### Headline capability deltas vs. Opus 4.6
- **3× more production tasks completed** on Rakuten-SWE-Bench
- **70% vs. Opus 4.6's 58%** on CursorBench
- **+13%** on a 93-task internal coding benchmark
- **21% fewer errors** on document reasoning tasks
- "Particular gains on the most difficult [SWE] tasks"
- **Vision improvements**: long-edge support up to **2,576 pixels** (~3.75 megapixels) — substantially larger than prior generations
- Better instruction following and multimodal understanding
- Improved consistency on long-running tasks (the failure mode [[anthropic-teaching-claude-why-2026-05-08]] and [[laban-llms-corrupt-documents-2026-05]] both target from different angles)

### New developer-facing primitives
- **`xhigh` effort level** — a new reasoning intensity tier above existing levels, giving developers finer-grained latency / quality control. (Names suggest the prior `low` / `medium` / `high` ladder is being extended.)
- **Task budgets in public beta** — first-class per-task token budget enforcement at the model layer. This is *exactly* the discipline that Rule 6 of [[mnilax-claude-md-12-rules-2026-05-09]] tries to enforce via CLAUDE.md (per-task 4K, per-session 30K) — i.e., a community-evolved CLAUDE.md rule is being absorbed into the model's native runtime.
- **`/ultrareview` slash command** — explicit code-review primitive, native to Claude Code (and orthogonal to the **Code Review** subsystem announced at Code w/ Claude 2026 — those operate at different scopes; relationship not yet captured).

### Connection to other May 2026 surfaces
- **[[claude-design]]** — visual design capability shipping native to Opus 4.7 (per existing wiki page; this announcement post does not foreground it but the broader May product cluster does).
- **[[claude-mythos]]** — the preview line announced at Code w/ Claude 2026 sits *alongside* Opus 4.7, not as a successor; positioning between the two not yet clarified by Anthropic publicly.

## Pages Updated

- [[claude-opus-4-7]] (updated — corrected GA date to 2026-04-16; added Rakuten-SWE-Bench / CursorBench / document-reasoning benchmark deltas; added pricing, model identifier, distribution; added `xhigh`, task budgets, `/ultrareview`)
- [[anthropic]] (updated — Opus 4.7 GA date corrected; product list now distinguishes April 16 GA from Code w/ Claude 2026 May 6 product-cluster surface)
- [[claude-code]] (updated indirectly — `/ultrareview` and task budgets become first-class Claude Code primitives; Code Review feature now has a sibling at the model level)

## Caveats

- All benchmark numbers are Anthropic-published. Independent benchmark validation by third parties is not yet captured in this wiki.
- "Rakuten-SWE-Bench" and "CursorBench" appear in the post; their methodologies and provenance (e.g., whether Rakuten-SWE-Bench is the standard SWE-Bench applied to Rakuten codebases or a Rakuten-specific variant) are not detailed here. Verify before quoting.
- The `xhigh` effort level is announced but its exact latency / token-cost / quality envelope vs. existing `high` is not detailed in the post (or in this ingest's WebFetch summary). Track for follow-up signal.
- The brief that surfaced this for re-ingestion ([[Daily Briefs/2026-05-10-personal.md]]) characterized the announcement as "standard capability claims without benchmarks or technical substance." That framing is contradicted by the actual blog content, which contains specific benchmark deltas. Likely the brief author skimmed the announcement; the underlying source has more substance than the brief's summary suggests.
