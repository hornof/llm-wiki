---
name: General Intuition
type: company
focus: agent foundation model trained on video-game play, aimed at robots
status: emerging
last_updated: 2026-11-15
---

## What It Is

**General Intuition** is a New York lab building one agent model that works in video games, in simulation and on robots ([[general-intuition-2-3b-game-trained-agents-2026-06-25]]). It was spun out in October 2025 from Medal, a clip-sharing platform for gamers run by the same CEO, **Pim de Witte**. Medal's hundreds of millions of hours of gameplay come with "action labels", records of which buttons the player pressed and when. De Witte argues those labels, not the footage, are the advantage, because competitors have to infer actions from video alone. The co-founders are Eloi Alonso, Adam Jelley and Vincent Micheli.

The company trains its agent inside its own world model, which it calls "the gym", and wants to sell the agent model itself. In TechCrunch's demo, the same model that played a Fortnite-like game drove a quadruped robot after eight minutes of real-world fine-tuning data. TechCrunch adds that no one has yet made this kind of model hold up in the physical world at scale.

*(Rewritten 2026-11-15 against the two TechCrunch articles, fetched for the first time. The earlier version called $2.3B a "total thesis bet"; it was the valuation. It also said the company "raises at ~$6B"; the round was in talks. And it was full of `canonical-` filler from an automated pass.)*

## Traction Signals

- **2026-08-24: in talks at a $6B pre-money valuation** (TechCrunch, sources familiar with the matter; [[dailybrief-roundup-2026-08-24]]). New investors would include Valor Equity Partners, Point72 Ventures and Seven Seven Six, with Khosla Ventures and General Catalyst participating again. The round was still being finalized and reported as oversubscribed. The money is for compute (through a CoreWeave partnership) and hiring, with a focus on robots. The wiki has no confirmation that it closed.
- **2026-06-25: $320M at a $2.3B valuation** ([[general-intuition-2-3b-game-trained-agents-2026-06-25]]), led by Khosla Ventures with General Catalyst, Jeff Bezos and Eric Schmidt among others. Total disclosed funding reached $454M, after a $134M round at launch. Most of it goes to compute for pre-training the next model, with some for wider API access.
- **Medal turned down an acquisition offer from a major lab**, per the company's chief of staff, and the founders say they aren't interested in being acquired.

## Key People

- **Pim de Witte**: co-founder and CEO; also runs Medal.
- **Eloi Alonso, Adam Jelley, Vincent Micheli**: co-founders.

## How to Use It

No public product the wiki has seen. In June the company planned to make its API more broadly available by the end of summer 2026; whether it did isn't recorded.

**Stated limit:** de Witte says the models won't be used to harm people, ruling out lethal autonomy, though search and rescue is fine.

## Compared To

- **Other world-model and spatial-AI labs:** [[ami-labs|AMI Labs]] (Yann LeCun), [[world-labs|World Labs]] (Fei-Fei Li) and [[ineffable-intelligence|Ineffable Intelligence]] (David Silver). General Intuition's difference is its training data: gameplay with the player's actions attached. See [[spatial-intelligence]].
- **Robotics foundation-model companies** such as [[physical-intelligence|Physical Intelligence]] train mainly on real-world robot data, which is slow and expensive to collect. General Intuition is betting gameplay is a scalable shortcut. [Judgment, following TechCrunch's framing.]

## Resources

- [[general-intuition-2-3b-game-trained-agents-2026-06-25]]: the $320M round, the demo and the data advantage (TechCrunch)
- [[dailybrief-roundup-2026-08-24]]: the $6B round in talks
- [[spatial-intelligence]]: related concept
