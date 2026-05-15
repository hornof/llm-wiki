---
title: 'Santiago Valdarrama (svpino): "Markdown was doomed from the start" + bruin-data/dac'
type: source
medium: twitter-thread
url: https://x.com/svpino/status/2055296002169671940
ingested: 2026-05-15
---

## Summary

[[people/svpino|Santiago Valdarrama]] (@svpino) X post, 2026-05-15, restating the HTML-over-Markdown thesis and introducing **[[tools/dac|bruin-data/dac]]** — an open-source **Dashboard-as-Code** tool: define dashboards in YAML or TSX, the tool serves HTML; ships **`SKILL.md` for both Claude Code AND Codex** out of the box. Database support: Postgres, MySQL, Snowflake, BigQuery, Redshift, Databricks. Continues the [[willison-html-effectiveness-2026-05|HTML-over-Markdown practitioner thread]] (Thariq Shihipar / Karpathy / Willison May 8) with a *concrete tool* rather than just a prompt-level pattern. Comment thread shows the thesis is now contested — Andrii Artemenko: *"Markdown wins on agent readability, human readability, and token efficiency. It beats HTML on almost any metric that matters."*

## Key Claims / Takeaways

### svpino's verbatim claim

> "Markdown was doomed from the start. It's just a format with low information density. HTML is better for humans, and agents can now consume and produce it without issues."

> "But nobody wants to type HTML, so here is an alternative: [DaC]"

### The pivot — "nobody wants to type HTML"

svpino's move is the most pragmatic statement of the HTML thesis to date: **HTML wins on rendering substrate, but is too verbose for humans to author by hand**. Solution: keep HTML as the output substrate; let agents *generate* HTML from a denser intermediate (YAML or TSX). This is structurally the same move as [[karpathy-html-output-taxonomy-2026-05-08|Karpathy's 4-step output-format taxonomy]] (raw text → markdown → HTML → interactive neural videos) — but instantiated as a shipped tool, not a framing.

### DaC specifics ([[tools/dac]])

- **AGPL-3.0**; bruin-data org on GitHub.
- **Built-in semantic layer**: define metrics + dimensions in `semantic/`, reference from any widget; DaC generates the SQL.
- **Codex AI agent built-in**: chat with your dashboard live, get it updated.
- **Skill installation**: `dac init` installs bundled `SKILL.md` at `.claude/skills/create-dashboard/SKILL.md` AND `.codex/skills/create-dashboard`. The dual-harness shipping is the structurally novel detail — first wiki capture of a tool that **ships SKILL.md for Claude Code *and* Codex** in the same package.
- Shells out to **Bruin CLI** for query execution against connected warehouses.

### Practitioner counter-takes (comment thread)

- **Andrii Artemenko** (@andrii_arte): *"Markdown wins on agent readability, human readability, and token efficiency. It beats HTML on almost any metric that matters."* — first wiki-captured counter to the HTML-over-Markdown thesis.
- **0xVibly**: *"Markdown won on convenience, not capability, and that tradeoff looks painfully outdated once agents can handle real structure."* — sides with svpino but more pragmatically; convenience-vs-capability framing.
- **dnu (@DnuLkjkjh)**: *"agents make html way less scary. markdown leaks structure fast."* — names the failure mode (Markdown loses structure under depth).
- **Daniel Moll**: *"you can manage a lot more semantics with HTML that is not possible with markdown."*

The thesis is no longer one-sided. The wiki should track this as a *practitioner-divided* question, not a settled one.

## Why It Matters

- **First wiki capture of a tool that ships dual-harness SKILL.md** (Claude Code + Codex in the same package). The implication: skill-as-shipped-package is becoming a vendor-portability primitive. Prior wiki coverage of the SKILL.md ecosystem ([[zodchiii-anatomy-perfect-skill]], [[julian-goldie-notebooklm-skills-factory]], [[heygurisingh-career-ops]]) was Claude-Code-specific; DaC's posture is "we ship to both major harnesses by default."
- **The "nobody wants to type HTML" pivot is the right move on the HTML thesis.** Treating HTML as the *output substrate* and YAML/TSX as the *input language* resolves the obvious objection ("HTML is verbose") without giving up the rendering-substrate advantage. Pairs with [[karpathy-html-output-taxonomy-2026-05-08]] as the practitioner-instantiated version of the four-step taxonomy.
- **First captured counter-take on HTML-over-Markdown.** Until this post, the wiki's HTML-over-Markdown thread was one-sided (Thariq Shihipar → Karpathy → Willison → DaC). Andrii Artemenko's *"token efficiency"* counter is the load-bearing objection: HTML costs more per equivalent semantic unit. This needs to enter the [[claude-code]] / [[model-rendered-ui]] discussion before the thesis gets propagated further as settled.
- **svpino as a first-wiki-capture practitioner voice.** Santiago Valdarrama (@svpino) is a popular AI/ML educator with sustained X reach. Worth a `people/svpino` page for future amplification tracking.
- **Bruin (the parent) as an agent-friendly data-platform pattern.** The Bruin CLI + DaC pair sketches a "data platform whose primary user is an agent" — a category worth tracking distinct from "data platform with AI features bolted on" (Snowflake Cortex, Databricks Mosaic, etc.).

## Cross-references

- [[people/svpino]] — author (new people page).
- [[tools/dac]] — bruin-data/dac; new tool page.
- [[willison-html-effectiveness-2026-05]] — Thariq Shihipar's original HTML-over-Markdown thesis; this source continues the thread.
- [[karpathy-html-output-taxonomy-2026-05-08]] — Karpathy's 4-step output-format taxonomy; DaC is the practitioner-instantiated version of step 3 (HTML).
- [[model-rendered-ui]] — long-arc framing; DaC sits at the YAML/TSX-to-HTML compile layer.
- [[claude-md-pattern]] / [[zodchiii-anatomy-perfect-skill]] — SKILL.md ecosystem; DaC's dual-harness shipping is a portability signal worth tracking.

## Pages Updated

- [[people/svpino]] (new — Santiago Valdarrama; AI/ML educator on X; HTML-over-Markdown practitioner voice)
- [[tools/dac]] (new — bruin-data/dac; Dashboard-as-Code; YAML/TSX → HTML; semantic layer; dual-harness SKILL.md shipping)
- [[concepts/model-rendered-ui]] (updated — DaC as practitioner-instantiated version of Karpathy's step-3 HTML; "nobody wants to type HTML" pivot framing)
