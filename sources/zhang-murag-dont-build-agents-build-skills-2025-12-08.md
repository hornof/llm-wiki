---
title: "Don't Build Agents, Build Skills Instead – Barry Zhang & Mahesh Murag, Anthropic"
type: source
medium: video
url: https://www.youtube.com/watch?v=CEvIs9y1uog
ingested: 2026-11-12
---

## Summary

A 16-minute AI Engineer Code 2025 talk by Anthropic's Barry Zhang and Mahesh Murag, posted 2025-12-08. Their argument: agents now share one architecture (a model, a shell and a filesystem), so what's missing is domain expertise, and skills are how to package it. The video wasn't watched. These notes come from the YouTube description and AI Engineer's write-up on its talk page (https://ai.engineer/talks/CEvIs9y1uog-agent-skills), which is a generated summary of the transcript, not the transcript. Found via [[godsystemsmd-skills-are-the-prompts-2026-11-05]].

## Key Claims / Takeaways

- **The gap is expertise, not intelligence.** The description: *"agents often lack the domain expertise and specialized knowledge needed for real-world work."*
- **Layering:** *"MCP supplies connectivity to external tools and data, while skills supply the procedural expertise needed to orchestrate useful workflows."* The write-up adds an agent loop and a runtime (filesystem and code) under both.
- **Origin of scripts in skills:** *"Zhang describes repeatedly observing Claude recreate a Python script for styling slides"*, then having Claude save it into a skill.
- **Three kinds of skill:** foundational (document editing, K-Dense's science skills), partner (Browserbase for Stagehand, Notion) and enterprise, including Fortune 100 internal workflows.
- **Next steps named:** testing whether the right skill triggers, versioning, dependencies. The write-up says these are presented as priorities, and that *"the transcript does not provide measured performance gains"*.
- **The thesis:** *"agents writing their own Skills from experience."* The write-up qualifies that shared skills *"are not a complete memory system"*.
- **Caveat:** these claims reach the wiki through a summary of the talk, not the speakers' words. [Provenance.]

## Pages Updated

- [[skill-md]] — new 2026-11-12 section
