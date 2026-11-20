---
title: "FBI says Artex AI open source hacking tool used to breach networks in 'under three hours'"
type: source
medium: article
url: https://techcrunch.com/2026/11/16/fbi-says-artex-ai-open-source-hacking-tool-used-to-breach-networks-in-under-three-hours/
ingested: 2026-11-20
---

## Summary

TechCrunch on an FBI flash advisory. Artex is an open-source AI penetration-testing platform that attackers connect to hosted frontier models (TechCrunch names Anthropic's and OpenAI's) or to open and non-US models. The FBI ties it to the breach of ConnectWise customers and of South Korean financial institutions. The FBI advisory itself was not read.

## Key Claims / Takeaways

- **Speed:** *"In some cases, Artex-linked attacks can move from targeting a system to active compromise “in under three hours.”"* The intrusions are "noisy", but fast enough that human defenders struggle to keep up.
- **Method:** fast network scanning, then simple bugs: *"weak protections and exposed or stolen passwords"*. No novel exploits described.
- **ConnectWise:** the FBI confirmed Microsoft's finding that attackers reached the Microsoft 365 environments *"of at least 2,250 of its customers."* Microsoft says the attackers are likely Chinese. ConnectWise says it can't confirm the number.
- **South Korea:** personal data *"of at least 68,000 people"* stolen; TechCrunch blames weak defenses such as missing multi-factor authentication.
- **Barracuda:** breached through a third-party credential it hadn't revoked. Its CISO: *"Defenders who rely on spotting malicious activity and then responding to it will often arrive after the attacker has finished"*
- **Timeline:** used in several attacks since its public debut in July.

## Pages Updated

- [[openai]] — context for Daybreak Red Team: the same agent pen-testing, used by attackers
