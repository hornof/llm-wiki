---
title: "OpenTeams / Nebari — 'The Distributed AI Economy: Intelligence Hubs, Frames, Cogs, and Ops' (whitepaper)"
type: source
medium: paper
url: https://nebari.dev
ingested: 2026-07-27
---

## Summary

A 32-page vendor whitepaper (June 2026, marked **CONFIDENTIAL / Revision 6**; `_raw/distributed-economy-white-paper.pdf`) from **OpenTeams**, the company behind the open-source **[[openteams|Nebari]]** AI-infrastructure stack, led by **[[travis-oliphant|Travis Oliphant]]** (creator of NumPy/SciPy, co-founder of Anaconda). It argues enterprises must **own** their AI ("sovereign, reproducible, auditable deployments") rather than **rent** it through black-box APIs, and proposes a three-layer architecture + marketplace to make that ownable. A near-direct architectural instantiation of the [[reverse-information-paradox]]. *(Primary fetched — full text; vendor vision doc, roadmap Phase 1 = "now–6 months," i.e. early/pre-scale — treat claims as positioning.)*

## Key Claims / Takeaways

- **The problem — "rented intelligence is fragile, and context leaks away"**: dependence on black-box vendor systems (Codex, Claude Code/Cowork, Grok, Gemini) means no inspection/reproduction/audit/ownership, and the **organizational context that fuels AI ROI dissipates** into vendor-side logs. Cites [[satya-nadella|Nadella]] (Davos 2026: *"if you're not able to embed the tacit knowledge of the firm in a set of weights in a model that you control… you have no sovereignty"*) and Robert F. Smith (Vista).
- **The three-layer architecture**:
  - **Layer 1 — Infrastructure**: **[[openteams|Nebari]]** (open-source modular AI stack, `nebari.dev`; 15+ composable packs) + **Nebi** (packaging/reproducibility layer — *"pip/npm for AI"*) + the **Intelligence Hub** (the org's sovereign deployment inside its own perimeter).
  - **Layer 2 — Execution**: **Frames** (scoped, inheritable, composable, shareable, discoverable artifacts carrying org context — rules/terminology/goals/style/norms/skills/prompts; *"a Frame is not a prompt; it is an organizational artifact governed by the org that owns it"*), **Cogs** (governed AI workers oriented by Frames — the auditable unit), **Ops** (installable, versioned, supervised workflows combining Cogs+Frames with human-in-the-loop checkpoints — *"close the books," "onboard this customer"*).
  - **Layer 3 — Economy**: a marketplace where Frames/Cogs/Ops are published, discovered, installed, and exchanged across Hubs (*"the work, the workers, and the context that orients them"*); most Frames shared free, some commercial.
- **Progression of value**: Models predict tokens → Frames orient → Cogs generate (Frame-oriented) → Ops deliver outcomes with human oversight.
- **"Intelligent Ops Factory"** — positioned as adjacent-but-more-fundamental than **[[chamath-decision-context-agents|8090's "Software Factory"]]**: where a software factory produces software, the Ops Factory produces *"operational intelligence the organization owns."*
- **Organizational Memory** = the Hub's persistent context substrate (a continuum from versioned Frame directories to full conversational records + semantic retrieval + knowledge graphs); names [[mem0]], Letta, Zep, Neo4j, pgvector as implementation options. *"Organizational Memory belongs to the organization that produced it. It cannot be rented or bought from a vendor."*
- **Positioning**: *"the Linux + App Store for enterprise AI."* Moat = open-source trust (Nebari/Nebi) × portable org context (Frames) × marketplace network effects. Same playbook Oliphant ran before: *"NumPy standardized arrays, Anaconda distributed the Python data science stack, Nebari is standardizing AI infrastructure."*
- **Market framing** (heavily cited): McKinsey sovereign-AI $500–600B by 2030; PwC — 56% of CEOs report zero AI financial impact, only 12% get both cost+revenue benefit; Deloitte — only 1% self-describe AI-mature, only 1-in-5 has mature agent governance; Brookings — *"full-stack AI sovereignty is structurally infeasible… the market for trusted intermediaries is permanent."*

## Why it matters

- **Architectural build-out of the [[reverse-information-paradox]]**: the Intelligence Hub's hard trust boundary + org-owned Organizational Memory is exactly Nadella's "own your learning loop" prescription, productized. **Frames** operationalize the [[claude-md-pattern|CLAUDE.md]]/[[context-engineering|context]] layer as a *governed, inheritable, exchangeable org asset* rather than a per-project file.
- **New named entity with real open-source pedigree** (Oliphant/Nebari) staking the "sovereign / owned intelligence" ground alongside [[chamath-decision-context-agents|8090]] and [[ai-native-organizations|AI-native-org]] rebuilds.

## Pages Updated
- [[openteams]] (new), [[travis-oliphant]] (new), [[reverse-information-paradox]], [[ai-native-organizations]]
