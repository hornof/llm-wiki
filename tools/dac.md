---
name: DaC (bruin-data/dac)
type: tool
category: framework
status: emerging
last_updated: 2026-05-15
---

## What It Is

**DaC** (Dashboard-as-Code, by bruin-data) is an open-source tool for defining, validating, and serving interactive dashboards from **YAML** or **TSX**, with a **built-in semantic layer** (metrics + dimensions defined once in `semantic/`, referenced from any widget; DaC generates the SQL). Built specifically for **AI agents to author dashboards reliably**. Database support spans Postgres, MySQL, Snowflake, BigQuery, Redshift, Databricks (via the **Bruin** CLI for query execution). AGPL-3.0; GitHub at [bruin-data/dac](https://github.com/bruin-data/dac).

Surfaced on this wiki via [[svpino-bruin-dac-markdown-doomed-2026-05-15|Santiago Valdarrama's X post]] framing it as the practitioner instantiation of the HTML-over-Markdown thesis: HTML is the output substrate, YAML/TSX is the human-and-agent-friendly input.

## Traction Signals

- **Dual-harness `SKILL.md` shipping**: `dac init` installs the bundled `create-dashboard` skill at **both** `.claude/skills/create-dashboard/SKILL.md` **and** `.codex/skills/create-dashboard`. **First wiki capture of a tool that ships SKILL.md for Claude Code *and* Codex in the same package.** The dual-shipping is the structurally novel detail — vendor-portability for skill packages.
- **Built-in Codex AI agent**: chat-with-your-dashboard-live primitive built into the tool, not just installable.
- **svpino surfacing (May 15 2026)** as the practitioner-instantiated version of the HTML-over-Markdown thread — [[svpino-bruin-dac-markdown-doomed-2026-05-15]].

## How to Use It

```bash
# Install (stable)
curl -fsSL https://raw.githubusercontent.com/bruin-data/dac/main/install.sh | bash

# Quickstart
dac init my-dashboards
cd my-dashboards
dac validate --dir .
dac validate --dir . --with-database
dac serve --dir . --open
```

The `dac init` starter includes (a) a SQL-backed YAML dashboard, (b) a semantic YAML dashboard, (c) a semantic model under `semantic/`, and (d) the bundled SKILL.md for both Claude Code and Codex.

Bundled examples in `examples/`: `basic-yaml`, `basic-tsx`, `semantic-yaml`, `semantic-tsx`.

## Key Concepts

- **Dashboard-as-Code** — dashboards as source-controlled artifacts (YAML or TSX), reviewable like code; agent-authored dashboards become diff-able and policy-checkable.
- **Semantic layer** — metrics + dimensions defined in `semantic/`, referenced from widgets; DaC generates the SQL. Decouples *what* a metric means from *how* it's computed at the warehouse layer.
- **TSX dashboards** — load-time queries can generate layout from the database; dynamic charts, tabs, loops, conditionals.
- **Bundled SKILL.md** — `.claude/skills/create-dashboard/SKILL.md` and `.codex/skills/create-dashboard`. Agent has authoring conventions installed alongside the runtime.

## Compared To

- **Metabase / Superset / Looker / Mode** — traditional BI dashboard tools; UI-first, not designed for agent authoring. DaC's posture inverts this: agent-first authoring, YAML/TSX as the *human and agent surface*, rendered HTML as the *consumer surface*.
- **dbt + Metabase** — semantic layer + dashboard tool composed externally; DaC bundles both.
- **Streamlit / Dash / Gradio** — Python-code-as-dashboard; closer in spirit but lacks the semantic-layer + multi-warehouse story.

## Resources

- [bruin-data/dac on GitHub](https://github.com/bruin-data/dac) — primary repository
- [[svpino-bruin-dac-markdown-doomed-2026-05-15]] — practitioner-surfacing source
- [[people/svpino]] — surfacer
- [[willison-html-effectiveness-2026-05]] / [[karpathy-html-output-taxonomy-2026-05-08]] — broader HTML-over-Markdown thread
- [[model-rendered-ui]] — long-arc framing for HTML-as-output substrate
