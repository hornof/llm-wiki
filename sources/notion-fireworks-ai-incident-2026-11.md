---
title: "Notice about the Fireworks AI incident that may impact some Notion workspaces"
type: source
medium: article
url: https://www.notion.com/help/security-incident-involving-a-third-party-ai-vendor
ingested: 2026-11-10
---

## Summary

Notion's help-center notice (fetched 2026-11-10) on a breach at Fireworks AI, an inference provider Notion used. Attackers may have obtained Notion AI chat transcripts that Notion had sent to Fireworks for a usage-analytics feature. Notion says the transcripts carried no user or workspace labels. This is the first breach the wiki records where an AI inference vendor, rather than the lab or the app, leaked customer prompts. Fireworks' own notice was not fetched.

## Key Claims / Takeaways

- **Scope.** *"<1% of Notion workspaces may have been affected"*. The exposed data was chat transcripts that *"weren't labeled with who wrote them or which workspace they came from"* and *"did not contain tool call results."*
- **What Fireworks was used for.** Classifying chats for the Insights feature, and serving open-weight models inside Notion. Insights is disabled.
- **Timeline.** Notion cut connections when it first heard of possible incidents. *"On November 6, Fireworks notified us that malicious actors may have accessed potential customer data."* Fireworks confirmed the dataset on November 8. By *"November 3rd"* Notion had disconnected and deleted its data at Fireworks.
- **Advice.** *"We recommend that you treat this data as if it were exposed."* Rotate any credentials pasted into Notion AI.
- **Why it matters for builders.** Unattributed transcripts are still the users' own words, and any secret pasted into a prompt went with them. A second inference provider behind an app is one more place for prompts to leak. Routing to cheap open-weight hosts has a security cost as well as a price advantage. [Judgment, not in the source.]

## Pages Updated

None. The wiki has no Notion or Fireworks page, and one incident doesn't justify creating them. Recorded here and in [[dailybrief-roundup-2026-11-10]].
