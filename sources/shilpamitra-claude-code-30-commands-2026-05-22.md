---
title: "ShilpaMitra: 'Claude Code Commands That Actually Matter' — 30-command taxonomy"
type: source
medium: reddit-post
url: https://www.reddit.com/r/WebAfterAI/comments/1tkoq5b/claude_code_commands_that_actually_matter_and_how/
ingested: 2026-05-24
---

## Summary

Reddit r/WebAfterAI post by @ShilpaMitra (2026-05-22) cataloguing **30 Claude Code commands organized by function** rather than alphabetically. First wiki capture of a comprehensive Claude Code command taxonomy — prior wiki coverage covered specific primitives (`/goal` + long-running cluster in [[claude-code-goal-command-2026-05]], CLAUDE.md in [[claude-md-pattern]], skills in [[zephyr-7-claude-setups-2026-05-15]]) but never a full surface inventory. Practitioner-content register; functional grouping is the load-bearing contribution.

## Key Claims / Takeaways

### Six functional groupings (the load-bearing taxonomy)

**1. Install and Launch (basics)**
- `npm install -g /claude-code` (note: the actual published Anthropic install is `@anthropic-ai/claude-code` — the `/claude-code` shorthand in the post is informal)
- `claude` — launch CLI
- `claude -c` — continue last conversation
- `claude -p "task"` — one-off command for scripting

**2. Session Management**
- `/clear` (alias `/reset`) — wipe conversation history
- `/compact` — *"compresses the current context by roughly 80%"* — most under-known command per the post; use before hitting context limit, not after
- `/branch` — fork the conversation to try two approaches; keeps both threads. (Comment thread notes: *"/fork? who wrote this text? I see only /branch in my claude."* — the `/fork` reference appears to be a draft-artifact; `/branch` is the current command.)
- `/context` — shows context-window utilization
- `/export` — saves conversation to file
- `/exit` (alias `/quit`)

**3. Model and Effort Controls** — *"This is where it gets interesting. Most people don't touch these."*
- `/goal [task]` — autonomous-agent mode (cross-references [[claude-code-goal-command-2026-05|the full `/goal` source]])
- `/plan` — *"Opus-level planning pass before agent starts executing"* — strategy-first discipline. First wiki capture of `/plan` as named primitive.
- `/effort [level]` — sets reasoning effort: `low`, `med`, `high`, `x`. *"Match the effort to the task complexity instead of running everything at max."* **First wiki capture of `/effort` as named primitive.**
- `/fast [on|off]` — speed-optimized output; turns off verbose thinking
- `/goal clear` — stops and resets the agent

**4. Files and Debugging**
- `/init` — creates CLAUDE.md at project root. *"Probably the highest-leverage thing you can do with Claude Code."* — direct practitioner validation of [[claude-md-pattern|the CLAUDE.md pattern]].
- `/diff` — shows uncommitted changes
- `/doctor` — diagnoses installation; *"catches 90% of setup issues automatically"*
- `/cost` — token usage / cost stats for the current session. **First wiki-captured Claude-Code-native cost-visibility primitive.**
- `'u/file.md'` — includes specific file in context
- `'u/src/folder/'` — includes entire directory

**5. MCP Servers and Skills**
- `/mcp` — lists connected MCP servers
- `claude mcp add` — adds new MCP server
- `/batch` — runs command across many files (e.g., *"add error handling to every API route"*). **First wiki capture of `/batch` as named primitive.**
- `/debug` — structured debugging flow: *"reproduce, isolate, hypothesize, instrument, fix, verify"*
- `Shift+Tab` — cycles through permission modes (ask-every / ask-dangerous / full-auto)

### Three pro tips (the editorial spine)

1. **Write a good CLAUDE.md** — *"It's the difference between re-explaining your project every time and having an agent that already knows how you work."* Direct echo of [[claude-md-pattern]] practitioner validation.
2. **`/goal` + Opus is for the hard problems** — *"This is where Claude Code stops being a tool and starts being a teammate."*
3. **`/doctor` first when anything breaks** — *"catches 90% of setup issues automatically."*

### Pieter-Levels-style comment-thread bug-pattern

Same day brief item (separate, captured in [[dailybrief-roundup-2026-05-24]]): **Pieter Levels reports a Claude Code CLI bug** where the `/effort` setting resets to medium daily. A research engineer suggests it affects outdated CLI versions. **Pairs directly with this source's `/effort` documentation** — `/effort` is named as a primitive in this post, and a daily-reset bug on the same primitive surfaces in the brief. Worth tracking whether the bug is resolved in current CLI versions.

## Why It Matters

- **First wiki capture of comprehensive Claude Code command taxonomy.** Six functional groupings × ~30 commands establishes a citable inventory the wiki lacked. Prior coverage was per-primitive ([[claude-code-goal-command-2026-05]] on `/goal`, [[claude-md-pattern]] on CLAUDE.md, [[zephyr-7-claude-setups-2026-05-15]] on the 7-setup taxonomy) but never the full surface.
- **Four newly-captured-as-named primitives**: `/plan` (Opus-level planning pass), `/effort [level]` (reasoning-effort control), `/batch` (multi-file command), `/cost` (token/cost visibility). Each is a wiki-citable Claude Code primitive that wasn't previously named.
- **Direct practitioner validation of [[claude-md-pattern]]** as *"the highest-leverage thing you can do with Claude Code."* Pairs with [[stahlberg-team-os-aakash-2026-05|Stulberg's 1,500-hour validation]] + [[zephyr-7-claude-setups-2026-05-15|Zephyr's setup #1 framing]] + [[claude-code-goal-command-2026-05|Luca Capone's CLAUDE.md-as-prerequisite framing]] as **four independent practitioner-validation surfaces** for the CLAUDE.md pattern.
- **`/compact` as the "command most people don't know about"** is the cleanest single-sentence wiki-citable framing of the context-management discipline. Pairs with [[anthropic-claude-cookbook-2026-05|Anthropic Cookbook's Automatic Context Compaction primitive]] — `/compact` is the user-facing surface of the same underlying capability.
- **`/effort [level]` primitive** is the user-facing surface of the [[svpino-subagent-pilled-2026-05-15|per-subagent model selection]] discipline at the conversation level — same task-appropriate-model-routing principle, captured as a single command. Pairs with [[zephyr-7-claude-setups-2026-05-15|Zephyr setup #6 model-routing-default]].
- **`/branch` for fork-and-experiment** is structurally adjacent to the [[stahlberg-team-os-aakash-2026-05|Team OS]] context-management discipline at the session level — a primitive for "try two approaches, keep both threads" without manual git-branch-style state management.

## Caveats

- **Reddit r/WebAfterAI is practitioner-content register, not Anthropic-official.** Specific syntax (`/goal clear` vs `/goal --clear` etc.) should be verified against Anthropic docs before propagating to entity pages.
- **Install command syntax artifact**: `npm install -g /claude-code` in the post is informal; the actual published name is `@anthropic-ai/claude-code`. Comment-thread `/fork` vs `/branch` confusion suggests the post may be a draft or version-skewed.
- **30-command claim** — the post enumerates ~20 commands with named primitives; the "30" framing may include the install variants + permission-mode cycling + `'u/file.md'` syntax variants. Not all are formally distinct commands.
- **No version specified** — Claude Code CLI has been iterating fast; commands available in this post may not exactly match the current `claude` version. The Levels-bug item suggests version-skew is operationally relevant.
- **Single-author practitioner-content** — would benefit from Anthropic-official primary verification. The post is useful as a *taxonomy framework*; the *exact command set* should be verified.

## Cross-references

- [[claude-code]] — entity page; updated with newly-captured-as-named primitives (`/plan`, `/effort`, `/batch`, `/cost`, `/compact`, `/branch`, `/context`, `/export`, `/diff`, `/doctor`, `/debug`).
- [[claude-md-pattern]] — direct practitioner validation; fourth independent surface validating CLAUDE.md-as-highest-leverage-investment.
- [[claude-code-goal-command-2026-05]] — `/goal` companion source; the 30-command taxonomy is the broader surface inventory `/goal` sits inside.
- [[zephyr-7-claude-setups-2026-05-15]] — Zephyr 7-setup taxonomy; `/effort` primitive surface for setup #6 model-routing-default discipline.
- [[stahlberg-team-os-aakash-2026-05]] — Stulberg 1500h Team OS pattern; `/branch` is the conversation-level fork-and-experiment primitive adjacent to Team OS context-management.
- [[svpino-subagent-pilled-2026-05-15]] — per-subagent-model-selection discipline; `/effort` is the conversation-level equivalent.
- [[anthropic-claude-cookbook-2026-05]] — Automatic Context Compaction primitive; `/compact` is the user-facing surface.
- [[dailybrief-roundup-2026-05-24]] — Pieter Levels `/effort` daily-reset bug as same-week practitioner-pattern signal.

## Pages Updated

- [[claude-code]] (updated — Six-functional-grouping command-taxonomy subsection added under Key Concepts; newly-named-as-primitive: `/plan`, `/effort`, `/batch`, `/cost`, `/compact`, `/branch`, `/context`, `/export`, `/diff`, `/doctor`, `/debug`, `/clear`, `Shift+Tab` permission-mode cycling; date bumped to 2026-05-24)
