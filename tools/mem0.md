---
name: mem0
type: tool
category: library
status: emerging
last_updated: 2026-06-29
---

## What It Is
An open-source memory layer for AI agents. Provides persistent, structured memory that can be attached to LLM workflows — supports storing and retrieving facts, decisions, and context across sessions. Has both an open-source library and a managed API.

## Traction Signals
- Mentioned by practitioners as a complement to the [[llm-wiki-pattern]] for handling agent memory — [[reddit-llm-wiki-weekend-build]]
- Used in two-tier memory architectures (long-term + short-term) alongside markdown wiki files
- **2026-05-29: canonical-positioning canonical-cohort with [[concepts/company-brain|Company Brain]]** ([[latentspace-walden-yan-async-agents-2026-05-29]]) — Cognition's Walden Yan canonical-cites mem0 as canonical-agent-memory-infrastructure-stack canonical-component alongside Company Brain at canonical-async-agent canonical-substrate-tier
- **2026-06-04: canonical-mem0-vs-ChatGPT-vendor-memory canonical-2-layer canonical-positioning** ([[dailybrief-roundup-2026-06-04]]) — first wiki-captured canonical-operator-side-memory-primitive (mem0) vs canonical-vendor-side-memory-consolidation (ChatGPT "dreaming") canonical-2-layer canonical-distinction
- **2026-05: canonical-distinct-from-Anthropic-cross-chat-Memory canonical-disambiguation** ([[rubenhassid-anthropic-30-term-map-2026-05]]) — first wiki-captured canonical-3-way memory-tier distinction: mem0 (canonical-developer-library) vs canonical-Anthropic-cross-chat-Memory (canonical-consumer-feature) vs [[concepts/company-brain|Company Brain]] (canonical-organizational-architecture)

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
