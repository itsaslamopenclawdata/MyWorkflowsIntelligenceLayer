---
title: "Nobody Could Define 'Loop Engineering' — an Anthropic Insider Just Published the Recipe (Fable 5)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-10"
duration_seconds: 923
video_id: "ss09UQpGmck"
url: "https://youtube.com/watch?v=ss09UQpGmck"
language: "en"
tags: [claude-fable-5, loop-engineering, agentic-loops, claude-managed-agents, lance-martin, self-correction, memory-ladder, anthropic, verifiers]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# Nobody Could Define 'Loop Engineering' — an Anthropic Insider Just Published the Recipe (Fable 5)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-10  **Duration:** 15:23  **Watch:** https://youtube.com/watch?v=ss09UQpGmck

> **Source note:** This is independent analysis of a public post by Lance Martin (engineer at Anthropic, ex-LangChain) titled "Designing loops with Fable 5." Vendor: Anthropic. The "vendor's engineer testing his own company's model" caveat is acknowledged in the video itself — see "The 4 honest catches" in Key Insights.

## TL;DR

A decode of Lance Martin's "Designing loops with Fable 5" post. The whole recipe in one picture: a self-correction loop inside the session + a memory loop across sessions + one non-negotiable rule (the maker is never the grader). Verified primitives: `/goal` in Claude Code uses a separate Haiku checker model after every turn; the API twin is "Outcomes" in Claude Managed Agents. The Parameter Golf receipt: Fable 5 improved an OpenAI-hosted ML pipeline ~6× more than Opus 4.7, betting on structural changes and pushing through a quantization regression to its biggest win. The 5-rung memory ladder: fail → investigate → verify → distill → consult — Sonnet 4.6 exits at rung 1, Opus 4.7 at rung 3 (7-33% verified), Fable 5 completes the ladder (73% in strongest runs). Three moves you can run today without the managed beta. Four honest catches including the meter nobody mentions.

## Key Insights

- **The two-loop picture**: (1) self-correction loop inside the session — agent does work, gets feedback, corrects, goes again until a written-down goal is satisfied; (2) memory loop across sessions — agent writes what it learned today into files, reads them back tomorrow. Plus the one rule that makes both trustworthy: the agent that did the work is never the one that grades it. Grading happens in a separate, independent context window. (02:23)
- **The verified primitives**:
  - **`/goal` in Claude Code**: type `/goal` plus a finish line ("all tests in the outage folder pass and the linter is clean"). After every turn, a separate small model (Haiku by default) checks whether your condition is now true. If the condition fails, Claude takes another turn. When it passes, the loop ends. (03:44)
  - **Outcomes in Claude Managed Agents** (API side): hand it a rubric and the harness spawns a grader agent in a completely independent context window. (04:22)
- **Why a verifier subagent beats self-critique**: Anthropic's own engineering blog: "Tuning a standalone evaluator to be skeptical is far more tractable than making a generator critical of its own work." Agents grading their own work tend to confidently praise it even when quality is mediocre. (04:38)
- **Parameter Golf receipt (the OpenAI gym)**: OpenAI's own challenge — train the best language model that fits in 16MB in 10 minutes on 8×H100s. Lance used Claude Managed Agents with the 8 GPUs as a sandbox, a rubric file with 9 checkable criteria, and let it run for up to 8 hours with no human in the middle. Fable 5 improved the training pipeline ~6× more than Opus 4.7. (05:09, 06:26)
- **The behavior insight (not the number)**: Opus 4.7's first experiment produced a small win, then almost everything after followed the same template — adjust a scalar, measure, keep if positive. Fable 5 bet on big structural changes. At one point it shipped a change that made things worse (a quantization regression), did not retreat to safe tweaks, pushed through the regression, and that line of work became its single biggest win. (06:42)
- **The 5-rung memory ladder** (Continual Learning Bench, UC Berkeley):
  - Rung 1: **fail** — get something wrong and write it down
  - Rung 2: **investigate** — before moving on, figure out why
  - Rung 3: **verify** — turn the diagnosis into a checked fact
  - Rung 4: **distill** — turn the fact into a general rule
  - Rung 5: **consult** — next session, read the rule instead of re-deriving it
  - Sonnet 4.6 exits at rung 1. Opus 4.7 climbs to rung 3 (verifies 7-33% of answers, median ~17%). Fable 5 tends to complete the ladder — verified 22 of 30 (73%) in its strongest runs, distilled into general rules. (09:09)
- **Three moves you can run today without the managed beta**:
  1. **The `/goal` loop** — in Claude Code, stop ending your prompt at "do the task." Write the finish line instead. A checker model owns the question, not your patience at 11pm. (10:56)
  2. **The separate grader** — before accepting any big piece of work, spawn one fresh sub-agent whose only job is to verify the result against your rubric in a clean context window. It has not seen the reasoning, so it cannot be seduced by it. (11:20)
  3. **The memory ladder** — Claude Code already gives you memory files that persist across sessions. The upgrade is discipline, not a tool. Do not let your agent store guesses. A memory entry earns its place by climbing the ladder. (11:37)
- **The 4 honest catches**:
  1. **Scale**: "just a few small-scale experiments." One challenge, one benchmark task, a handful of runs. Directionally fascinating, not peer-reviewed. (12:23)
  2. **Headline number is best case**: 73% verification is Fable 5 on its strongest runs, not its average day. (12:41)
  3. **Managed version is gated**: Claude Managed Agents is in beta, API only, not on Bedrock or Vertex yet. Companies on those clouds build these loops themselves. (12:53)
  4. **The meter nobody mentions**: an 8-hour self-correcting loop on 8×H100s spends money every minute, win or lose. Self-correction = more turns. Separate grader = second agent billing tokens. Memory = every session reads extra context. The recipe is real, and the most expensive way to use a model that is already expensive. (13:07)
- **The leverage moved**: rather than directly prompting and steering Fable 5, it is often better to design loops that let the model self-correct and manage its own context. Your prompts now matter less. Your finish lines, your rubrics, and your memory discipline matter more. (14:15)

## Notable Quotes

> "The agent that did the work is never the one that grades it. Grading happens in a separate, independent context window. The maker is never the grader. Burn that into your wall." (03:13, 04:55)

> "Tuning a standalone evaluator to be skeptical is far more tractable than making a generator critical of its own work." — Anthropic engineering blog, quoted (04:48)

> "Which experimenter are you? Because most of us, after one early win, spend the rest of the project adjusting scalars." (07:41)

> "Your prompts now matter less. Your finish lines, your rubrics, and your memory discipline matter more. The leverage moved again." (14:29)

## Tools and Resources Mentioned

- **Claude Code `/goal` command** (vendor: Anthropic) — write a finish line, a separate Haiku checker evaluates after every turn
- **Claude Managed Agents — Outcomes** (vendor: Anthropic, API beta) — hand a rubric, harness spawns a grader agent in an independent context
- **Claude Managed Agents — Memory store** (vendor: Anthropic, API beta) — a directory mounted into the sandbox, read/written with the same file tools
- **Parameter Golf challenge** (vendor: OpenAI, on OpenAI's GitHub) — 16MB model, 10 min, 8×H100s
- **Continual Learning Bench** (vendor: UC Berkeley) — long sequence of questions against a SQL database, fresh agent session per question
- **Free Loop Recipe PDF from Hyperautomation Labs**: https://hyperautomationlabs.co/free/fable-5-loop-recipe
- **Lance Martin's original post (source)**: https://x.com/RLanceMartin/article/2064397389189071163
- **Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

## Action Items

- [ ] Rewrite your next Claude Code task to use `/goal` with a measurable finish line instead of an open-ended prompt
- [ ] Before accepting any big piece of agent work, spawn a fresh sub-agent in a clean context to verify against your rubric
- [ ] Audit your memory file discipline — every entry should record FAILED / WHY / VERIFIED / RULE, not just "I tried X"
- [ ] Apply the 5-rung memory ladder to your own note system (most are rung-1 memory dumps)
- [ ] Set a hard `--max-turns` cap on any self-correcting loop before turning it on
- [ ] If running on AWS Bedrock or GCP Vertex, plan to build these primitives yourself (Managed Agents isn't there yet)
- [ ] If you publish a benchmark yourself, surface the meter — Fable 5 at 2× Opus pricing over hours is not a rounding error

## Open Questions

- How does `/goal` actually work mechanically — is Haiku always the checker, can you swap the checker model, what's the latency cost per turn?
- Does the memory ladder result hold outside the SQL-database continual-learning benchmark?
- For the Parameter Golf comparison, was the 8-hour budget the same for both Fable 5 and Opus 4.7, and was the rubric identical?
- What's the actual cost of an 8-hour Fable 5 self-correcting loop at $10/$50 per M tokens on 8×H100s?
- Does Claude Managed Agents ship with the memory ladder as a built-in primitive, or is the discipline a user-level pattern?
- Will the "managed beta" gated status change before or after the June 23 metered cutoff?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 15:23 transcript)</summary>

0:00 Days ago,
0:01 two of the most senior AI engineers
0:03 alive said the same six words.
0:06 Stop
0:07 prompting your agents.
0:09 Start designing loops.
0:11 It hit millions of views.
0:14 And the most upvoted reply was, "Nobody
0:17 actually knows what that means." Well,
0:20 somebody just answered.
0:22 Two days ago, an engineer inside
0:24 Anthropic, Lance Martin,
0:26 published the actual recipe.
0:29 How people design loops around Claude
0:31 fable 5.
0:33 Inside the company that built it. And he
0:35 didn't just describe it.
0:37 He tested it on OpenAI's own public
0:40 challenge.
0:41 A machine learning competition that
0:43 OpenAI created
0:45 on OpenAI's own GitHub.
0:48 He let Claude run in it for 8 hours
0:50 straight with no human in the middle.
0:53 The result was not close.
0:55 So, this video is the decode.
0:58 Two loops, one rule.
1:00 The self-correction loop that runs while
1:02 the agent works.
1:04 The memory loop that survives after the
1:05 session dies.
1:07 The one rule that makes both of them
1:09 trustworthy.
1:10 And the four honest catches the post
1:12 does not put in bold.
1:14 First, who is Lance Martin? And why does
1:17 this post carry weight?
1:19 Because the internet is drowning in loop
1:21 gurus right now. And this is not one of
1:24 them.
1:25 Lance Martin spent years as a founding
1:27 era engineer at LangChain, leading the
1:29 open-source Python framework that half
1:31 the industry used to build its first
1:34 agents.
1:35 Before that, a Stanford PhD.
1:37 Then computer vision for self-driving
1:39 cars.
1:40 In January, he joined Anthropic. And his
1:43 stated mission was simple.
1:46 Help people get the most out of Claude.
1:48 So, when he writes, quote,
1:50 "Mythos-class models like Claude fable 5
1:53 have changed the way many of us work at
1:55 Anthropic." That is not marketing copy.
1:58 That is an engineer describing his own
2:00 daily workflow with experiments
2:02 attached. And one more thing.
2:05 Boris Cherny,
2:06 the creator of Claude Code,
2:08 the man who says his job is to write
2:10 loops,
2:11 Lance opens the post by quoting him.
2:15 This is the inside answer to the exact
2:18 question
2:19 the entire internet was asking last
2:23 week.
2:23 Here is the whole recipe in one picture.
2:26 Strip away the benchmarks
2:29 and Lance's post says one thing.
2:33 Stop steering the model sentence by
2:35 sentence.
2:36 Build two loops around it instead. Loop
2:39 one runs inside the session.
2:42 The agent does the work,
2:44 collects feedback from its environment,
2:46 corrects itself, and goes again
2:49 until a goal you wrote down is actually
2:51 satisfied.
2:52 That is the self-correction loop.
2:54 Loop two runs across sessions.
2:57 The agent writes what it learned today
2:59 into files,
3:00 and it reads them back tomorrow.
3:03 That is the memory loop, an outer loop
3:06 wrapped around every session the agent
3:08 will ever run.
3:09 And then, one rule that makes both loops
3:12 trustworthy.
3:13 The agent that did the work is never the
3:15 one that grades it.
3:17 Grading happens in a separate,
3:19 independent context window. So,
3:22 self-correction inside the session,
3:24 memory across sessions,
3:26 a grader that is never the maker.
3:29 That is the recipe.
3:31 Everything else in this video is the
3:33 receipts and exactly how to build each
3:35 piece.
3:36 So, how do you actually build loop one?
3:39 Lance names two primitives, and I
3:41 verified both against the official docs.
3:44 They are real shipping features.
3:46 In Claude Code, it is the goal command.
3:49 You type {slash} goal, then a finish
3:51 line.
3:52 All tests in the outage folder pass
3:55 and the linter is clean.
3:57 From that moment, Claude keeps working.
4:00 And after every single turn, a separate
4:02 small model,
4:04 Haiku, by default, checks whether your
4:06 condition is now true.
4:08 Not Claude grading itself.
4:10 A second model checking.
4:13 If the condition fails, Claude takes
4:15 another turn.
4:17 When it passes, the loop ends.
4:19 On the API side, the same idea is called
4:22 outcomes
4:23 inside Claude managed agents.
4:26 You hand it a rubric and the harness
4:28 spawns a grader agent in a completely
4:30 independent context window.
4:32 And here is why that separation matters
4:34 so much.
4:36 Anthropic's own engineering blog found
4:38 that agents grading their own work
4:41 tend to confidently praise it
4:43 even when the quality is mediocre.
4:46 Their words,
4:48 "Tuning a standalone evaluator to be
4:50 skeptical is far more tractable than
4:52 making a generator critical of its own
4:54 work.
4:55 The maker is never the grader.
4:58 Burn that into your wall."
5:01 Now the receipts. And the first one has
5:04 a twist the post only mentions in
5:06 passing. To test the self-correction
5:09 loop, Lance needed a hard, measurable
5:12 challenge. He picked parameter golf,
5:15 an open machine learning competition.
5:18 Train the best language model you can
5:21 that fits inside a 16 MB file in under
5:24 10 minutes on eight H100 GPUs.
5:28 There is one training file.
5:30 The agent edits it, launches a run,
5:32 polls the log,
5:34 reads the score,
5:35 and decides what experiment to try next.
5:39 Here is the twist.
5:41 Parameter golf was created by OpenAI.
5:44 It is OpenAI's challenge on OpenAI's
5:47 GitHub
5:49 fronted by OpenAI's chief research
5:51 officer.
5:53 So, an Anthropic engineer walked Claude
5:56 into OpenAI's own gym and asked it to
5:59 lift. The setup was clean.
6:02 Claude managed agents
6:04 with the eight GPUs attached as a
6:05 sandbox.
6:07 A Rubik file with nine checkable
6:09 criteria.
6:10 Run a baseline.
6:12 Run 20 experiments.
6:14 And a greater agent that refused to let
6:16 Claude stop until every criterion was
6:18 met.
6:19 Then he let it run for up to eight
6:21 hours.
6:22 No human in the middle.
6:24 The loop was the supervisor.
6:26 He ran that same eight-hour loop with
6:28 Opus 4.7 and with Claude Fable 5.
6:32 Fable 5 improved the training pipeline
6:35 roughly six times more than Opus 4.7
6:37 did.
6:38 But the number is not the lesson.
6:40 The behavior is.
6:42 Lance sorted the experiments into two
6:44 kinds.
6:45 Scalar changes.
6:47 Nudge a constant, adjust a learning
6:48 rate.
6:49 Tweak and measure.
6:52 And structural changes.
6:54 Rip out and redesign a piece of the
6:56 architecture itself.
6:58 Opus 4.7's very first experiment
7:00 produced a small win.
7:02 And then almost everything after
7:03 followed the same template.
7:05 Adjust a scalar. Measure. Keep it if
7:08 positive.
7:10 A safe little ritual repeated for eight
7:12 hours.
7:13 Fable 5 bet on big structural changes.
7:17 And here is the detail I cannot stop
7:18 thinking about.
7:20 At one point, it shipped a change that
7:22 made things worse.
7:24 A quantization regression.
7:26 It did not retreat to safe tweaks.
7:29 It pushed through the regression,
7:31 kept working the idea.
7:33 And that line of work
7:35 became its single biggest win of the
7:36 whole run.
7:38 Be honest with yourself for a second.
7:41 Which experimenter are you?
7:43 Because most of us, after one early win,
7:47 spend the rest of the project adjusting
7:49 scalars.
7:50 That is the loop inside a session. Now,
7:53 the outer loop. Memory.
7:55 Every agent session eventually dies.
7:58 The context fills up. The session ends.
8:01 And tomorrow, the agent starts from
8:03 zero.
8:05 Re-deriving everything it already
8:07 figured out yesterday at your expense.
8:10 Memory is the loop wrapped around that.
8:13 During a session, Claude writes what it
8:15 learned into files.
8:17 In future sessions, it reads them back.
8:20 In Claude-managed agents, this is
8:22 literal.
8:23 A memory store
8:25 mounted into the sandbox as a directory
8:27 shared across sessions
8:29 read and written with the same file
8:31 tools as everything else.
8:34 To test whether models actually use it
8:36 well,
8:37 Lance grabbed a brand new benchmark.
8:40 Continual learning bench out of UC
8:42 Berkeley.
8:43 The task,
8:44 answer a long sequence of questions
8:46 against a SQL database.
8:49 And every question is a fresh agent
8:51 session.
8:53 The only thing that survives from one
8:54 question to the next is the memory
8:56 folder.
8:58 So, the real thing being measured is not
9:00 can the model write database queries.
9:03 It is
9:04 does the model learn from its own
9:06 yesterday?
9:07 And this is where Lance hands us the
9:09 most useful framework in the whole post.
9:12 Using memory well is a ladder with five
9:14 rungs.
9:15 Rung one, fail.
9:17 Get something wrong and write it down.
9:20 Rung two, investigate.
9:23 Before moving on, figure out why.
9:26 Rung three,
9:27 verify.
9:29 Turn the diagnosis into a checked fact.
9:32 Rung four,
9:33 distill.
9:34 Turn the fact into a general rule.
9:37 rung five consult
9:39 Next session, read the rule instead of
9:42 re-deriving it.
9:44 Now, watch where each model gets off the
9:46 ladder.
9:47 Sonnet 4.6 exits at rung one.
9:51 Its memory is a pile of failure notes
9:53 and open guesses.
9:55 Maybe the price column has a different
9:57 name, {question mark}
9:59 and it rarely reads its own notes back.
10:02 Opus 4.7 climbs to rung three.
10:06 It builds a real schema reference
10:09 and it flags its own uncertainty.
10:12 But, it only verifies 7 to 33% of its
10:15 answers.
10:17 The median run, about 17%.
10:21 Fable five tends to complete the ladder.
10:24 In its strongest runs, it verified 22 of
10:26 30 questions,
10:28 73%.
10:30 And it distilled what it learned into
10:32 general rules that made every future
10:34 task cheaper.
10:36 Now, open your own notes app.
10:39 Most human note systems are a rung one
10:41 memory, a pile of things that went
10:42 wrong,
10:44 never investigated, never distilled,
10:47 never consulted.
10:48 So, what can you actually run today
10:51 without Anthropic's managed
10:52 infrastructure?
10:54 Three moves.
10:56 Move one, the goal loop.
10:58 This one is free.
11:00 In Claude code, stop ending your prompt
11:02 at do the task.
11:05 Write the finish line instead.
11:07 /goal
11:09 All tests pass. The linter is clean. The
11:11 build succeeds.
11:13 Now, a checker model owns the question,
11:16 is it done?
11:17 Not your patience at 11:00 p.m.
11:20 Move two, the separate grader.
11:23 Before you accept any big piece of work,
11:25 spawn one fresh sub-agent whose only job
11:29 is to verify the result against your
11:30 rubric in a clean context window.
11:33 It has not seen the reasoning, so it
11:35 cannot be seduced by it.
11:37 Move three, the memory ladder.
11:40 Claude code already gives you memory
11:42 files that persist across sessions.
11:45 The upgrade is not a tool.
11:47 It is discipline.
11:49 Do not let your agent store guesses.
11:52 A memory entry earns its place by
11:54 climbing the ladder. What failed? Why?
11:57 The verified fact, the general rule.
12:00 And if you want the fully managed
12:02 version of all three moves, Claude
12:04 managed agents with outcomes and memory
12:06 stores is that exact recipe hosted. It
12:10 is in beta on the API right now.
12:13 Now the catches.
12:15 Because this is still a vendor's
12:16 engineer
12:18 testing his own company's model,
12:20 and you deserve the unbolted fine print.
12:23 Catch one, scale.
12:26 Lance says it himself, quote,
12:28 "Just a few small-scale experiments."
12:31 One challenge,
12:32 one benchmark task, a handful of runs.
12:36 Directionally fascinating.
12:38 Not a peer-reviewed result.
12:40 Catch two,
12:41 the headline number is the best case.
12:45 That 73% verification figure is Fable 5
12:48 on its strongest runs,
12:50 not its average day. Catch three, the
12:53 managed version is gated.
12:55 Claude managed agents is in beta,
12:57 API only,
12:59 and it is not on Bedrock or Vertex yet.
13:03 If your company lives there, you are
13:04 building these loops yourself for now.
13:07 And catch four,
13:08 nobody in the post mentions the meter.
13:11 An 8-hour self-correcting loop on 8 H100
13:14 GPUs
13:15 is a loop that spends money every
13:17 minute, win or lose.
13:19 Self-correction means more turns.
13:22 A separate grader means a second agent
13:24 billing tokens.
13:26 Memory means every session reads extra
13:28 context.
13:29 The The recipe is real.
13:32 It is also the most expensive way to use
13:33 a model that is already expensive.
13:36 So, design the loop and cap it.
13:39 So, 1 week ago
13:41 stop prompting.
13:42 Start designing loops.
13:44 was a vibe.
13:46 Today, it has a recipe.
13:48 Published from inside the building.
13:51 A self-correction loop inside the
13:53 session with the finish line written
13:55 down.
13:56 A memory loop across sessions climbing
13:59 five rungs.
14:00 Fail. Investigate. Verify. Distill.
14:04 Consult.
14:06 And one non-negotiable rule.
14:08 The maker is never the grader.
14:11 But here is the line in Lance's post
14:13 that matters most.
14:15 Rather than directly prompting and
14:17 steering Fable 5
14:18 it is often better to design loops
14:21 that let the model self-correct and
14:23 manage its own context.
14:25 Read that again.
14:27 Your prompts now matter less.
14:29 Your finish lines, your rubrics
14:31 and your memory discipline matter more.
14:34 The leverage moved again.
14:36 And that is a skill you can start
14:38 building this afternoon.
14:40 I have packed the whole thing into one
14:42 free PDF.
14:44 The Fable 5 loop recipe.
14:47 The two loop diagram.
14:49 The gold command setup. A copy-paste
14:51 verifier rubric.
14:53 The five-rung memory ladder and all four
14:56 catches.
14:58 Comment the word recipe
15:00 and I will send it straight to you.
15:02 Full credit to Lance Martin.
15:05 The link to his original post is the
15:07 first line of the description.
15:09 I drop bite-size AI breakdowns every day
15:12 on Instagram.
15:13 And the full deep dives right here on
15:16 YouTube.
15:17 Subscribe.
15:18 The loops are getting smarter.
15:20 The people who design them should be
15:21 too.

</details>
