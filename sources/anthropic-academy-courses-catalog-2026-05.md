---
title: "Anthropic Academy — Courses Catalog"
type: source
medium: webpage
url: https://anthropic.skilljar.com/
ingested: 2026-05-05
---

## Summary

Catalog page for **Anthropic Academy** (Skilljar-hosted at `anthropic.skilljar.com`, linked from `anthropic.com/learn`) listing the official self-serve learning paths Anthropic publishes for Claude users, developers, partners, educators, and AWS / Google Cloud customers. Captured 2026-05-05. This is the **primary source** for the official Claude / MCP / Skills / Subagents curriculum referenced in the [[anthropic-claude-partner-network]] page (which lists "Anthropic Academy training" as a Partner Portal benefit).

Most directly relevant to the wiki's hands-on goals: the **Skills**, **Subagents**, **MCP**, and **Claude Code** courses are first-party reference material for [[writing-claude-code-skills]], [[claude-code]], and [[mcp]]. Worth completing in priority order if formalizing skill-authoring practice.

## Course Inventory (16 courses captured)

### Claude end-user track
- **Claude 101** — Claude for everyday work tasks; core features; gateway to advanced topics
- **Introduction to Claude Cowork** — work alongside Claude on real files and projects; Cowork task loop, plugins, skills, file/research workflows, multi-step steering ("productive in your first week"). *First wiki appearance of [[anthropic|Cowork]] as the subject of an official course.*
- **AI Capabilities and Limitations** — introductory course about how AI works
- **AI Fluency: Framework & Foundations** — collaborate with AI systems effectively, efficiently, ethically, and safely

### Claude Code track
- **Claude Code 101** — Claude Code in daily development workflow → [[claude-code]]
- **Claude Code in Action** — integrate Claude Code into development workflow

### Skills + Subagents track
- **Introduction to agent skills** — build, configure, and share Skills in Claude Code; "reusable markdown instructions that Claude automatically applies to the right tasks at the right time"; covers Skill creation, distribution, troubleshooting → [[writing-claude-code-skills]]
- **Introduction to subagents** — use and create subagents in Claude Code to manage context, delegate tasks, build specialized workflows that "keep your main conversation clean and focused" *(first official wiki reference to subagents as a named primitive separate from Skills)*

### Anthropic API + MCP track
- **Building with the Claude API** — full spectrum of working with Anthropic models via the Claude API
- **Introduction to Model Context Protocol** — MCP servers and clients from scratch in Python; tools, resources, prompts → [[mcp]]
- **Model Context Protocol: Advanced Topics** — advanced MCP implementation: sampling, notifications, file system access, transport mechanisms; production MCP server development

### Cloud-partner track
- **Claude with Amazon Bedrock** — first-of-its-kind training originally created for AWS employees, opened publicly
- **Claude with Google Cloud's Vertex AI** — comprehensive coverage of Anthropic models via Vertex AI

### Education + nonprofit track
- **AI Fluency for educators** — applying AI Fluency to teaching practice + institutional strategy
- **AI Fluency for students** — AI Fluency for learning, career planning, academic success
- **Teaching AI Fluency** — teach and assess AI Fluency in instructor-led settings
- **AI Fluency for nonprofits** — AI fluency for nonprofit professionals; mission-aligned

## Why This Matters for the Wiki

- **First-party canonical reference** for the Claude/Skills/MCP/Subagents stack. Where the wiki has been quoting practitioner blog posts (e.g. [[julian-goldie-notebooklm-skills-factory]], [[heygurisingh-career-ops]]) and primary X threads, Anthropic Academy publishes the *official* curriculum for the same topics.
- **"Subagents" appears here as a first-class named primitive** in an Anthropic-published course title. The wiki has been treating Skills as the dominant Claude Code authoring surface; this is signal that subagents (orchestration / context-isolation primitive) are now a co-equal teaching topic.
- **Cowork has an official onboarding course** ("Introduction to Claude Cowork"), confirming Cowork is a fully-shipped product surface, not a label-only feature. Adds weight to the [[claude-financial-services]] note that Cowork is a vertical-agent plugin host alongside [[claude-code]].
- **Partner Network → Academy linkage**: Anthropic Academy is the training arm referenced as a [[anthropic-claude-partner-network]] benefit. Owners pursuing the [[claude-certified-architect]] cert can use Academy courses as exam prep alongside the practitioner roadmaps already ingested.

## Pages Updated

- [[anthropic-academy-courses-catalog-2026-05]] (this page, new)
- [[claude-code]] — added Anthropic Academy as official learning resource
- [[mcp]] — added Anthropic Academy MCP courses (intro + advanced) as official references
- [[writing-claude-code-skills]] — added Anthropic Academy "Introduction to agent skills" and "Introduction to subagents" as official-curriculum complements
