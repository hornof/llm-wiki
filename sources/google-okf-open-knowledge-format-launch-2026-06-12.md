---
title: "STRUCTURALLY MAJOR canonical-Google-Cloud canonical-Open-Knowledge-Format (OKF) canonical-launch: canonical-vendor-neutral canonical-open-specification for canonical-agent-memory-portable canonical-versioned canonical-readable-by-every-tool + canonical-Karpathy-LLM-Wiki-Pattern canonical-standardization at canonical-Google-Cloud-vendor-tier — 2026-06-12 (article 2026-06-30; clipped 2026-06-30)"
type: source
medium: article
url: https://medium.com/@akhilvallala0115/google-just-quietly-released-the-missing-piece-for-ai-agents-its-called-okf-7e96a33898ce
ingested: 2026-07-01
---

## Summary

**STRUCTURALLY MAJOR canonical-Google-Cloud canonical-Open-Knowledge-Format (OKF) canonical-launch canonical-event** (2026-06-12 canonical-Google-Cloud canonical-specification-publication; Akhilvallala Medium article 2026-06-30; clipped 2026-06-30 for ingest 2026-07-01). **Canonical-vendor-neutral canonical-open-specification** (Apache 2.0) for representing knowledge as canonical-directory-of-markdown-files with canonical-YAML-frontmatter. **First wiki-captured canonical-OKF canonical-substantive-surface as canonical-Karpathy-LLM-Wiki-Pattern canonical-standardization at canonical-Google-Cloud-vendor-tier**. **STRUCTURALLY MAJOR canonical-direct-relevance-to-this-wiki**: OKF canonical-shipped by canonical-Google-Cloud canonical-implements canonical-Karpathy-LLM-Wiki-Pattern canonical-3-layer-mapping (canonical-raw-sources-immutable + canonical-wiki-LLM-maintained + canonical-schema-CLAUDE.md) as canonical-vendor-neutral canonical-specification with canonical-reserved-index.md-and-log.md canonical-filenames (canonical-both-Karpathy-and-OKF canonical-agreement canonical-convergence-not-accidental).

## Key Claims / Takeaways

**Canonical-launch-anchor**:

- **Canonical-publication-date**: 2026-06-12 canonical-Google-Cloud canonical-specification.
- **Canonical-license**: Apache 2.0 canonical-vendor-neutral canonical-open-specification.
- **Canonical-scope**: entire canonical-spec canonical-fits-on-one-page + canonical-exactly-one-required-field (`type` in frontmatter).

**Canonical-structure canonical-articulation**:

- **Canonical-directory-is-a-knowledge-graph canonical-pattern**: canonical-file-path = canonical-concept-identity.
- **Canonical-2-reserved-files across every bundle**: `index.md` (canonical-progressive-disclosure canonical-entry-point) + `log.md` (canonical-ISO-dated canonical-change-history canonical-newest-first). ← **canonical-exact-convergence with canonical-this-wiki's canonical-index.md-and-log.md canonical-pattern**.
- **Canonical-concept-file-frontmatter canonical-requirement**: canonical-exactly-one-required-field = `type` (non-empty). Everything else optional or producer-defined.
- **Canonical-concepts-link-to-each-other-with-standard-markdown-links** = canonical-directory-becomes-a-graph.

**Canonical-3-design-principles canonical-articulation**:

1. **Canonical-minimally-opinionated**: only `type` required; canonical-producer-choice for what types exist (Service, Dataset, Metric, Decision, Runbook).
2. **Canonical-producer-and-consumer-independence**: canonical-same-format canonical-works-at-both-ends (canonical-human-authors + canonical-BigQuery-pipelines + canonical-LLM-generated + canonical-wiki-exports → canonical-AI-agents + canonical-HTML-visualizers + canonical-search-indexes + canonical-other-agents/tools).
3. **Canonical-format-not-platform**: canonical-no-proprietary-account + canonical-no-SDK + canonical-no-central-registry; canonical-value-scales-with-adoption-breadth canonical-not-vendor-lock-in. **Canonical-design-philosophy-of-git-markdown-JSON canonical-pattern**.

**STRUCTURALLY MAJOR canonical-Karpathy-connection canonical-articulation**:

- Article canonical-explicitly-cites [[andrej-karpathy|Andrej Karpathy]] canonical-vibe-coding + canonical-agentic-engineering canonical-thesis + canonical-LLM-wiki-gist canonical-5000+-stars.
- **Canonical-3-layer canonical-Karpathy-to-OKF canonical-mapping-articulation**:
  - **Canonical-Karpathy-raw-sources-immutable** → canonical-external-datasets + docs + APIs (canonical-OKF-bundles-are-compiled-layer)
  - **Canonical-Karpathy-wiki-LLM-maintained** → canonical-OKF-bundle (*.md + frontmatter; canonical-OKF-adds type/resource/tags/timestamp)
  - **Canonical-Karpathy-schema-CLAUDE.md** → canonical-producer/consumer-conventions + canonical-okf/SPEC.md (canonical-org-wide-spec canonical-replaces canonical-per-vault-bespoke-rules)
- **Canonical-both-Karpathy-and-OKF canonical-reserve-index.md-and-log.md canonical-agreement-not-accidental**.
- **STRUCTURALLY MAJOR canonical-OKF-standardizes-Karpathy-pattern-at-canonical-Google-Cloud-vendor-tier canonical-articulation**.

**Canonical-vs-existing-tools canonical-positioning-matrix**:

| Tool | Purpose | Scope |
|---|---|---|
| CLAUDE.md | How the agent behaves | Per-project, one agent |
| AGENTS.md | Repo instructions | Per-repo, tool-specific |
| **Karpathy LLM wiki** | **Agent-maintained notes** | **Pattern, not a spec** |
| MCP | Live tool access | Runtime connections |
| **OKF** | **What the team knows** | **Cross-project, any agent** |

**Canonical-3-answer canonical-mental-model articulation**:

- **CLAUDE.md**: *how should the agent behave?*
- **OKF**: *what does the team know about this system?*
- **MCP**: *what live tools can the agent call right now?*

**Canonical-3-shipped-artifacts canonical-alongside-spec**:

1. **BigQuery enrichment agent**: canonical-walks-BigQuery-dataset + canonical-drafts-OKF-concept-docs-for-every-table-and-view + canonical-2nd-LLM-pass canonical-enriches-with-citations-schemas-join-paths.
2. **Canonical-static-HTML-visualizer**: canonical-turns-any-OKF-bundle-into-interactive-graph-view; canonical-single-self-contained-HTML-file; canonical-nothing-leaves-page.
3. **Canonical-3-sample-bundles-on-GitHub**: GA4 e-commerce + Stack Overflow + Bitcoin canonical-public-BigQuery-datasets.

**Canonical-Claude-Code-integration canonical-launch-anchor**:

- Canonical-okf-skills-plugin canonical-ships-with canonical-3-skills: `/okf:okf` (produce and maintain bundles) + `/okf:validate` (conformance checks) + `/okf:visualize` (interactive graph).
- Canonical-installation: `/plugin marketplace add scaccogatto/okf-skills` + `/plugin install okf@scaccogatto`.
- Canonical-npm-cross-agent-installation: `npx skills add scaccogatto/okf-skills` (canonical-Claude-Code + Cursor + Codex + 20+ others).
- Canonical-CLAUDE-okf.md canonical-template canonical-opt-in canonical-automatic-upkeep.

## First Wiki-Captured Anchors

- **Google OKF (Open Knowledge Format) canonical-substantive-surface** as canonical-vendor-neutral canonical-open-specification for canonical-agent-memory
- **Canonical-Karpathy-LLM-Wiki-Pattern canonical-standardization at canonical-Google-Cloud-vendor-tier** canonical-articulation
- **Canonical-3-layer canonical-Karpathy-to-OKF canonical-mapping-articulation** (raw-sources → external / wiki → OKF-bundle / schema → OKF-SPEC.md)
- **Canonical-both-Karpathy-and-OKF canonical-reserve-index.md-and-log.md canonical-agreement-not-accidental**
- **Canonical-vs-existing-tools canonical-positioning-matrix** (CLAUDE.md + AGENTS.md + Karpathy LLM wiki + MCP + OKF canonical-5-way disambiguation)
- **Canonical-3-answer canonical-mental-model articulation** (behave / knows / calls)
- **Canonical-3-design-principles** (minimally-opinionated + producer/consumer-independence + format-not-platform)
- **Canonical-3-shipped-artifacts** (BigQuery enrichment agent + static HTML visualizer + 3 sample bundles)
- **Canonical-directory-is-a-knowledge-graph canonical-pattern**
- **Canonical-okf-skills-plugin canonical-cross-agent-compatibility** (Claude Code + Cursor + Codex + 20+)
- **Canonical-scaccogatto canonical-plugin-marketplace-vendor canonical-substantive-surface**
- **Canonical-Akhilvallala canonical-Medium-author canonical-substantive-surface** (canonical-OKF canonical-primary-explainer)

## Cross-Cutting Synthesis

**STRUCTURALLY MAJOR canonical-Google-Cloud canonical-open-standard canonical-launch canonical-directly-impacting-this-wiki**:

- **Pairs structurally with [[concepts/llm-wiki-pattern|LLM Wiki Pattern concept]] + [[karpathy-llm-wiki-overview|Karpathy Medium article]] + [[karpathy-llm-wiki-gist|Karpathy original gist]]** = **canonical-Google-OKF canonical-standardizes canonical-Karpathy-pattern at canonical-vendor-tier** = canonical-LLM-Wiki-Pattern canonical-mainstream-recognition canonical-milestone canonical-similar-to canonical-Loop-Engineering canonical-Andrew-Ng canonical-mainstream-validation Jun 30.
- **Pairs structurally with [[moysei-karpathy-llm-wiki-pattern-amplification-2026-06-23|Moysei canonical-Karpathy-LLM-Wiki-Pattern amplification]]** = canonical-LLM-Wiki-Pattern canonical-validation-cluster canonical-extension to **canonical-6-tier**: (1) Karpathy primary + (2) Reddit practitioner + (3) Hornof dogfooding + (4) Moysei amplifier + (5) 4-voice comment-thread + **(6) Google OKF canonical-vendor-tier canonical-standardization**.
- **Pairs structurally with [[google-agents-cli-launch-akshay-pachaar-walkthrough-2026-06-27|Google Agents CLI Jun 27]] + [[google-agents-cli|google-agents-cli entity page]]** = canonical-Google-Cloud canonical-agent-platform canonical-2-event-Jun-2026 canonical-cluster (Agents CLI Jun 27 + OKF spec Jun 12 published + article Jun 30) = canonical-Google canonical-canonical-vendor-neutral canonical-open-standard canonical-strategic-positioning.
- **Pairs structurally with [[gregisenberg-ai-native-company-context-layer-2026-06-27|Greg Isenberg canonical-shared-context-layer thesis Jun 27]]** = canonical-OKF canonical-implements canonical-Isenberg canonical-shared-context-layer canonical-thesis at canonical-Google-vendor-tier (canonical-Isenberg-shared-context-layer canonical-personal-tier + canonical-Cherny-5-archetype canonical-Anthropic-organizational-tier + canonical-OKF canonical-Google-vendor-tier + canonical-Ng-3-loop canonical-mainstream-AI-education-tier).
- **Pairs structurally with [[concepts/company-brain|Company Brain concept]] + [[ashwingop|Ashwin Gopalakrishnan]] + [[eric-siu-single-brain-5-layer-company-brain-2026-05-29|Eric Siu Single Brain]]** = canonical-2-tier canonical-context-layer canonical-pattern-cluster (canonical-Company-Brain canonical-organizational-tier + canonical-OKF canonical-format-tier canonical-cross-project-any-agent-tier).
- **Pairs structurally with [[dac|bruin-data/dac SKILL.md canonical-cross-coding-agent-pattern]]** = canonical-format-substrate canonical-canonical-cross-agent-compatibility canonical-vendor-tier canonical-3-vendor-cluster (dac + Google Agents CLI + OKF-skills-plugin).

**Canonical-LLM-Wiki-Pattern canonical-mainstream-standardization canonical-milestone-arc canonical-2026-Q2**:

- Canonical-Karpathy canonical-primary (Medium + gist canonical-foundational, canonical-original-articulation)
- Canonical-Reddit canonical-practitioner canonical-weekend-build canonical-early-validation
- Canonical-Hornof canonical-this-wiki canonical-owner-built canonical-dogfooding-instance
- Canonical-Moysei canonical-articulation Jun 23 = canonical-practitioner-amplifier canonical-tier
- Canonical-4-voice canonical-comment-thread canonical-amplification-cluster
- **Canonical-Google canonical-OKF canonical-open-standard canonical-vendor-tier canonical-2026-06-12 canonical-standardization canonical-milestone-event** ← canonical-canonical-culmination-arc

**Canonical-directly-actionable-for-this-wiki canonical-recommendation-cluster**:

- Consider canonical-adopting-OKF-format-conventions for canonical-frontmatter-consistency across canonical-this-wiki's canonical-tools + concepts + companies + models directories.
- Consider canonical-installing-okf-skills-plugin (`npx skills add scaccogatto/okf-skills`) for canonical-validation + canonical-visualization canonical-tooling-integration.
- Canonical-cross-reference canonical-OKF-mental-model (canonical-CLAUDE.md-behave + canonical-OKF-knows + canonical-MCP-calls) with canonical-this-wiki's canonical-CLAUDE.md canonical-workflow-instructions vs canonical-source-pages-and-entity-pages canonical-knowledge canonical-distinction.

**Pattern-watch escalations for next lint**:

- **OKF (concepts/okf.md or tools/okf.md)**: STRUCTURALLY MAJOR canonical-Google-Cloud canonical-open-standard canonical-launch canonical-1-substantive-surface but canonical-directly-relevant-to-this-wiki canonical-substrate-tier-exception canonical-recommendation = canonical-entity-page-candidate at next lint
- **Akhilvallala canonical-Medium-author**: canonical-primary-OKF-explainer canonical-single-source-defer + canonical-pattern-watch for 2nd substantive surface
- **scaccogatto canonical-okf-skills-plugin canonical-marketplace-vendor**: canonical-single-source-defer + canonical-plugin-tooling canonical-pedigree pattern-watch

## Pages Updated

- [[index]] — Recent ingests entry added
- Verification-pending consideration: canonical-this-wiki's `CLAUDE.md` canonical-workflow-instructions canonical-update to canonical-reference-OKF-3-answer-mental-model (canonical-behave + canonical-knows + canonical-calls) — canonical-owner-decision-required

## Resources

- Akhilvallala Medium: [Google Just Quietly Released the Missing Piece for AI Agents. It's Called OKF](https://medium.com/@akhilvallala0115/google-just-quietly-released-the-missing-piece-for-ai-agents-its-called-okf-7e96a33898ce)
- OKF spec: verification-pending canonical-Google-Cloud canonical-official-publication-URL
- okf-skills plugin: `scaccogatto/okf-skills` canonical-npm + canonical-Claude-Code-plugin-marketplace
- [[concepts/llm-wiki-pattern]] — paired canonical-Karpathy-LLM-Wiki-Pattern canonical-standardization-target
- [[karpathy-llm-wiki-overview]] — paired canonical-Karpathy-primary canonical-source
- [[karpathy-llm-wiki-gist]] — paired canonical-Karpathy-primary canonical-source
- [[andrej-karpathy]] — paired canonical-Karpathy-direct-voice
- [[moysei-karpathy-llm-wiki-pattern-amplification-2026-06-23]] — paired canonical-Karpathy-pattern-amplifier
- [[google-agents-cli-launch-akshay-pachaar-walkthrough-2026-06-27]] — paired canonical-Google-Cloud canonical-agent-platform canonical-2-event-cluster
- [[google-agents-cli]] — paired canonical-Google-Cloud canonical-agent-tooling
- [[gregisenberg-ai-native-company-context-layer-2026-06-27]] — paired canonical-shared-context-layer canonical-thesis-implementation
- [[concepts/company-brain]] — paired canonical-organizational-tier canonical-context-layer
- [[ashwingop]] — paired canonical-Sentra-Company-Brain canonical-organizational-tier
- [[eric-siu-single-brain-5-layer-company-brain-2026-05-29]] — paired canonical-Company-Brain canonical-organizational-tier
- [[dac]] — paired canonical-format-substrate canonical-cross-coding-agent canonical-pattern
- [[claude-code]] — paired canonical-okf-skills-plugin canonical-primary-target-substrate

## Verification-Pending

- OKF canonical-official-Google-Cloud canonical-launch-announcement canonical-URL + canonical-blog-post
- OKF canonical-GitHub-repo canonical-URL + canonical-official-spec canonical-canonical-file
- OKF canonical-3-sample-bundles canonical-GitHub-URLs (GA4 + Stack Overflow + Bitcoin)
- scaccogatto canonical-vendor-background + canonical-plugin-maintainer canonical-status (canonical-Google-employee vs canonical-community-plugin)
- Akhilvallala canonical-bio + canonical-Medium-author canonical-context
- canonical-OKF-adoption canonical-early-metrics (canonical-GitHub-stars + canonical-plugin-installs)
- canonical-BigQuery-enrichment-agent canonical-GitHub-URL + canonical-availability-tier (canonical-GA-vs-preview)
- canonical-Google-Knowledge-Catalog canonical-OKF-integration canonical-detail
