---
name: Claude Code
type: tool
category: cli
status: gaining-traction
last_updated: 2026-04-26
---

## What It Is
Anthropic's official CLI and agentic coding tool. Runs Claude models in a terminal with direct access to your filesystem, shell, and tools. Designed for software engineering tasks — reading/writing code, running tests, executing commands — but also used for document-heavy workflows like the [[llm-wiki-pattern]].

## Traction Signals
- Recommended by Karpathy as the LLM agent layer for running the LLM Wiki pattern — [[karpathy-llm-wiki-overview]]
- This wiki itself is maintained via Claude Code
- Karpathy specifically cites "Claude Code or Codex" as the primary interface for [[agentic-engineering]] — the professional discipline of coordinating agents for production-quality software — [[karpathy-vibe-coding-agentic-engineering]]
- April 2026 r/claude community actively discusses CLI as displacing standard IDE integrations for agentic tasks — [[reddit-3-things-claude-output-quality]]
- Multiple practitioners report Claude Code CLI as more token-efficient than MCP-heavy setups
- Naval Ravikant (April 2026): explicitly cited Claude Code as the tool enabling a 2-person team to replicate 80% of most B2B SaaS products in under 90 days — used as evidence for the "pure software is uninvestable" thesis — [[sources/naval-ravikant-saas-is-next]]

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

## Skill Writing (slash commands)
Skills live at `~/.claude/skills/<name>/SKILL.md` and are invoked as `/<name>`. Six patterns that separate working skills from ones that never fire — [[zodchiii-anatomy-perfect-skill]]:
1. **Description = WHEN, not just WHAT**: Include trigger keywords; front-load use case in first 250 chars; under 50 chars → 3-5x fewer invocations
2. **Directive, not conversational**: Imperative verbs + numbered steps
3. **Explicit output format**: Without it, Claude invents a new format every time
4. **"Read first" step**: Tell Claude to inspect existing project files before generating
5. **Define out of scope**: Prevents wrong-skill routing; appears in 70% of high-quality skills
6. **Under 500 lines**: Use progressive disclosure (sub-files loaded only when referenced)

See [[tutorials/writing-claude-code-skills]] for a full walkthrough.

## Compared To
- Cursor / Windsurf: IDE-based, better for interactive coding; Claude Code is terminal-native and better for agentic/autonomous tasks
- ChatGPT / Claude.ai: web interfaces without persistent filesystem access

## Community Sentiment
- April 2026: r/claude practitioners confirm structured output format enforcement as a genuine quality improvement; CLI displacing browser for agentic workflows — [[reddit-3-things-claude-output-quality]]

## Resources
- [[karpathy-llm-wiki-overview]] — cites Claude Code as the recommended LLM agent for the wiki pattern
- [[reddit-3-things-claude-output-quality]] — April 2026 practitioner thread; community-validated tips and workflow patterns
- [[zodchiii-anatomy-perfect-skill]] — April 2026 thread; 6-pattern framework for effective skills
- [[tutorials/writing-claude-code-skills]] — full skill-writing walkthrough
