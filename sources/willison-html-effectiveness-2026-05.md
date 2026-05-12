---
title: Using Claude Code — The Unreasonable Effectiveness of HTML (Willison commentary)
type: source
medium: article
url: https://simonwillison.net/2026/May/8/unreasonable-effectiveness-of-html/
ingested: 2026-05-11
---

## Summary

[[simon-willison]] post (May 8 2026) surfacing a longform piece by [[thariq-shihipar]] (Anthropic, Claude Code team) titled "Using Claude Code: The Unreasonable Effectiveness of HTML." The core pattern Thariq documents: **ask [[claude-code]] to return HTML instead of Markdown** for any task where the consumer is going to look at the output in a browser, an IDE preview, or Claude.ai's own renderer. Concrete examples include sortable tables, collapsible trees, live calculators, and styled output — all generated from a single prompt shift.

## Key Claims / Takeaways

- **HTML beats Markdown for interactive / rendered outputs**: Markdown's flat-text rendering ceiling caps the output quality when the consumer is a real UI surface. HTML hits the actual rendering substrate the user is going to see.
- **The pattern is a prompt-level swap, not a tooling change**: "Return as HTML, not Markdown." No SDK changes, no plugin, no skill — just a format specifier in the prompt.
- **Claude generates valid HTML more reliably than most humans write it** (Thariq's framing): the model has been trained on enough HTML and CSS that hand-coded "tasteful Markdown" is a strictly worse target.
- **Surface for the wiki**: applies to [[claude-code]] specifically (because that's where Thariq's examples are sourced), but the underlying technique is host-agnostic — works in Claude.ai chats, [[claude-desktop]] artifacts, and Claude Code's terminal preview equally.
- **Willison's role here is amplification + practitioner-test**: he confirms the pattern works in his own usage. Treats it as a near-zero-cost upgrade to default prompting habits.
- **Counterpoint to the prevailing "Markdown is the lingua franca of LLMs" assumption**: useful for thinking about output-format prompting more generally — *match the format to the renderer*, don't default to Markdown out of habit.

## Companion Amplification (Karpathy, same day)

[[andrej-karpathy]] independently amplified Thariq's article on May 8 2026 ([[karpathy-html-output-taxonomy-2026-05-08]]), extending the practitioner pattern into a 4-step output-format taxonomy (raw text → markdown → HTML → ... → interactive neural videos). Two high-signal voices (Willison + Karpathy) surfaced the same article on the same day from different angles — the Willison post focuses on the practitioner pattern in [[claude-code]]; the Karpathy thread places HTML in a longer trajectory toward [[model-rendered-ui]].

## Why This Matters for the Wiki

First wiki appearance of [[thariq-shihipar]] as a tracked Anthropic-side practitioner voice. Concrete prompt-engineering pattern with practitioner validation from a high-signal independent ([[simon-willison]]) — exactly the kind of pattern this wiki tracks under [[claude-code]] community sentiment / practitioner patterns. Adjacent to [[claude-cowork]]'s artifact-first surface design.

## Pages Updated

- [[thariq-shihipar]] — new person page
- [[claude-code]] — HTML output pattern added under Practitioner Patterns
- [[simon-willison]] — additional notable take added (HTML-over-Markdown amplification)
