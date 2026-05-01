---
title: "@heygurisingh — career-ops, Open-Source AI Job Search on Claude Code (8.2k stars)"
type: source
medium: twitter-thread
url: https://x.com/heygurisingh/status/2049912647722860840
ingested: 2026-04-30
---

## Summary

X post (April 30 2026) reporting on **career-ops**, an open-source AI job-search system built on Claude Code by [@santifer](https://github.com/santifer). The author was laid off, built the system to evaluate 740+ job offers, landed a Head of Applied AI role, and then open-sourced the entire pipeline (MIT, 8.2k GitHub stars at time of post). One slash command takes a job URL and returns: structured A-F evaluation, ATS-optimized PDF tailored to the role, salary research, interview prep, and a tracker entry.

The wider claim is **philosophical, not just technical**: career-ops is *explicitly* a filter, not a spray-and-pray tool. The system refuses to recommend applying to anything scoring below 4.0/5. Its purpose is to find the few offers worth a human's time out of hundreds — the inverse of the typical "auto-apply to 1000 jobs" growth-hack tool that floods recruiters with garbage.

## Key Claims / Takeaways

- **Author**: santifer — built it after being laid off; evaluated 740+ offers with it; landed Head of Applied AI; open-sourced under MIT.
- **8.2k GitHub stars at announcement** (per the post, April 30 2026) — strong traction signal independent of the X buzz.
- **Single slash command interface**: `/<command> <job-url>` triggers the full pipeline. Concretizes the [[writing-claude-code-skills]] pattern at scale.
- **14 skill modes**: evaluate, scan, pdf, batch, apply, deep research, negotiation scripts, LinkedIn outreach (8 named; 6 unnamed). Each mode is a separate skill file invoking a specific stage of the pipeline.
- **Portal scanner pre-loaded with 45+ companies**: Anthropic, OpenAI, ElevenLabs, Mistral, Cohere, Stripe, Retool, Vercel, Decagon, etc. — the AI-frontier-lab list is notable.
- **19 search queries across job boards**: Ashby, Greenhouse, Lever, Wellfound, Workable.
- **ATS-optimized PDF generation via Playwright** with Space Grotesk + DM Sans. (Same Playwright MCP integration as [[alfiejcarter-linkedin-claude-stack]] — emerging convention.)
- **Go terminal dashboard built with Bubble Tea** to browse the job pipeline. Notable: a Claude Code skill stack with a *separate Go TUI* on top of it. Crosses the line from "pure prompt scaffolding" into "real software product."
- **Batch mode evaluates 10+ offers in parallel using Claude sub-agents** — concrete example of the Claude Code sub-agent feature (real parallel context windows) in production, distinct from prompt-time persona simulation (cf. [[aina-ai2-eight-senior-prompts]] pattern #7).
- **Story Bank for interview prep**: accumulates **STAR + Reflection** stories across job evaluations until the user has 5-10 master answers covering any behavioral question. Career-ops is doing **continuous learning across sessions**, not just one-shot generation.
- **Self-modifiable**: Because the system is itself a Claude Code skill stack, the user can ask Claude to rewrite it ("change archetypes to backend roles," "add these 10 companies," "translate the modes to English"). Claude reads the same files it executes, so it knows exactly what to edit. This is a clean instance of the [[llm-wiki-pattern]] applied to a tool's *own configuration* — the system is its own knowledge base.
- **Fit evaluation by reasoning, not keyword matching**: CV vs. JD comparison is done by Claude reasoning over both, not TF-IDF or substring matching. The 4.0/5 threshold filters by judged fit.

## Quote on the Philosophy

> "It's not a spray-and-pray tool. It's a filter. The system literally refuses to recommend applying to anything scoring below 4.0/5. The whole point is to find the few offers worth your time out of hundreds, not to flood recruiters with garbage."

## Why This Matters

career-ops is one of the cleanest **end-to-end Claude Code skill stacks** in the wild as of April 2026. It pulls together:

- the senior-role prompt pattern ([[aina-ai2-eight-senior-prompts]]),
- profile-context + format-library scaffolding ([[alfiejcarter-linkedin-claude-stack]] — `profile.md`/`hooks.md` cousin),
- Playwright MCP for output generation,
- real Claude Code sub-agents for parallel batch processing,
- a Go TUI sitting on top of the skill stack,
- self-modifiability via the [[llm-wiki-pattern]] applied to its own config,
- a stated **filter, not firehose** philosophy that aligns with the [[saas-disruption-thesis]] direction (agents replace toil, raise human leverage, but the human still picks).

It's a strong existence proof for "Claude Code as a production substrate" rather than as a chat interface. **8.2k stars on a 100% Claude-Code-native project is a real traction signal for the underlying tool.**

## Pages Updated

- [[claude-code]] — added April 2026 traction signal: career-ops as flagship open-source skill stack (8.2k stars, MIT, real sub-agent usage, Go TUI on top)
- [[playwright-mcp]] — added career-ops as a real-world usage example
- [[agentic-engineering]] — career-ops fits the "agent-leveraged professional software" framing — added as a real-world example

## Pages Created

- [[career-ops]] — dedicated tool page
- This source page

## Resources

- Original X post: https://x.com/heygurisingh/status/2049912647722860840
- GitHub repo: https://github.com/santifer/career-ops
- Related: [[alfiejcarter-linkedin-claude-stack]] — same week, same Playwright MCP integration, similar skill-stack framing
- Related: [[aina-ai2-eight-senior-prompts]] — same-week prompt-pattern context
- Related: [[writing-claude-code-skills]] — pattern this stack instantiates
