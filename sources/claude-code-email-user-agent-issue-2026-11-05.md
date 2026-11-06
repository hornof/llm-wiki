---
title: "Bug Report: Privacy violation in User-Agent header (anthropics/claude-code #107757)"
type: source
medium: github-repo
url: https://github.com/anthropics/claude-code/issues/107757
ingested: 2026-11-06
---

## Summary

A GitHub issue opened 2026-11-05: Claude Code put the user's account email in the User-Agent header of web requests it made, so third-party sites received it. The reporter blames it for daily scam email. An Anthropic team member replied that a built-in mod now blocks this from v2.1.317, and a commit on 2026-11-06 references the issue. Commenters found gaps in the fix.

## Key Claims / Takeaways

- **The report.** *"claude code divulged my email to arbitrary 3rd parties in the User-Agent request header while conducting web searches without my permission"*. The reporter wants it *"removed from the harness entirely"* and is *"migrating my company to Pi with OpenRouter"*. The issue drew *"667"* thumbs-up at fetch time.
- **The fix.** *"We introduced a built-in mod called cc-plugin-privacy to deterministically block this behavior in v2.1.317 and later"*, *"enabled by default"* and switchable via `/plugins`. Commit message: *"Refuse web calls that carry the account owner's email address"*.
- **How it happens, per commenters.** When Claude writes its own `curl -A` or a fetch script, it fills in a descriptive User-Agent, sometimes with the email, often because a site asks for a contact (*"Claude Code and other agents typically do this when a site asks for mail in User Agent like SEC or Wiki Media"*). One commenter scanned their transcripts and found two cases.
- **Gaps reported.** The mod matches only the account address, so a User-Agent naming the project still passes, and so does an email written into a script with Edit and then run. One commenter says on 2.1.319 a test command containing the address *"still runs without being refused"*. Another asks that model-written requests default to *"a generic User-Agent such as claude-code/<version>"*.
- **Second leak, same mechanism.** The made-up User-Agent can name the project or client, which *"ties your identity to what you are working on"*.

## Pages Updated

- [[claude-code]] — Traction Signals
