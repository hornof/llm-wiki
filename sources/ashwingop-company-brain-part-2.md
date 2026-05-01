---
title: "Company Brain, Part 2: Factual Memory"
type: source
medium: blog-post
url: https://x.com/ashwingop/status/2049885545288077720
published: 2026-04-30
ingested: 2026-05-01
---

## Summary

Follow-up to [[ashwingop-company-brain-part-1]] by [[ashwingop]]. Deep dive on the **factual memory** layer of the [[company-brain]]: what it actually has to be in order to be useful, and why most existing enterprise approaches (knowledge bases, RAG-over-docs, enterprise search with a chat box) do not get there. Sets up the next post in the series, which will cover **interaction memory** (the layer where decisions, judgment, disagreement, and tradeoff live).

Two main moves: (1) **factual memory has to emerge from the individual outward** (not be imposed top-down as a central repository), and (2) **the durable version is a semantic file system** — provenance, permissions, ownership, freshness, source-of-truth, and relationships between artifacts — not RAG embeddings.

## Key Claims / Takeaways

- **Factual memory ≠ shared drive ≠ wiki ≠ enterprise search with chat.** It is "the company's ability to answer questions about what exists and what happened across all the places where work leaves a trace."
- **Central-repository framing is the failure mode.** "That is how knowledge bases die. People do not work in repositories. They work in docs, Slack, meetings, tickets, local notes, spreadsheets, CRM systems, design tools, GitHub, and email. If the Company Brain asks people to stop working naturally and start feeding a central archive, it will fail."
- **Memory has to be built from the individual outward.** Two distinct things: an individual brain (drafts, private notes, half-formed opinions, working memory) and a company brain (official documents, shared decisions, customer commitments, policies, projects, operating knowledge). They overlap but are not the same.
- **Emergence > imposition.** A personal note becomes a team doc becomes a roadmap decision becomes a customer commitment. "If I were drawing this, I would not draw a giant database at the center with arrows pointing into it. I would draw small individual workspaces at the edge."
- **Attribution is non-negotiable.** Who created this, who modified it, who owns it, who made it official, is it current, is it contradicted by something newer, can this person see the underlying source, can this be trusted for a customer conversation or is it a working hypothesis.
- **Durable factual memory is not RAG.** "RAG can retrieve fragments. A well-built demo can feel magical. But a company does not only need plausible snippets. It needs durable structure: provenance, permissions, ownership, freshness, source-of-truth boundaries, and relationships between artifacts." This is a sharp delineation against the prevailing RAG-centric enterprise-AI orthodoxy. — see [[rag]] for the contrast.
- **Semantic file system as the architecture.** "A memory layer where artifacts are not just blobs of text. The relationships around the artifact matter as much as the artifact itself. A customer call connects to an account, the account connects to open issues, the issues connect to tickets, the tickets connect to product areas, the product areas connect to owners, and the owners connect to decisions… **The quality of the relationships determines the quality of the memory.**"
- **Interface ≠ chat alone.** "It should be mutable. It should show up inside the work itself, bring facts forward based on what someone is doing, and respect the boundary between assistance and surveillance."
- **Personalization is part of memory.** Same question, different answers depending on the asker — IC needs implementation details and owners, manager needs blockers/risk/scope, CEO needs the shape of the issue across customers and strategy. "Personalization is not decoration here. It is part of memory."
- **Concrete examples** of what "good factual memory" looks like in real use:
  - IC asks "I'm picking up the billing integration. What should I know?" → synthesized specs, prior tickets, known risks, owners, customer commitments, recent incidents, open decisions; explains what is current, what is stale, where evidence comes from.
  - Manager asks "What is actually blocking onboarding?" → tickets + status updates + ownership + customer escalations + meeting artifacts + unresolved dependencies; separates facts from interpretation.
  - CEO asks "What do we know about enterprise churn?" → CRM data + support tickets + renewal notes + call summaries + account history + product issues + dashboard metrics, *without erasing the differences in source weight*.
- **Memory participates; knowledge bases wait.** Proactive surfacing: open commitments before a customer call, related asks while editing a roadmap doc, prior incidents on ticket assignment, precedent on pricing exceptions, personalized maps for new employees on onboarding.
- **The hard part is not the integrations.** "The hard part is preserving the shape of the company's knowledge as it moves across people, teams, artifacts, and systems."
- **Series setup**: factual memory cannot capture *why* a decision was made — that lives in interactions: meetings, messages, disagreement, judgment, escalation, tradeoff. **Interaction memory** is the next layer to be developed.

## Notable Reframes vs. Adjacent Categories

- **vs. Glean / enterprise search**: synthesis across sources + personalization + provenance + stale-information detection + uncertainty admission + proactive delivery. "A Company Brain has to go further" than retrieval.
- **vs. RAG**: explicit. RAG retrieves fragments; "retrieval alone will fail when meaning has to persist."
- **vs. central knowledge bases**: emergent vs. imposed; "drop-in memory tends to look like another repository."

## Pages Updated

- [[company-brain]] — Layer 1 (factual memory) substantially fleshed out with semantic-file-system framing, individual-outward emergence, personalization-as-memory
- [[ashwingop]] — added Part 2 takes (semantic file system, memory participates / KB waits, factual memory ≠ RAG)
- [[sentra]] — added factual-memory positioning
- [[rag]] — contrast against Ashwin's "factual memory ≠ RAG" position
