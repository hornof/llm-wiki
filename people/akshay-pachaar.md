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

## Notable Takes

- **"MCP vs CLI was the wrong debate"** (May 2026): both sides survived but stopped being the runtime — they became the primitives the runtime composes. The actual story is [[code-mode]]. Concrete token-cost data: Playwright MCP = 13.7K, Chrome DevTools MCP = 18K, 5-server setup = 55K *before any work*, full schema-piping workflows hit 150K. The fix is for the model to write code that calls tools through a runtime — *"tool definitions belong in code, not in context."* — [[akshay-pachaar-mcp-vs-cli-2026-05-09]]
- **300M MCP SDK downloads, up from 100M at the start of 2026** (May 2026) — surfaced the Anthropic-stated traction number to argue MCP is not dying despite the Code-Mode reframe; it's the primitive Code Mode composes. — [[akshay-pachaar-mcp-vs-cli-2026-05-09]]

## Where to Follow

- X: @akshay_pachaar
