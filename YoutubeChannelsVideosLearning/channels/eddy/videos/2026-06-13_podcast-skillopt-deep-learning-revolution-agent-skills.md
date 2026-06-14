---
title: "(Podcast) SkillOpt — The Deep Learning Revolution for AI Agent Skills"
channel: "Eddy Explainer"
channel_slug: "eddy"
channel_id: "UCZ_4HvkkWlRdM8t5nOiOiYA"
published: "2026-06-13"
duration_seconds: 1200
video_id: "IMLsGCTlfJo"
url: "https://www.youtube.com/watch?v=IMLsGCTlfJo"
language: "en"
tags: [skillopt, prompt-optimization, text-space, agent-skills, optimizer-architecture, cosine-schedule, rejected-edit-buffer, meta-update, long-horizon, eddy]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# (Podcast) SkillOpt — The Deep Learning Revolution for AI Agent Skills

**Channel:** Eddy Explainer  **Published:** 2026-06-13  **Duration:** 20:00  **Watch:** https://www.youtube.com/watch?v=IMLsGCTlfJo

> **Companion notes:** The 9-min short version (`OXEq_1tstJ0`) lives at `2026-06-13_skillopt-text-space-optimizer-agent-skills.md`. This is the long-form podcast expansion — same paper, deeper on the deep-learning analog (parameter / gradient / learning rate / validation gate), the optimizer architecture, the rejected-edit buffer mechanics, the prompt-vs-procedure debate, and the long-horizon stability questions.

> **Vendor disambiguation (read this first):** The transcript mentions several products that are NOT this stack (MiniMax):
> - **GPT-5.5 / GPT-5.4 / GPT-5.4-Nano** — OpenAI's frontier and small models, used as SkillOpt's target and optimizer.
> - **QN-3.5-4B** (transcribed "Quinn 3.54B") — a small open model used as a transferability target.
> - **Claude Code** — Anthropic's CLI coding harness, used as a cross-harness transfer target.
> - **Codex** — OpenAI's coding harness, used as the source of a cross-harness transferred skill.
> None of these are MiniMax. SkillOpt is a research framework from Microsoft Research Shanghai, Shanghai Jiao Tong University, and Fudan University (May 2026 paper).

---

## TL;DR
A 20-min two-host podcast deep dive on **SkillOpt** (May 2026 paper from Microsoft Shanghai + SJTU + Fudan), framed explicitly as the "deep learning revolution for AI agent skills." The argument: don't fine-tune frozen frontier models — treat the skill markdown as a *trainable parameter* and run a full ML loop over it (rollout → reflect → edit → gate), governed by a **cosine-scheduled edit budget** and a **validation gate that rejects ties** to prevent silent drift and bloat. A **rejected-edit buffer** and a **protected epoch-wise meta-update** give SkillOpt a two-speed memory (fast surgical edits vs. durable longitudinal rules). Headline results: GPT-5.5 +23.5 avg over 6 benchmarks; LiveMath 37.6 → 66.9 from a *single* accepted edit (a "rank choices by theorem strength" rule); SpreadsheetBench 41.8 → 80.7; AlfWorld evolves from a generic "search → pick → place" plan into destination memory + loop breakers. Cross-model transfer is so strong that a skill optimized on GPT-5.4 still gives massive lifts when handed to GPT-5.4-Nano or QN-3.5-4B; cross-harness (Codex → Claude Code) +60 pts on SpreadsheetBench; cross-math (OlympiadBench → OmniMath) also holds. Long-form goes deeper than the short on: the optimizer-as-separate-model architecture, the cosine schedule, the "reject ties" rule, the protected meta-update section, and the philosophical question of what happens when skills start optimizing the optimizers.

---

## Key Insights

### The framing: training the procedure, not the weights
- **The "forgetful intern" analogy** (4:04–4:32). Frontier models are brilliant but forgetful at domain-specific procedures. Changing the model weights is "literal brain surgery" — usually impossible (closed source) or prohibitively expensive. The pragmatic alternative: hand the agent a "constantly evolving instruction manual" it must read before every task. SkillOpt is the engine that writes and perfects that manual.
- **The "yelling through the tailpipe" critique** (0:54–1:12). Current prompt engineering is compared to fixing a car engine by yelling instructions through the tailpipe — treating these systems as unpredictable black boxes and just throwing words at them. SkillOpt is positioned as the escape from that guesswork.
- **"Whack-a-mole" brittleness** (3:14–3:37). When a human or AI rewrites a prompt ad hoc to fix one edge case, they often delete a rule that was handling 10 other things. Existing methods are brittle: they do not *reliably* improve under feedback.
- **It is not a prompting trick** (2:08–2:30). Eddy is explicit: "this isn't a YouTube tutorial on prompt engineering." SkillOpt represents a fundamental shift — treating the text file as an optimizable external brain and applying deep-learning rigor to human language.

### The deep-learning analog, in detail
- **Parameter → the skill document itself** (4:50–4:58). The text file *is* the weights.
- **Gradient → structured edit suggestions** (5:00–5:12). Gradients are derived from comparing the agent's past successes and failures.
- **Learning rate → a strict edit budget governed by a cosine schedule** (6:56–7:46). A "literal limit on words" measured in atomic edits (add one line, delete one rule, replace one sentence). The budget follows a mathematical curve that smoothly tapers: bigger sweeping changes on day 1 (up to 4 edits per step); by day 10, the budget drops to 1–2 surgical tweaks. This forces prioritization of the most critical fixes and prevents "large semantic jumps" that wipe out working procedures.
- **Validation check → a held-out gate that *rejects ties*** (7:48–9:00). This is the most counterintuitive design choice and the long-form gives it a full minute. The candidate skill is tested on unseen tasks and must achieve a *strictly higher* score — ties are rejected. The reason: **silent drift / bloat**. Accepting ties lets the document accumulate extra rules that don't immediately hurt. Fast-forward 50 training steps and the document is bloated with useless, overly specific rules; the agent gets confused by its own manual; performance eventually degrades. The strict gate ensures every change actually moves the needle in a positive direction.

### The optimizer architecture (long-form's deepest expansion)
- **Two separate models** (5:30–5:48). The frozen target model (the "intern") runs tasks using the current skill document. A *completely separate* optimizer model watches the rollouts and proposes edits. They are architecturally and behaviorally distinct.
- **The optimizer does not look at the final score** (5:48–6:10). It compares the *step-by-step reasoning traces* of successful runs against failed runs, pinpoints the exact logical divergence — the exact moment the target model made a wrong assumption or took a bad step — and translates that specific gap in logic into an English rule to prevent that specific wrong step in the future.
- **"How does a language model calculate a gradient out of words?"** (5:14–5:28) — a real audience question, addressed head-on. The answer: the optimizer model *is* the gradient calculator. It takes failures as input and produces edits as output. The math is replaced by a learned text-to-edit function.

### The two-speed memory system (deeply expanded in the long-form)
- **Fast surgical edits** (10:00–10:50) — step-by-step localized edits within the rolling training. Used to fix immediate errors on the current batch.
- **Slow epoch-wise meta-update** (9:55–10:48) — runs at the end of a *full epoch* (one complete pass over the dataset). Zooms out, asks: "What are the persistent failures across all these tasks? What are the stable successes?" Then writes a *concise piece of longitudinal guidance* into a **specially protected section** of the text file. **Protected = the local edits aren't allowed to touch this section.** This captures durable long-horizon lessons that shouldn't be accidentally erased by a short-term fix.
- **"Two-speed system"** (10:42–10:48) — fast reactive tweaks vs. durable procedural lessons. The host calls this out as a "brilliant" design that separates "what I just learned" from "what I have learned."

### The rejected-edit buffer (the playbook of banned plays)
- **Mechanics** (9:02–9:54). When an edit fails the validation gate, the system *keeps it* as a record of what not to do. The next time the optimizer is looking at failures, it reviews that buffer and knows not to suggest the same fix again.
- **The sports-team analogy** (9:18–9:30). A "playbook of banned plays" — a list of things they tried in practice that resulted in an interception, so they know never to call them in a real game.
- **Institutional memory** (9:50–9:54). The buffer creates institutional memory for the optimizer. Stops the system from endlessly repeating its own mistakes. Saves both time and compute.
- **Why it isn't a "massive waste of resources"** (9:02–9:18) — addresses the obvious objection head-on. Without negative feedback, every failed proposal would have to be re-derived from scratch.

### The headline numbers, benchmark-by-benchmark
- **GPT-5.5 average +23.5 points** across 6 benchmarks in direct chat (11:21–11:34). Best-or-tied on **52/52** evaluated cells (combinations of model × benchmark × harness).
- **LiveMath: 37.6 → 66.9 (+29.3) from a single accepted edit** (12:21–12:44). The rule: the optimizer noticed the model was frequently selecting *true but mathematically weaker corollaries* instead of the strongest theorem. It added a single sentence: "rank choices by theorem strength and prefer a justified stronger result option." The model already knew the math — it just didn't understand the *procedural demand* of the test format.
- **SpreadsheetBench: 41.8 → 80.7** (13:18–13:44). The rule: inspect the workbook structure first, then write *evaluated static values* across the target range rather than relying on Excel's internal recalculation — described as a "forensic accounting trick" the AI discovered on its own by analyzing its past failures.
- **AlfWorld: generic → strict policy** (13:46–14:18). Initial skill was "search for object, pick it up, place it, plan." After SkillOpt it evolved into a highly strict policy with: (1) destination memory, (2) rules to stop searching the exact same locations repeatedly, (3) loop breakers. The transformation: "confused tourist wandering around a house" → "highly efficient robot butler."
- **The golf-coach analogy** (14:19–14:54). A bad coach gives 50 things to think about and paralyzes the swing. A master coach takes 20 swings, identifies the one core structural flaw, gives one specific procedural adjustment — "just keep your left elbow straight" — and suddenly you're hitting it straight down the fairway. **"SkillOpt is the master coach. The constraint is what makes it powerful."**

### The transferability story (the "superpower")
- **Cross-model downward transfer** (15:36–16:18). Optimize a skill using GPT-5.4 (large, capable, expensive). Then hand the resulting one-page text file to a much smaller, cheaper model like GPT-5.4-Nano or a different architecture entirely like QN-3.5-4B. The smaller models still see massive performance leaps — and in *relative* terms, the small cheap models benefit *the most* from receiving refined procedural instructions. The analogy: "downloading the hard-won experience of a senior executive into an entry-level worker just by handing them a one-page memo."
- **Cross-harness transfer: Codex → Claude Code** (16:21–16:48). Train a skill in Codex (very specific Python execution / tool use), drop the same text file into Claude Code (different execution model, possibly bash, different software tool sets). It still works — +60 points on SpreadsheetBench during that transfer. Proves the skill captures genuine reusable procedural knowledge, not "specific software buttons" of one environment.
- **Cross-math transfer: OlympiadBench → OmniMath** (16:50–17:00). The optimizer isn't just memorizing test answers; it captures the philosophy of how to evaluate math theorems in a way that applies universally.
- **The economic argument** (15:10–15:35). The expensive optimization loop runs *once* offline. The resulting plain-English artifact is highly portable. Any user can then deploy it to any cheap fast local model and instantly upgrade its capabilities to an expert level. "We are moving from the era of trying to adapt the machine's brain to adapting the machine's instructions."

### The "edit economy" (the long-form's mic-drop)
- **1 to 4 accepted edits** are usually enough for the bulk of the gain (long-form confirms; expanded with the LiveMath single-edit +29.3 case). Token cost: **0.6 to 46.4 million tokens per point of gain** (the long-form gives both bounds).
- **Final artifact: 300–2,000 tokens** — roughly a page or two of text. The hosts explicitly note: "How is a two-page document driving a 23-point increase in a frontier model? It shows how much leverage a single well-placed procedural rule can have when you apply it to a model that already possesses vast latent knowledge" (11:58–12:16).
- **Human-auditable** — plain English, not a garbled matrix of numbers. A human engineer can open the file, audit what the AI learned to do differently, and safely deploy it.

### The prompt-vs-procedure debate (philosophical core)
- **"Yelling through the tailpipe"** revisited as the failure mode of prompts (18:15–18:21). The manual is no longer just a prompt — it is a **continuously optimized parameter** (18:54–18:58). This is the "profound paradigm shift in how we think about the interface between human intent and machine execution."
- **"What happens to traditional software engineers?"** (19:00–19:32). If SkillOpt proves that a single plain English document is the most efficient way to program frontier AIs, then for 50 years we have been forcing humans to learn the rigid language of machines (Python, C++, Java). This research suggests the ultimate programming language — the code that unlocks the most advanced capabilities of our most powerful machines — was invented 50,000 years ago. **It's just human speech.**
- **The long-horizon question** (19:34–19:42). "What happens when these text-based meta-skills become so advanced that they start optimizing the optimizers? We are entering uncharted territory for sure." The hosts explicitly leave this as an open thought experiment, not a solved problem.
- **"Something to think about the next time you catch yourself asking AI to write a Python script"** (19:42–19:50). The framing is that the listener is *already* coding in the most powerful language on Earth.

---

## Notable Quotes

> "Imagine you could change like exactly one sentence in a standard instruction manual and instantly make an artificial intelligence 30% smarter at advanced mathematics." — 0:06

> "We are currently treating these incredibly advanced systems like unpredictable black boxes. We just keep throwing words at them and hoping the output improves." — 1:14

> "It represents a fundamental shift in how we adapt AI to specific domains. It treats a simple text file, what the researchers actually call the skill, as an optimizable external brain." — 2:20

> "Imagi[ne] you have a brilliant but incredibly forgetful intern. They know all the facts in the world. They keep messing up the company's specific filing procedure." — 4:05

> "How does a language model calculate a gradient out of words? How does it look at a failed math problem and know what English sentence to write?" — 5:18

> "It is literally diagnosing the text." — (optimizer reflecting on rollout failures)

> "If you let an AI rewrite everything from scratch, it makes huge uncontrolled leaps in logic. It completely forgets the procedures that were actually working fine." — 6:36

> "A cosign schedule means the edit budget follows a mathematical curve that smoothly tapers off over time." — 7:15

> "Rejecting a tie seems overly punishing, though. Like, if a new rule doesn't hurt the score, why not keep it just in case it helps later?" — 8:32

> "If you accept ties, the document can start accumulating extra rules that don't actually help, but don't explicitly hurt right away. Eventually, that bloat degrades performance." — 8:40

> "Think of it like a sports team's playbook of banned plays. A strict list of things they tried in practice that resulted in an interception." — 9:18

> "It creates an institutional memory for the optimizer." — 9:52

> "An epoch-wise slow update runs at the end of a full epoch. It zooms out. It asks, 'What are the persistent failures across all these tasks? What are the stable successes?'" — 10:15

> "This captures durable long-horizon lessons that shouldn't be accidentally erased by a short-term fix." — 10:35

> "The model actually knew the math. It just needed to be told exactly how to evaluate the multiple choice option." — 12:57

> "SkillOpt is the master coach. The constraint is what makes it powerful." — 14:50

> "In relative terms, the small cheap models benefit the most from receiving these highly refined procedural instructions." — 16:04

> "It is quite literally like downloading the hard-won experience of a senior executive into an entry-level worker just by handing them a one-page memo." — 16:09

> "The manual is no longer just a prompt. It is a continuously optimized parameter." — 18:54

> "The code that unlocks the most advanced capabilities of our most powerful machines was invented 50,000 years ago. It's just human speech." — 19:28

> "What happens when these text-based meta-skills become so advanced that they start optimizing the optimizers?" — 19:36

---

## Tools and Resources Mentioned

- **SkillOpt** — text-space optimizer for agent skills. From a May 2026 paper by **Microsoft Research Shanghai, Shanghai Jiao Tong University, and Fudan University**. Described as "the world's very first systematic, controllable text-space optimizer for agent skills." Source paper is repeatedly referenced but the URL is not given on-audio in this episode.
- **GPT-5.5** — OpenAI's frontier model; the primary target in SkillOpt's evaluation. Direct chat: +23.5 avg across 6 benchmarks. ⚠️ **GPT-5.5 is OpenAI's product, NOT this stack (MiniMax).**
- **GPT-5.4** — OpenAI's larger / more capable model; used as the *optimizer-side* model in cross-model transfer experiments. ⚠️ **GPT-5.4 is OpenAI's product, NOT this stack (MiniMax).**
- **GPT-5.4-Nano** — OpenAI's smaller / cheaper model; used as a *downward* transfer target. Gains hold and in relative terms are largest on this tier. ⚠️ **GPT-5.4-Nano is OpenAI's product, NOT this stack (MiniMax).**
- **QN-3.5-4B** (transcribed "Quinn 3.5 4B") — a small open model used as a transferability target across *architectures* (not just model sizes). Demonstrates the optimized skill transfers beyond OpenAI's model family. ⚠️ **QN-3.5-4B is a small open model, NOT this stack (MiniMax).**
- **OpenAI Codex** — used as the *source* execution harness for cross-harness transfer. ⚠️ **Codex is OpenAI's product, NOT this stack (MiniMax).**
- **Anthropic Claude Code** — used as the *destination* execution harness in the Codex → Claude Code transfer (+60 pts on SpreadsheetBench). ⚠️ **Claude Code is Anthropic's CLI coding tool, NOT this stack (MiniMax).**
- **SpreadsheetBench** — complex spreadsheet coding tasks. Baseline ~41.8% → 80.7% with SkillOpt. The optimizer's discovered rule: inspect workbook structure first, then write evaluated static values rather than rely on Excel's internal recalculation.
- **LiveMath (LiveMathBench / LiveMathematician)** — advanced mathematical reasoning benchmark. 37.6 → 66.9 (+29.3) from a single accepted edit about ranking choices by theorem strength.
- **AlfWorld** — embodied virtual-environment benchmark. Initial generic "search → pick → place" skill evolves into a strict policy with destination memory, no-repeat search, and loop breakers.
- **OlympiadBench → OmniMath** — math-to-math cross-benchmark transfer. The optimized skill maintains high scores when moved, proving the optimizer isn't memorizing test answers.
- **Cosine schedule** — the mathematical curve that controls the textual learning rate (edit budget tapers over time). Familiar from real neural-network training, here applied to text edits.
- **Rejected-edit buffer** — the "playbook of banned plays." Stores edits that failed the validation gate so the optimizer doesn't re-propose them.
- **Epoch-wise meta-update** — a slow, protected longitudinal update to a special section of the skill document; local edits cannot touch it.

---

## GitHub Repos and URLs Referenced

- No specific GitHub repo, arXiv URL, or HuggingFace link is given on-audio in this long-form episode. The paper is cited as a "May 2026 paper from Microsoft Research Shanghai, Shanghai Jiao Tong University, and Fudan University." If you want the source, search `SkillOpt text space optimizer agent skills Microsoft Shanghai SJTU Fudan 2026`.

---

## Action Items

- [ ] **Treat every system prompt / role definition / multi-step procedure as a trainable parameter**, not a static artifact. Run the rollout → reflect → edit → gate loop on it.
- [ ] **Use a cosine-scheduled edit budget**, not a flat cap. Allow up to ~4 edits per step early in training; taper to 1–2 by the end. This mirrors neural-net LR schedules and prevents large destructive semantic jumps.
- [ ] **Make the validation gate strict: reject ties.** This is the non-obvious rule that prevents silent drift / bloat. Ties today become bloat tomorrow. Accept only edits that mathematically improve performance on held-out, unseen tasks.
- [ ] **Maintain a rejected-edit buffer (playbook of banned plays).** Every edit that fails the gate goes in. The optimizer consults it before proposing new edits. This is institutional memory — don't re-derive what you've already disproved.
- [ ] **Reserve a protected section of the skill for the slow epoch-wise meta-update.** Local edits are forbidden from touching it. The fast surgical edits fix today's errors; the slow meta-update captures durable long-horizon principles that shouldn't be erased by a short-term fix.
- [ ] **Optimize once, deploy many times.** Run the expensive loop offline against a strong model (e.g. GPT-5.4). Hand the resulting one-page text file to cheaper targets (GPT-5.4-Nano, QN-3.5-4B, or a local model). The small cheap models benefit *most* in relative terms.
- [ ] **For cross-harness portability, train in your lowest-friction environment and copy the result.** Codex → Claude Code was the headline example (+60 pts on SpreadsheetBench). The skill captures reusable procedural knowledge, not environment-specific tool calls.
- [ ] **Trust a small number of surgical edits.** 1–4 accepted edits are usually enough for the bulk of the gain (LiveMath's entire +29.3 came from one rule). Resist the urge to keep iterating once the gate stops firing.
- [ ] **Use the "master coach" rule when designing the skill manually.** Don't pile on 50 instructions. Find the one core procedural flaw and write the one specific rule. Constraint is what makes the procedure powerful.
- [ ] **For domain-specific deployments, build domain-specific evaluator sets.** The held-out validation set *is* the optimization target. A weak validator produces bloat; a strong one produces a clean, auditable, expert skill.

---

## Open Questions

- **Optimizer-optimizer recursion (the long-form's own mic-drop).** The hosts explicitly ask: "What happens when these text-based meta-skills become so advanced that they start optimizing the optimizers?" Is there a stable fixed point, or does SkillOpt-on-SkillOpt diverge? Does the meta-update section itself become a target for a higher-order meta-meta-update?
- **Long-horizon stability of the cosine schedule.** Is a 10-day cosine schedule the right horizon, or does the optimal schedule scale with task complexity? Does the budget need to be re-decayed mid-training when the loss landscape shifts?
- **The 1-edit +29.3 case is the most striking result in the paper — but is it generalizable?** Does single-edit dominance hold across all math benchmarks, or is it specific to multiple-choice format? When does a single rule suffice vs. when does the optimizer need 3–4 coordinated edits?
- **The protected meta-update section is treated as a black box in the podcast.** How is its length bounded? How are conflicts between meta-update content and local edits resolved? What is the rewrite rule when the slow update and a fast edit disagree?
- **Rejecting ties: how is "tie" defined?** Statistical tie (within noise of the held-out set) vs. exact tie? What is the tolerance, and does it need to be domain-specific? An overly strict gate could starve the optimizer of legitimate signal.
- **Cross-architecture transfer (QN-3.5-4B): how deep does it go?** Does the skill transfer to a model that was *not* trained with RLHF? With a different tokenizer? With a different context window? The podcast hints at universality; the paper presumably bounds it.
- **The frozen-model assumption breaks for self-improving agents.** SkillOpt assumes the target model is frozen. What happens when the target model itself is being fine-tuned continuously (e.g. online RL)? Does the skill drift out of sync with the weights? Does the rejected-edit buffer become a stale cache?
- **Cost asymmetry.** 0.6–46.4M tokens per point of gain is a 77× range. What drives that variance? Domain? Model size? Benchmark noise? Without understanding the variance, you can't budget for an optimization run.
- **The "forgetful intern" assumes skills are read pre-task.** What about agents with persistent memory (e.g. long-context agents, agents with vector stores)? Does SkillOpt generalize to *edits to memory* rather than *edits to a single system prompt*?
- **SkillOpt vs. constitutional AI / RLHF / DPO.** All four are "alignment-by-text-edit" paradigms. Are they complementary? Does SkillOpt's gain stack on top of a heavily RLHF'd model, or does it saturate?
- **The "what happens to software engineers" question.** SkillOpt is positioned as democratization ("you do not need a team of machine learning engineers"). But someone still has to design the rollout tasks, the held-out validation set, and the optimizer prompts. Is the bottleneck shifting from ML engineering to evaluation engineering?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 20:00 transcript)</summary>

0:00 Imagine
0:01 [snorts]
0:03 [music]
0:06 you could change like exactly one
0:08 sentence in a standard instruction
0:10 manual and instantly make an artificial
0:13 intelligence 30% smarter at advanced
0:15 mathematics,
0:16 >> right? Which sounds like science
0:17 fiction.
0:18 >> It really does. Yeah. I mean, you write
0:19 no new code. You don't spend millions of
0:21 dollars on neural network training. You
0:23 just change one single English sentence.
0:26 >> And that's the reality we're looking at
0:27 today.
0:28 >> Yeah. Because if you have ever sat at
0:31 your computer trying to get an AI agent
0:34 to do a complex task, maybe analyzing a
0:38 giant spreadsheet or, you know, combing
0:40 through a huge folder of documents. You
0:43 know exactly how frustrating it is when
0:45 it just completely fumbles.
0:46 >> Oh, absolutely. It searches the wrong
0:48 files. Yeah.
0:49 >> Or it formats the answer backward,
0:51 >> right? Or it gets stuck in an endless
0:52 loop. And what is our usual solution for
0:54 that? We just tweak the prompt. We add
0:56 something like, "Hey, make sure you read
0:58 column B." Or we throw in that classic,
1:00 "Take a deep breath and think step by
1:02 step."
1:03 >> Yeah. Which, if we're being honest,
1:04 feels less like computer science and
1:06 more like trying to fix a car engine by
1:08 yelling instructions through the
1:10 tailpipe.
1:10 >> I love that analogy. It's so true. We're
1:12 just yelling at it.
1:13 >> We really are. We are currently treating
1:15 these incredibly advanced systems like
1:18 unpredictable black boxes. We just keep
1:20 throwing words at them and hoping the
1:22 output improves which is well it's just
1:24 not a sustainable way to build reliable
1:26 tools.
1:26 >> Exactly. But today we are exploring a
1:29 way to eliminate that guesswork
1:30 entirely. So welcome to today's deep
1:34 dive. We're looking at this really
1:36 fascinating May 2026 paper from
1:39 researchers at Microsoft Shanghai Jaoong
1:42 University Tom University and Foudan
1:44 University
1:45 >> and they've introduced a system called
1:46 Skilloft.
1:47 >> Skilloft. Right. So, our mission today
1:50 for you listening is to understand how
1:51 these researchers figured out a way to
1:53 train a plain English text document with
1:56 the exact same mathematical discipline
1:58 that engineers use to train a neural
2:00 network. It's literally a shortcut to
2:02 making any AI agent incredibly smart
2:05 without touching its underlying code.
2:07 >> And um we should probably clarify right
2:08 out of the gate, this isn't just a
2:10 clever new prompting trick,
2:11 >> right? This isn't a YouTube tutorial on
2:13 prompt engineering.
2:14 >> Exactly. We aren't talking about a list
2:16 of best practices for writing better
2:18 queries. Skill up represents a
2:20 fundamental shift in how we adapt AI to
2:22 specific domains. It treats a simple
2:25 text file, what the researchers actually
2:27 call the skill, as an optimizable
2:30 external brain.
2:31 >> An external brain.
2:32 >> Yeah. It is taking the absolute rigors
2:34 of deep machine learning and applying
2:36 them directly to human language. Okay,
2:38 let's unpack this because your point
2:40 about treating the text file like a
2:42 brain highlights a structural problem we
2:44 really need to understand first. Why do
2:46 current AI agents fail at these complex
2:50 multi-step tasks to begin with? I mean,
2:52 these models have literally read the
2:54 entire internet. Why can't they just
2:55 navigate a spreadsheet?
2:57 >> Well, it comes down to how we currently
2:59 give them their procedural skills. Right
3:01 now, an agent's skills are usually
3:03 handcrafted by a human developer. Or
3:05 maybe they are generated one shot by
3:07 asking another AI to just write a good
3:09 prompt. And at best they are loosely
3:11 self-revised based on a few errors. But
3:14 the fundamental flaw here is that these
3:15 methods are brittle.
3:16 >> Brittle in what way?
3:18 >> They do not reliably improve when they
3:20 get feedback. Like when a human or an AI
3:24 just ad hoc rewrites a prompt, they
3:26 might fix one specific edge case. Sure.
3:29 But in doing so, they accidentally
3:30 delete a crucial rule that was handling
3:33 10 other things perfectly.
3:34 >> Well, it's like a game of whack-a-ole.
3:35 You fix one bug and create two more.
3:37 >> Exactly.
3:38 >> So, we need the agent to learn and
3:40 adapt. But the traditional machine
3:41 learning way to fix this would be to
3:44 update the actual model weights, right?
3:46 The underlying math of the neural
3:48 network,
3:48 >> right? The parameters themselves.
3:50 >> But for Frontier models like the GBT 5.5
3:53 model they test in this paper, changing
3:55 the weights is often impossible. the
3:57 model is closed source or it's simply
3:59 way too expensive to fine-tune for every
4:01 little task. So, let me try an analogy
4:03 here.
4:04 >> Go for it.
4:04 >> Imagine you have a brilliant but
4:06 incredibly forgetful intern. They know
4:08 all the facts in the world. They keep
4:10 messing up the company's specific filing
4:12 procedure.
4:13 >> Happens all the time. Right now, instead
4:15 of trying to perform literal brain
4:16 surgery on the intern to hardwire the
4:19 procedure into their neurons, which is
4:21 what changing the model weights would
4:24 be, what if we just gave them the
4:25 ultimate constantly evolving instruction
4:28 manual?
4:28 >> And they are required to read the manual
4:30 before every single task. Exactly.
4:32 >> That is a perfect analogy. And Skilloft
4:35 is basically the engine that writes and
4:37 perfects that manual. What the
4:38 researchers did was systematically map
4:41 traditional deep learning concepts
4:44 directly onto text.
4:44 >> Okay, if we connect this to the bigger
4:46 picture, how does that mapping actually
4:48 work?
4:49 >> So in a standard neural network, you
4:50 optimize parameter weights. In skillup,
4:54 those parameter weights become the skill
4:55 document itself, that instruction
4:57 manual.
4:58 >> The text file is the weights.
4:59 >> Okay. Right. And in deep learning, you
5:01 follow a gradient, which is the
5:02 mathematical direction you need to move
5:04 to improve performance. In skillup, that
5:07 gradient becomes structured at its
5:09 suggestions. They're derived from
5:10 looking at the agents past successes and
5:12 failures.
5:13 >> Wait, wait. I need to stop you there. I
5:15 understand how an algorithm calculates a
5:17 mathematical gradient using calculus.
5:19 Numbers, sure, but how does a language
5:22 model calculate a gradient out of words?
5:25 How does it look at a failed math
5:27 problem and know what English sentence
5:29 to write?
5:30 >> That is where the optimizer model comes
5:31 in. Skill Opt actually uses two separate
5:34 AI models. Oh, two of them.
5:36 >> Yeah. You have your frozen target model,
5:38 your intern running a batch of tasks
5:40 using the current skill document. Then
5:42 you have a completely separate model
5:44 acting as the optimizer.
5:46 >> And what is the optimizer doing while
5:48 the intern is working?
5:48 >> The optimizer isn't just looking at the
5:50 final score. It is comparing the
5:52 step-by-step reasoning traces of the
5:53 successful runs against the failed runs.
5:56 It pinpoints the exact logical
5:58 divergence, the exact moment the target
6:00 model made a wrong assumption or took a
6:02 bad step.
6:03 >> Wow. And then it translates that
6:05 specific gap in logic into an English
6:07 rule to prevent that specific wrong step
6:10 in the future.
6:11 >> Okay, but that raises a massive risk,
6:13 doesn't it? If we give this optimizer AI
6:15 a red pen and let it rewrite the
6:17 instruction manual every time it gets
6:19 confused, aren't we going to end up with
6:20 just a chaotic, contradictory mess of a
6:23 document? Like, why not just let it
6:25 rewrite the whole document from scratch
6:27 every time the agent fails? Just say,
6:28 "Hey, that didn't work. Write a better
6:30 manual." Because of a phenomenon the
6:32 researchers call large semantic jumps.
6:35 >> Large semantic jumps.
6:36 >> Yeah. If you let an AI rewrite
6:38 everything from scratch, it makes huge
6:41 uncontrolled leaps in logic. It
6:44 completely forgets the procedures that
6:45 were actually working fine, it is highly
6:47 unstable.
6:48 >> So the whackable problem again.
6:50 >> Exactly. To prevent this, Skill
6:51 Optinforces what they call a textual
6:53 learning rate. It basically acts as a
6:56 strict edit budget.
6:57 >> How does an edit budget work in
6:58 practice? like a a literal limit on
7:00 words.
7:01 >> The system is restricted in how many
7:03 atomic edits it can make per step. So
7:05 say adding one line, deleting one rule
7:08 or replacing one sentence. And this
7:10 budget is controlled by a cosine
7:11 schedule.
7:12 >> Okay, just to translate for anyone who
7:13 might not be deep into the math, a
7:15 cosign schedule means the edit budget
7:18 follows a mathematical curve that
7:20 smoothly tapers off over time.
7:21 >> Precisely. It allows for bigger, more
7:24 sweeping changes on day one of training.
7:26 So perhaps up to four edits at once. But
7:28 by day 10, as the skill document gets
7:31 closer to perfect, the budget drops.
7:33 >> It slows down,
7:34 >> right?
7:35 >> The optimizer is only allowed to make
7:37 one or two tiny surgical tweaks. This
7:41 forces stable controlled optimization.
7:43 It forces the optimizer to prioritize
7:45 only the absolute most critical fixes.
7:48 >> Okay, so we have controlled the volume
7:50 of edits. But the paper also details
7:53 this incredibly strict bouncer at the
7:55 door for these edits which they call the
7:57 validation gate.
7:58 >> Yes, the gate is crucial
7:59 >> because after the optimizer proposes
8:01 these bounded edits, it creates a
8:03 candidate skill document.
8:04 >> But that document isn't deployed yet. It
8:06 has to be tested on a heldout validation
8:09 set of tasks. Tasks that is not seen
8:11 during the training batch.
8:12 >> It has to prove itself first.
8:14 >> Exactly. The new skill document
8:16 absolutely must achieve a strictly
8:18 higher score than the current school
8:20 document. If the score drops, the edits
8:22 are rejected. But here's the part that
8:25 surprised me. Even if the score ties,
8:28 the edits are rejected. Rejecting a tie
8:30 seems overly punishing, though. Like, if
8:33 a new rule doesn't hurt the score, why
8:34 not keep it just in case it helps later?
8:36 >> Because of silent drift, then bloat.
8:38 >> Bloat.
8:39 >> Yeah. If you accept ties, the document
8:41 can start accumulating extra rules that
8:43 don't actually help, but don't
8:45 explicitly hurt right away. Fast forward
8:47 50 training steps and your document is
8:49 bloated with useless, overly specific
8:51 rules.
8:52 >> Oh, and then the agent gets confused by
8:53 its own manual.
8:54 >> Exactly. Eventually, that bloat degrades
8:56 performance. The strict gate ensures
8:58 every single change actually moves the
9:00 needle in a positive direction.
9:02 >> And what happens to all those rejected
9:04 edits? I mean, if the optimizer spends
9:06 computing power proposing a fix and it
9:08 fails the validation gate, isn't that
9:10 just a massive waste of resources? It
9:13 would be if they didn't have a mechanism
9:14 for negative feedback. Skilloft uses a
9:17 rejected edit buffer. Think of it like a
9:20 sports team's playbook of banned plays.
9:23 >> Ban plays. I like that.
9:24 >> Yeah. It is a strict list of things they
9:26 tried in practice that resulted in an
9:28 interception so they know never to call
9:30 them in a real game.
9:31 >> So it remembers its mistakes.
9:32 >> Right. When an edit fails the validation
9:34 gate, the system keeps it as a record of
9:36 what not to do. The next time the
9:38 optimizer is looking at failures, it
9:41 reviews that buffer and knows not to
9:43 suggest that same fix again because it
9:44 lowered the score last time.
9:46 >> That saves so much time and computing
9:48 power. It stops the system from just
9:49 endlessly repeating its own mistakes.
9:51 >> Exactly. It creates an institutional
9:53 memory for the optimizer.
9:55 >> Now, I also noticed the paper mentions
9:57 an epicwise slow update or meta update.
10:00 What is that doing and how does it
10:02 relate to this memory? So, an epoch is
10:04 one full cycle of training over your
10:06 entire data set. The step-by-step
10:08 localized edits we just talked about are
10:11 great for fixing immediate errors, but
10:13 the slow update runs at the end of a
10:15 full epoch.
10:16 >> So, it zooms out.
10:17 >> It looks at the big picture. It asks,
10:19 "What are the persistent failures across
10:21 all these tasks? What are the stable
10:23 successes?" Then, it writes a concise
10:26 piece of longitudinal guidance into a
10:28 specially protected section of the text
10:30 file. protected, meaning
10:32 >> meaning the local edits aren't allowed
10:33 to touch this section. This captures
10:35 durable long horizon lessons that
10:36 shouldn't be accidentally erased by a
10:40 short-term fix.
10:41 >> So, you essentially have a two-speed
10:43 system. Fast surgical edits for
10:45 immediate problems and slow protected
10:47 updates for foundational principles.
10:49 >> Exactly. You would think with all of
10:51 this, the final output of this intense
10:54 optimization, the batching, the budgets,
10:56 the validation gates would be a massive
10:59 thousandpage textbook of highly specific
11:02 rules.
11:02 >> You really would.
11:03 >> But the [clears throat] results in the
11:04 paper are staggering precisely because
11:06 that isn't the case. Here's where it
11:07 gets really interesting. Let's look at
11:09 the numbers. They tested Skill Opt
11:10 across 52 different combinations of
11:12 models, benchmarks, and execution
11:13 harnesses. And out of 52 combinations
11:17 tested, Skill Up was the best or tied
11:19 for the best on all 52.
11:21 >> All 52. On the GBT 5.5 direct chat
11:25 alone, it lifted the average accuracy
11:27 across six different benchmarks by a
11:30 massive 23.5 points compared to using no
11:33 skill document at all.
11:34 >> The consistency across completely
11:36 different types of tasks is what makes
11:37 this a breakthrough.
11:39 >> It is. But the most surprising fact from
11:41 this entire paper, for me at least, is
11:43 the edit economy. These massive gains
11:46 did not come from thousands of complex
11:48 changes. The final best underscore
11:50 skill.md file, the actual text file, the
11:53 output is usually between 300 and 2,000
11:55 tokens long,
11:56 >> which is incredibly short.
11:58 >> Just to put that in perspective for you
11:59 listening, 2,000 tokens is roughly 1500
12:02 words. That is literally just a page or
12:03 two of text. How is a two-page document
12:06 driving a 23 point increase in a
12:08 frontier model? Well, it shows how much
12:10 leverage a single well-placed procedural
12:12 rule can have when you apply it to a
12:13 model that already possesses vast latent
12:16 knowledge. Let's look at the live
12:17 mathematician bench benchmark which
12:19 tests advanced mathematical reasoning.
12:21 The performance jumped from a score of
12:23 37.6 to 66.9. That is a 29.3 point gain.
12:29 And that entire gain came from exactly
12:31 one single accepted edit during the
12:34 whole optimization process.
12:35 >> Wait, really? One single sentence
12:37 changed and the model jumped almost 30
12:39 points in advanced math. What was the
12:41 rule and how did the optimizer even find
12:43 it?
12:44 >> So the optimizer noticed that in
12:45 multiple choice questions about
12:47 mathematical theorems, the target model
12:49 was frequently selecting true but
12:50 mathematically weaker corollaries
12:53 instead of the strongest possible
12:54 theorem.
12:55 >> Oh, so the model actually knew the math.
12:57 >> It knew the math perfectly, but it
12:59 didn't understand the specific
13:00 procedural demand of the test format. So
13:03 the optimizer wrote a rule that
13:04 explicitly told the agent to rank
13:06 choices by theorem strength and prefer a
13:08 justified stronger result option.
13:10 >> That is wild. It didn't need to be
13:12 taught math. It just needed to be
13:14 told exactly how to evaluate the multiple
13:16 choice option. And we see this exact
13:18 same efficiency in the spreadsheet bench
13:20 tests. Performance there went from 41.8
13:24 to 80.7.
13:25 The optimizer discovered a procedural
13:27 rule telling the AI to inspect the
13:29 workbook structure first and then to
13:31 write evaluated static values across the
13:34 target range rather than relying on
13:36 Excel's internal recalculation
13:38 >> which is essentially a forensic
13:39 accounting trick.
13:40 >> Yeah. Yeah.
13:41 >> And the AI discovered it on its own just
13:43 by analyzing its past failures.
13:45 >> Precisely. And it applies to embodied
13:47 environments as well. Like look at the
13:48 ALF world benchmark. This is an
13:51 environment where the agent has to
13:52 navigate a virtual house, find objects,
13:54 and move them to specific locations.
13:56 >> Okay. A simulated robot basically.
13:58 >> Yeah. The initial skill document was
14:00 just a generic search for object, pick
14:02 it up, place it, plan. But after the
14:04 skill up process, it evolved into a
14:06 highly strict policy. It added
14:08 destination memory. It added rules to
14:10 stop searching the exact same locations
14:12 over and over. It added loop breakers.
14:14 So, it went from a confused tourist
14:16 wandering around a house to a highly
14:18 efficient robot butler. You know, it
14:20 makes me think of a world-class golf
14:22 coach. If you hire a bad coach, they're
14:25 going to give you 50 different things to
14:27 think about your grip, your hips, your
14:28 shoulders, the wind speed, and they will
14:31 completely paralyze your swing.
14:32 >> Too much information,
14:34 >> right? But a master coach possesses
14:37 incredible restraint. They want you to
14:39 take 20 swings, identify the one core
14:42 structural flaw, and give you one
14:44 specific procedural adjustment. Like
14:46 just keep your left elbow straight, and
14:48 suddenly you're hitting it straight down
14:49 the fairway.
14:50 >> That's a great way to look at it. Skill
14:51 Opt is the master coach. The constraint
14:53 is what makes it powerful.
14:54 >> That restraint is vital. But the real
14:57 superpower of this system, and the
14:59 reason this research is so highly
15:01 anticipated, isn't just that it makes
15:03 one specific model smarter. It is the
15:06 transferability of that coaching. This
15:08 is huge. Yes,
15:09 >> this is exactly what I wanted to get
15:10 into because I can hear someone
15:12 listening to this right now thinking,
15:13 "Well, this is a fascinating experiment,
15:15 but I don't have the compute budget or
15:17 this technical expertise to run two
15:20 massive frontier AIs arguing with each
15:23 other over an instruction manual for
15:24 thousands of epochs. How does this
15:27 actually help the end user?"
15:29 >> Because the final skill is just a plain
15:31 English text artifact, it is highly
15:32 portable. You only have to run the
15:35 expensive optimization loop once.
15:37 >> Just once.
15:38 >> Yes. The researchers did crossmodel
15:40 transfer experiments. They optimized a
15:42 skill using a larger, more capable, and
15:45 far more expensive model like GPT 5.4.
15:48 Then they took that resulting one-page
15:50 text file and handed it down to a much
15:52 smaller, cheaper model like GPT 5.4 Nano
15:55 or even a completely different
15:56 architecture like Quinn 3.54B.
15:58 >> And what happened?
15:59 >> Those smaller target models still saw mass
16:01 ive performance leaps. In fact, in
16:03 relative terms, the small cheap models
16:05 benefit the most from receiving these
16:07 highly refined procedural instructions.
16:09 >> It is quite literally like downloading
16:11 the hard one experience of a senior
16:13 executive into an entry-level worker
16:16 just by handing them a one-page memo.
16:18 >> Exactly.
16:18 >> And it is incredibly resilient. Yeah.
16:21 >> Across entirely different environments.
16:22 The paper shows what they call cross
16:24 harness transfer.
16:25 >> Right. Moving between different software
16:27 setups.
16:28 >> Yeah. They trained a skill in a codeex
16:30 environment which has a very specific
16:31 way of executing Python code and using
16:34 tools.
16:36 >> Then they dropped that exact same text
16:38 file into a clawed code environment
16:39 which might use bash or entirely
16:40 different software tool sets and it
16:44 still worked. It gained almost 60 points
16:46 on spreadsheet bench during that clawed
16:48 code transfer
16:49 >> which is phenomenal.
16:50 >> It really is. It even transfers across
16:52 different math benchmarks, maintaining
16:54 high scores when moving from Olympiad
16:56 Bench to Omnimath,
16:58 >> which proves that the optimizer is not
16:59 just memorizing the test answers. And it
17:02 isn't just memorizing the specific
17:04 software buttons of one environment. It
17:06 is capturing genuine reusable procedural
17:09 knowledge. It learns the philosophy of
17:12 how to approach spreadsheet forensics or
17:15 how to evaluate math theorems in a way
17:17 that applies universally across
17:19 different tasks and models.
17:21 >> So what does this actually mean for you
17:23 the listener trying to integrate AI into
17:26 your workflow? It means the adaptation
17:28 of AI to your specific job, your
17:31 specific company domain is being
17:33 democratized.
17:34 >> It really is. You do not need a team of
17:37 machine learning engineers tweaking
17:38 neural network weights to get a custom
17:40 AI that understands your company's
17:42 filing system. You or someone in the
17:44 open source community runs this scaleup
17:47 loop once offline. You get a plain
17:49 English text file that you can read,
17:51 audit and verify yourself in 5 minutes.
17:53 >> And then you can deploy that file to any
17:55 cheap, fast local model you want and
17:57 instantly upgrade its capabilities to an
17:59 expert level. We are moving from the era
18:01 of trying to adapt the machine's brain
18:03 to adapting the machine's instructions.
18:05 >> But we are finally doing so with the
18:07 mathematical rigor we used to reserve
18:09 only for the machine.
18:10 >> Exactly. So let's quickly recap the
18:13 journey we just took. We started with
18:15 the frustrating, brittle world of
18:20 manually tweaking AI prompts. You know,
18:21 yelling through the tailpipe and hoping
18:23 for the best. And we explored how
18:25 Skillup maps deep learning concepts onto
18:28 text using rollout batches, reflection
18:30 many batches, and an edit budget guided
18:31 by a cosign schedule.
18:32 >> We saw how a strict validation gate and
18:34 a playbook of band plays the rejected
18:36 edit buffer keep the AI from going off
18:38 the rails. And we ended with this tiny,
18:41 elegant, heavily validated text file
18:43 that can be transferred across
18:44 completely different models and
18:46 environments to produce massive gains.
18:48 It is a profound paradigm shift in how
18:50 we think about the interface between
18:52 human intent and machine execution. The
18:54 manual is no longer just a prompt. It is
18:56 a continuously optimized parameter.
18:59 >> Yeah. And before we go, consider this.
19:01 If SkillP proves that a single plain
19:03 English document is the most efficient
19:04 way to quote unquote program frontier
19:06 AIs, what happens to traditional
19:08 software engineers?
19:09 >> That is the million-dollar question,
19:11 >> right? I mean, we have spent the last 50
19:13 years forcing humans to learn the rigid
19:16 language of machines, Python, C++, or
19:19 Java just to get them to do what we
19:22 want. But this research suggests the
19:24 ultimate programming language, the code
19:26 that unlocks the most advanced
19:27 capabilities of our most powerful
19:29 machines, was invented 50,000 years ago.
19:32 >> It's just human speech.
19:34 >> Just human speech. What happens when
19:36 these textbased meta skills become so
19:38 advanced that they start optimizing the
19:40 optimizers? We are entering uncharted
19:42 territory for sure.
19:43 >> Something to think about the next time
19:44 you catch yourself asking AI to write a
19:46 Python script for you. You might already
19:48 be coding in the most powerful language
19:50 on Earth. Thank you so much for taking
19:52 this deep dive with us.
19:54 [music]

</details>
