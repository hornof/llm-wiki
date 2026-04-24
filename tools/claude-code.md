---
name: Claude Code
type: tool
category: cli
status: gaining-traction
last_updated: 2026-04-24
---

## What It Is
Anthropic's official CLI and agentic coding tool. Runs Claude models in a terminal with direct access to your filesystem, shell, and tools. Designed for software engineering tasks — reading/writing code, running tests, executing commands — but also used for document-heavy workflows like the [[llm-wiki-pattern]].

## Traction Signals
- Recommended by Karpathy as the LLM agent layer for running the LLM Wiki pattern — [[karpathy-llm-wiki-overview]]
- This wiki itself is maintained via Claude Code
- April 2026 r/claude community actively discusses CLI as displacing standard IDE integrations for agentic tasks — [[reddit-3-things-claude-output-quality]]
- Multiple practitioners report Claude Code CLI as more token-efficient than MCP-heavy setups

## How to Use It
Install via npm (`npm install -g @anthropic-ai/claude-code`), authenticate, then run `claude` in a terminal. For wiki workflows: open the wiki directory, instruct Claude to ingest/query/lint per the CLAUDE.md schema.

## Key Concepts
- **CLAUDE.md**: configuration file in a project directory that gives Claude persistent context and instructions — equivalent to a system prompt for a codebase
- **Tool use**: Claude Code can read/write files, run shell commands, search the web, and call MCP servers
- **Hooks**: shell commands that run automatically on events (e.g., after each response)
- **Harnesses**: the internal prompting/settings layer baked into IDE integrations (Claude Code, Cursor, Windsurf, Copilot); distinct from orchestration frameworks like LangChain or CrewAI
- **context-mode (MCP)**: MCP server setting that constrains file ingestion scope — without it, MCP can pull entire `node_modules` into context and exhaust token limits

## Practitioner Patterns (community-sourced)
- **Format locking**: Enforce an exact response schema in the system prompt (e.g., "1 sentence, max 3 bullets, 1 next action") — Claude follows format constraints more reliably than other models per community reports
- **Context clearing**: Use `/clear` between distinct tasks; fresh context reduces hallucinations and token burn
- **Model tiering**: Drop to Haiku for simple formatting/parsing; reserve Sonnet/Opus for complex reasoning

## Compared To
- Cursor / Windsurf: IDE-based, better for interactive coding; Claude Code is terminal-native and better for agentic/autonomous tasks
- ChatGPT / Claude.ai: web interfaces without persistent filesystem access

## Community Sentiment
- April 2026: r/claude practitioners confirm structured output format enforcement as a genuine quality improvement; CLI displacing browser for agentic workflows — [[reddit-3-things-claude-output-quality]]

## Resources
- [[karpathy-llm-wiki-overview]] — cites Claude Code as the recommended LLM agent for the wiki pattern
- [[reddit-3-things-claude-output-quality]] — April 2026 practitioner thread; community-validated tips and workflow patterns
