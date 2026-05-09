---
name: Sentra
type: company
status: early-stage
last_updated: 2026-05-09
---

## What It Is

Sentra ([sentra.app](https://www.sentra.app/)) is a startup building **enterprise general intelligence**: "a shared intelligence/memory layer that sits on all communication channels, knowledge bases and agent traces to understand how everyone in an organization actually works as well as how work actually gets done, constructing a living world model of the entire company in near real time" — direct quote from founder [[ashwingop]], April 2026.

Founded by Ashwin Gopalan; incorporated approximately early 2025 (described as "over a year" old as of April 2026). The product is positioned as a **Company Brain** — a memory substrate for the company, not a chatbot over docs, not a dashboard, not just meeting notes, not just agents. See [[company-brain]] for the conceptual framing.

## Positioning

Sentra sits at the intersection of four categories that are all "moving toward the same center from a different wedge" (Ashwin's framing — [[ashwingop-company-brain-part-1]]):

| Category | What they know | Examples |
| --- | --- | --- |
| Knowledge tools | what exists | Glean |
| Meeting tools | what was said | Granola, Otter |
| Workflow tools | how to act | Zapier, ServiceNow |
| Agent tools | how to attempt tasks | Dust |

Sentra's bet is that the durable position is the integration point: **factual memory + human communication + context graph and reasoning + governed action**. Missing any one gives you "a searchable archive" or "transcripts and summaries" or "plausible guesses" or "brittle automation."

## Architecture (as described)

Three-layer memory thesis:
1. **Factual memory** — record of what happened across meetings, messages, emails, docs, tickets, CRM, commits, incidents, dashboards, calls, support — with provenance, permissions, timestamps, grounding. Built as a **semantic file system** where artifact relationships matter as much as artifacts; *not* RAG-over-enterprise-data. Memory has to **emerge from the individual outward** rather than be imposed top-down. Personalization, proactivity ("memory participates, knowledge bases wait"), and respect for the individual-vs-company boundary are core. — [[ashwingop-company-brain-part-2]]
2. **Context graph / reasoning layer** — facts become a model of the company; calls connect to opportunities connect to gaps connect to roadmap decisions. This is also where metacognition lives: knowing when evidence is weak, context is stale, teams have conflicting assumptions, commitments lack owners.
3. **Action coordination** — drafting follow-ups from commitments, creating tickets from recurring complaints, warning about cross-team assumption mismatches, deciding what an agent can safely do unattended vs. what needs approval.

See [[company-brain]] for the concept page.

## Updated Positioning (May 2026)

After a year of design-partner work, [[ashwingop]] sharpened the positioning to **"shared semantic company state"** — the substrate beneath both humans and agents — and disclosed that the project's original internal name was **"Enterprise General Intelligence"** before being simplified to Company Brain. Ambition unchanged; primitive sharpened. New product principles introduced (see [[company-brain]] for full treatment): **pace > automation** (latency collapse is the real wow, not task automation), **surfacing > browsing** (TikTok analogy, not a knowledge-graph browser), **cockpit > copilot** (a memory instrument, not another employee). Ontology layer added above the three memory layers: same substrate, different role-specific lenses (CEO / PM / lawyer / support / agent), each producing valid but distinct memories from the same underlying artifacts. — [[ashwingop-company-brain-year-lessons-2026-05]]

## Substrate vs. Lens (Part 7, May 7 2026)

[[ashwingop-semantics-ontology-2026-05-07]] introduces the architectural separation that ties the rest of Sentra's stack together:

- **Substrate**: shared, permissioned, inspectable, durable. One memory underneath the company.
- **Lens**: functional, customizable, per-vertical. Each function (sales, product, support, legal, leadership) carries a narrower ontology of how it sees its slice.

The substrate-vs-lens framing reframes Sentra's wedge: not "one assistant per company" (the dominant 2026 enterprise AI playbook, where adoption stays uneven across functions), but **one substrate, many lenses**. Sales / product / support / legal / leadership all pull from the same memory, each through its own ontology. *"The substrate holds the same memory underneath. The lens decides what that memory means in context."*

Falsifiable bet attached: within 18 months from May 7 2026 (≈ end of 2027), the gap between companies that built shared semantic state and companies that bolted agents onto fragmented data will be measurable in **decisions-into-action rate** — *how often the company successfully does the thing it decided to do* — not in AI usage metrics. Both groups will have high usage; only the first will close the loop.

## Reading the Anthropic Managed Agents Launch (Part 8, May 2026)

After [[anthropic]]'s Managed Agents launch at Code w/ Claude 2026 ([[willison-code-w-claude-2026]]), Ashwin published Part 8 — [[ashwingop-managed-agents-company-brain-2026-05-08]] — reading the move as a structural signal:

- **Even agents are moving from "everyone builds the loop themselves" to managed primitives** (sessions, containers, tools, files, events, permissions, state). By analogy, the *next* infra layer is the company-state substrate every app, agent, and human surface acts from.
- **Anthropic's Memory ≠ Company Brain.** The Memory tool and Managed Agents Memory provide file-based directories, workspace-scoped collections, path-traversal protection — i.e., a knowledge base. **"A knowledge base stores useful information. Company Brain maintains operational state."**
- **The App Mistake**: every serious company will instinctively rebuild the substrate. Vibe coding makes the demo seductive. But "infrastructure is not judged by the first answer. It is judged by what happens after six months of writes, permission changes, stale documents, duplicate customers, renamed projects, conflicting sources, and agents acting at the same time."
- **Markdown brains are prototypes.** Karpathy's [[llm-wiki-pattern|LLM Wiki]] and Garry Tan's GBrain are explicitly named as "directionally right" — but bound to the single-owner, single-trust-boundary regime. Companies don't get that simplicity.
- **The AWS lesson**: cloud didn't make infrastructure disappear; it made the primitive reliable enough to build higher up. **Shared infrastructure with company-specific ontology** is the right architecture — not generic-vs-internal binary.
- **Tool access (MCP) ≠ Company Brain.** Query-time context — agent calls tools, searches systems, assembles context on the fly — is flexible but slow, expensive, hard to verify, and easy to miss the thing that matters. Company Brain maintains state as work happens, then agents act from it.
- **The hard part is state**: concurrency, provenance, permission propagation, ontology binding, action traces, evals, deletion, conflict handling. Apps sit on top; brain underneath.

Crisp closing positioning: *"The companies that win will not be the ones with the most internal AI demos. They will be the ones that turn work into company state quickly enough for humans and agents to act from it."*

## Traction Signals

- **9-piece longform series** on X (Apr 29 – May 9, 2026) — [[ashwingop-company-brain-part-1]], [[ashwingop-company-brain-part-2]], plus parts 3–5 (interaction memory, action memory, "memory is state, not a service"), the year-lessons summary [[ashwingop-company-brain-year-lessons-2026-05]], the May 7 semantics-and-ontology piece [[ashwingop-semantics-ontology-2026-05-07]], and the May 8 Managed-Agents reading [[ashwingop-managed-agents-company-brain-2026-05-08]]. Substantive, link-rich, with citations to McKinsey, Glean, Granola, Otter, ServiceNow, Walsh & Ungson on organizational memory, and (in Part 8) explicit engagement with [[karpathy-llm-wiki-gist|Karpathy's LLM Wiki gist]] and Garry Tan's GBrain framing.
- People are pinging Ashwin saying "isn't this what you're building?" after YC's April 2026 RFS named "company brain" — Ashwin claims the product but acknowledges the name is YC's framing. Now confirmed via primary source: **two separate YC partners independently described the same gap in [[yc-summer-2026-rfs]]** — [[tom-blomfield]] under "Company Brain" (§5) and [[diana-hu]] under "The AI Operating System for Companies" (§16). Two-partner overlap inside one RFS is a strong demand-side signal for Sentra's wedge.
- Independent validation of the underlying problem: McKinsey ([building agentic AI foundations](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/building-the-foundations-for-agentic-ai-at-scale)) argues agentic AI needs stronger data foundations, lineage, access control, governance to scale — Ashwin uses this as supporting evidence.

## Caveats

- Funding, headcount, customers not disclosed in the ingested sources. Stub company page; promote beyond `early-stage` only on stronger primary evidence.
- Vision-heavy posts; no public product walkthrough, demos, or pricing observed in this wiki yet.
- Direct competitive overlap with multiple well-funded incumbents (Glean, Dust, Zapier Agents, ServiceNow). Wedge depends on whether Sentra ships the "memory substrate" before incumbents extend into the same layer.

## Resources

- [[ashwingop]] — founder
- [[company-brain]] — concept page
- [[ashwingop-company-brain-part-1]] — April 2026 thesis (Part 1)
- [[ashwingop-company-brain-part-2]] — April 2026 deep dive on factual memory (Part 2)
- [[ashwingop-company-brain-year-lessons-2026-05]] — May 2026 year-of-design-partners summary
- [[ashwingop-semantics-ontology-2026-05-07]] — Part 7: semantics ≠ ontology; substrate vs. lens; falsifiable 18-month "decisions-into-action" bet
- [[ashwingop-managed-agents-company-brain-2026-05-08]] — Part 8: reading Anthropic Managed Agents as the structural signal pointing to Company Brain
- [[ashwingop-systems-of-record-2026-05-09]] — Part 9: from systems of record to systems of intelligence; "model-as-brain is like RAM-as-permanent-storage"; uncomfortable question for incumbent SaaS
- Site: https://www.sentra.app/
