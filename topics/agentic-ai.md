---
name: Agentic AI
type: topic
last_updated: 2026-04-21
---

## What It Is
The paradigm of LLMs that take actions autonomously — calling tools, making decisions, executing multi-step plans — rather than just generating text responses. An "agent" is an LLM in a loop: perceive → think → act → observe → repeat.

## Why It Matters for AI Engineering
Agents are the current frontier of applied AI engineering. Moving from "LLM as a smart autocomplete" to "LLM as an autonomous worker" unlocks entirely new application categories but introduces new engineering challenges around reliability, observability, and safety.

## Key Patterns
- **Tool use**: LLM calls external functions (search, code execution, APIs)
- **ReAct**: Reasoning + Acting — LLM interleaves thinking steps with tool calls
- **Multi-agent**: multiple specialized agents collaborate, delegate, or check each other's work
- **Human-in-the-loop**: agent pauses for human approval at key decision points

## Key Protocols
- **MCP (Model Context Protocol)**: Anthropic's open standard for connecting LLMs to tools and data sources — [[mcp]]
- **A2A (Agent-to-Agent)**: protocol for agents to communicate with each other [unsourced — needs ingestion]
- **OpenAI Agents SDK**: OpenAI's framework for building agents [unsourced — needs ingestion]

## Tools in This Space
- [[crewai]] — multi-agent role-playing framework
- [[langchain]] — agent engineering platform (LangGraph for stateful agents)
- [[llama-index]] — document agents and RAG
- [[claude-code]] — agentic coding tool

## Resources
- [[github-hornof-profile]] — wiki owner is actively tracking crewAI, learn-agentic-ai, OpenAI Agents SDK
