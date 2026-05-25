---
title: "Ruben Hassid: Claude Cowork 2.0 setup walkthrough + 100-tip LinkedIn summary"
type: source
medium: article
url: https://ruben.substack.com/p/claude-cowork-20
ingested: 2026-05-25
---

## Summary

Two layers of practitioner-content from **Ruben Hassid** captured together: (1) **"Cowork."** Substack post published 2026-04-07 (~7 weeks ago, freshly clipped) — concrete Cowork setup walkthrough with folder architecture + AskUserQuestion-based interview prompt + per-file purpose framing; (2) **LinkedIn 100-tip infographic post** (~1 month old) — 10-category summary covering Cowork setup, model selection, prompting, AskUserQuestion, connectors, plugins, Excel, projects/teams, artifacts, advanced mastery. **First wiki capture of Ruben Hassid as a tracked voice** (484,000-subscriber `how-to-ai.guide` newsletter; consistent high-engagement Claude-practitioner-content output across X and LinkedIn). **First wiki-canonical Cowork setup walkthrough.** Hassid framing repeatedly cross-confirms wiki-tracked patterns (CLAUDE.md-as-prerequisite + 200-line ceiling + behavioral-contract discipline).

## Key Claims / Takeaways

### Hassid's Cowork folder architecture (the load-bearing technical contribution)

Single **Claude Cowork** root folder with 3 (or 4) subfolders:

- **`ABOUT ME/`** — *"The only folder Cowork reads automatically."* Three core files:
  - **`about-me.md`** — *"Who you are. How you think. How you want Claude to write for you."* Trimmed from 22,000+ words to **under 2,000 words** (10× noise reduction). Hassid: *"I asked Claude to interview me through 100 questions"* originally; later trimmed.
  - **`anti-ai-style.md`** — what Claude must NOT do (the cleanest framing: *"80% of your file should be what you're NOT"*).
  - One more file (third core; specifics in the linked content).
- **`OUTPUTS/`** — Claude's results land here.
- **`TEMPLATES/`** — reusable scaffolds Claude can use.
- **`PROJECT/`** (added in 100-tip LinkedIn version) — per-project context.

**Critical practitioner framing**: *"Files are basically compressed prompts."* (How to AI comment on the LinkedIn version.)

### The AskUserQuestion-based about-me interview prompt (verbatim structure)

Hassid provides a substantial system prompt that instructs Cowork to **interview the user using `AskUserQuestion` (one question at a time, 15-20 questions)** then compile into a condensed `about-me.md` under 2,000 tokens. Six structured sections: **Who I Am** (3 questions) / **How I Work** (4 questions) / **What Good Looks Like** (4 questions) / **What You Hate** (4 questions) / **Your Rules** (3 questions) / **Your Opinions** (3 questions). Hard rules in the interview: *"If I give a vague answer, push back. Ask for a specific example or rephrase."*

Output structure: `# ABOUT ME: [Name]` → `## Who I am` / `## How I work` / `## What good looks like` / `## What I hate` / `## My rules` / `## Instructions for Claude` (10 numbered rules for how Claude must DO and NOT DO, derived from the interview).

**This is the cleanest single-prompt operationalization of the [[claude-md-pattern|CLAUDE.md behavioral-contract pattern]] captured for the Cowork surface specifically.** Pairs structurally with [[milesdeutscher-claude-personal-cfo-2026-05-14|Deutscher's Investor Strategy Architect 7-phase interview prompt]] for personal-finance domain — same pattern, different application.

### The 100-tip LinkedIn infographic (10 categories, 10 tips each)

Surveyed verbatim:

1. **Cowork Setup** — desktop app (not browser); single COWORK folder; 4 subfolders; download Hassid's anti-ai-style.md template.
2. **Pick the Right Model** — **"Opus 4.6 + Extended Thinking for complex tasks. Sonnet = quick edits. Haiku = scanning files. The model matters less than the prompt. Bad prompt on Opus > Great prompt on Haiku."** First wiki-captured Opus 4.6 + Extended Thinking framing as Cowork-canonical default.
3. **Prompting** — *"Stop writing long prompts. Files > prompts. One task per prompt. Say 'Does NOT sound like' to kill the AI voice. Give the task, not the method."*
4. **AskUserQuestion Tool** — *"Start with AskUserQuestion in all 1st prompts. Claude builds you a clickable form."* First wiki-captured framing of AskUserQuestion as the default first-prompt move.
5. **Connectors** — Settings → Connectors → Browse → Add. Slack, Google Drive, Notion, Gmail, 50+ tools. *"Free on all plans."*
6. **Plugins** — Cowork → Customize → Browse → Install. *"Marketing, Legal, Sales, Data — pick your role."*
7. **Claude in Excel** — "Claude by Anthropic" from Microsoft Marketplace. Reads every tab. *"Drop a PDF in. Claude extracts the tables. No macros."*
8. **Projects & Teams** — *"One Project per deliverable. Not per client. Upload a great example. It matches the standard."*
9. **Artifacts** — *"Charts, dashboards, trackers — inside the chat. They work automatically in Cowork. Share with non-Claude users as HTML."* Cross-confirms [[karpathy-html-output-taxonomy-2026-05-08|HTML-as-output framing]] at the Cowork-product level.
10. **Advanced Mastery** — *"Keep your files under 200 lines. Shorter is better. 80% of your file should be what you're NOT. Review outputs (especially financial). Claude does 80% busywork. You do the 20%."* — **first wiki-captured 200-line ceiling framing applied beyond CLAUDE.md** (carries forward to the about-me.md / anti-ai-style.md files in the ABOUT ME folder).

### Comment-thread payload (LinkedIn)

- **Karolis Balsiukevicius**: *"The '80% should be what you're NOT' tip is the one most people skip. Took me weeks to figure out that telling Claude who I am matters less than telling it who I'm not. My about-me file is mostly rules about what to avoid. Works way better."* — **first wiki-captured practitioner formalization of anti-style-instruction as the load-bearing CLAUDE.md / about-me content discipline.**
- **Robin Jose**: *"Anthropic's own Claude Code docs stay under 200 lines for a reason. The best abstraction isn't a bigger checklist; it's fewer decisions. Your 80-20. Ruben's 80 tips are great for beginners, but power users eventually collapse them back into 5 core moves."* — cross-confirms [[mnilax-claude-md-12-rules-2026-05-09|the 200-line ceiling]] from a different angle; explicit **beginner-tip-density → expert-collapse-back-to-5-moves** progression.
- **Nlink Tech**: *"The idea of using examples to set the standard is underrated. Models tend to mimic patterns better than they follow abstract instructions."* — Hassid replies: *"Those examples become the standard, and you won't have to prompt it every time."*

## Why It Matters

- **First wiki-canonical Cowork-specific setup walkthrough.** Prior wiki coverage of Cowork ([[claude-cowork]] entity page, [[milesdeutscher-claude-personal-cfo-2026-05-14|Deutscher CFO]], [[stahlberg-team-os-aakash-2026-05|Stulberg Team OS]]) treated Cowork as a substrate or surface; Hassid provides the **first canonical practitioner-content walkthrough** of how to actually set Cowork up.
- **Validates [[claude-md-pattern|the CLAUDE.md pattern]] at the Cowork-product surface** at every layer: minimal files, 200-line ceiling, anti-style instructions as load-bearing, examples > instructions. Pairs with [[shilpamitra-claude-code-30-commands-2026-05-22|ShilpaMitra Claude Code 30-command taxonomy]] (file-based behavioral contract) and [[stahlberg-team-os-aakash-2026-05|Stulberg Team OS]] (team-scale CLAUDE.md discipline). **The CLAUDE.md behavioral-contract pattern is now community-canonical across at least 5 independent practitioner surfaces.**
- **The anti-style-instruction framing ("80% should be what you're NOT")** is the **first wiki-captured formalization** of negative-instruction-as-primary in the CLAUDE.md / about-me layer. Pairs with [[claude-md-pattern|Karpathy's January 2026 thread]] naming three Claude failure modes — Hassid's framing extends from "name the failure modes" to "make 80% of the file about preventing them."
- **"Files > prompts"** as the practitioner-canonical operating model. Pairs with [[anthropic-claude-cookbook-2026-05|Anthropic Cookbook]] file-based primitives and [[code-mode]] runtime pattern.
- **AskUserQuestion-as-default-first-prompt** is the first wiki-captured framing of `AskUserQuestion` as a canonical Cowork first-move. Worth tracking whether this becomes community-canonical.
- **Hassid as a tracked voice**: 484,000-subscriber newsletter at `how-to-ai.guide`; consistent high-engagement Claude practitioner-content across X / LinkedIn / Substack. **Multiple substantive sources now warrant entity-page creation** (the "Cowork." Substack + the 100-tip LinkedIn post + the [[hassid-cant-beat-ai-cost-collapse-2026-05-18|"You can't beat AI" cost-collapse essay]] = three independent substantive Hassid surfaces).

## Caveats

- **Hassid is in the content-marketing register** — the LinkedIn post ends with five-step CTA back to `how-to-ai.guide` newsletter; the Substack ends with similar. **Treat the framework as substantive; the gated content as marketing-tier.**
- **Cowork.. substack post published 2026-04-07** — ~7 weeks ago. Treat as **mid-April practitioner-canonical** rather than current; Cowork has had updates in May ([[anthropic-agent-view-claude-code-2026-05-11|agent view in Claude Code]], etc.) that may not be reflected in Hassid's walkthrough.
- **Opus 4.6 + Extended Thinking** is Hassid's recommendation — pairs with [[shilpamitra-claude-code-30-commands-2026-05-22|the `/effort` primitive discipline]] but specific to Cowork's GUI surface rather than Claude Code's CLI. Reasonable default; not Anthropic-canonical.
- **200-line ceiling** is from [[mnilax-claude-md-12-rules-2026-05-09|Mnilax]] originally; Hassid is cross-confirming, not originating. **Anti-style framing** ("80% what you're NOT") is the most-clearly-Hassid-originating contribution; worth attributing carefully.
- **Hassid 30M-ARR-per-day Anthropic claim** in the post intro (*"Claude adds $323.5 million in ARR per day. PER DAY. It's now bigger than ChatGPT in terms of revenue."*) is striking and not directly verified in the brief synopsis — pairs with [[aakashgupta-anthropic-growth-acceleration-2026-05-09|May 9 growth-acceleration capture]] but at a different aggregation level. Worth flagging for verification — $323.5M/day = $118B/year, well above any Anthropic-stated run-rate.

## Cross-references

- [[claude-cowork]] — entity page; Hassid's setup walkthrough is the first wiki-canonical practitioner-content reference.
- [[claude-md-pattern]] — anti-style-instruction framing + AskUserQuestion-interview pattern + 200-line ceiling cross-confirmation; fifth+ independent practitioner-validation surface.
- [[milesdeutscher-claude-personal-cfo-2026-05-14]] — same-pattern Investor Strategy Architect interview prompt for personal-finance domain.
- [[stahlberg-team-os-aakash-2026-05]] / [[shilpamitra-claude-code-30-commands-2026-05-22]] / [[zephyr-7-claude-setups-2026-05-15]] — adjacent practitioner-validation surfaces for the file-based behavioral-contract discipline.
- [[mnilax-claude-md-12-rules-2026-05-09]] — 200-line ceiling origin; Hassid cross-confirms.
- [[karpathy-html-output-taxonomy-2026-05-08]] — HTML-as-output framing; Hassid Artifacts tip 9 cross-confirms at Cowork-product level.
- [[hassid-cant-beat-ai-cost-collapse-2026-05-18]] — companion Hassid substantive surface (3rd source threshold for entity-page creation).
- [[aakashgupta-anthropic-growth-acceleration-2026-05-09]] — Hassid $323.5M/day-ARR-add claim worth comparing.

## Pages Updated

- [[claude-cowork]] (updated — Hassid setup walkthrough added as first canonical practitioner-content reference; folder architecture + AskUserQuestion-interview prompt + anti-style framing captured; date bumped to 2026-05-25)
- [[claude-md-pattern]] (updated — Hassid anti-style "80% what you're NOT" framing added as Notable Variant; fifth+ independent practitioner-validation surface; date bumped to 2026-05-25)
