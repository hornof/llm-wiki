---
title: Claude Code Did My Taxes (Vladimir Klimontovich)
type: source
medium: article
url: https://klmn.sh/essays/claude-code-for-taxes
ingested: 2026-05-14
---

## Summary

[[vladimir-klimontovich]]'s personal-essay walkthrough, published 2025-01-07 on klmn.sh, of using [[claude-code]] to prepare a complex multi-jurisdiction US tax return (Federal + NYS + NYC, joint filing, two Schedule Cs through one LLC, foreign accounts, SEP IRA / 401k / HSA / Child Care Credit optimization). The essay is one of the cleanest publicly-available practitioner narratives of using Claude Code for a **non-coding, high-stakes, document-heavy personal workflow** — exactly the pattern this wiki tracks under the [[llm-wiki-pattern]] / [[claude-md-pattern]] umbrella, but applied to tax prep instead of code or research. Final result: 2 hours of effort across 5 clean-slate runs; **estimated cost ~few-dozen-dollars-of-tokens against $1,300-2,000 CPA fees** for an equivalent return.

## Key Claims / Takeaways

### The workflow pattern (replicable)

- **`task.md`** — single imperative prompt file describing the goal, workflow constraints, and known facts about the filer. Iterated across 5 runs.
- **Sub-agents for data extraction** — large PDFs (W-2s, 1099s, bank statements) parsed in separate agents that emit `<doc>-summary.md` files. Keeps context small.
- **"If it's large, don't read it directly — launch a Python script to extract the data"** — explicit fallback path inside `task.md` for any document above a token-budget threshold. Claude Code spawns the Python script itself.
- **`answers.md` persistence** — answers to clarifying questions saved to a persistent file so subsequent clean-slate runs don't re-ask. Plus a `COMMONSENSE_CLASSIFICATION_RULES.md` for transaction-classification rules.
- **Two-step output** — generate `result.json` first (all numbers), then generate the PDF from JSON. Decouples "did Claude do the math" from "did Claude format the form right."
- **Cold-start avoidance** — prior year's tax return given as input. Claude uses it to understand structure, forms, edge cases (foreign accounts, dual Schedule Cs). Klimontovich is explicit: this is *not* a from-zero workflow.

### The full `task.md` prompt (verbatim structure)

```
# Tax return
You're the Tax Professional, your task is to prepare tax return for me — Federal, NYS, NYC.

# Workflow
Some documents are in the current folder ... if not clear, ask questions
using the tool. Ask as many questions as possible in one session ...

For each document like W-2 — parse it in a separate agent (as it might be
big) and save essential data into `<original-document-name>-summary.md`.
For PDFs, if it's large don't read it directly, launch a Python script
to extract info. If `*-summary.md` already exists, use that instead.

Once file is complete and you know all the numbers, use them to generate
actual PDFs and output them.

If you're not sure, ask questions via tool. But look at `answers.md`
beforehand. Try to ask as many questions as possible in a single session.
Save answers to `answers.md` ... so in the next run session you won't
need to ask again.

# Output
Maintain `result.json` ... keep data needed for printing final tax
return for Fed, NYS and NYC.

# Facts
[role-specific facts: filing status, income types, LLC structure,
SEP IRA targets, home-office calculation method, ECEP in W-2, etc.]

# Calculating business income / expenses
See `COMMONSENSE_CLASSIFICATION_RULES.md` ...

# Estimates
[quarterly estimate payment history]
```

### Effort and cost

- **2 hours total** across **5 clean-slate runs** ("nuke the context, edit artifacts from previous runs like `answers.md`, and improve `task.md`").
- Cost: $200/month Claude MAX subscription; estimated **few dozen dollars** of actual token cost for the tax prep.
- CPA equivalent: **$1,300-2,000+** for a return of comparable complexity. Even amortized over iteration time, the math works *if the prompt is reusable year-over-year*.

### Failure modes Klimontovich names

- **Context filled up too fast** on the first three attempts — fixed by sub-agent extraction and persistent summaries.
- **Last-mile filing gap**: result.json → PDF was hard. Claude Code "sometimes misses fields." No public API for tax forms; can't e-file without CPA-licensed software or TurboTax import.
- **Strategic advice was bad without pressure**: when asked to recommend optimizations, Claude Code initially recommended LLC → S-Corp conversion without accounting for SEP IRA contribution-limit interactions. Klimontovich: *"I would not yet follow any strategic advice blindly — ask questions and pressure for details."*

### Self-described preconditions

- **"It wasn't a cold start"** — Klimontovich gave Claude Code the prior year's return as foundation.
- **Domain knowledge required** — Klimontovich's wife runs a financial-consulting business; he calls himself "a financial nerd." Knew what he wanted to optimize and how before asking.
- **Clean financial hygiene** — never mixed business and personal accounts. This is the precondition that makes the transaction-classification step tractable.

## Why It Matters

- **Concrete proof of [[claude-code]] applied to a non-coding personal workflow.** Most wiki Claude Code practitioner sources are coding/research/skill-builder sources ([[heygurisingh-career-ops]], [[alfiejcarter-linkedin-claude-stack]], [[tomcrawshaw-claude-code-blueprint]], etc.). This is the cleanest *personal-finance / document-prep* case study captured to date.
- **The `task.md` pattern is the [[claude-md-pattern]] in disguise.** Same imperative-prompt-as-behavioral-contract discipline ([[mnilax-claude-md-12-rules-2026-05-09]]). The wiki's CLAUDE.md / SKILL.md ecosystem is the codified version of what Klimontovich wrote ad-hoc.
- **Sub-agent + persistent-state pattern is foundational.** Sub-agents for parsing large PDFs + `answers.md` / `result.json` for cross-run state is the same architecture as [[anthropic-claude-cookbook-2026-05|Anthropic's named cookbook primitives]] (Programmatic Tool Calling, Tool Search with Embeddings, Automatic Context Compaction). This is a practitioner discovering the recipe before the cookbook formalized it.
- **The $1,300-2,000 → few-dozen-dollars cost-collapse on a "personal CPA" workflow** is a data point for the [[naval-ravikant-saas-is-next|SaaS-disruption thesis]] *transferred to professional services*. Tax-prep CPA fees are exactly the kind of high-margin professional-services revenue that gets squeezed when individuals can run their own agentic workflow.
- **Last-mile-is-hardest framing** is honest and useful: the PDF-form-fill step is where the workflow still breaks. Real bottleneck is regulatory/integration, not model capability. Same *"last mile"* pattern in any AI-applied vertical.

## Cross-references

- [[vladimir-klimontovich]] — author (new people page).
- [[tools/claude-code]] — host harness; tax-prep workflow added under Practitioner Patterns.
- [[claude-md-pattern]] — `task.md` is a domain-specific specialization of the behavioral-contract pattern.
- [[anthropic-claude-cookbook-2026-05]] — Klimontovich's sub-agent / persistence pattern is the ad-hoc version of Anthropic's named cookbook primitives.

## Pages Updated

- [[vladimir-klimontovich]] (new — YC S20 founder Jitsu, ex-GetIntent acquired; tax-prep Claude Code essay author)
- [[tools/claude-code]] (updated — non-coding-workflow practitioner pattern added; `task.md` / sub-agents / `answers.md` / two-step output recipe captured)
