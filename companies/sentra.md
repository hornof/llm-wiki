---
name: Sentra
type: company
status: early-stage
last_updated: 2026-05-06
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

## Traction Signals

- **6-piece longform series** on X (Apr 29 – May 6, 2026) — [[ashwingop-company-brain-part-1]], [[ashwingop-company-brain-part-2]], plus parts 3–5 (interaction memory, action memory, "memory is state, not a service") and the year-lessons summary [[ashwingop-company-brain-year-lessons-2026-05]]. Substantive, link-rich, with citations to McKinsey, Glean, Granola, Otter, ServiceNow, Walsh & Ungson on organizational memory.
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
- Site: https://www.sentra.app/
