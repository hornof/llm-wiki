---
title: "Schedule recurring tasks in Claude Code Desktop"
type: source
medium: article
url: https://code.claude.com/docs/en/desktop-scheduled-tasks
ingested: 2026-11-09
---

## Summary

Anthropic's Claude Code documentation page for scheduled tasks in the Desktop app, fetched 2026-11-09 to check a practitioner guide ([[imryven-second-brain-claude-obsidian-guide-2026-10-27]]). Desktop can run a Claude Code prompt on a schedule, either locally with file access or in the cloud. Local runs depend on the machine being awake. The page date wasn't captured. A search result described it as about 179 days old, so menu paths may have moved.

## Key Claims / Takeaways

- **Local vs. cloud.** Local task: *"runs on your machine with direct access to your files and tools, but only fires while the app is open and your computer is awake"*. *"Use cloud tasks for work that should run reliably without your machine."*
- **Sleep skips runs.** *"If your computer sleeps through a scheduled time, the run is skipped."* *"Closing the laptop lid still puts it to sleep."*
- **One catch-up run.** Desktop checks for missed runs *"in the last seven days"* on start or wake, and runs *"exactly one catch-up run for the most recently missed time and discards anything older"*.
- **Permissions.** Each task has its own permission mode, and *"Allow rules from ~/.claude/settings.json also apply to scheduled task sessions."* To avoid stalls, *"click Run now after creating a task, watch for permission prompts, and select “always allow” for each one."*
- **Runs are full sessions.** Claude *"can edit files, run commands, create commits, and open pull requests"* in a run, as in any session.
- **Bearing on this wiki.** A nightly ingest of this vault would need to be a local task with git and `gh` allowed, and the Mac awake. A sleeping Mac skips the run and later gets one catch-up run.

## Pages Updated

- [[claude-desktop]] — open question on native scheduled tasks resolved
