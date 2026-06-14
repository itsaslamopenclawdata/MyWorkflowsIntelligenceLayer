---
title: "SkillOpt — How to Train AI Agent Skills Using Text Space Optimization"
channel: "Eddy Explainer"
channel_slug: "eddy"
channel_id: "UCZ_4HvkkWlRdM8t5nOiOiYA"
published: "2026-06-13"
duration_seconds: 567
video_id: "OXEq_1tstJ0"
url: "https://www.youtube.com/watch?v=OXEq_1tstJ0"
language: "en"
tags: [skillopt, prompt-optimization, text-space, agent-skills, gpt-5, claude-code, codex, eddy]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# SkillOpt — How to Train AI Agent Skills Using Text Space Optimization

**Channel:** Eddy Explainer  **Published:** 2026-06-13  **Duration:** 09:27  **Watch:** https://www.youtube.com/watch?v=OXEq_1tstJ0

## TL;DR
Eddy Explainer's 9-min intro to **SkillOpt**, described as the world's first systematic, controllable text-space optimizer for agent skills. It maps traditional ML training (parameters, gradients, learning rate, validation gates) onto natural-language edits of a skill markdown file. 4-step loop: roll out → reflect → edit → gate. **A 25-point accuracy jump on GPT-5.5 across 6 benchmarks / 7 models / 3 harnesses — clean sweep of 52/52 cells.** SpreadsheetBench: 41.8% → 80.7%. Codex-trained skill ported to Claude Code: 22.1 → 81.8 (+60 pts). Zero extra inference cost at deployment — the training happens offline. Final output is a tiny 300-2,000 token `best_skill.md` you can drop into any frozen model.

## Key Insights
- **The "train the procedure, not the weights" mindset.** If an agent fails a tricky task, SkillOpt doesn't assume the model's fundamental reasoning is permanently broken — it assumes the agent just needs a better set of instructions, a better procedure. (0:18–0:35)
- **The key phrase: "text space optimizer."** Not code. Not neural parameters. It systematically optimizes natural human language, applying the same scientific rigor that deep-learning engineers use to train neural networks. (2:35–3:05)
- **The ML-to-text mapping.** Parameters → the skill document itself. Gradients → proposed text edits based on performance. Learning rate → strict edit budget. Validation check → held-out selection gate: edit kept only if it mathematically proves it improves performance on completely unseen data. (3:10–3:35)
- **The 4-step optimization loop.** (1) **Rollout** — run a batch of tasks using the current text skill. (2) **Reflect** — let the optimizer propose structured edits based on the errors. (3) **Edit** — add, delete, or replace text in the instruction manual. (4) **Gate** — strictly validate against held-out data. If it doesn't boost the score, it gets thrown out. (3:38–5:00)
- **Small calculated steps, not destructive jumps.** The system takes a batch, separates successes from failures, asks an optimizer AI to reflect on what went wrong, merges those reflections, ranks them under a strict textual learning-rate schedule, validates rigorously. "It's basically a highly controlled, automated factory for creating the absolutely perfect prompt." (4:10–4:35)
- **The rejected-edit buffer.** SkillOpt saves failed text edits as negative feedback so the AI literally learns from its past mistakes. An "epic-wise slow update" locks in stable, long-term rules. This separates fast reactive tweaks from durable procedural lessons. (5:00–5:25)
- **The numbers.** On GPT-5.5, SkillOpt lifts average zero-shot accuracy by a **massive 23.5 points** across complex benchmarks. "A nearly 25-point leap in intelligence, not by retraining a multi-billion parameter model, but literally just by automatically optimizing the text file it reads before it starts its task." (5:35–6:00)
- **Clean sweep, 52/52 cells.** Tested exhaustively across 6 rigorous benchmarks, 7 different target models, 3 execution harnesses. "Tied or beat the absolute best baselines on exactly 52 out of 52 evaluated cells. A clean sweep." (6:00–6:18)
- **SpreadsheetBench concrete case.** Baseline model ~41.8% on complex spreadsheet coding tasks. After SkillOpt optimization, exact same frozen model shoots to **80.7%**. "It nearly doubled its capability simply because its procedural instructions were mathematically refined." (6:30–6:50)
- **The holy grail: transferability.** "You can optimize a text skill in one environment and literally just copy-paste it into another." A Codex-trained skill ported to Claude Code: **22.1 → 81.8 (a near 60-point performance explosion).** Proves SkillOpt discovers universally true procedural knowledge, not model-specific weights. (6:55–7:25)
- **Zero extra inference cost at deployment.** All heavy lifting (rollout batches, optimizer model, reflection loops) happens offline during training. "Your final deployed model runs exactly as fast and as cheaply as it did before. You get all these massive 20-to-60-point gains without adding a single extra model call." (7:25–7:50)
- **Efficiency.** Gains usually only require **1 to 4 accepted edits**. Token cost: 0.6 to 46.4 million tokens per point of gain. Output is plain English, auditable by a human. (7:55–8:25)
- **The mic-drop deliverable.** The final optimized "brain" of the agent is literally just an exportable markdown file called `best_skill.md`, 300-2,000 tokens. Drop it into any frozen model and instantly turn it into an expert. (8:30–8:50)

## Notable Quotes
> "We're not optimizing code, and we're not updating neural parameters. It systematically optimizes natural human language, applying the exact same scientific rigor that deep learning engineers use to train neural networks." — 2:50

> "It nearly doubled its capability simply because its procedural instructions were mathematically refined." — 6:48

> "A great plan up front creates vastly superior code downstream." — (n/a, different video)

> "The final hyper-optimized brain of your agent is literally just a tiny exportable markdown file." — 8:35

## Tools and Resources Mentioned
- **SkillOpt** — text-space optimizer for agent skills. Described as the world's first systematic, controllable version. (Source: research paper cited; URL not given in this short.)
- **GPT-5.5** — the frontier model SkillOpt was tested against, with a 23.5-point average lift.
- **Codex / Claude Code** — the cross-harness transferability example (Codex-trained skill → Claude Code: 22.1 → 81.8).
- **Anthropic Claude Code** — referenced as a deployment harness. ⚠️ **Claude Code is Anthropic's CLI coding tool, NOT this stack (MiniMax).**
- **OpenAI Codex** — referenced as a deployment harness and source of the transferred skill. ⚠️ **Codex is OpenAI's product, NOT this stack (MiniMax).**
- **SpreadsheetBench / AlfWorld / LiveMath / SearchQA** — benchmarks SkillOpt was evaluated on.

## GitHub Repos and URLs Referenced
- (No specific GitHub repo or arXiv URL is given in the short version. The companion long-form `Izbt-JmVmCQ` and `IMLsGCTlfJo` videos cover SkillOpt in greater depth.)

## Action Items
- [ ] For any agent skill (system prompt, role definition, multi-step procedure), treat it as a trainable artifact. Run the 4-step loop: rollout → reflect → edit → gate.
- [ ] Don't blindly increase edit count. SkillOpt's empirical finding is 1-4 accepted edits are usually enough for the bulk of the gain — protect over-editing with a strict edit budget.
- [ ] For cross-harness portability, train your skill in your lowest-friction environment and copy the resulting markdown into your production harness. Codex → Claude Code transfer is the headline example.
- [ ] For deployment, freeze the model. Run the optimization offline. You get the gains without any per-call inference cost increase.
- [ ] For evaluation, use held-out validation gates. Do not let optimizer edits through that don't improve performance on unseen data.

## Open Questions
- The 1-4-edit finding is surprising — is it model-specific, domain-specific, or universal? Is it sustainable on long-tail, narrow tasks vs. broad reasoning?
- The matched-target-as-optimizer self-improvement pattern (smaller model rewriting its own skill) is mentioned as a "future of skills" thread. What's the failure mode — does it converge, or does it cycle through locally optimal rewrites?
- Is SkillOpt publicly available as a library? The short version cites a paper but no repo URL.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 9:27 transcript)</summary>

0:06 Okay, let's dive right into this
0:07 explainer. So, agents keep getting
0:09 smarter, and the gap between a frozen
0:11 model and a truly autonomous
0:12 practitioner keeps getting smaller.
0:14 But have you ever wondered what
0:15 actually makes the difference between a
0:16 basic prompt and a brilliant, adaptive
0:18 skill that just keeps getting better at
0:20 a job?
0:22 If you have, you need to know about
0:23 this. You need to know about Skill
0:24 Opt.
0:26 Because, honestly, it's not just about
0:27 some tiny marginal improvement here. We
0:28 are looking at a fundamental
0:29 breakthrough in how frozen models
0:30 learn. Complex tasks.
0:32 The whole philosophy is captured
0:33 perfectly in this quote from the source
0:34 material. Train the procedure, not the
0:35 weights. It is a total mindset shift.
0:38 If an agent fails to solve a tricky
0:39 math problem or gets lost navigating a
0:40 virtual environment, Skill-Op doesn't
0:41 just assume the model's fundamental
0:42 reasoning is permanently broken. No, it
0:43 assumes the agent just needs a better
0:40 set of instructions, a better procedure
0:41 to guide how it gathers evidence, uses
0:42 tools, and formats its output.
0:44 Okay, so how do you practically train a
0:45 text document? Skill-Op pulls this off
0:46 by deliberately mirroring a traditional
0:47 machine learning loop, but doing it
0:48 entirely in natural language. It uses a
0:49 four-step continuous loop, rollout,
0:50 reflect, edit, and gate. By cycling
0:51 through these four stages, the AI just
0:52 continuously refines its own skills
0:53 without ever once touching its neural
0:55 weights. Let's break these down real
0:56 quick.
0:58 Step one is the rollout. You can think
0:59 of this as the equivalent of a
0:60 traditional machine learning forward
0:01 pass, but purely for text. So, the
0:02 frozen target model is handed its
0:03 current skill document and sent out to
0:04 execute a batch of tasks. While it
0:06 works, the system records the whole
0:07 shebang, the messages, the tool calls
0:08 it makes, the feedback it gets, and
0:09 most importantly, its final scores.
0:10 It's basically gathering the raw
0:11 evidence of what happens when those
0:12 current instructions actually hit
0:13 reality. Then we have step two, reflect.
0:14 Think of this one as a language level
0:15 backward pass.
0:16 Here, an optimizer model, which by the
0:17 way sits completely separate from the
0:18 target model doing the task, looks at
0:18 all that rollout data. It separates the
0:19 successes from the failures into mini
0:20 batches. Why? So it can pinpoint
0:21 exactly which instructions caused the
0:22 errors while being super careful to
0:23 preserve the procedures that are
0:24 already working perfectly. It's
0:25 literally diagnosing the text.
0:27 Step three is the edit phase. This is
0:29 where the optimizer proposes structured
0:30 edits to the skill document. It might
0:31 add a new rule, delete a bad one, or
0:32 replace an instruction that's just
0:33 confusing.
0:34 But here is the absolute genius part.
0:35 It does all of this under a strict edit
0:36 budget. This budget acts like a textual
0:37 learning rate. Think about it. If you
0:38 let an AI just rewrite its whole prompt
0:39 unconditionally, it might accidentally
0:40 wipe out highly useful rules it already
0:41 learned.
0:43 So the budget bounds the edits,
0:44 forcing the system to be incredibly
0:45 precise and measured in its evolution.
0:47 And finally, step four, the gate. This
0:49 is the ultimate quality control. Just
0:50 because the optimizer proposed some
0:51 shiny new instructions, doesn't mean
0:52 the target model automatically adopts
0:53 them. Nope. The candidate skill is kept
0:54 only if it definitively improves
0:55 performance on a held-out validation
0:56 set. It's a really strict propose-and
0:57 test mechanism. If the new text
0:58 document doesn't actually perform
0:59 better in reality, it just gets thrown
0:60 out. Section two, meet Skill-Opt,
0:61 training text.
0:63 Enter Skill-Opt. To our knowledge,
0:64 this is the world's very first
0:65 systematic, controllable text space
0:66 optimizer for agent skills. And that
0:67 phrase right there, text space
0:68 optimizer, is the absolute key to all
0:70 of this. It's not optimizing code, and
0:71 it's not updating neural parameters.
0:72 It systematically optimizes natural
0:73 human language, applying the exact
0:74 same scientific rigor that deep
0:75 learning engineers use to train neural
0:76 networks.
0:78 What's truly fascinating is how
0:79 perfectly the researchers mapped
0:80 complex machine learning engineering
0:81 directly over to simple text editing.
0:82 In traditional ML, you optimize
0:83 parameters, right? Well, in Skill-Opt,
0:84 the parameter is the skill document
0:85 itself. The gradients, or the
0:86 mathematical direction you need to
0:87 improve, becomes a proposed text edit
0:88 based on how the agent performed. The
0:89 learning rate becomes a strict edit
0:90 budget, and the validation check, it
0:91 becomes a held-out selection gate,
0:92 which means a text edit is only kept if
0:93 it mathematically proves it improves
0:94 performance on completely unseen data.
0:95 Section three, inside the optimization
0:96 loop. So, how does this actually run
0:97 under the hood? Basically, an optimizer
0:98 model watches how the frozen agent
0:99 completes a task. Then, it proposes
0:01 bounded edits. Specifically, it decides
0:02 to add, delete, or replace text in the
0:03 instruction manual.
0:04 Skill opt navigates this entire
0:05 text-based loss landscape with very
0:06 small, highly calculated steps. It
0:07 completely avoids those destructive
0:08 semantic jumps, what the paper calls
0:09 ad hoc updates, making sure the skill
0:10 actually gets better step by step
0:11 instead of just randomly changing its
0:12 entire personality overnight.
0:13 There's a beautifully complex engine
0:14 driving these simple text edits. The
0:15 system takes a batch of attempts,
0:16 separates the successes from the
0:17 failures, and essentially asks an
0:18 optimizer AI to reflect on what went
0:19 wrong. These reflections are then
0:20 merged, ranked under that strict
0:21 textual learning rate schedule we
0:22 talked about, and rigorously
0:23 validated. It's basically a highly
0:24 controlled, automated factory for
0:25 creating the absolutely perfect prompt.
0:26 All of this boils down to four
0:27 rapid-fire steps. One, run a batch of
0:28 tasks using the current text skill.
0:29 Two, let the optimizer propose highly
0:30 structured edits based on the errors.
0:31 Three, strictly validate those edits
0:32 against held-out data. And hey, if it
0:33 doesn't boost the score, it gets
0:34 thrown out immediately. And four,
0:35 update the skill document. You just
0:36 loop this over and over, and your text
0:37 instructions get mathematically
0:38 sharper every single round.
0:40 Now, think about the memory system for
0:41 a second. How do you stop an AI from
0:42 making the exact same bad text edit
0:43 twice? Skill opt actually uses a
0:44 rejected edit buffer. It saves failed
0:45 text edits as negative feedback so
0:45 the AI literally learns from its past
0:46 mistakes. Meanwhile, an epic-wise slow
0:47 update locks in stable, long-term
0:48 rules. This brilliantly separates fast
0:49 reactive tweaks from the durable
0:50 procedural lessons the agent actually
0:51 needs to master a domain.
0:52 Section four, massive gains, zero
0:54 cost.
0:55 Now, you're probably wondering, does
0:56 this actually work? The numbers in
0:57 this paper are absolutely staggering.
0:58 On GPT-5.5, which is already an
0:59 incredible frontier model, Skill opt
0:60 lifts the average zero-shot accuracy
0:61 by a massive 23.5 points across
0:62 complex benchmarks. Think about that.
0:63 We're talking about a nearly 25-point
0:64 leap in intelligence, not by
0:65 retraining a multi-billion parameter
0:66 model, but literally just by
0:67 automatically optimizing the text
0:68 file it reads before it starts its
0:70 task. And to prove this wasn't just a
0:71 fluke, the researchers tested it
0:72 exhaustively across six rigorous
0:73 benchmarks, seven different target
0:74 models, and three execution harnesses,
0:75 Skill-Op tied or beat the absolute
0:76 best baselines on exactly 52 out of
0:77 52 evaluated cells. A clean sweep.
0:78 It outperformed human experts, one
0:80 shot AI prompts, and other state
0:81 of-the-art prompt optimization
0:82 frameworks every single time.
0:83 Take Spreadsheet Bench as a perfect
0:85 example of this contrast. The baseline
0:86 model was really struggling, pulling
0:87 in about a 41.8% accuracy when trying
0:88 to execute complex spreadsheet coding
0:89 tasks. But, by running Skill-Op and
0:90 optimizing the text instructions,
0:91 that exact same frozen model shot up
0:92 to an incredible 80.7%. It nearly
0:93 doubled its capability simply
0:94 because its procedural instructions
0:95 were mathematically refined.
0:96 But, here is the holy grail of AI,
0:97 transferability. You can optimize a
0:98 text skill in one environment and
0:99 literally just copy-paste it into
0:01 another. For example, a text skill
0:02 trained inside the Codex harness was
0:03 ported directly over to Claude code.
0:05 The result? A near 60-point
0:06 performance explosion. It lifted
0:07 Claude from a 22.1 all the way up to
0:08 an 81.8. This proves that Skill-Op
0:09 isn't just gaming one specific
0:10 model, it is discovering universally
0:11 true procedural knowledge.
0:12 And honestly, the absolute best part,
0:14 zero extra inference cost at
0:15 deployment. Because all this heavy
0:16 lifting, the rollout batches, the
0:17 optimizer model, those reflection
0:18 loops, all of it happens offline
0:19 during training. Your final deployed
0:20 model runs exactly as fast and as
0:21 cheaply as it did before. You get all
0:22 these massive 20 to 60 point gains
0:23 without adding a single extra model
0:24 call when your users are actually
0:25 running the tool.
0:26 Section five, the future of skills.
0:27 The efficiency here will blow your
0:28 mind. You think these massive
0:29 accuracy jumps would require
0:30 thousands of changes, right? Nope.
0:31 The researchers found they usually
0:32 only require one to four accepted
0:33 edits. The token cost is incredibly
0:34 low, between 0.6 and 46.4 million
0:35 tokens per point of gain. And the
0:36 output isn't some garbled unreadable
0:35 matrix of numbers. It is highly
0:36 readable procedural logic in plain
0:37 English. A human engineer can just
0:38 open the file, audit exactly what
0:39 the AI learned to do differently, and
0:40 safely deploy it.
0:41 So, the ultimate mic drop of this
0:42 entire paper is this quote right
0:43 here. After all that complex AI
0:44 training, all those epochs and
0:45 rigorous validation gates, the
0:46 final hyper-optimized brain of your
0:47 agent is literally just a tiny
0:48 exportable markdown file. It's called
0:49 best_skill.md. It's between 300 and
0:50 2,000 tokens, and you can carry it
0:51 anywhere. Drop it into any frozen
0:52 model, and instantly turn it into an
0:53 absolute expert in your specific
0:54 domain. It leaves us with a
0:55 thrilling, maybe even slightly
0:56 intimidating possibility. If the
0:57 instruction manual itself can learn,
0:58 reflect, and evolve autonomously
0:59 under strict mathematical controls.
0:60 If you no longer have to cross your
0:61 fingers and guess at the perfect
0:62 prompt, what impossible task will
0:63 you conquer with your next frozen
0:64 agent? Thank you so much for joining
0:65 me for this explainer. Start thinking
0:66 about what's going into your own
0:67 best_skill.md, and I'll catch you in
0:68 the next one.

</details>
