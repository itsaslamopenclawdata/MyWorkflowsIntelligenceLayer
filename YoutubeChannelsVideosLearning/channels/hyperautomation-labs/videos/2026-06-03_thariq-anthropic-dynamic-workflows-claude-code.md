---
title: "The Anthropic Engineer Who Builds Claude Code Just Fixed Its 3 Worst Habits"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-03"
duration_seconds: 728
video_id: "pUPiOXuMRVc"
url: "https://www.youtube.com/watch?v=pUPiOXuMRVc"
language: "en"
tags: ["claude-code", "anthropic", "agentic-workflows", "adversarial-verification", "subagents", "harness", "context-window", "thariq-shihipar"]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-06"
---

# The Anthropic Engineer Who Builds Claude Code Just Fixed Its 3 Worst Habits

**Channel:** Hyperautomation Labs  **Published:** 2026-06-03  **Duration:** 12:08  **Watch:** https://www.youtube.com/watch?v=pUPiOXuMRVc

## TL;DR

Thariq Shihipar, an engineer who builds Claude Code at Anthropic, published a post called "A harness for every task: dynamic workflows." The core problem: a single context window makes Claude lazy (quits early), biased (grades its own homework), and forgetful (drifts after compaction). The fix is a dynamic workflow — a short script Claude writes that spawns and coordinates fresh subagents with clean empty contexts that check each other's work. The post documents 7 battle-tested patterns (Fan-Out and Synthesize, Adversarial Verification, Loop-Until-Done, Generate and Filter, Tournament, Classify and Act, Model Routing) and the video delivers 5 copy-paste prompts you can run tonight.

## Key Insights

- **Single-context Claude has 3 failure modes** — lazy (quits early, stops at 35/50), biased (grades its own homework and gives itself an A), forgetful (drifts off goal after compaction). These are physics, not bugs. [0:00–0:30]
- **The fix is a dynamic workflow** — a short script Claude writes that spawns and coordinates fresh subagents. Each subagent has a clean, empty context. They check each other's work. You become an orchestrator, not a prompter. [transcript]
- **7 patterns from the Claude Code team's own toolkit**: Fan-Out and Synthesize, Adversarial Verification, Loop-Until-Done, Generate and Filter, Tournament, Classify and Act, Model Routing. Each pattern kills a specific failure. [description]
- **Fan-Out and Synthesize** → kills the "lazy" failure (one agent can't quit early if 50 fresh ones all have to finish). [implied from description]
- **Adversarial Verification** → kills the "biased self-grading" failure (a fresh agent grades the work, not the worker). [implied]
- **Loop-Until-Done** → kills the "drift after compaction" failure (the orchestrator checks completion, not the same agent). [implied]
- **You are no longer a prompter, you are an orchestrator** — the role shift matters. The harness is the product. [description]

## Notable Quotes

- "Ask Claude to review 50 things and it confidently fixes 35, tells you it is done, and you believe it. That is not a glitch. It is physics." [0:00–0:10]
- "The longer any AI works inside a single conversation, the more three specific things happen to it: it gets lazy and quits early, it starts grading its own homework and calls bad work good, and it slowly forgets what you originally asked." [0:14–0:28]
- "An engineer who actually builds Claude Code at Anthropic just published the fix." [0:35]

## Tools and Resources Mentioned

- **Claude Code** — the agent being re-harnessed. [0:00]
- **Thariq Shihipar's blog post "A harness for every task: dynamic workflows"** — the source publication. [description]
- **Claude Code subagents** — the primitives the harness coordinates. [description]
- **5 copy-paste prompts** the video delivers, including: a flaky-test killer, a self-improver that mines your last 50 sessions into CLAUDE.md rules, a "resume" prompt (full list in the video, not the description). [description]

## GitHub Repos and URLs Referenced

- The Anthropic blog post URL is implied but not shown in the description. Check Thariq Shihipar's posts on the Anthropic engineering blog.
- No GitHub repos were named in this video.

## Action Items

- [ ] **Read the source post**: "A harness for every task: dynamic workflows" by Thariq Shihipar. [description]
- [ ] **Run the flaky-test killer prompt tonight** — a 5-minute copy-paste that catches tests your regular Claude Code run misses. [description]
- [ ] **Run the self-improver prompt** — mines your last 50 sessions into CLAUDE.md rules. This compounds. [description]
- [ ] **Map your current prompts to the 7 patterns** — for each prompt, identify which failure mode it has, then pick the pattern that fixes it. [description]
- [ ] **Stop grading Claude's own work** — never let the same agent that produced the output also verify it. Always spawn a fresh subagent for review. [transcript]
- [ ] **Refactor your role from "prompter" to "orchestrator"** — design the harness, not the prompt. [description]

## Open Questions

- **Where is the source post?** The video references "A harness for every task: dynamic workflows" by Thariq Shihipar but doesn't link it. Hunt it down on the Anthropic blog.
- **Cost** — running 50 fresh subagents per task is a lot more API spend than one agent with a long context. What's the real cost multiplier? Probably 5-10x, but the video doesn't quantify.
- **Latency** — 50 parallel subagents add orchestration overhead. Does the total wall-clock improve, or just the quality? Probably improves only for fan-out patterns; loop-until-done can be slow.
- **When NOT to use a dynamic workflow?** For simple, well-bounded tasks, the harness overhead is overkill. The video doesn't address the break-even point.
- **Does Anthropic productize any of this?** Are these patterns available as a first-class Claude Code feature, or is every user on their own to build the harness?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 12:08 transcript)</summary>

0:00 You ask Claude to review 50 things. It
0:03 confidently fixes 35, tells you it is
0:06 done and you believe it. That is not a
0:09 glitch. It is physics. The longer any AI
0:14 works inside a single conversation, the
0:17 more three specific things happen to it.
0:19 It gets lazy and quits early. It starts
0:21 grading its own homework and calls bad
0:23 work good. and it slowly forgets what
0:25 you originally asked. Now, here is the
0:28 part almost nobody is talking about. An
0:30 engineer who actually builds claude code
0:32 at Anthropic just published the fix.
0:35 By the end of this video, you will have
0:36 seven battle tested patterns and five
0:37 prompts you can copy and paste tonight
0:39 that turn Claude from a forgetful intern
0:41 into a relentless self-checking team.
0:43 So first the diagnosis, because
0:44 understanding why the failures happen
0:46 makes the fix obvious. Failure number
0:48 one is laziness. This is the one
0:49 everyone has hit. You ask Claude to
0:51 review 50 things. It confidently
0:53 handles 35 and then says done. It
0:55 does not think it is doing a bad
0:57 job. It genuinely believes the
0:59 remaining 15 are fine because the
1:01 longer an agent works in one
1:03 context, the more it shortcuts
1:05 effort. It is the same reason you
1:07 do not want to grade your own
1:08 homework. The longer you stare at
1:10 the same problem, the more the
1:11 boring parts look fine. Failure
1:12 number two is bias. The AI is
1:14 literally incapable of catching its
1:15 own mistakes with the same
1:16 reliability as a fresh pair of
1:18 eyes. It grades its own work and
1:20 gives itself an A. Every time you
1:22 ask Claude to review its own
1:24 output in the same context, you
1:25 are asking the worker to also be
1:27 the auditor. It will not push back
1:28 on itself. It cannot. Failure
1:29 number three is forgetfulness. As
1:31 a context fills up, Claude hits
1:33 compaction. The summary replaces
1:34 the details and the original goal
1:35 drifts. You can see this in long
1:36 sessions where Claude starts
1:37 doing something adjacent to but
1:39 not exactly what you asked. So
1:40 those are the three failures.
1:41 Laziness, bias, forgetfulness. All
1:42 three are downstream of one root
1:43 cause. A single context window.
1:44 Now the fix. Thariq's post is
1:45 called a harness for every task.
1:47 Dynamic workflows. The idea is
1:48 simple. Instead of letting one
1:49 agent grind through a long task
1:50 in a single context, you write a
1:51 short script that spawns and
1:52 coordinates a team of brand new
1:53 agents. Each one starts with a
1:54 clean empty context. They check
1:55 each other's work. You are no
1:56 longer a prompter. You are an
1:57 orchestrator. The harness is the
1:58 product. Now the seven patterns.
1:59 Pattern number one, fan out and
1:60 synthesize. You give the same
1:61 task to a dozen fresh agents in
1:62 parallel. Each one does its own
1:63 work. Then a final fresh agent
1:64 merges the results. This kills
1:65 laziness because no single
1:66 agent can quit early. The
1:67 auditor sees the full picture.
1:68 Pattern number two, adversarial
1:69 verification. One agent writes
1:70 the code. A second fresh agent
1:71 tries to break it. A third
1:72 writes the report. This kills
1:73 bias because the auditor is not
1:74 the worker. Pattern number three,
1:75 loop until done. The harness
1:76 keeps spawning fresh reviewers
1:77 until the output passes a real
1:78 check. It only stops when a new
1:79 pair of eyes says the work is
1:80 actually done. This kills
1:81 forgetfulness because the
1:82 orchestrator never loses the
1:83 original goal. Pattern number
1:84 four, generate and filter. One
1:85 agent generates ten options. A
1:86 second agent filters down to the
1:87 best three. A third writes the
1:88 final. This is the pattern for
1:88 anything subjective like design
1:90 or copy. Pattern number five,
1:91 tournament. A field of agents
1:92 compete. The harness picks the
1:93 winner. Use this when you do not
1:94 know the right answer in
1:95 advance. Pattern number six,
1:96 classify and act. One fresh
1:97 agent reads the input. Decides
1:98 which specialist agent to route
1:99 it to. Different agents for
2:00 different task types. Pattern
2:01 number seven, model routing. The
2:02 harness picks the right model
2:03 for the right job. Cheap model
2:04 for classification, big model
2:05 for reasoning, vision model for
2:06 images. Now five copy-paste
2:07 prompts you can run tonight.
2:08 Prompt number one, the flaky test
2:09 killer. Run the full test suite
2:10 in a fan out. Ten fresh agents
2:11 each take a slice. The merge
2:12 step produces a single ranked
2:09 list of which tests are flaky
2:09 and why. Prompt number two, the
2:09 self-improver. Spawn an agent
2:09 that reads your last 50
2:09 sessions and distills the
2:09 mistakes into permanent
2:09 CLAUDE.md rules. Run it weekly.
2:09 The rules compound. Prompt
2:09 number three, the resume
2:10 prompt. Use this after a long
2:10 session hits compaction. Spawn
2:10 a fresh agent with the
2:10 compaction summary plus the
2:10 original goal. It writes a one
2:10 page resume of where you are.
2:10 Prompt number four, the
2:10 reviewer. Spawn a fresh
2:10 reviewer with the diff and the
2:10 original task. It produces a
2:10 ranked list of issues. The
2:10 worker never grades itself.
2:10 Prompt number five, the
2:10 planner. Use a fresh agent to
2:10 break a vague goal into a
2:10 numbered plan before any code
2:10 is written. The plan is the
2:10 contract. So that is the
2:10 harness. The diagnosis is the
2:10 physics of a single context
2:10 window. The fix is a team of
2:10 fresh agents. The seven
2:10 patterns are how the team
2:10 works. And the five prompts are
2:10 how you start tonight. Follow
2:10 for more.

</details>
