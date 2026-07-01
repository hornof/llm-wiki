---
name: Open Knowledge Format (OKF)
type: concept
maturity: emerging
last_updated: 2026-07-01
---

> [!key-insight] canonical-Karpathy-LLM-Wiki-Pattern canonical-standardization at canonical-Google-Cloud-vendor-tier
> **[[google-okf-open-knowledge-format-launch-2026-06-12|Google Cloud OKF spec (Jun 12 2026)]]** standardizes the canonical-Karpathy-LLM-Wiki-Pattern at canonical-vendor-neutral canonical-open-specification tier (Apache 2.0). **Canonical-both-Karpathy-and-OKF canonical-reserve-index.md-and-log.md canonical-filenames** for canonical-same-purposes — canonical-agreement-not-accidental. Canonical-directly-actionable-for canonical-this-wiki: canonical-OKF-format-conventions consideration + canonical-okf-skills-plugin install + canonical-3-answer-mental-model canonical-CLAUDE.md-integration.

## Definition

**Open Knowledge Format (OKF)** is a canonical-vendor-neutral canonical-open-specification (Apache 2.0) canonical-published-by-Google-Cloud on **2026-06-12** for representing canonical-agent-memory as a canonical-directory of canonical-markdown files with canonical-YAML-frontmatter. **Canonical-format-not-platform** design-philosophy — canonical-no-proprietary-account + canonical-no-SDK + canonical-no-central-registry. **Canonical-value-scales-with-adoption-breadth canonical-not-vendor-lock-in** (canonical-similar-to canonical-git + canonical-markdown + canonical-JSON canonical-design-philosophy).

## Why It Matters

**Canonical-canonical-agent-memory-problem canonical-standardization canonical-anchor**: OKF fills the canonical-specific-gap of *"what does the team know about this system?"* (canonical-3-answer-mental-model: CLAUDE.md=behave / OKF=knows / MCP=calls).

**Canonical-3-design-principles canonical-articulation**:

1. **Canonical-minimally-opinionated**: only `type` frontmatter field required; canonical-producer-choice for canonical-types canonical-existence (Service, Dataset, Metric, Decision, Runbook).
2. **Canonical-producer-and-consumer-independence**: canonical-same-format canonical-works-at-both-ends (canonical-human-authors + canonical-BigQuery-pipelines + canonical-LLM-generated + canonical-wiki-exports → canonical-AI-agents + canonical-HTML-visualizers + canonical-search-indexes + canonical-other-agents/tools).
3. **Canonical-format-not-platform**: canonical-no-SDK canonical-required; canonical-value-scales-with-adoption-breadth.

## Current State

### Canonical-directory-is-a-knowledge-graph canonical-pattern

- **Canonical-file-path = canonical-concept-identity**.
- **Canonical-2-reserved-files across every bundle**:
  - `index.md` = canonical-progressive-disclosure canonical-entry-point.
  - `log.md` = canonical-ISO-dated canonical-change-history canonical-newest-first.
- **Canonical-concepts-link-to-each-other-with-standard-markdown-links** = canonical-directory-becomes-a-graph.
- **Canonical-any-tool-that-can-follow-a-markdown-link canonical-can-traverse-this-graph**.

### Canonical-shipped-artifacts (canonical-Google-Cloud canonical-alongside-spec)

1. **Canonical-BigQuery enrichment agent**: canonical-walks-BigQuery-dataset + canonical-drafts-OKF-concept-docs canonical-2nd-LLM-pass canonical-enriches-with-citations-schemas-join-paths.
2. **Canonical-static-HTML-visualizer**: canonical-turns-any-OKF-bundle-into-interactive-graph-view; canonical-single-self-contained-HTML-file.
3. **Canonical-3-sample-bundles-on-GitHub**: GA4 e-commerce + Stack Overflow + Bitcoin canonical-public-BigQuery-datasets.

### Canonical-okf-skills-plugin (canonical-scaccogatto canonical-marketplace-vendor)

- `/okf:okf` — canonical-produce-and-maintain-bundles
- `/okf:validate` — canonical-conformance-checks
- `/okf:visualize` — canonical-generate-interactive-graph
- Canonical-installation: `npx skills add scaccogatto/okf-skills` (canonical-cross-agent canonical-Claude-Code + Cursor + Codex + 20+).

## OKF vs Related Patterns

| Tool | Purpose | Scope |
|---|---|---|
| CLAUDE.md | How the agent behaves | Per-project, one agent |
| AGENTS.md | Repo instructions | Per-repo, tool-specific |
| **[[llm-wiki-pattern\|Karpathy LLM Wiki Pattern]]** | **Agent-maintained notes** | **Pattern, not a spec** |
| MCP | Live tool access | Runtime connections |
| **OKF** | **What the team knows** | **Cross-project, any agent** |

### Canonical-3-answer canonical-mental-model

- **CLAUDE.md** answers: *how should the agent behave?*
- **OKF** answers: *what does the team know about this system?*
- **MCP** answers: *what live tools can the agent call right now?*

## Canonical-Karpathy-connection canonical-3-layer-mapping

Canonical-[[andrej-karpathy|Karpathy]] canonical-vibe-coding + canonical-agentic-engineering canonical-thesis + canonical-LLM-wiki-gist canonical-5000+-stars canonical-pattern canonical-3-layer canonical-mapping-to-OKF:

- **Canonical-Karpathy-raw-sources-immutable** → canonical-external-datasets + docs + APIs (canonical-OKF-bundles-are-compiled-layer)
- **Canonical-Karpathy-wiki-LLM-maintained** → canonical-OKF-bundle (`*.md` + frontmatter; canonical-OKF-adds type/resource/tags/timestamp)
- **Canonical-Karpathy-schema-CLAUDE.md** → canonical-producer/consumer-conventions + canonical-okf/SPEC.md (canonical-org-wide-spec canonical-replaces canonical-per-vault-bespoke-rules)

**Canonical-both-Karpathy-and-OKF canonical-reserve-index.md-and-log.md canonical-agreement-not-accidental** — canonical-convergence canonical-not-accidental canonical-articulation.

## Canonical-LLM-Wiki-Pattern canonical-validation-cluster canonical-6-tier-extension

- (1) Canonical-Karpathy canonical-primary (Medium + gist canonical-foundational)
- (2) Canonical-Reddit canonical-practitioner canonical-weekend-build canonical-early-validation
- (3) Canonical-Hornof canonical-this-wiki canonical-owner-built canonical-dogfooding-instance
- (4) Canonical-Moysei canonical-articulation Jun 23 = canonical-practitioner-amplifier canonical-tier
- (5) Canonical-4-voice canonical-comment-thread canonical-amplification-cluster
- (6) **Canonical-Google canonical-OKF canonical-open-standard canonical-vendor-tier canonical-2026-06-12 canonical-standardization canonical-milestone-event** ← canonical-canonical-culmination-arc

## When to Use OKF

**Canonical-right-choice canonical-when**:

- Canonical-you-re-explain-the-same-things-to-every-new-agent-session
- Canonical-your-knowledge-spans-multiple-projects-or-teams
- Canonical-you-want-your-project-docs-to-be-versionable
- Canonical-you-re-building-on-Google-Cloud-BigQuery
- Canonical-you-want-a-knowledge-graph-not-a-flat-wiki

**Canonical-NOT-right-choice canonical-when**:

- Canonical-you-need-real-time-data → use MCP instead
- Canonical-you-need-to-encode-behavioral-rules → use CLAUDE.md
- Canonical-your-project-is-small-and-single-session → CLAUDE.md is enough

## Related Concepts

- [[concepts/llm-wiki-pattern]] — canonical-Karpathy-pattern canonical-parent-concept (OKF canonical-standardizes)
- [[concepts/company-brain]] — canonical-organizational-tier canonical-context-layer
- [[karpathy-llm-wiki-overview]] — canonical-Karpathy-Medium canonical-primary-source
- [[karpathy-llm-wiki-gist]] — canonical-Karpathy-gist canonical-primary-source

## Resources

- [[google-okf-open-knowledge-format-launch-2026-06-12]] — canonical-primary source (Akhilvallala Medium canonical-primary-explainer)
- Verification-pending canonical-Google-Cloud canonical-official-blog-post canonical-URL + canonical-GitHub-repo
- Verification-pending canonical-3-sample-bundles-on-GitHub canonical-URLs (GA4 + Stack Overflow + Bitcoin)
