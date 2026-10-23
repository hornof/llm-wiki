---
title: "AINews: OpenAI's Patch the Planet program"
type: source
medium: article
url: https://www.latent.space/p/ainews-openais-patch-the-planet-program
ingested: 2026-10-22
---

## Summary

Latent Space AINews (2026-10-22) on **PHP2Shell**, a pair of flaws in PHP's handling of out-of-memory conditions and fatal errors (CVE-2026-109618, CVE-2026-109619). PHP shipped a security release on 2026-10-21 after about two months of coordinated remediation under OpenAI's **Patch the Planet** coalition. **The brief's "OpenAI's agents found" is not what the article says.** Ryan Austin of the security firm Calif found the flaws in August 2026 using [[gpt-5-6|GPT-5.6 Sol]]. Wiz (now Google Cloud) reportedly found the same bugs independently with Gemini 4 Argon, GPT-5.6 Sol and its own Wiz Atlas. The primary, patchtheplanet.org, renders no text without JavaScript and wasn't read. OpenAI's own announcement is an X post (status 2112907856018309586).

## Key Claims / Takeaways

- **Impact (researcher-reported):** pre-auth RCE demonstrated against WordPress, Drupal and Joomla, plus a claimed remote memory disclosure against any PHP app. No CVSS scores were published.
- **"70% of the web"** appears only in the headline, with no source in the body.
- **Disclosure:**
  - Governments got confidential advance notice.
  - Cloudflare shipped stopgap WAF rules, including on its free tier.
  - The NSA advised updating immediately, or taking systems offline if that wasn't possible.
  - OpenAI published a Codex skill for checking exposure.
- **Unverified:** that details leaked before the patch, and Censys's ~1.5M unpatched servers.
- **Patch the Planet vs Daybreak:** Patch the Planet is a remediation coalition. Daybreak is the access program for cyber models, with the $1B Frontline Defenders subsidy from 2026-09-08.
- **Other items in the issue (all secondary, none folded):**
  - Anthropic API version `2026-10-21` removes `temperature`, `top_p` and `top_k` from Messages.
  - Claude Duet, a proactive assistant, is in research preview.
  - The Linux kernel dropped its requirement to declare AI assistance.
  - DeepSeek DeepInfer.
  - Recursive's Flint MoE, ~40B total / 2.5B active.

## Pages Updated

- [[ai-vulnerability-discovery]]: new 10-22 section
- [[openai]]: 10-22 entry
- [[gpt-5-6]]: Sol as the discovery model
