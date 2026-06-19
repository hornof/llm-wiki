---
title: "hornof/knowledge-work-plugins — wiki-owner-authored open-source repository of 11 plugins for knowledge workers in Claude Cowork + Claude Code (2026-06-17)"
type: source
medium: github-repo
url: https://github.com/hornof/knowledge-work-plugins
ingested: 2026-06-18
---

## Summary

**Wiki owner [[owner/profile|@hornof]]** maintains the open-source repository **`hornof/knowledge-work-plugins`** (clipped 2026-06-17; saved as `_raw/hornofknowledge-work-plugins...md`) — **11 plugins for knowledge workers** to use in [[claude-cowork|Claude Cowork]] (also Claude Code compatible). **First wiki-captured owner-side substantive published artifact in the wiki**. **First wiki-captured 11-role canonical-plugin taxonomy** for Claude Cowork (productivity + sales + customer-support + product-management + marketing + legal + finance + data + enterprise-search + bio-research + cowork-plugin-management). **First wiki-captured canonical plugin-structure articulation**: `.claude-plugin/plugin.json` + `.mcp.json` + `commands/` + `skills/` — all file-based markdown + JSON, no code, no infrastructure, no build steps. Pairs structurally with [[claude-code-artifacts-launch-2026-06-18|Jun 18 Anthropic Claude Code Artifacts launch]] + [[block-builderbot-launch-2026-06-17|Jun 17 Block Builderbot Slack-native canonical-trigger]] + [[zodchii-builder-checker-looping-team-2026-06-16|Zodchii CLAUDE.md canonical stop-rules home]] at the **canonical-plugin-and-SKILL.md infrastructure-substrate** layer.

## Key Claims / Takeaways

### The repository

- **Maintainer**: [[owner/profile|@hornof]] (wiki owner)
- **Repository**: `github.com/hornof/knowledge-work-plugins`
- **Purpose**: open-source plugins turning Claude into a specialist for role, team, and company
- **Compatibility**: primarily [[claude-cowork|Claude Cowork]]; also Claude Code compatible

### The 11 canonical-role-plugin taxonomy

| Plugin | Function | Canonical connectors |
|---|---|---|
| **productivity** | Manage tasks + calendars + daily workflows + personal context | Slack, Notion, Asana, Linear, Jira, Monday, ClickUp, Microsoft 365 |
| **sales** | Research prospects + prep calls + review pipeline + draft outreach + build competitive battlecards | Slack, HubSpot, Close, Clay, ZoomInfo, Notion, Jira, Fireflies, Microsoft 365 |
| **customer-support** | Triage tickets + draft responses + package escalations + research customer context + turn resolved issues into KB articles | Slack, Intercom, HubSpot, Guru, Jira, Notion, Microsoft 365 |
| **product-management** | Write specs + plan roadmaps + synthesize user research + keep stakeholders updated + track competitive landscape | Slack, Linear, Asana, Monday, ClickUp, Jira, Notion, Figma, Amplitude, Pendo, Intercom, Fireflies |
| **marketing** | Draft content + plan campaigns + enforce brand voice + brief on competitors + report on performance | Slack, Canva, Figma, HubSpot, Amplitude, Notion, Ahrefs, SimilarWeb, Klaviyo |
| **legal** | Review contracts + triage NDAs + navigate compliance + assess risk + prep meetings + draft templated responses | Slack, Box, Egnyte, Jira, Microsoft 365 |
| **finance** | Prep journal entries + reconcile accounts + generate financial statements + analyze variances + manage close + support audits | Snowflake, Databricks, BigQuery, Slack, Microsoft 365 |
| **data** | Query + visualize + interpret datasets — SQL + statistical analysis + dashboards + validation | Snowflake, Databricks, BigQuery, Definite, Hex, Amplitude, Jira |
| **enterprise-search** | Find anything across email + chat + docs + wikis | Slack, Notion, Guru, Jira, Asana, Microsoft 365 |
| **bio-research** | Connect to preclinical research tools + databases (literature search + genomics + target prioritization) | PubMed, BioRender, bioRxiv, ClinicalTrials.gov, ChEMBL, Synapse, Wiley, Owkin, Open Targets, Benchling |
| **cowork-plugin-management** | Create new plugins + customize existing ones for org-specific tools and workflows | — |

**First wiki-captured 11-role canonical-plugin taxonomy** for Claude Cowork knowledge-worker deployment.

### The canonical plugin-structure articulation

```
plugin-name/
├── .claude-plugin/plugin.json   # Manifest
├── .mcp.json                    # Tool connections
├── commands/                    # Slash commands you invoke explicitly
└── skills/                      # Domain knowledge Claude draws on automatically
```

**First wiki-captured canonical plugin-structure articulation**:
- **Skills** — encode domain expertise + best practices + step-by-step workflows; Claude draws on them automatically when relevant
- **Commands** — explicit actions you trigger (e.g., `/finance:reconciliation`, `/product-management:write-spec`, `/sales:call-prep`, `/data:write-query`)
- **Connectors** — wire Claude to external tools via [MCP servers](https://modelcontextprotocol.io/)

Per the README: *"Every component is file-based — markdown and JSON, no code, no infrastructure, no build steps."*

**First wiki-captured "file-based — markdown and JSON, no code, no infrastructure, no build steps" canonical-discipline articulation** at owner-tier. Pairs structurally with:
- [[writing-claude-code-skills|SKILL.md canonical pattern]] — skills extension at plugin-level
- [[zodchii-builder-checker-looping-team-2026-06-16|Zodchii CLAUDE.md as canonical stop-rules home]] — file-based discipline-pattern
- [[claude-cowork|Claude Cowork]] — Anthropic-vendor-side substrate
- [[mcp|MCP Model Context Protocol]] — Anthropic + Block co-developed connector-protocol substrate

### Customization canonical-pattern

The README articulates **4 canonical customization patterns**:

1. **Swap connectors** — Edit `.mcp.json` to point at specific tool stack
2. **Add company context** — Drop terminology + org structure + processes into skill files
3. **Adjust workflows** — Modify skill instructions to match team's actual practice
4. **Build new plugins** — Use `cowork-plugin-management` plugin or follow structure to create new role/workflow plugins

**First wiki-captured 4-canonical-customization-pattern articulation** for Claude Cowork plugin substrate at owner-tier.

### Strategic positioning

> *"As your team builds and shares plugins, Claude becomes a cross-functional expert. The context you define gets baked into every relevant interaction, so leaders and admins can spend less time enforcing processes and more time improving them."*

**First wiki-captured "cross-functional expert via shared plugin substrate" canonical-strategic-positioning** at owner-tier. Pairs structurally with:
- [[concepts/company-brain|Sentra + Single Brain Company-Brain canonical architectures]] — plugin-tier vs Company-Brain-tier abstraction
- [[block-builderbot-launch-2026-06-17|Block Builderbot AI-native engineering at scale]] — plugin-tier vs engineering-orchestration-tier
- [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14|Nadella frontier-ecosystem firm-CEO-tier thesis]] — plugin-tier as canonical learning-loop substrate component

### Owner-tier publication context

This is the **first wiki-captured substantive published artifact by the wiki owner** — extends [[owner/profile|owner profile]] from CV-only-tier to **technical-publication-tier**. Pairs structurally with [[owner/publications|owner publications]].

### Cross-cutting framings

- **First wiki-captured owner-side substantive published artifact in the wiki** — extends owner profile from CV-only-tier to technical-publication-tier
- **First wiki-captured 11-role canonical-plugin taxonomy** for Claude Cowork (productivity + sales + customer-support + product-management + marketing + legal + finance + data + enterprise-search + bio-research + cowork-plugin-management)
- **First wiki-captured canonical plugin-structure articulation** (`.claude-plugin/plugin.json` + `.mcp.json` + `commands/` + `skills/`)
- **First wiki-captured "file-based — markdown and JSON, no code, no infrastructure, no build steps" canonical-discipline articulation at owner-tier**
- **First wiki-captured 4-canonical-customization-pattern articulation** (swap-connectors + add-company-context + adjust-workflows + build-new-plugins)
- **First wiki-captured "cross-functional expert via shared plugin substrate" canonical-strategic-positioning at owner-tier**
- **First wiki-captured 11-canonical-knowledge-worker-role MCP-connector-stack canonical taxonomy** (~75 distinct external SaaS connectors across 11 plugins)

## Pages Updated

- [[owner/profile]] — knowledge-work-plugins repository added; extends owner technical-publication-tier
- [[owner/publications]] — knowledge-work-plugins added as canonical-publication
- [[claude-cowork]] — knowledge-work-plugins canonical-plugin-marketplace-extension context
- [[claude-code]] — claude-code-compatible canonical plugin-substrate
- [[mcp]] — 11-plugin canonical-connector-stack canonical-validation
- `` `[[concepts/skill-md]]` `` — plugin-level Skills + Commands canonical-pattern extension (no concept page exists; defer until 2nd substantive concept-focus surface)
- [[writing-claude-code-skills]] — Skills canonical-pattern extension at plugin-level
- [[concepts/agentic-engineering]] — file-based markdown + JSON canonical-discipline articulation
- [[concepts/company-brain]] — plugin-tier vs Company-Brain-tier canonical abstraction

## Adjacent sources

- [[claude-code-artifacts-launch-2026-06-18]] — same-day Anthropic Claude Code Artifacts canonical-feature launch
- [[block-builderbot-launch-2026-06-17]] — Jun 17 Block Builderbot production-scale firm-tier operationalization
- [[zodchii-builder-checker-looping-team-2026-06-16]] — file-based CLAUDE.md canonical stop-rules home
- [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]] — LangChain 4-layer canonical-articulation
- [[eric-siu-single-brain-5-layer-company-brain-2026-05-29]] — Single Brain 5-layer Company-Brain canonical-architecture
- [[ashwingop-company-brain-year-lessons-2026-05]] — Sentra Company Brain year-lessons

## Verification-pending

- Specific repository fork-relationship — README install commands use `anthropics/knowledge-work-plugins` rather than `hornof/knowledge-work-plugins` (verification-pending: is this Anthropic upstream + Hornof fork? Is this Anthropic-internal-contribution maintained at hornof/?)
- Specific repository star-count + community-adoption-metrics
- Specific Claude Cowork plugin-marketplace listing status (does this surface at claude.com/plugins/?)
- Specific repository commit-history + contribution-cadence
- Specific bio-research plugin connector-list verification (PubMed + BioRender + bioRxiv + ClinicalTrials.gov + ChEMBL + Synapse + Wiley + Owkin + Open Targets + Benchling = 10-connector preclinical-research-tier stack)
