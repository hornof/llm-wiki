---
title: "caveman: make your AI agent say less and read less"
type: source
medium: github-repo
url: https://github.com/JuliusBrussee/caveman
ingested: 2026-10-28
---

## Summary

`JuliusBrussee/caveman`, a local proxy plus skill that cuts agent tokens in two ways. Output is written in terse "caveman" prose, and input context is compressed before it reaches the model. It installs into Claude Code, Codex, Gemini CLI and *"30+ more"* agents. The repo showed *"Star 116k"* when fetched. The wiki first saw it on [[gregisenberg-3-token-saving-plugins-2026-07-08|2026-07-08]] as one of three token-saving plugins, so it has grown a lot since. **The savings figures are the README's own.** The Adobe Research and JetBrains mentions weren't checked.

## Key Claims / Takeaways

- **Headline numbers (README):** *"33.2% fewer input tokens, whole sessions"*, *"54% cheaper with Auto, same score"*, and *"1.4 to 2.4× cheaper with caveman-style output"* (attributed to Adobe Research, across eight models).
- **The example:** a 63-token explanation becomes 20 tokens (*"63 token become 20"*), and the code stays exact.
- **Runs locally**, with the user's keys and Claude Pro/Max login.

## Pages Updated

- [[context-engineering]]: entry
