---
title: Anthropic announces agents for financial services
type: source
medium: article
url: https://www.anthropic.com/news/finance-agents
ingested: 2026-05-14
---

## Summary

Anthropic primary, announced 2026-05-05: ten named pre-built agents for financial services, available as plugins on all paid Claude plans and as [[anthropic-claude-cookbook-2026-05|Managed Agents]] through Claude Platform (public beta). Built on [[models/claude-opus-4-7|Claude Opus 4.7]], which Anthropic claims is state-of-the-art on financial tasks (64.37% on Vals AI Finance Agent benchmark). Launch partners span investment banking, hedge funds, custody, insurance, and ratings — Citadel, FIS, BNY, Carlyle, Mizuho, Travelers, Walleye Capital, Hg, Dun & Bradstreet, Morningstar. Brief-author flagged this as the named "fintech vertical on your want list" — directly relevant to VPE-role evaluation in regulated B2B AI.

## Key Claims / Takeaways

- **The ten agents:** Pitch builder, Meeting preparer, Earnings reviewer, Model builder, Market researcher, Valuation reviewer, General ledger reconciler, Month-end closer, Statement auditor, KYC screener. Note the split: six on the research/coverage side (pitches, comps, briefs, sector tracking), four on the finance/ops side (reconciliation, close, audit, compliance).
- **Model:** Claude Opus 4.7, "state-of-the-art on financial tasks" per Anthropic; 64.37% on Vals AI Finance Agent benchmark (Anthropic citation).
- **Integrations (data + workflow surface):** FactSet, S&P Capital IQ, MSCI, PitchBook, Morningstar, Chronograph, LSEG, Daloopa, Financial Modeling Prep, Fiscal AI, Guidepoint, IBISWorld, SS&C Intralinks, Third Bridge, Verisk, and Moody's (the last as an MCP app — first public Anthropic-Moody's MCP integration).
- **Launch customer quotes:**
  - **Citadel** (Atte Lahtiranta): "Claude for Excel meets them there … with a step-change in efficiency."
  - **FIS** (Stephanie Ferris): "compresses AML investigations from days to minutes."
  - **Walleye Capital** (Will England): "100% of employees … use Claude Code."
  - **Morningstar** (Adam Wheat): "Users aren't just getting faster answers. They're getting better ones."
- **Distribution surfaces:** plugins on every paid Claude tier (low-friction); Managed Agents via [[companies/anthropic|Claude Platform]] public beta (enterprise managed-runtime); Claude for Excel/PowerPoint/Word add-ins now generally available (Office-suite-of-record bet).
- **What's structurally new:** named pre-built agents shipped by the model lab, not by an ISV — Anthropic is moving up the stack into vertical SaaS positioning while keeping the underlying model lab independent. Parallel to OpenAI's GPT Store but priced and packaged for regulated enterprise from launch.

## Why It Matters

- **Fintech VPE relevance:** the named launch partners (Citadel, BNY, Carlyle, Mizuho, FIS, Walleye, Hg) span sell-side, buy-side, custody, alt-asset GPs, and core banking infrastructure. Any AI-applied fintech role evaluation needs to know what Anthropic ships natively — these ten agents define the build-vs-buy boundary for the next 12 months.
- **Walleye "100% of employees use Claude Code"** is the cleanest practitioner traction signal in the announcement; quote-able for VPE evaluation conversations.
- **Moody's via MCP** is the first public Anthropic-Moody's MCP integration — worth watching as a template for ratings-data integration in regulated workflows. Cross-references [[concepts/mcp]].
- **Companion to the broader May repositioning:** combined with [[anthropic-gates-foundation-200m-2026-05-14]] (institutional/philanthropic) and [[techcrunch-anthropic-ramp-business-customers-2026-05-13]] (Ramp #1), Anthropic now has commercial-vertical, infra-compute, and institutional-distribution all moving on the same week. Not three independent news items.

## Cross-references

- [[anthropic-gates-foundation-200m-2026-05-14]] — same-week institutional Anthropic move.
- [[techcrunch-anthropic-ramp-business-customers-2026-05-13]] — Ramp #1 context (Anthropic 34.4% vs OpenAI 32.3%).
- [[anthropic-claude-cookbook-2026-05]] — Managed Agents named primitive context.
- [[tools/claude-code]] — Walleye "100% of employees use Claude Code" traction quote.

## Pages Updated

- [[companies/anthropic]] (updated — May 5 finance agents added under traction signals; ten-agent product surface, Office add-ins GA, Managed Agents public beta)
- [[tools/claude-code]] (updated — Walleye Capital 100%-of-employees adoption quote added under Community Sentiment)
