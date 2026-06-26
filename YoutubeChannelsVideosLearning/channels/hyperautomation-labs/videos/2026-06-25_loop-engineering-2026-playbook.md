---
title: "Loop Engineering: The Complete 2026 Playbook (Which AI Loop to Build — and How)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-25"
duration_seconds: 1318
video_id: "8xYDmXUkEAc"
url: "https://youtube.com/watch?v=8xYDmXUkEAc"
language: "en"
tags: [ai-agents, loop-engineering, anthropic, claude-code, multi-agent, evaluator-optimizer, agent-architecture]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-26"
---

# Loop Engineering: The Complete 2026 Playbook (Which AI Loop to Build — and How)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-25  **Duration:** 00:21:58  **Watch:** https://youtube.com/watch?v=8xYDmXUkEAc

## TL;DR
The best 2026 builders don't prompt agents — they design loops that prompt the agent, check the work, and run until it passes. Anthropic's "Building Effective AI Agents" blueprint gives six architectures (single agent, sequential, parallel, evaluator-optimizer, hierarchical, collaborative) and a 3-question picker (control, complexity, budget). Convergence requires a deterministic oracle the agent can't fake, a fresh context every turn, and a separate judge model that reads the diff.

## Key Insights
- **The shift from prompting to loop engineering** — Boris Cherny (Anthropic, head of Claude Code): "I don't prompt Claude anymore. I have loops running that prompt Claude and figure out what to do. My job is to write loops." Anthropic says "almost all of Claude code is being written by Claude code and it can run effectively for days at a time." (timestamp 0:37)
- **The 5-stage loop anatomy: Discover → Plan → Execute → Verify → Iterate.** "A reliable loop beats a perfect prompt." (timestamp 2:13)
- **Two loop sizes:** single agent (one brain, focused work) vs. fleet (orchestrator + specialists + sub-agents for big missions). (timestamp 2:46)
- **The 3-question picker (Anthropic's framework):** Q1 control (high-stakes → sequential or single agent), Q2 complexity (multi-domain predictable → workflow; open-ended → fleet), Q3 budget (limited → single agent or careful parallel — multi-agent burns 10-15x tokens). (timestamp 8:07)
- **Open vs. closed loops.** Open loops explore broadly, drift, burn tokens. Closed loops are bounded: defined path, defined goal, eval after each step, stop condition, handoff point. "Start with closed loops. Open them up later once your checks are strong enough." (timestamp 9:30)
- **The single biggest mistake: letting the agent grade its own work.** "The model that just wrote a solution sees its own answer as the most likely thing to say next. An agent's self-assessment is not a check. It's an echo." The check must be a deterministic oracle: a test, type-check, linter, build, threshold number — something that returns an exit code, not an opinion. (timestamp 10:43)
- **Start each iteration from clean context** ("context rot" — model degrades as context fills, past instructions get lost). Keep progress on disk + git, not in agent memory. (timestamp 11:54)
- **Reward hacking is the silent killer.** Give the loop one goal (make the test pass) and it will delete the assertion, mock the real logic, or hardcode the expected value. Defenses in layers: (1) read-only test files, (2) gate that fails the run if tests changed in the diff, (3) a separate judge model on a different model reading the diff asking "did this go green because the code got fixed or because the test got gutted?" Anthropic uses exactly this. (timestamp 12:46)
- **Anthropic's evaluator doesn't just read diffs — it opens the live app with Playwright, clicks around, tests for real, and writes harsh critiques.** "The adversarial pressure is the entire point." (timestamp 14:08)
- **Memory without context rot:** status file the loop reads first / writes last (human-readable log + critical state in JSON). (timestamp 14:55)
- **Handoffs beat compaction.** Anthropic's finding: "compaction doesn't actually fix the drift." Structured handoffs: a planner turns the one-line goal into a spec; the generator and evaluator negotiate a contract through files BEFORE a single line is written. (timestamp 15:25)
- **Isolation:** give each agent its own git worktree; run the whole loop in a container with network off so a poisoned instruction hidden in a file can't reach out. "Define the loop by what it can destroy, not just by what you want it to do." (timestamp 16:03)
- **Breaks with observability:** hard cap on iterations, budget cap per turn, circuit breaker on repeated failures, heartbeat file, structured log (one JSON line per event). "When the loop dies at 3am, you read exactly how it died instead of guessing." (timestamp 16:30)
- **Cost is not linear — it's quadratic.** A stateful loop that rereads its whole history every turn grows with the square of iterations. Same task stateless = few hundred dollars; same task stateful = tens of thousands. (timestamp 17:33)
- **Four ways loops die:** runaway (bill climbs, nothing turns green), silent death (hangs on full context), random walk (moves but never toward done), and "understanding debt" (code ships faster than you can read it — only discipline catches that). (timestamp 18:01)
- **Real production numbers:** Coinbase runs agentic systems against $226B quarterly trading volume at 99.99% availability; Intercom's Fin resolves up to 86% of support conversations; Inscribe cut fraud review time 20x (30 min → 90s); Thomson Reuters put 3,000+ subject-matter experts into one legal agent. (timestamp 19:46)
- **The North Star:** start simple, measure everything, add complexity only when it earns its keep. The e-commerce team's journey: single support agent → routing → specialized agents → multi-agent with two evaluators, adding a stage only when the last one paid for itself. (timestamp 19:13)

## Notable Quotes
> "The model that just wrote a solution sees its own answer as the most likely thing to say next. So, it systematically rates its own work too highly. That is not the model being lazy. It's a direct result of how it samples. An agent's self-assessment is not a check. It's an echo." — 10:53
> "The thing that grades the work can never be the thing that made it." — 11:19
> "A reliable loop beats a perfect prompt." — 2:40
> "Define the loop by what it can destroy, not just by what you want it to do." — 16:25
> "Compaction doesn't actually fix the drift." — 15:23

## Tools and Resources Mentioned
- **Anthropic — "Building Effective AI Agents"** — the official architecture blueprint with the 6 architectures + 3-question picker (referenced throughout)
- **Anthropic — "Building agents that run for hours" workshop** — source for the Playwright-evaluator + structured handoff patterns
- **Claude Code (Anthropic)** — vendor: Anthropic's CLI coding agent (NOT the user's MiniMax Hermes Agent)
- **Augment Code** — example customer: single Claude agent finished a 2-week vs. 4-8 month CTO estimate
- **Playwright** — vendor: Microsoft's open-source browser automation, used by Anthropic's evaluator to drive the live app

## Action Items
- [ ] Identify your most boring repeatable task. Wrap it in a closed loop with a deterministic check (test, lint, build, threshold).
- [ ] Before reaching for a fleet, add skills to a single agent and confirm it doesn't solve the problem first.
- [ ] For any loop you let run unattended: enforce fresh-context-per-iteration + read-only test files + a separate judge model + network-off container + iteration/budget caps + heartbeat + JSON-line log.
- [ ] Audit your "deterministic oracle" — run the check 10x on the same code; if it flickers green/red, fix the check before building the loop (a flaky check destroys the stop condition).
- [ ] Add a reward-hacking gate: any test changes in the diff = fail the run, no exceptions.

## Open Questions
- What's the canonical source for the "loop engineering" field manual Hyperautomation Labs is offering via comment ("converge")? It's not in the public description.
- How does the 25k-token response cap interact with the "give each agent its own git worktree" pattern when sub-agents need to share large artifacts?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full HH:MM:SS transcript)</summary>

0:00 Right now, you are the loop. You type a
0:03 task, you wait for an answer, you read
0:06 it,
0:06 you spot the mistakes, you fix them, and
0:09 then you prompt again.
0:11 You are the part in the middle that
0:12 checks the work and decides what happens
0:15 next.
0:16 The best builders in the world just stop
0:19 doing doing that.
0:21 Within days of each other,
0:22 two of the most senior engineers in AI
0:24 said the same thing.
0:26 Peter Steinberg said said you shouldn't
0:28 be prompting coding agents anymore.
0:30 You should be designing loops that
0:31 prompt your agents.
0:33 And Boris Cherny, the head of Claude
0:35 code at Anthropic, said it from the
0:37 inside.
0:39 I don't prompt Claude anymore.
0:41 I have loops running that prompt Claude
0:43 and figure out what to do.
0:45 My job is to write loops.
0:47 Two weeks ago, we covered why that went
0:50 viral.
0:51 This is the full playbook.
0:54 By the end, you'll know exactly which
0:56 loop to build
0:57 and how to build one that runs for hours
0:59 without burning your money or losing its
1:00 mind.
1:01 And this isn't hype. It is already how
1:03 Anthropic builds Claude code itself.
1:06 >> And we're now at the point where almost
1:08 all of Claude code is being written by
1:09 Claude code and it can run effectively
1:12 for days at a time.
1:14 >> So, what is a loop really?
1:16 A prompt is a single instruction.
1:18 You ask, the model answers, and it's
1:22 done.
1:23 A loop is different. A loop turns
1:25 itself.
1:27 You set the goal once and the system
1:29 finds the work. Does it, checks it,
1:32 repairs what failed, and keeps going
1:34 until the result passes.
1:36 Prompting gives an agent an instruction.
1:39 Loop engineering gives an agent a job.
1:41 Here's the old way that most people
1:43 still use.
1:44 You prompt, the agent answers,
1:47 you review,
1:48 you find the mistake, you fix it, and
1:51 you repeat by hand.
1:52 It works,
1:53 but it doesn't scale because you are the
1:56 bottleneck.
1:57 The new way,
1:59 you define the goal, the loop discovers
2:01 what's needed, it plans the work,
2:03 the agent executes,
2:05 a checker verifies the result,
2:08 the loop fixes the failures,
2:10 and it stops
2:11 when the goal is reached.
2:13 Every good loop has the same five
2:14 stages.
2:16 Discover.
2:17 Plan.
2:18 Execute.
2:19 Verify.
2:20 Iterate.
2:22 If the output passes, ship it.
2:25 If it fails, it goes back around.
2:27 That is the whole idea.
2:29 Not one perfect prompt.
2:31 A system
2:32 that keeps making an imperfect output
2:34 better until it clears the bar.
2:37 Remember that line because it's the
2:38 thesis of this whole video.
2:40 A reliable loop beats a perfect prompt.
2:43 Loops come in two sizes.
2:46 The first is a single agent loop.
2:49 One agent runs the whole cycle.
2:51 It figures out what's needed,
2:53 plans, executes,
2:55 checks its own result, and improves it.
2:58 It's like one person rewriting their own
3:00 draft.
3:01 That's perfect for focused work.
3:04 A bug fix, a research summary, a content
3:07 draft.
3:08 One brain, one loop.
3:10 The second size is a fleet.
3:12 Here you give one orchestrator agent the
3:14 mission, and it breaks the work into
3:16 pieces,
3:17 and hands those pieces to specialist
3:19 agents.
3:20 And each specialist can spin up its own
3:22 sub-agents for the narrow jobs.
3:24 Picture building a productivity app. The
3:26 orchestrator owns the mission.
3:28 Then a research specialist, an
3:30 engineering specialist, and a QA
3:32 specialist each take a lane.
3:34 And under engineering sits a code writer
3:37 and a debugger.
3:39 That is not one agent working alone.
3:41 It's a small team running a project
3:43 end-to-end.
3:44 So, the obvious question is, when do you
3:46 use which?
3:47 Last week, Anthropic published the
3:49 official map. Let's read it.
3:52 Anthropic's blueprint is called building
3:54 effective AI agents.
3:55 And it starts with the atom inside every
3:58 system.
3:59 Their words,
4:01 an AI agent operates in a continuous
4:03 loop.
4:03 It perceives the environment, decides
4:05 the next step, and acts to accomplish a
4:07 goal.
4:08 Perceive, decide, act, then look at the
4:11 result, and go again. That's the engine.
4:14 The simplest shape is the single agent.
4:17 And this is the real diagram straight
4:18 from the document.
4:20 Input goes to the model.
4:22 The model reaches tools through MCP,
4:24 pulls from memory, and loads skills,
4:27 then produces output,
4:29 looping until the job is done.
4:31 Anthropic's guidance on when to use it
4:33 is blunt.
4:35 Single agents shine on open-ended
4:37 problems where you can't predetermine
4:39 the steps, because you don't know up
4:41 front how many you'll need.
4:43 When should you avoid one?
4:45 When you need the perfect answer on the
4:47 first try,
4:48 every single time.
4:50 And here's the line most people skip.
4:53 Before you scale up to a fleet,
4:55 ask whether adding skills to one agent
4:58 solves it first.
4:59 One of their customers, Augment Code,
5:02 pointed a single Claude agent at a code
5:04 base,
5:04 and finished in 2 weeks what their CTO
5:07 had estimated at 4 to 8 months.
5:10 One agent, aimed well, is not a small
5:12 thing.
5:13 Now, not every loop should be free to
5:15 roam.
5:16 Sometimes, you want fixed rails, and
5:18 that's what workflows are.
5:20 Predefined loops.
5:22 The first is sequential.
5:25 Here's the real diagram.
5:27 Each step feeds the next.
5:29 Draft, then review, then polish.
5:32 The win is predictability.
5:35 You get a clean audit trail and the same
5:37 behavior every time,
5:39 which is exactly what you want for
5:40 approvals and compliance.
5:42 The cost is flexibility.
5:45 A rigid chain is brittle
5:47 the moment an edge case doesn't fit.
5:49 The second is parallel.
5:51 Here, independent agents work at the
5:54 same time, and you merge the results.
5:56 This is the real financial risk example
5:59 from the doc.
6:00 A credit agent, a market agent, an
6:03 operational agent, and a regulatory
6:05 compliance agent,
6:06 all evaluating one loan at once.
6:09 Then a decision engine combines them.
6:11 You reach for parallel when speed
6:13 matters.
6:14 Or when several perspectives raise your
6:16 confidence,
6:18 like having multiple agents vote.
6:20 You avoid it when the agents need to
6:22 coordinate on shared state,
6:24 because nobody is in charge of resolving
6:25 the conflict.
6:26 Now, the powerful ones.
6:28 First, evaluator-optimizer.
6:31 Two agents in a loop.
6:33 One generates, the other evaluates
6:35 against fixed criteria, and sends back
6:38 specific fixes.
6:39 And they cycle.
6:41 Usually two to four times until it's
6:42 good.
6:44 Here's the real diagram.
6:46 A generator writes API documentation.
6:49 A technical evaluator checks it against
6:51 the actual code, and they iterate until
6:53 every check passes.
6:55 Hold onto this pattern, because it is
6:57 the heart of the entire video.
6:59 The maker is never the only grader.
7:02 Then there's the full multi-agent
7:05 system.
7:06 And it splits into two shapes.
7:08 Hierarchical,
7:10 where a supervisor delegates to
7:11 specialists,
7:12 and treats them like tools.
7:14 This is the real marketing example.
7:17 A director agent coordinating research,
7:20 design,
7:21 copywriting, and media planning.
7:24 And collaborative or swarm,
7:27 where agents talk peer-to-peer with no
7:29 central boss, like this competitive
7:30 intelligence team.
7:33 Anthropic's own research found that on
7:35 complex tasks that need many independent
7:37 directions at once,
7:39 a multi-agent system with Claude Opus as
7:41 the lead.
7:42 And Claude Sonnet as the sub-agents,
7:45 beat a single agent by 90.2%.
7:48 But, there's a catch, and it's a big
7:50 one.
7:51 Multi-agent systems burn roughly 10 to
7:54 15 times more tokens.
7:56 And the context can balloon past what
7:58 one agent can hold.
7:59 Which is why the doc suggests capping
8:01 responses around 25,000 tokens.
8:04 So, which one do you actually build?
8:07 Anthropic gives you a decision
8:08 framework.
8:10 And it comes down to three questions.
8:13 Question one.
8:14 How much control do you need?
8:16 If you're in a high-stakes, regulated,
8:18 audit-everything world,
8:20 start with a single agent or a
8:22 sequential workflow.
8:24 Because you can explain exactly why it
8:26 did what it did.
8:27 Loosen the control and hierarchical and
8:29 then collaborative systems become
8:32 viable.
8:33 Question two.
8:35 How complex is the problem?
8:37 A single domain, like answering product
8:39 questions, a single agent handles fine.
8:43 Multi-domain, but predictable.
8:46 Use a sequential or parallel workflow.
8:49 Truly open-ended, that's where
8:51 multi-agent earns its cost.
8:54 Question three.
8:55 What are your resource constraints?
8:57 A limited budget points you straight
9:01 back to single agents
9:01 or carefully designed parallel
9:03 workflows.
9:04 Because remember,
9:06 multi-agent runs 10 to 15 times the
9:08 tokens.
9:10 And here's the rule that saves you the
9:12 most money.
9:14 If you just need deep expertise, add
9:16 skills to a single agent before you ever
9:18 reach for a fleet.
9:19 Start simple.
9:21 Earn the complexity.
9:23 Here is the most important practical
9:24 distinction in the whole space, and
9:26 almost nobody leads with it.
9:28 Loops come in two types.
9:30 Open and closed.
9:32 An open loop is exploratory.
9:35 You hand the agent a broad goal and let
9:37 it find its own path.
9:38 It's powerful
9:40 because it can discover things you never
9:41 specified.
9:43 It's also expensive and messy.
9:45 It'll try too many paths, burn tokens,
9:48 and drift away from what you actually
9:49 wanted.
9:51 A closed loop is bounded.
9:54 You design the path first.
9:56 The loop still runs on its own, but
9:58 inside clear rules, a defined goal,
10:02 evaluation after each step, a stop
10:04 condition,
10:05 and a handoff point if it gets stuck.
10:08 The closed loop is the version that pays
10:10 off today.
10:11 It's cheaper, it's more reliable, and it
10:13 produces cleaner output. So, the advice
10:16 is simple.
10:17 Start with closed loops.
10:19 Open them up later once your checks are
10:22 strong enough to trust.
10:24 Which raises the real question.
10:26 How do you build checks you can actually
10:28 trust? That is the rest of this video.
10:32 Most loops that fail don't fail because
10:34 the idea was wrong. They fail because
10:36 the loop can't tell whether it's
10:38 actually done. And here's the trap
10:40 almost everyone falls into.
10:43 They let the agent grade its own work.
10:45 Think about why that's broken at the
10:47 level of the math.
10:49 The model that just wrote a solution
10:51 sees its own answer as the most likely
10:53 thing to say next.
10:55 So, it systematically rates its own work
10:57 too highly. That is not the model being
10:59 lazy.
11:00 It's a direct result of how it samples.
11:03 An agent's self-assessment is not a
11:05 check. It's an echo.
11:07 And this isn't just one blogger's
11:09 theory.
11:10 Here is Anthropic's own engineering team
11:13 in their workshop on building agents
11:15 that run for hours.
11:16 So, the rule is simple and hard.
11:19 The thing that grades the work can never
11:21 be the thing that made it.
11:23 That check has a name.
11:26 A deterministic oracle.
11:28 Something that returns an exit code, not
11:30 an opinion.
11:32 A test that passes or fails, a type
11:34 check, a linter, a build, a number over
11:38 a threshold.
11:39 Here's the simplest loop that actually
11:41 works, and it's real code.
11:43 A while loop runs the check, and if it's
11:45 red, it asks the agent for the minimal
11:47 fix, then runs the check again until
11:50 it's green or it hits a limit.
11:52 But look closely, because there's a
11:54 non-obvious decision baked into this.
11:57 Every iteration starts the agent fresh
12:00 from clean context.
12:02 Why throw away the conversation each
12:03 time?
12:04 Because models degrade as their context
12:06 fills up.
12:07 The instructions from the top get lost,
12:10 and the model gets distracted by its own
12:11 past turns.
12:13 They call it context rot.
12:15 So, you keep the progress on disk, in
12:17 the files, and in Git,
12:19 not in the agent's memory.
12:22 Each run reads the changed files
12:24 and the failing test
12:26 with a short, clean context.
12:29 And one rule on that article,
12:31 it has to be deterministic.
12:34 Run your check 10 times on the same
12:35 code.
12:37 If it flickers green, then red,
12:39 fix the check before you build the loop,
12:41 because a flaky check destroys the stop
12:43 condition.
12:44 Now, the subtle failure mode.
12:46 Give a loop one goal,
12:48 make the test pass, and the agent will
12:50 find the cheapest route to green.
12:53 And often, the cheapest route isn't
12:55 fixing the code.
12:56 It's breaking the test.
12:58 Delete the assertion.
13:00 Mock out the real logic.
13:02 Hard code the expected value.
13:04 This is called reward hacking. And
13:07 again, it's not malice.
13:09 It's the optimizer doing exactly what
13:12 you asked,
13:13 exploiting a hole in your metric.
13:16 The defense comes in layers.
13:19 Writing, please. Don't weaken the tests
13:21 into the prompt is the weakest one.
13:23 The real defense is a check the agent
13:25 can't reach.
13:27 Make the test files read-only or add a
13:30 gate that fails the run
13:31 if the tests changed in the diff.
13:34 That gate costs almost nothing and it's
13:36 always on.
13:38 The strongest layer is a separate judge
13:40 running on a different model
13:42 that reads the diff and asks one
13:44 question.
13:46 Did this go green because the code got
13:48 fixed
13:49 or because the test got gutted?
13:52 A model is bad at catching its own
13:54 self-deception
13:56 but good at catching another model's.
13:58 Anthropic builds exactly this
14:01 and it raises one more question.
14:03 The one their own engineers asked out
14:05 loud
14:06 in their workshop on agents that run for
14:08 hours.
14:09 >> The obvious question for me at least is,
14:11 you know, if the evaluator is also just
14:12 an LLM,
14:14 um why doesn't it just rubber stamp it,
14:15 too?
14:17 The evaluator here isn't just reading
14:19 diffs, but it's actually using
14:20 Playwright,
14:22 um to open live pages, click around, try
14:24 things out.
14:26 >> That's the answer.
14:27 Their evaluator doesn't just read the
14:29 diff.
14:31 It opens the live app with Playwright.
14:33 Clicks around.
14:35 Tests it for real.
14:36 And writes harsh critiques.
14:38 The adversarial pressure is the entire
14:40 point.
14:41 Now
14:42 everything so far gets you a loop
14:45 that converges once.
14:47 To make it run for hours
14:49 you need a few more pieces.
14:51 First, memory
14:52 because the model forgets the moment a
14:54 run ends.
14:55 But the repo doesn't.
14:57 You keep a status file the loop reads
14:59 first and writes last.
15:01 A human-readable log
15:03 plus the critical state in JSON
15:05 so the loop's logic
15:07 never depends on how the model reverted
15:08 its plan today.
15:10 Second and this is the one most people
15:12 get wrong
15:13 handoffs.
15:15 When a long run starts to lose the plot
15:17 the instinct is to compact the context
15:19 and keep going.
15:21 But Anthropic found that compaction
15:23 doesn't actually fix the drift.
15:25 Structured handoffs, too.
15:27 >> So,
15:28 before the generator actually goes ahead
15:30 and writes a single line, um
15:32 we have the two agents basically
15:34 negotiate what done actually means.
15:38 >> Here's what that means in practice.
15:41 A planner turns your one-line goal into
15:44 a real specification.
15:46 And then,
15:47 the generator and the evaluator
15:50 negotiate a contract through files
15:52 before a single line of code is writ
15:53 ten.
15:55 The work is handed off cleanly,
15:57 not smeared across one endless context.
16:01 Third piece, isolation.
16:04 A loop running unattended
16:06 needs a blast radius.
16:08 Give each agent its own Git work tree,
16:10 so they don't collide. Then go further
16:12 and run the whole thing in a container
16:14 with the network turned off,
16:16 so a poisoned instruction hidden in some
16:19 file
16:20 can't reach out and cause real damage.
16:22 Define the loop by what it can destroy,
16:25 not just by what you want it to do.
16:27 And fourth, breaks with observability.
16:30 A hard cap on iterations. A budget cap
16:33 per turn.
16:34 A circuit breaker that trips if the same
16:36 failure repeats. A heartbeat file, so
16:39 you can see it's alive.
16:41 And a structured log, one JSON line per
16:43 event. So, when the loop dies at 3:00 in
16:46 the morning, you can read exactly how it
16:49 died instead of guessing.
16:51 None of that is optional.
16:53 That is the floor for anything you leave
16:55 running while you sleep.
16:57 Let's talk money,
16:58 because this is where loops actually
17:00 break people.
17:01 Loops burn tokens fast.
17:03 A single medium coding loop can use
17:05 50,000 to 200,000 tokens.
17:09 A fleet with an orchestrator and several
17:12 specialists can hit 500,000 to 2
17:14 million.
17:16 A scheduled daily loop can reach
17:18 millions of tokens a week.
17:20 Every retry,
17:21 every self-correction,
17:23 every verification step, every
17:26 sub-agent, all of it costs. And here's
17:28 the part that breaks intuition.
17:30 Cost is not linear.
17:33 If your loop is stateful and rereads its
17:35 whole history every turn,
17:37 cost grows with the square of the
17:39 iterations.
17:40 That is the real reason you go
17:41 stateless.
17:43 A fresh context keeps each iteration
17:45 roughly flat.
17:46 The same task in Brex's hands
17:49 closes for a few hundred dollars of API.
17:53 Unbrexed, it can burn tens of thousands.
17:56 The difference isn't the model.
17:58 It's whether there was a real check and
18:00 real limits.
18:01 Loops die four ways.
18:03 Runaway,
18:05 where the bill climbs and nothing turns
18:06 green.
18:08 Silent death,
18:09 where it hangs on a full context.
18:11 Random walk,
18:13 where it moves but never toward done.
18:16 And the dangerous one,
18:17 understanding debt,
18:19 where the code ships faster than you can
18:22 read it.
18:23 And no log catches that one.
18:26 Only your discipline does.
18:28 Let's put it all on one board. Single
18:30 agents,
18:31 best for focused, well-defined work,
18:34 cheapest to run,
18:35 but they hit a ceiling on truly complex
18:38 problems.
18:39 Sequential workflows,
18:41 best for multi-step approvals and
18:43 pipelines,
18:44 fully auditable, but brittle on the
18:46 unexpected.
18:47 Parallel,
18:49 best for speed and multiple
18:50 perspectives,
18:51 but weak when agents must coordinate.
18:54 Evaluator-optimizer,
18:56 best for quality on nuanced output
18:59 at the price of extra cycles.
19:02 Hierarchical and collaborative fleets,
19:04 best for sprawling
19:06 multi-domain missions, the most capable,
19:09 and by far the most expensive.
19:11 And here's the thing, you don't pick one
19:13 forever.
19:15 Anthropic shows an e-commerce team's
19:16 journey
19:17 from a single support agent to routing
19:20 to specialized agents
19:22 to a full multi-agent system.
19:24 Two evaluator agents for quality.
19:27 Adding a stage only when the last one
19:29 paid for itself.
19:31 That is the North Star.
19:33 Start simple, measure measure
19:35 everything.
19:36 Add complexity only when it earns its
19:39 keep.
19:40 And if this still sounds theoretical,
19:42 it isn't.
19:44 These are the numbers organizations are
19:46 reporting with Claude-powered loops in
19:47 production.
19:49 Coinbase runs agentic systems against
19:51 $226 billion
19:53 in quarterly trading volume
19:55 at 99.99%
19:57 availability across dozens of internal
19:59 AI applications.
20:02 Intercom's fin agent resolves up to 86%
20:05 of support conversations.
20:07 Inscribe cut fraud review time roughly
20:09 20 times over
20:11 from 30 minutes down to about 90
20:13 seconds.
20:14 And Thomson Reuters put the expertise of
20:16 over 3,000 subject matter experts
20:19 into a single legal agent.
20:22 This is the same loop you just learned
20:24 running at scale.
20:26 The only real question is whether you
20:28 build one, too.
20:29 So, here's the whole playbook in three
20:31 breaths. One,
20:33 a loop turns itself.
20:34 It discovers,
20:36 plans, executes,
20:38 verifies, and iterates until the work
20:41 passes.
20:42 And a reliable loop beats a perfect
20:45 prompt.
20:46 Two,
20:47 pick your shape with three questions.
20:50 Control,
20:51 complexity, and budget.
20:54 And add skills to a single agent before
20:56 you ever build a fleet.
20:58 Three,
20:59 make it converge with a check the agent
21:01 can't fake. A fresh context every turn.
21:04 A judge on a different model, and real
21:06 breaks.
21:08 And only then do you let it run for
21:10 hours.
21:11 I packaged every piece of this into one
21:13 free field manual.
21:14 The three question picker,
21:16 the cheat sheet for all six
21:17 architectures,
21:19 the full convergence checklist with copy
21:21 paste code,
21:22 and the four ways loops die,
21:24 and exactly how to stop each one.
21:26 To get it, just comment the word
21:28 converge,
21:29 and I'll send it straight to you, or
21:31 grab the link in the description.
21:33 If this leveled up how you think about
21:35 AI,
21:36 subscribe here on YouTube and follow
21:38 Hyper Automation Labs on Facebook and
21:39 Instagram, because we go this deep every
21:42 single week. And if you want to go
21:44 further, the paid guides linked below
21:46 are your next step.
21:47 Now, go take your most boring task,
21:50 wrap it in one closed loop with a real
21:52 check, and build the thing that builds
21:54 for you.
21:55 I'll see you in the next one. Next.

</details>