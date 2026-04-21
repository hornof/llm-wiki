---
name: mem0
type: tool
category: library
status: emerging
last_updated: 2026-04-21
---

## What It Is
An open-source memory layer for AI agents. Provides persistent, structured memory that can be attached to LLM workflows — supports storing and retrieving facts, decisions, and context across sessions. Has both an open-source library and a managed API.

## Traction Signals
- Mentioned by practitioners as a complement to the [[llm-wiki-pattern]] for handling agent memory — [[reddit-llm-wiki-weekend-build]]
- Used in two-tier memory architectures (long-term + short-term) alongside markdown wiki files

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
