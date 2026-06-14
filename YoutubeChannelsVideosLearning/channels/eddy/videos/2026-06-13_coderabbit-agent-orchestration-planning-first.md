---
title: "How CodeRabbit Built an AI Agent Orchestration System with Claude"
channel: "Eddy Explainer"
channel_slug: "eddy"
channel_id: "UCZ_4HvkkWlRdM8t5nOiOiYA"
published: "2026-06-13"
duration_seconds: 503
video_id: "WR3oLVG4Ji8"
url: "https://www.youtube.com/watch?v=WR3oLVG4Ji8"
language: "en"
tags: [coderabbit, claude, agent-orchestration, planning-first, prd, claude-opus, claude-sonnet, claude-haiku, eddy]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# How CodeRabbit Built an AI Agent Orchestration System with Claude

**Channel:** Eddy Explainer  **Published:** 2026-06-13  **Duration:** 08:23  **Watch:** https://www.youtube.com/watch?v=WR3oLVG4Ji8

## TL;DR
Eddy Explainer's 8-min take on how CodeRabbit processes 2M pull requests / week across 15,000 customers and built a planning-first orchestration layer in front of Claude to solve the "technically correct but functionally useless code" failure mode. The 4-step orchestration: analyze requirements → surface missing assumptions → write a detailed PRD plan → then generate code. Routing: Claude Opus for strategic orchestration, Sonnet for structured planning, Haiku for narrow targeted tasks. Eval harness uses LLM-as-judge to score plans against downstream code outcomes. Four actionable best practices: define "maximum possible product," ask Claude to list your implicit assumptions, have AI surface edge cases, save planning artifacts for reuse.

## Key Insights
- **The data.** CodeRabbit processes 2M pull requests / week across 15,000 customers — a god's-eye view of where human-AI interaction breaks down at scale. (0:18–0:35)
- **The trap.** AI coding tools have collapsed idea-to-prototype time, but a weird failure mode emerged alongside the speed: the most frequent failure isn't broken buggy code. "The code compiles. It passes the automated tests. The machine is thrilled... but the human is staring at the screen totally frustrated because the underlying business problem wasn't solved." (1:30–2:30)
- **The root cause.** David Loker, VP of AI at CodeRabbit: "As we gain experience as developers, we internalize knowledge. All those things are in our head, and we assume other developers know them, too. But then, we make that assumption of the AI system, as well, that it also implicitly understands. We're not even aware that we're assuming those things. **This, right here, is the hidden danger. The true bug isn't in the code itself. It's actually in our vague prompts and all that silent, implicit human knowledge that we just failed to share.**" (2:15–2:45)
- **David's punchline story.** He was building a memory system for a side project. Asked the AI to build it, clearly specifying "the system required users." Spent hours iterating. Then asked the agent how to use the app — instructions said to pass in a user token. **There was no login page.** He told the AI it required users but never typed "users need a way to sign in." The AI guessed. Hours of work produced a product missing its own front door. (3:21–3:53)
- **Late validation is wildly expensive.** If you wait until the end of a development sprint to discover the AI guessed totally wrong, you've wasted a massive amount of time, money, and compute. "**The cheaper code generation gets, the more expensive it becomes to sprint full speed in the completely wrong direction.**" (3:55–4:18)
- **The fix: planning first.** CodeRabbit built an orchestration layer using Claude that sits between the coding request and the coding agent. It forces the AI to write a master plan (a collaborative PRD) first. The human team reviews, validates assumptions, agrees on the plan — only then does code generation begin. (4:23–4:50)
- **The 4-step orchestration flow.** (1) Analyze initial requirements. (2) **Surface the assumptions you left out** (the magic part). (3) Output a detailed PRD plan. (4) Code generation begins. "It acts as a massive quality gate right at the very front of the process." (4:55–5:18)
- **Routing by task complexity (not one model for everything).** **Claude Opus** drives the orchestration loop and high-level strategic understanding. **Claude Sonnet** sequences that strategy into structured planning steps. **Claude Haiku** handles narrow targeted tasks (distilling context, tool use) where a smaller, faster model does the job. (5:18–5:58)
- **The Goldilocks problem with plans.** Too granular → rigid, goes stale when the codebase shifts. Too high-level → AI starts blindly guessing again, the exact problem they're solving. Solution: a planning-specific eval harness using **LLM judges** to score plan quality. They measure: did the final code work? Did it build unrequested extras? How many tokens did it burn? "A great plan up front creates vastly superior code downstream." (5:58–7:00)
- **Four actionable best practices.** (1) Don't just give basic specs — explicitly define your **maximum possible product (MPB)**, the actual tangible outcome you want. (2) Turn the tables — ask Claude, "what assumptions am I missing here? What is still implicit?" (3) Have the AI actively help you identify edge cases or weird workflows that a human mind might forget. (4) Create a record of work — save planning artifacts so they can be reused and so you can double-check initial intent against final output. (7:06–7:42)
- **The closing frame.** "AI gives us unbelievable leverage, right? But leverage applied in the wrong direction just creates a much bigger mess, much faster. Are your AI agents building what you actually want, or are they just building what they guess?" (7:44–8:05)

## Notable Quotes
> "The true bug isn't in the code itself. It's actually in our vague prompts and all that silent, implicit human knowledge that we just failed to share." — 2:40 (David Loker, CodeRabbit)

> "The cheaper code generation gets, the more expensive it becomes to sprint full speed in the completely wrong direction." — 4:15

> "A great plan up front creates vastly superior code downstream." — 6:58

> "Are your AI agents building what you actually want, or are they just building what they guess?" — 8:02

## Tools and Resources Mentioned
- **CodeRabbit** — AI code review platform; processes 2M PRs/week, 15,000 customers. Built the planning-first orchestration layer described here. ⚠️ **CodeRabbit's product, NOT this stack (MiniMax).**
- **Anthropic Claude (Opus / Sonnet / Haiku)** — the three-model routing inside CodeRabbit's orchestration. Opus for strategy, Sonnet for planning steps, Haiku for narrow targeted tasks.
- **LLM-as-judge eval harness** — the pattern CodeRabbit uses to score plan quality; downstream metrics like "did final code work" become the plan's score signal.

## GitHub Repos and URLs Referenced
- (No specific GitHub repos cited in this short version. The 19-min podcast `-0mi8-uudQQ` covers the same topic with more depth on the orchestration pattern and Eval harness.)

## Action Items
- [ ] Define your "maximum possible product" (MPB) before prompting for any non-trivial code. List the actual tangible outcome, not the implementation.
- [ ] After writing your spec, ask the AI: "what assumptions am I missing here? What is still implicit?" This is the cheapest way to surface hidden knowledge gaps.
- [ ] Have the AI help you identify edge cases and weird workflows before you start coding. The agent that suggests edges during planning is the same agent that will fail on those edges during execution.
- [ ] Save your planning artifacts (PRDs, plan docs, assumption lists) to a record of work. Reuse them; double-check initial intent against final output.
- [ ] If you operate at any scale (>50 PRs/week, >5 codebases), build an eval harness that measures downstream code outcomes (worked, overbuilt, token cost) and use that as a feedback signal on plan quality.
- [ ] Don't route everything through your most expensive model. Match the model to the task: Opus for orchestration, Sonnet for planning steps, Haiku for narrow targeted work.

## Open Questions
- CodeRabbit's eval harness scores plans via "did the final code work" — but how do they handle the inverse (a plan that scored low but produced working code, or a plan that scored high but produced broken code)?
- The "maximum possible product" framing is new to me. Is this a CodeRabbit coinage, or is there a published definition / template?
- For a solo developer without 15,000 customers, what's the smallest viable planning-first layer? Is this pattern overkill for a single feature build?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 8:23 transcript)</summary>

0:01 [snorts]
0:03 [music]
0:06 >> Hey everyone and welcome to the
0:08 Explainer. I am absolutely thrilled
0:10 you're joining us today because we're
0:11 tackling one of the single most
0:13 frustrating problems in software
0:14 development right now. We're looking at
0:16 a genuinely brilliant engineering
0:17 solution from the team at Code Rabbit.
0:19 You know, they process an astonishing 2
0:21 million pull requests a week across
0:22 something like 15,000 customers. And
0:24 with that massive mountain of data, they
0:26 figured out exactly why AI coding agents
0:28 sometimes just go completely off the
0:30 rails. But more importantly, they
0:32 figured out how to stop it. We are going
0:34 to break down their exact blueprint.
0:36 Now look, we all know AI coding tools
0:38 have completely collapsed the time
0:40 between an idea and a working prototype,
0:42 right? I mean, they're generating
0:44 functions, boilerplate, and complex
0:46 logic at absolute breakneck speeds. It
0:48 honestly feels like magic sometimes. The
0:50 throughput is just climbing, lines of
0:53 code are piling up, and sprints that
0:55 used to take weeks are literally taking
0:57 days or even hours. But here's the
0:59 catch. All of that speed is a complete
0:00 and total illusion if the code it spits
0:02 out doesn't actually solve the problem
0:03 you set out to fix.
0:06 Okay, let's dive into this. Is it the
0:07 right code? Because this is where the
0:08 rubber really meets the road. If the
0:09 code is generated incredibly fast, but
0:11 it's fundamentally the wrong code, well,
0:13 you haven't actually saved any time at
0:14 all. In fact, you might have just
0:16 created a massive tangled headache for
0:18 yourself and your entire team. So, we
0:20 really need to look closely at what
0:21 happens when the AI's output totally
0:25 misses the human intent. Chapter 1, the
0:27 AI coding trap, when AI guesses wrong.
0:31 So, when Code Rabbit analyzed those
0:32 millions of AI generated pull requests
0:34 across their massive customer base,
0:36 they noticed a really disturbing trend.
0:38 The most frequent failure mode wasn't
0:39 actually broken buggy code. No, the AI
0:41 wrote code that compiled perfectly. It
0:43 passed all the automated unit tests.
0:45 Structurally, it looked totally sound,
0:46 and yet it still failed completely to do
0:48 what the development team actually meant
0:50 for it to build. The code was
0:52 technically correct, but functionally
0:54 useless.
0:55 Chapter 2, the missing front door, a
0:57 costly assumption.
0:59 David Loker, the VP of AI over at Code
0:60 Rabbit, perfectly diagnosed the root
0:62 cause here. He said, and I quote, "As we
0:64 gain experience as developers, we
0:65 internalize knowledge. All those things
0:66 are in our head, and we assume other
0:67 developers know them, too. But then, we
0:69 make that assumption of the AI system,
0:70 as well, that it also implicitly
0:72 understands. We're not even aware that
0:74 w
0:75 e're assuming those things. This, right
0:77 here, is the hidden danger. The true bug
0:78 isn't in the code itself. It's actually
0:80 in our vague prompts and all that
0:81 silent, implicit human knowledge that we
0:82 just failed to share."
0:84 Now, what's really fascinating about
0:85 this dynamic is the massive disconnect
0:87 happening behind the scenes. On one
0:89 side, you have the human developer's
0:90 brain, which is holding all this
0:92 unwritten, implicit context. You just
0:93 inherently know the user needs to log
0:94 in. You know the database needs strict
0:96 security. You know the basic
0:98 architecture. All because it's just
0:00 obvious to you. But think about the AI
0:01 side of things. The AI doesn't have your
0:04 life experience. When it faces a vague
0:05 prompt, it doesn't pause to ask you for
0:07 clarification. It just blindly guesses.
0:09 It fills in those gaps with whatever it
0:11 considers statistically plausible,
0:13 completely missing the core features you
0:15 actually needed.
0:16 And get this, here is the ultimate
0:17 punchline to David Laper's story. He was
0:19 building a memory system for a side
0:20 project, right? He asked the AI agent to
0:21 build it, clearly specifying that the
0:22 system required users. He spent hours
0:24 iterating with this agent until
0:26 everything ran perfectly. But then, when
0:28 he asked the agent how to actually use
0:29 the app, the instructions told him to
0:30 pass in a user token. The problem? There
0:32 was a literally no login page. He told
0:33 the AI it required users, but he never
0:35 explicitly typed out "users need a way
0:36 to sign in." Because to a human, duh,
0:37 that's obvious. The AI guessed, and
0:38 hours of work resulted in a product
0:39 completely missing its own front door.
0:41 Which brings us to a really harsh
0:42 reality. Late validation is wildly
0:44 expensive. If you're waiting until the
0:45 very end of a development sprint, after
0:46 hours of generating, compiling, and
0:47 testing, just to realize the AI guessed
0:48 totally wrong about your core
0:49 requirements, you've wasted a massive
0:50 amount of time, money, and compute
0:51 power.
0:53 The cheaper code generation gets, the
0:54 more expensive it becomes to sprint full
0:55 speed in the completely wrong direction.
0:58 Chapter three, planning first, the
0:60 orchestration layer.
0:62 So, how do you fix it? Instead of just
0:64 throwing prompts over the fence at
0:65 a coding agent, Code Rabbit built an
0:66 orchestration layer using Claude. This
0:68 layer sits directly between the coding
0:69 request and the coding agent itself. It
0:70 essentially forces the AI to write a
0:71 master plan first, a collaborative
0:73 product requirements document, or PRD.
0:75 This ensures that absolutely everything
0:76 implicit becomes explicitly written out.
0:77 The human team reviews this document,
0:79 validates all the assumptions, and
0:80 agrees on the game plan before single
0:81 line of code is ever generated. Let's
0:83 look at how this builds into a
0:84 completely new orchestration workflow.
0:85 Step one, the system analyzes your
0:87 initial requirements.
0:88 Step two, and honestly, this is the
0:90 magic part, it actively surfaces the
0:91 assumptions that you left out. Step
0:92 three, it outputs a detailed PRD plan.
0:93 And only then, at step four, does the
0:95 actual code generation finally begin. It
0:97 acts as a massive quality gate right at
0:98 the very front of the process.
0:00 Chapter four, routing Claude, matching
0:02 task complexity.
0:03 And this brilliantly illustrates how you
0:04 optimize an AI system for cost, latency,
0:06 and raw intelligence. Code Rabbit
0:08 doesn't just use one massive model for
0:10 everything. No, they use Claude Opus for
0:12 the heavy lifting, driving that
0:14 orchestration loop, and handling the
0:15 high-level strategic understanding.
0:17 Then, they route that output over to
0:18 Claude Sonnet, which completely excels
0:20 at sequencing that strategy into
0:21 structured planning steps. Finally, they
0:23 bring in Claude Haiku for narrow
0:25 specific tasks like distilling context
0:27 or targeted tool use where smaller
0:28 incredibly fast model does the job
0:30 perfectly. They aren't guessing here.
0:31 They actively match the complexity of
0:33 the task to the exact right model.
0:34 Chapter five, measuring plans, building
0:36 an eval harness.
0:37 Now, the Code Rabbit team actually ran
0:38 into a classic Goldilocks problem when
0:40 designing these AI generated plans. See,
0:41 if the plan was too granular and deeply
0:42 detailed, it became rigid and it went
0:44 completely stale the second the
0:45 underlying codebase shifted. But, if the
0:46 plan was too high-level and vague, well,
0:22 it left room for the AI to start blindly
0:24 guessing again, which was the exact
0:25 problem they were trying to solve in the
0:27 first place. They really had to find the
0:29 exact right level of abstraction. So,
0:31 the crucial point is how they actually
0:32 solved this. They built an evaluation
0:33 harness specifically dedicated to
0:34 planning. They used LLM judges to
0:35 objectively score different dimensions
0:36 of the plan's overall quality. Because a
0:38 plan eventually becomes code, they could
0:39 measure things like, "Did the final code
0:41 actually work? Did it build extra things
0:43 we didn't even ask for? How many tokens
0:45 did it burn through?" By comparing
0:46 workflows with and without this planning
0:48 layer, they objectively proved that a
0:49 great plan up front creates vastly
0:50 superior code downstream. Chapter six,
0:52 better AI systems actionable best
0:54 practices.
0:55 Okay, let's wrap up with four rapid-fire
0:57 best practices straight from the Code
0:58 Rabbit team that you can use right now.
0:59 Number one, don't just give basic specs.
0:01 Explicitly define your maximum possible
0:02 product or MPB. What is the actual
0:03 tangible outcome you want? Two, turn the
0:04 tables. Actively ask Claude, "Hey, what
0:05 assumptions am I missing here? What is
0:07 still implicit?" Three, have the AI
0:08 actively help you identify edge cases or
0:09 weird workflows that a human mind might
0:10 easily just forget. And four, create a
0:12 record of work. Save these planning
0:13 artifacts so they can be reused and so
0:15 you can double-check the initial intent
0:16 against the final output before you roll
0:18 it out. This methodology is just
0:19 incredibly empowering.
0:20 Which leaves us with this final thought.
0:22 AI gives us unbelievable leverage,
0:23 right? But leverage applied in the wrong
0:24 direction just creates a much bigger
0:25 mess, much faster.
0:27 So, I really want you to look closely at
0:27 your own workflows, your own prompts,
0:28 and your own internal processes, and ask
0:29 yourself this. Are your AI agents
0:30 building what you actually want, or are
0:31 they just building what they guess?
0:32 Thank you so much for joining me on this
0:33 explainer. I really hope this totally
0:34 reshapes how you think about AI
0:35 orchestration. See you next time.

</details>
