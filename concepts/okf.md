---
name: Open Knowledge Format (OKF)
type: concept
maturity: emerging
last_updated: 2026-10-15
---

> [!key-insight] Google Cloud standardised the LLM Wiki pattern — and reserved the same two filenames
> **[[google-okf-open-knowledge-format-launch-2026-06-12|Google Cloud's OKF spec]]** (2026-06-12, Apache 2.0) takes [[andrej-karpathy|Karpathy's]] [[llm-wiki-pattern|LLM Wiki pattern]] and publishes it as a vendor-neutral open specification. **Both reserve `index.md` and `log.md`, for the same purposes** — which is the detail that makes the convergence hard to read as coincidence. **Directly actionable for this wiki**: whether to adopt OKF's frontmatter conventions, whether to install the `okf-skills` plugin, and whether the three-answer mental model below belongs in `CLAUDE.md`.

## Definition

**Open Knowledge Format (OKF)** is an **Apache 2.0 open specification published by Google Cloud on 2026-06-12** for representing agent memory as **a directory of markdown files with YAML frontmatter.**

Its design philosophy is **"format, not platform"**: no proprietary account, no SDK, no central registry. **The stated bet is that value scales with how widely the format is adopted rather than with lock-in** — the same argument made for git, markdown and JSON.

## Why It Matters

**It fills a specific gap: *"what does the team know about this system?"*** — a question neither of the adjacent conventions answers. The spec's own framing is a three-way split:

| Convention | Answers |
|---|---|
| **CLAUDE.md** | *how should the agent behave?* |
| **OKF** | *what does the team know about this system?* |
| **MCP** | *what live tools can the agent call right now?* |

**That taxonomy is the most useful thing in the spec**, and it is why the key-insight above flags it for `CLAUDE.md` integration — this wiki currently answers the first and third questions implicitly and the second one by accident.

### Three design principles

1. **Minimally opinionated** — only the `type` frontmatter field is required. Which types exist is the producer's choice; the spec suggests Service, Dataset, Metric, Decision, Runbook.
2. **Producer and consumer independence** — the same format works at both ends. Authors can be humans, BigQuery pipelines, LLMs or wiki exports; consumers can be AI agents, HTML visualisers, search indexes or other tools.
3. **Format, not platform** — no SDK required.

## Current State

### The directory *is* the knowledge graph

- **A file's path is the concept's identity.**
- **Two reserved files in every bundle**: `index.md` is the progressive-disclosure entry point; `log.md` is an ISO-dated change history, newest first.
- **Concepts link to each other with ordinary markdown links**, which makes the directory a graph — and means **any tool that can follow a markdown link can traverse it.**

### What Google Cloud shipped alongside the spec

1. **A BigQuery enrichment agent** — walks a dataset, drafts OKF concept docs, then a second LLM pass enriches them with citations, schemas and join paths.
2. **A static HTML visualiser** — turns any OKF bundle into an interactive graph view as a single self-contained file.
3. **Three sample bundles on GitHub** — GA4 e-commerce, Stack Overflow and Bitcoin, all from public BigQuery datasets.

### The `okf-skills` plugin (third-party, `scaccogatto`)

| Command | Does |
|---|---|
| `/okf:okf` | produce and maintain bundles |
| `/okf:validate` | conformance checks |
| `/okf:visualize` | generate the interactive graph |

Install: `npx skills add scaccogatto/okf-skills`. Works across Claude Code, Cursor, Codex and 20+ other agents.

## OKF vs related patterns

| Tool | Purpose | Scope |
|---|---|---|
| CLAUDE.md | How the agent behaves | Per-project, one agent |
| AGENTS.md | Repo instructions | Per-repo, tool-specific |
| **[[llm-wiki-pattern\|Karpathy LLM Wiki Pattern]]** | **Agent-maintained notes** | **A pattern, not a spec** |
| MCP | Live tool access | Runtime connections |
| **OKF** | **What the team knows** | **Cross-project, any agent** |

## The Karpathy connection, layer by layer

[[andrej-karpathy|Karpathy's]] LLM Wiki gist (5,000+ stars) maps onto OKF in three layers:

| Karpathy | OKF |
|---|---|
| **Raw sources, immutable** | external datasets, docs and APIs — OKF bundles are the *compiled* layer |
| **Wiki, LLM-maintained** | the OKF bundle itself (`*.md` plus frontmatter; OKF adds `type`, `resource`, `tags`, `timestamp`) |
| **Schema in CLAUDE.md** | producer/consumer conventions plus `okf/SPEC.md` — **an org-wide spec replacing per-vault bespoke rules** |

**Both reserve `index.md` and `log.md` for the same purposes.** Two independent designs arriving at the same two filenames is the strongest evidence the wiki holds that this is a real pattern rather than one person's taste.

## How the pattern accumulated validation

Six surfaces, in order:

1. **Karpathy's primary** — the Medium post and gist.
2. **A Reddit practitioner's weekend build** — earliest independent instance.
3. **This wiki** — the owner's own dogfooding instance.
4. **Moysei's articulation** (2026-06-23) — practitioner amplification.
5. **A four-voice comment thread** around it.
6. **Google Cloud's OKF spec** (2026-06-12) — **a vendor publishing it as an open standard**, which is where a pattern becomes infrastructure.

## When to Use OKF

**A good fit when:**

- You re-explain the same things to every new agent session.
- Your knowledge spans multiple projects or teams.
- You want project docs to be versionable.
- You are building on Google Cloud and BigQuery.
- You want a knowledge graph rather than a flat wiki.

**The wrong tool when:**

- You need real-time data — **use MCP.**
- You need to encode behavioural rules — **use CLAUDE.md.**
- The project is small and single-session — **CLAUDE.md is enough.**

## Related Concepts

- [[llm-wiki-pattern]] — the parent pattern OKF standardises
- [[company-brain]] — the organisational-scale version of the same context layer
- [[karpathy-llm-wiki-overview]], [[karpathy-llm-wiki-gist]] — Karpathy's primaries

## Resources

- [[google-okf-open-knowledge-format-launch-2026-06-12]] — the primary source held (an Akhilvallala Medium explainer)

## Verification-pending

- **Google Cloud's official blog post and the GitHub repo** — the wiki has a third-party explainer, not the spec itself.
- **Whether this wiki should adopt OKF conventions**, which is the actionable question and has been open since 2026-06-12.

> [!note] Rewritten 2026-10-15
> The 2026-07-01 version carried **46 instances of `canonical-` filler** from an automated pass — the worst in the corpus, measured at the 2026-10-15 lint. Content preserved, prose rewritten; two path-form wikilinks (`[[concepts/llm-wiki-pattern]]`, `[[concepts/company-brain]]`) corrected to slug-form per `CLAUDE.md` conventions. See lint rule 7.

*(2026-10-21 backlog triage: 1 item removed. Low value; the spec itself is the open item.)*

