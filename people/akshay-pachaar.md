---
name: Akshay Pachaar
type: person
affiliation: Independent (AI/ML educator)
signal_sources: [twitter]
last_updated: 2026-09-20
---

## Who They Are

- **Explains Jev — and corrects its vendor's central claim (2026-09-18)** ([[jev-typesafe-system-one-model-2026-09-18]]): his explainer of [[jev|TypeSafe's Jev]] is the wiki's only independent voice on it, and the valuable part is that he refuses the marketing. TypeSafe says the model *cannot hallucinate*; Pachaar: *"Jev cannot return an option outside the schema… But it can confidently choose the wrong valid option. Type safety prevents invalid shapes. It does not guarantee correct judgment."* His replacement wording — *"Jev cannot break the declared output schema, but it can still be wrong"* — is what the wiki now carries. Also supplies the framing for the whole category: *"language generation is the wrong interface when code already knows the possible answers."*

@akshay_pachaar on X. Independent AI/ML educator and explainer-thread author. Posts on LLMs, AI agents, and machine learning patterns. Functions as a synthesizer who takes Anthropic / Cloudflare / OpenAI primary publications and distills them into reference-grade practitioner threads with concrete numbers.

## Their Current Focus

- **2026-07-25 — "Graph Engineering Clearly Explained"** ([[akshay-pachaar-graph-engineering-explainer-2026-07-25]]): the wiki's anchor synthesis for [[graph-engineering]] — separates the substance (3 primitives, 4 hard problems, decision rule) from the meme after [[peter-steinberger|Steinberger]]'s question + [[hamel-husain|Hamel Husain]]'s article. Also posted the compact *"prompt → context → harness → loop → graph engineering"* layering ladder (*"each layer wraps the one before"*). Continues his role as the field's reference-grade distiller.

Agent runtimes, tool-calling patterns, MCP. May 2026 work focused on the [[code-mode]] pattern reframing of the year-long MCP-vs-CLI debate.

## "LLM Routing Can Cost More Than Not Routing" (2026-09-06)

[[pachaar-llm-routing-can-cost-more-2026-09-06]] — a deep-dive arguing the routing pattern breaks in production, with the **prefix-cache** mechanism as the core finding: switching models mid-agent-loop destroys a cache worth **45–80% of input-token cost.** Folded to [[ai-margin-collapse]], [[loop-engineering]], [[kv-cache-optimization]] and [[jev]].

**Two notes on him as a source, both of which this page should carry.**

**He is the wiki's most useful technical explainer and he writes sponsored content.** This piece is paid placement for DigitalOcean's Inference Router, and the structure shows it — four failure modes, each answered by the sponsor's product. **The numbers divide cleanly and the wiki should keep splitting them that way**: RouteLLM (ICLR 2025) and the Uber figures are externally checkable; the Arch-Router and Plano benchmarks are the sponsor's own, on the sponsor's own models. **Mechanism sound, product claims marketing.**

**He is also, separately, the source the wiki over-trusted once.** The 2026-09-27 CMU-on-Jev fold came from his thread and **overstated the paper's finding** — his rendering had confidence failing to expose errors where the abstract says the gap is *concentrated in low-confidence decisions* ([[jev-as-a-judge-arxiv-2609-26550]]). **That was a secondhand-fold failure rather than an error of his**, but it is the reason to fetch primaries behind his summaries. **Here he cites RouteLLM and an arXiv survey without links.**

**Worth crediting:** he is also the source of the sharpest correction on the Jev record — *"Jev cannot break the declared output schema, but it can still be wrong"* — and this piece argues against a pattern he has elsewhere promoted. **He pushes back on his own material, which is rarer than it should be.**

## Notable Takes

- **"MCP vs CLI was the wrong debate"** (May 2026): both sides survived but stopped being the runtime — they became the primitives the runtime composes. The actual story is [[code-mode]]. Concrete token-cost data: Playwright MCP = 13.7K, Chrome DevTools MCP = 18K, 5-server setup = 55K *before any work*, full schema-piping workflows hit 150K. The fix is for the model to write code that calls tools through a runtime — *"tool definitions belong in code, not in context."* — [[akshay-pachaar-mcp-vs-cli-2026-05-09]]
- **300M MCP SDK downloads, up from 100M at the start of 2026** (May 2026) — surfaced the Anthropic-stated traction number to argue MCP is not dying despite the Code-Mode reframe; it's the primitive Code Mode composes. — [[akshay-pachaar-mcp-vs-cli-2026-05-09]]

## Where to Follow

- X: @akshay_pachaar
