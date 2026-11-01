---
title: "Do the Math: How We Took Over ChatGPT Accounts"
type: source
medium: article
url: https://www.parameter.ai/labs/we-found-a-gap-at-openai
ingested: 2026-10-31
---

## Summary

Parameter Labs (Mukul Goyal, 2026-10-28) shows how a public ChatGPT share link could run attacker JavaScript in the victim's signed-in session. Two features combined: an interactive graph that loaded the MathLive library, and an HTML Preview. MathLive accepted messages from any origin and inserted HTML into the main page, and ChatGPT's content policy allowed scripts from YouTube, whose oEmbed endpoint echoed a callback. OpenAI fixed it on 2026-10-26.

## Key Claims / Takeaways

- **Impact:** an attacker could *"take over anyone's account simply by sending them a link"*. The researchers read a private conversation and sent it to an outside server.
- **Victim action:** *"Opening the shared link was the only required action"* in the automatic version.
- **Root causes:** MathLive's controller *"used an origin policy of none"*, and an unsandboxed `srcdoc` iframe inherited the chatgpt.com origin.
- **Fix and payout:** *"OpenAI fixed the issue on October 26 and classified the report as P1."* Reported 10-18, with *"a total bounty of $5,000"*.
- **Lesson for builders:** the sandboxed Preview worked as designed. The hole came from a third-party library in the trusted page. Two features that were each safe alone combined into an exploit.

## Pages Updated

- [[openai]]
