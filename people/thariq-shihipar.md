---
name: Thariq Shihipar
type: person
affiliation: Anthropic (Claude Code team)
signal_sources: [blog, twitter]
last_updated: 2026-06-02
twitter: "@trq212"
---

## Who They Are

Member of the [[claude-code]] team at [[anthropic]]. Author of "Using Claude Code: The Unreasonable Effectiveness of HTML" — a practitioner-grade post documenting how [[claude-code]] produces better, more interactive outputs when the user asks for HTML instead of Markdown. Surfaced into the wiki via [[simon-willison]]'s May 8 2026 amplification.

## Their Current Focus

- Practitioner-facing patterns for getting useful output out of [[claude-code]].
- Output-format prompting: matching the format to the renderer rather than defaulting to Markdown.

## Notable Takes

- **HTML > Markdown for any rendered consumer (May 8 2026)**: ask Claude Code to return HTML when the output will be viewed in a browser, IDE preview, or Claude.ai renderer. Markdown's flat-text ceiling caps quality; HTML hits the actual rendering substrate. Includes concrete examples: sortable tables, collapsible trees, live calculators. — [[willison-html-effectiveness-2026-05]]
- **"Claude generates valid HTML more reliably than most humans write it"**: trust the model on format; hand-coded "tasteful Markdown" is a strictly worse target when HTML is available.

## Amplification History

Thariq's article triggered two independent amplifications inside ~72 hours:

- **[[andrej-karpathy]] (May 8 2026, [[karpathy-html-output-taxonomy-2026-05-08]])**: quote-tweets Thariq, confirms the pattern works ("This works really well btw"), and extends it into a 4-step output-format taxonomy (raw text → markdown → HTML → ... → interactive neural videos). Bridges the Thariq practitioner pattern to the [[model-rendered-ui]] research direction.
- **[[simon-willison]] (May 8 2026, [[willison-html-effectiveness-2026-05]])**: independent blog amplification with practitioner-test confirmation.

Two high-signal voices independently surfaced the same article on the same day — strong validation signal for the underlying technique, and the trigger for the wiki to add HTML-output prompting as a tracked [[claude-code]] practitioner pattern.

## 2nd Surface: Suzanne's Learn Quiz Pattern (2026-06-01)

[[trq-suzanne-learn-quiz-2026-06-01]] — Thariq shares a colleague's *Learn Quiz* prompt (used after Claude completes work in a session to *quiz the operator on what was just done*). **First wiki-captured concrete Anthropic-internal Claude-usage practice** surfacing from a non-employee-position-paper, non-cookbook surface. Pairs with [[nateherk-opus-4-8-aios-2026-05-29|Nate Herk's `/session-handoff`]] as the *comprehension-side* complement to the *resume-side* session-management primitive.

Establishes Thariq as a **practitioner-content surfacing role** for Anthropic-internal practices — pairs with his original *Unreasonable Effectiveness of HTML* surfacing role (May 2026).

## Where to Follow

- Personal blog (surfaced via Willison amplification)
- Twitter / X: [@trq212](https://x.com/trq212)
