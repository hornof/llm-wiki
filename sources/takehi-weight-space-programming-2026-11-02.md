---
title: "Sparks of Weight-Space Programming: LLMs can natively read & write neural network weights"
type: source
medium: article
url: https://rikiyat.github.io/blog/weight-space-programming/
ingested: 2026-11-02
local_source: "_raw/Sparks of Weight-Space Programming LLMs can natively read & write neural network weights.md"
---

## Summary

A blog post from MIT CSAIL, 2026-11-02, by Rikiya Takehi, Jayden Teoh, Alex Zhang and Omar Khattab. They gave GPT-6 Astra the raw weights of small networks as text and asked it to say what the networks do, fix them or write new ones, without gradient descent or training loops. It mostly succeeded. Their biggest result: Astra edited 0.016% of Qwen3.5-0.8B's weights to stop its reasoning loops, which raised math and instruction-following scores. Two experiments failed, and the authors report both. Full logs are public (github.com/RikiyaT/lm_understand-logs). It's a blog post, not peer-reviewed, and a benchmark is promised. Also clipped: Takehi's X thread (`_raw/Post by @rikiyatakehi on X.md`) and Garry Tan's quote of it (`_raw/Post by @garrytan on X 6.md`).

## Key Claims / Takeaways

- **The idea:** *"a general-purpose LLM reads and writes a network’s weights directly (i.e., not through an optimizer, and in particular not with gradient descent) around some natural language spec"*.
- **Reading:** given only the weights of four game policies with the same architecture, and no list of options, Astra *"was still able to name the right game for all four networks."* Given only the middle layers of three small character-level language models, it named the training language every time and found every copying head (induction head) and no false ones.
- **Fixing:** a PPO car policy that stalled on a ramp. With one recorded episode and no tools, Astra's edit *"makes the car succeed in all 1,024 episodes, changing 3.5% of the weights."*
- **Writing from scratch:** for three MinAtar games, with no training and no test runs, *"Astra’s generated networks beat PPO trained for 100 million steps in all three games."* Against PPO at 500M steps, they *"score 20 times as much in Breakout, come close in Asterix, and reach 60% of its score in Seaquest."* The thread reports only the Breakout figure, *"20× higher than PPO trained for 500M steps"*, which reads as if it held for all three.
- **Go:** writing a 1.5M-weight 9×9 Go network in a Python sandbox, *"With 50 forward passes, Astra’s generated network beats the equal-sized PPO network that was trained on 20 million games."*
- **Qwen3.5-0.8B and loops:** Astra traced the loops to one direction written by the MLPs of layers 15 and 19 and subtracted it. *"With 50 forward passes, MATH-500 rose from 7.9% to 48.1% and GSM8K from 13.8% to 67.1%."* Instruction following improved too: *"IFEval, which measures instruction following, rose from 21.0% to 62.3%."* The edit touches *"131,072 of the model’s 0.8 billion weights (0.016%)."* With 10 or 25 forward passes the loops barely moved.
- **Failure 1, sycophancy:** asked which of two fine-tuned Gemma 3 270M copies was sycophantic, *"from the weights alone, Astra was unable to tell."* Allowed to see attention patterns on texts it wrote, it picked the sycophant in all three pairs.
- **Failure 2, a model that doesn't loop:** on Gemma 3 270M, *"Astra could not improve it."* The authors' conclusion: *"Editing weights could remove an obstacle that hid an ability, but it could not add an ability the model lacked."* So the Qwen jump came from removing loops, not from making the model better at math.
- **What they expect next (speculation):** auditing weights for hidden problems such as backdoors without running test sets, unlearning without data, and grafting circuits between models with different architectures.
- **Reading it:** every network is small, and the headline Qwen result depends on a known, single-direction failure. A reply to Tan's post notes that a patch touching 0.016% of the weights *"is something you can diff, review and roll back"*. Tan calls it a *"new use of smaller models"*, but it's a frontier model editing a small one.

## Pages Updated

- [[gpt-6-astra]]
- [[mechanistic-interpretability]]
- [[qwen]]
