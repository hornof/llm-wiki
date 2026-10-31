---
title: "Official Claude Code Extension Compromise: Security Advisory"
type: source
medium: article
url: https://phorion.io/blog/offical-claude-code-vsx-compromise/
ingested: 2026-10-31
---

## Summary

Phorion, an endpoint-security company, found a backdoor in the Claude Code for VS Code extension as distributed on the Cursor Marketplace (2026-10-30, updated 10-31). Versions 2.1.312 and 2.1.313 carried code that installs a persistent SSH backdoor on macOS, Linux and Windows. Cursor removed both versions. The post doesn't say how the bundle was compromised, and nothing in it implicates the VS Code Marketplace copy or Anthropic's own release.

## Key Claims / Takeaways

- **Affected:** *"Claude Code for VSCode 2.1.312 or 2.1.313"* from the Cursor Marketplace. Cursor's notice names macOS and Windows builds.
- **No click needed:** the injected code *"executes as soon as Node loads the file, before the extension’s normal activate callback even runs."*
- **What it does:**
  - Appends an attacker key (comment `svc-telemetry`) to `~/.ssh/authorized_keys`.
  - Opens a reverse SSH tunnel to `134.209.82[.]225`.
  - Persists through a LaunchAgent on macOS, a cron entry on Linux, or a startup script on Windows, and beacons host details.
- **A bug blunts it on macOS:** the check for Remote Login fails without admin rights, so the script never turns SSH on. Persistence and keys still land.
- **Cleanup:** *"uninstalling the extension alone won’t remove the backdoor"*. Kill the tunnel, remove the persistence files and the key, and rotate credentials if SSH was on.
- **Scale (secondary):** a Digg teaser citing BleepingComputer says it exposed *"up to 5,000 Cursor users"*, available about 11 hours on 10-29 (not verified here).
- **This Mac (checked 2026-10-31):** no Cursor install, no Anthropic extension in VS Code, and none of the files or the key.

## Pages Updated

- [[claude-code]]
- [[anysphere]]
