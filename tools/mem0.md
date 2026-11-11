---
name: mem0
type: tool
category: library
status: emerging
last_updated: 2026-08-31
dormant_since: 2026-11-03
---

## What It Is
An open-source memory layer for AI agents. Provides persistent, structured memory that can be attached to LLM workflows — supports storing and retrieving facts, decisions, and context across sessions. Has both an open-source library and a managed API.

## Traction Signals
- Mentioned by practitioners as a complement to the [[llm-wiki-pattern]] for handling agent memory — [[reddit-llm-wiki-weekend-build]]
- Used in two-tier memory architectures (long-term + short-term) alongside markdown wiki files
- **2026-05 to 2026-06: cross-referenced, not cited.** Three earlier bullets here said Walden Yan's Latent Space interview ([[latentspace-walden-yan-async-agents-2026-05-29]]), the 2026-06-04 brief ([[dailybrief-roundup-2026-06-04]]) and Ruben Hassid's Anthropic term map ([[rubenhassid-anthropic-30-term-map-2026-05]]) positioned mem0. On checking, none of the three sources mentions mem0. The link was added by the wiki in each case, to set mem0 (a developer library you call from code) apart from vendor-side memory such as ChatGPT's and Claude's cross-chat Memory, and from [[company-brain|Company Brain]] as an organizational architecture. That distinction is still useful, but it is the wiki's, not a traction signal. *(Rewritten 2026-11-10 lint; the earlier text was `canonical-` filler.)*
- **2026-08-27: placed in the 9-brain "company brain" field-map** ([[femke-plantinga-company-brain-teardown-2026-08-27]], Slite): characterized as *"a memory library you call from your own code — stores only what you explicitly tell it to, and **ranks fresh facts above idle ones** at search time."* The explicit-store + freshness-ranking framing situates mem0 as the **developer-library archetype** among 9 company brains (vs. git-repo brains like GBrain/Sylph, temporal-KG brains like Zep/Graphiti, and agent-memory like Letta). See [[company-brain]]. *(Vendor teardown; positioning summary.)*

## How to Use It
Integrate as a memory store in agent workflows. Can be used alongside a markdown wiki: the wiki holds synthesized, human-readable knowledge; mem0 holds agent decisions and short-term working memory.

## Key Concepts
- **Long-term memory**: persistent facts and decisions across sessions
- **Short-term memory**: working context within a session
- **Open memory**: mem0's managed memory layer (cloud-hosted option)

## Compared To
- Plain markdown files: mem0 adds structured retrieval and agent-native APIs; markdown is more human-readable and inspectable
- Vector stores (Pinecone, Chroma): mem0 is higher-level and memory-specific; vector stores are lower-level retrieval infrastructure

## Resources
- [[reddit-llm-wiki-weekend-build]] — mentioned by u/SprintSingh as complement to LLM Wiki for agent memory management
