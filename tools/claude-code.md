---
name: Claude Code
type: tool
category: cli
status: gaining-traction
last_updated: 2026-04-21
---

## What It Is
Anthropic's official CLI and agentic coding tool. Runs Claude models in a terminal with direct access to your filesystem, shell, and tools. Designed for software engineering tasks — reading/writing code, running tests, executing commands — but also used for document-heavy workflows like the [[llm-wiki-pattern]].

## Traction Signals
- Recommended by Karpathy as the LLM agent layer for running the LLM Wiki pattern — [[karpathy-llm-wiki-overview]]
- This wiki itself is maintained via Claude Code

## How to Use It
Install via npm (`npm install -g @anthropic-ai/claude-code`), authenticate, then run `claude` in a terminal. For wiki workflows: open the wiki directory, instruct Claude to ingest/query/lint per the CLAUDE.md schema.

## Key Concepts
- **CLAUDE.md**: configuration file in a project directory that gives Claude persistent context and instructions — equivalent to a system prompt for a codebase
- **Tool use**: Claude Code can read/write files, run shell commands, search the web, and call MCP servers
- **Hooks**: shell commands that run automatically on events (e.g., after each response)

## Compared To
- Cursor / Windsurf: IDE-based, better for interactive coding; Claude Code is terminal-native and better for agentic/autonomous tasks
- ChatGPT / Claude.ai: web interfaces without persistent filesystem access

## Resources
- [[karpathy-llm-wiki-overview]] — cites Claude Code as the recommended LLM agent for the wiki pattern
