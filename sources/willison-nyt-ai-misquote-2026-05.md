---
title: Quoting New York Times Editors' Note
type: source
medium: article
url: https://simonwillison.net/2026/May/10/new-york-times-editors-note/
ingested: 2026-05-11
---

## Summary

[[simon-willison]] short post (May 10 2026) flagging a *New York Times* editor's note. A *Times* reporter used an AI-generated summary of Canadian Conservative leader Pierre Poilievre's views and inserted the summary text as a **direct quotation** — not paraphrased, not labeled as AI-generated. The misattribution was published, then caught after the fact. The editor's note retracts the quote and explains how it happened.

Willison's framing: this is the failure mode where AI summarization output is treated as *source material* rather than as a derived artifact requiring verification.

## Key Claims / Takeaways

- **First-party editorial confirmation that an AI summary leaked into a flagship newsroom's direct-quotation stream**: not a hypothetical risk, not a contractor-tier publication — the *New York Times* shipped this. Surface artifact (a quotation in a newspaper) was indistinguishable from the verified version until someone audited against the original.
- **The failure is a workflow gap, not a model defect**: the reporter mistook a tool's output for human language by Poilievre. The editor's process did not catch it before publication. Both failures stack.
- **Adjacent to [[verifiability-and-jagged-intelligence]]**: this is the journalism-domain manifestation of the same pattern as DELEGATE-52's ~25% document-corruption finding ([[laban-llms-corrupt-documents-2026-05]]) — model output looks correct enough to pass casual review, fails on adversarial-grade fact-checking, and the harm vector is downstream trust in *the publisher*, not in the model.
- **Willison's broader pattern**: he treats individual incidents as falsifiability data for the ongoing convergence story he is tracking (see [[simonwillison-vibe-coding-agentic-engineering-2026-05]] — "as the coding agents get more reliable, I'm not reviewing every line of code anymore"). Same shape: reliability creep → review discipline erosion → high-stakes leak.

## Why This Matters for the Wiki

A clean, citable data point that the verifiability/jaggedness phenomenon is leaking into journalism workflows. Useful as illustration in the [[verifiability-and-jagged-intelligence]] concept page and as an existence proof when discussing AI-output-as-source-material risk in mainstream-news context.

## Pages Updated

- [[simon-willison]] — additional notable take added (NYT failure as workflow-gap framing)
- [[verifiability-and-jagged-intelligence]] — journalism-domain illustration appended
