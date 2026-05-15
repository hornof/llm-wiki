---
name: Vladimir Klimontovich
type: person
affiliation: Jitsu (CEO / founder; YC S20)
signal_sources: [blog, twitter, linkedin]
last_updated: 2026-05-14
---

## Who They Are

Vladimir Klimontovich is a tech founder and product engineer. CEO and founder of [Jitsu](https://jitsu.com/) (YC S20) — an open-source customer-data platform that pulls or streams event data into data warehouses (ClickHouse / Snowflake / BigQuery). Prior: co-founder and CTO/COO of GetIntent (2013-2018; an RTB advertising platform; acquired in 2019). Russian-language audience via the Telegram channel `@termsheet` where he writes about startups and tech.

Surfaced on this wiki via his 2025-01-07 personal essay [[klmn-claude-code-taxes-2026-01-07|"Claude Code Did My Taxes"]] — one of the cleanest practitioner narratives of using [[claude-code]] for a non-coding, high-stakes personal workflow.

## Their Current Focus

- Building Jitsu — open-source customer data platform; integrations with ClickHouse and other warehouses.
- Practitioner-level application of agentic AI tooling ([[claude-code]]) to non-coding workflows where the underlying task is document-heavy and structured.

## Notable Takes

- **Claude Code as personal-CPA substitute (2025-01-07)**: prepared a complex multi-jurisdiction US joint tax return (Federal + NYS + NYC, two Schedule Cs, SEP IRA / 401k / HSA optimization, foreign accounts) entirely via Claude Code with a single `task.md` prompt and persistent `answers.md` / `result.json` state files. **2 hours / 5 clean-slate runs / few-dozen dollars of tokens vs. $1,300-2,000 CPA fees** for a return of equivalent complexity. Codifies an ad-hoc version of the [[anthropic-claude-cookbook-2026-05|sub-agent + persistence + tool-search]] pattern *before* Anthropic formalized it as cookbook primitives — [[klmn-claude-code-taxes-2026-01-07]]
- **"Last mile is always the hardest"**: PDF-form generation from a clean `result.json` is where the workflow breaks; no IRS API, no clean Claude-to-TurboTax import. Honest framing — most personal-AI-workflow gaps are regulatory/integration gaps, not model-capability gaps.
- **Don't take strategic advice without pressure**: Claude Code's first-pass tax-optimization advice recommended an LLC→S-Corp conversion without accounting for SEP IRA contribution-limit interactions. Klimontovich's heuristic: *"I would not yet follow any strategic advice blindly — ask questions and pressure for details."*
- **Preconditions matter**: explicitly notes the workflow assumes (a) prior-year tax return as foundation, (b) domain knowledge — knew what to optimize before asking, (c) clean financial hygiene — never mixed business / personal accounts. Useful as a counterweight to "AI replaces CPAs" narratives that elide the precondition stack.

## Where to Follow

- Personal site: [klmn.sh](https://klmn.sh/)
- Twitter/X: [@vl_klmn](https://twitter.com/vl_klmn)
- LinkedIn: [klimontovich](https://www.linkedin.com/in/klimontovich/)
- Telegram (Russian-language): `@termsheet`
- Email: `v@klmn.io`

## Cross-references

- [[klmn-claude-code-taxes-2026-01-07]] — sole wiki source page for Klimontovich.
- [[claude-code]] — host harness for the tax-prep workflow.
- [[claude-md-pattern]] — `task.md` is a domain-specific specialization of the behavioral-contract pattern.
