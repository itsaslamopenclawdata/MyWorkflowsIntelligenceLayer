---
title: "An AI Approved a $1.4M Loan at 2:47 AM — How to Design Agentic AI Systems"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-24"
duration_seconds: 712
video_id: "RGIcn7A3Cqs"
url: "https://www.youtube.com/watch?v=RGIcn7A3Cqs"
language: "en"
tags: [agentic-ai, ai-governance, human-in-the-loop, supervision-design, automation, anthropic, claude, parasuraman, roi, process-design]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-25"
---

# An AI Approved a $1.4M Loan at 2:47 AM — How to Design Agentic AI Systems

**Channel:** Hyperautomation Labs
**Published:** 2026-06-24
**Duration:** 11 min 52 sec
**Watch:** https://www.youtube.com/watch?v=RGIcn7A3Cqs

## TL;DR

A top-10 US bank's AI agent approved a $1.4M line of credit at 2:47 AM with no human in the loop — the decision was technically correct, but the bank rolled the agent back 6 weeks later because supervisors had quietly stopped watching. The video reframes agentic AI design as designing **two systems** (the agent + the human supervision around it), then gives a 6-principle blueprint: start with workflows not agents, treat autonomy as a tiered dial keyed to blast radius, instrument humans with the same rigor as models, engineer visible friction, rotate watchers before they go numb, and close the override loop with a named owner on every high-stakes decision. The central insight is Parasuraman's law: **the better your agent performs, the worse your human gets at catching the one decision that matters** — reliability breeds inattention, so you cannot fix it with policy, only with system design.

## Key Insights

- **The "2:47 AM failure"** (Ravi Palwe, Forbes): the agent wasn't broken, the supervisors had decayed. Three-week decay curve: week 1–3 sharp, week 4–6 faster, week 7–10 skim under 15s, week 12 just clicking through.
- **Override rate is a trap metric.** When it drifts from 8% → <2%, leadership celebrates the agent getting smarter — but the agent didn't change, the reviewer stopped catching. Falling override rate = alarm, not trophy.
- **Measurement blind spot:** dashboards instrument the agent (accuracy, latency, drift, error rate) to the decimal, while supervisors get nothing — no time-on-case, no reasoning-expansion rate. "The agent gets a dashboard. The supervisor gets a chair." In 3 engagements, time-on-case had dropped 60–80% by week 12, and nobody had measured it.
- **Parasuraman's law (human factors):** when automation is reliable, humans catch ~30% of errors; when it visibly stumbles sometimes, detection climbs to ~75%. This is a property of brains, not a personality flaw. You cannot fix it with a sternly worded email — you have to design around it.
- **Workflow vs. agent:** workflows = human decides steps, AI fills them in (on rails); agents = AI decides its own steps and acts (full autonomy). Anthropic's guidance: use the simplest thing that works; every drop of autonomy is a drop of supervision you now must design for.
- **Autonomy as a dial by blast radius:** low-stakes/reversible → run + sample review; medium → act + human notified + clawback; high-stakes/irreversible (large loan, payment, anything un-undoable) → agent prepares, human must actively approve before execution. Same agent, different leash.
- **Engineered friction wins:** slip in known-bad cases the agent should fail and verify the reviewer catches them; on high-stakes decisions, force the reasoning trace open before approve can be clicked; rotate in cases that genuinely need judgment. An agent that never appears to need you is an agent nobody watches the day it's finally wrong.
- **Rotation is a multiplier:** in a wealth-management rollout, rotating supervisors across agent workflows every 6 weeks improved error catch rate ~35% with zero changes to the underlying agent. Attention is a resource that depletes; rotation refills it.
- **Closed override loops sustain supervision:** every override feeds a documented review, the agent's policy actually updates, and the team that flagged it sees their judgment mattered. Open loops teach supervisors their input changes nothing — and supervision that goes nowhere is supervision that quits.
- **Named ownership at 2:47 AM:** the scariest question wasn't "was the agent right?" — it was "who owns this?" Every high-stakes decision needs a named human owner before ship.

## Notable Quotes

- "Once you see the 2:47 a.m. failure, you'll find it hiding inside almost every AI agent project. And it tends to strike right around week 12."
- "From the outside, an agent improving and a reviewer checking out look exactly the same. And only one of them is good news."
- "The agent gets a dashboard. The supervisor gets a chair." — Palwe
- "The better your agent performs, the worse your human gets at catching the one decision that matters."
- "Reliability breeds inattention. It's a property of human brains. Not a personality flaw you can train away or motivate away."
- "Use the simplest thing that works and only reach for an autonomous agent when a workflow genuinely can't do the job." — Anthropic guidance, paraphrased
- "Every drop of autonomy you hand over is a drop of supervision you now have to design for."
- "Attention is a resource that depletes, and rotation is how you refill it. Build it into the schedule from day one. Not after the first incident."
- "An agent that never appears to need you, is an agent nobody will be watching the day it's finally wrong."
- "Supervision that goes nowhere is supervision that quits."
- "You don't just need to know what's running. You need to know who is still awake to watch it."

## Tools and Resources Mentioned

- **Anthropic** guidance to engineers: prefer the simplest thing that works; reach for an autonomous agent only when a workflow genuinely cannot do the job.
- **Raja Parasuraman** — human-factors researcher whose automation-reliability / human-detection findings (~30% vs ~75%) anchor the argument.
- **Ravi Palwe** (Forbes) — originator of the "2:47 a.m. failure" framing and the case studies cited (top-10 US bank; wealth-management rotation experiment).
- **Claude Code, Codex, Claude "selling," Claude certification prep** — author's four companion guides (links in description).
- **One-page supervision checklist** — free downloadable from the author covering autonomy tiers, supervisor metrics, rotation cadence, and the three Monday questions; keyword "watcher" in comments or link in description.

## GitHub Repos and URLs Referenced

- No GitHub repositories, code links, or technical URLs were referenced in this video. All cited sources are written pieces:
  - Ravi Palwe, *Forbes* article on the "2:47 a.m. failure."
  - Raja Parasuraman's human-factors research on automation reliability and operator vigilance.
- Channel follow links (non-technical):
  - Hyperautomation Labs on YouTube
  - Hyper Automation Labs on Instagram and Facebook

## Action Items

- **Run the 3 Monday questions (half a day):**
  1. What is your average time-on-case today, and what was it in month one? If you don't know → that's your first problem.
  2. What was the override rate in month one, and what is it now? If it dropped a lot, decide honestly: agent improving, or human disengaging?
  3. When was the last time a supervisor's override actually changed the agent's behavior? If "never" → your loop is open.
- **Map every agent decision to a blast-radius tier** (low / medium / high) and assign the matching autonomy + review pattern. Same model, different leash depending on how much damage a single mistake can do.
- **Start every agent build with a workflow first.** Only escalate to agentic autonomy when the workflow genuinely cannot do the job, and treat each autonomy escalation as a supervision-design deliverable, not a feature flag.
- **Build a supervisor dashboard that mirrors the model dashboard** — time-on-case, reasoning-expansion rate, override rate over time. Treat a falling override rate as an alarm; investigate whether the agent improved or the humans checked out.
- **Schedule rotation of supervisors across agent workflows every ~6 weeks** before fatigue sets in. Expect ~35% improvement in error-catch rate with no model changes (per the wealth-management case study).
- **Engineer visible friction deliberately:** inject known-bad cases and verify reviewers catch them; on high-stakes decisions, force the reasoning trace open before approve can be clicked; mix in genuine judgment-call cases.
- **Close the override loop:** every override → documented review → agent policy actually updates → change communicated back to the flagger. No open loops.
- **Assign a named human owner to every high-stakes decision before ship**, so "who owns this?" always has an answer at 2:47 AM.
- **Download the one-page supervision checklist** (comment "watcher" or grab the link in description) and walk it through with the team.

## Open Questions

- Where is the right cutover between a "medium-stakes" clawback window and a "high-stakes" synchronous human-approval step? The video gives the principle but not a numerical rubric.
- For high-frequency, near-real-time decisions (e.g., fraud blocks, market-making), how do you apply the named-owner + friction principles without introducing unacceptable latency?
- How do you measure "reasoning expansion" without invading supervisor privacy or creating Goodhart-style gaming of the metric itself?
- What does the right rotation cadence look like for non-financial, lower-stakes agents (e.g., internal IT helpdesk vs. loan approval)? The 6-week figure comes from one wealth-management rollout; generalizability is untested in the video.
- Does Parasuraman's ~30% / ~75% detection rate generalize to LLM-based agents specifically, or only to classical automation? The video cites the finding as a hard law but doesn't distinguish.
- At what team size does a dedicated human-supervision designer / "watcher" become a real role vs. an additional responsibility bolted onto existing ops?
- How do you detect a 2:47 AM-style failure *before* week 12, ideally in pilot? Are there leading indicators earlier in the decay curve worth instrumenting?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 11 min 52 sec transcript)</summary>

0:00 At 2:47 in the morning, inside a top 10
0:02 US bank,
0:04 an artificial intelligence agent
0:05 approved a $1.4 million line of credit.
0:08 No human looked at it. Nobody even knew
0:11 it had happened until the morning
0:12 stand-up, 6 hours later.
0:14 And here's the unsettling part.
0:16 The decision was completely correct.
0:19 The borrower met every criterion.
0:21 The agent was right.
0:23 6 weeks later, they rolled it back
0:25 anyway.
0:26 Not for a model error.
0:28 Not for a regulator.
0:30 But because the people paid to supervise
0:31 that agent had quietly stopped looking
0:33 at the screen.
0:35 A consultant named Ravi Palwe
0:37 wrote about this in Forbes, and he calls
0:39 it the 2:47 a.m. failure.
0:41 Once you see it, you'll find it hiding
0:43 inside almost every AI agent project.
0:46 And it tends to strike right around week
0:47 12.
0:48 Here's the mistake almost everyone
0:50 makes.
0:51 When people set out to design an agentic
0:53 AI system,
0:55 they think they're designing one thing.
0:57 The agent.
0:59 The model. The tools. The prompts.
1:02 The guardrails.
1:04 But you're actually designing two
1:05 systems.
1:06 The agent and the human supervision
1:08 wrapped around it.
1:10 And the second one is the one nobody
1:11 designs.
1:12 It just happens.
1:14 A few people get assigned to review the
1:16 agent's decisions,
1:18 and everyone assumes that's enough.
1:20 It isn't because human attention is not
1:22 a constant.
1:23 It decays.
1:25 And it decays on a schedule you can
1:26 almost set your watch to.
1:28 So, let me show you that decay curve
1:30 because it's the heart of this whole
1:32 problem.
1:33 In the first 3 weeks, supervisors are
1:35 sharp.
1:36 They open every case. They expand the
1:39 agent's reasoning.
1:40 They catch the small mistakes.
1:42 By week 4 to 6, they're still reviewing,
1:44 just faster.
1:46 The little issues repeat, so they start
1:48 trusting the agent on the obvious calls.
1:51 By week 7 to 10, they're skimming, under
1:54 15 seconds a the
1:55 And by week 12, they're just clicking
1:58 through.
1:58 Now, watch the number that fools
2:00 everyone.
2:01 The override rate.
2:03 How often a human corrects the agent
2:06 starts around 8% and drifts below two.
2:09 And the institution celebrates.
2:11 Look, the agent is getting smarter.
2:13 Except, it isn't.
2:15 The agent didn't change at all.
2:17 The supervisor is simply catching less.
2:19 From the outside, an agent improving
2:22 and a reviewer checking out look exactly
2:24 the same. And only one of them is good
2:26 news.
2:27 So, why does no one catch this in time?
2:29 A measurement blind spot.
2:31 We instrument the agent down to the
2:33 decimal point.
2:34 Accuracy, latency,
2:36 error rate, drift,
2:39 beautiful dashboards, all green.
2:41 But, the supervisor?
2:43 We measure nothing.
2:44 Nobody tracks how long a reviewer
2:47 actually spends per case
2:48 or whether they still open the reasoning
2:50 at all.
2:51 As Pal V puts it, the agent gets a
2:53 dashboard. The supervisor gets a chair.
2:56 In three separate engagements,
2:59 he asked one simple question.
3:01 What's your average time on case in week
3:02 12 versus week one?
3:04 Every single time,
3:06 nobody had measured it.
3:08 When they finally did, time on case had
3:10 dropped 60 to 80%.
3:12 The supervisors hadn't gotten lazy.
3:15 The work changed underneath them and no
3:16 instrument was pointed at it.
3:18 And here's the part that turns this from
3:20 a story into a law.
3:23 This is not about lazy employees.
3:25 Decades ago, a human factors researcher
3:28 named Raja Parasuraman measured it.
3:31 When automation is reliable most of the
3:33 time,
3:34 humans catch only about 30% of its
3:36 errors.
3:37 But, when the automation visibly
3:38 stumbles now and then,
3:40 human detection climbs back up toward
3:41 75%.
3:43 Read that again.
3:44 The better your agent performs, the
3:46 worse your human gets at catching the
3:48 one decision that matters.
3:50 Reliability breeds inattention.
3:52 It's a property of human brains. Not a
3:55 personality flaw you can train away or
3:57 motivate away.
3:58 Which means you cannot fix this with a
3:59 sternly worded email. You have to design
4:02 around it. So, let's build the
4:04 blueprint. Six principles.
4:06 Principle one,
4:07 start simpler than you think.
4:10 Workflow before agent.
4:12 Burn this distinction into your memory.
4:16 A workflow is when you, the human,
4:19 decide the steps and the AI just fills
4:22 them in.
4:23 Predictable, on rails.
4:25 An agent is when the AI decides its own
4:28 steps and acts on its own.
4:31 Full autonomy feels exciting.
4:33 But, most tasks don't need it.
4:37 Anthropic's own guidance to engineers is
4:40 blunt.
4:41 Use the simplest thing that works and
4:43 only reach for an autonomous agent when
4:45 a workflow genuinely can't do the job.
4:47 Every drop of autonomy you hand over is
4:49 a drop of supervision you now have to
4:51 design for.
4:52 So, don't give it away for free.
4:54 Make the agent earn it.
4:56 Principle two, autonomy is a dial, not a
5:00 switch.
5:01 The bank's mistake wasn't using an
5:03 agent.
5:04 It was letting one agent run at the same
5:07 autonomy level for a $100 decision and a
5:11 $1.4 million one.
5:14 Design your system in tiers based on
5:16 blast radius.
5:18 Low stakes and reversible,
5:20 let it run and review by sample.
5:24 Medium stakes,
5:25 the agent acts, but a human is notified
5:28 and can claw it back.
5:29 High stakes or irreversible,
5:31 a large loan, a payment, anything you
5:34 can't undo, the agent prepares the
5:36 decision,
5:37 but a human has to actively approve it
5:39 before it happens.
5:40 Same agent, different leash depending on
5:43 how much damage a single mistake can do.
5:45 Principle three, instrument the human.
5:48 Not just the agent.
5:50 This is the fix for that blind spot.
5:52 Whatever you measure for the model,
5:54 measure a mirror of it for the
5:56 supervisor.
5:57 Track time on case.
5:59 Track how often they expand the
6:01 reasoning before approving.
6:03 Track the override rate over time.
6:05 And here's the mindset flip.
6:07 Treat a falling override rate as an
6:09 alarm. Not a trophy.
6:12 When overrides quietly drop,
6:14 don't assume the agent got better.
6:16 Assume your humans might be checking
6:17 out. And go find out which one it
6:19 actually is.
6:21 If you don't have a number for whether
6:23 your supervisors are still supervising,
6:25 you have a measurement problem long
6:27 before you have a safety problem.
6:30 Principle four.
6:31 The counter intuitive one.
6:33 Engineer a little visible friction.
6:35 Remember Parasuraman.
6:37 A perfectly smooth agent puts humans to
6:40 sleep.
6:41 So wake them up on purpose.
6:43 Periodically,
6:45 slip in a known bad case.
6:47 A test the agent should fail.
6:50 And check that your reviewer actually
6:52 catches it.
6:53 On high stakes decisions,
6:55 force the reasoning trace open before
6:58 anyone can click approve.
7:00 Rotate in cases that genuinely need a
7:02 judgment call.
7:04 You are deliberately building moments
7:05 where the human has to think.
7:07 Because an agent that never appears to
7:09 need you, is an agent nobody will be
7:11 watching the day it's finally wrong.
7:13 Principle five. Rotate the watchers
7:15 before they go numb.
7:17 Supervision fatigue isn't a maybe. It's
7:19 a timer.
7:21 So don't let one person stare at the
7:23 same agent forever.
7:25 In one wealth management rollout Palvi
7:26 describes, simply
7:29 rotating supervisors across different
7:30 agent workflows every six weeks
7:32 improved their error catch rate by about
7:35 35%.
7:36 With zero changes to the underlying
7:38 agent.
7:39 Same model, same data.
7:41 Fresh eyes, dramatically better
7:43 catching.
7:45 Attention is a resource that depletes,
7:47 and rotation is how you refill it.
7:49 Build it into the schedule from day one.
7:51 Not after the first incident.
7:53 Principle six,
7:55 close the override loop and put a name
7:58 on every decision.
8:00 When a human catches a mistake and
8:02 overrides the agent, where does that
8:05 correction go?
8:06 If the answer is nowhere, you have an
8:08 open loop.
8:09 And an open loop is poison.
8:11 Because supervisors quickly learn that
8:13 their input changes nothing.
8:15 And supervision that goes nowhere
8:17 is supervision that's uh that quits.
8:20 So, close it.
8:21 Every override feeds a documented
8:23 review.
8:24 The agent's policy actually gets
8:26 updated.
8:28 And that change is communicated back to
8:29 the team that flagged it.
8:31 They see their judgment mattered, so
8:33 they keep judging.
8:35 And one more thing,
8:36 before you ship, every high-stakes
8:38 decision
8:40 needs a named human owner.
8:42 At 2:47 a.m., the scariest question
8:46 wasn't whether the agent was right. It
8:48 was, "Who owns this?"
8:50 Make sure that always has an answer.
8:53 Let's make this absurdly practical.
8:55 Here are three questions you can answer
8:57 about any agent you're running in about
8:58 half a day.
9:00 One,
9:01 "What is your average time on case
9:03 today?
9:03 And what was it in month one?"
9:06 If you don't know, that's your first
9:07 problem.
9:08 Two,
9:09 "What was the override rate in month
9:11 one, and what is it now?"
9:13 If it's dropped a lot, decide honestly,
9:16 is that the agent improving or the human
9:18 disengaging?
9:19 Three,
9:21 "When was the last time a supervisor's
9:22 override
9:24 actually changed the agent's behavior?"
9:26 If the answer is never, your loop is
9:28 open.
9:29 Three questions, half a day.
9:32 The teams that ask them early get to fix
9:34 the answer.
9:35 The teams that don't read about their
9:37 own 2:47 a.m. in a postmortem 6 months
9:39 later.
9:40 So, here's the whole thing in one line.
9:42 When you design an agentic AI system,
9:45 design the supervision like you design
9:48 the agent.
9:49 Everyone obsesses over making the agent
9:51 smarter.
9:52 The teams that survive past week 12
9:55 obsess over keeping the humans awake.
9:58 Match autonomy to stakes.
10:00 Instrument the people, not just the
10:02 model.
10:03 Add friction on purpose.
10:06 Rotate your watches. Close the loop and
10:08 name an owner.
10:09 None of that is about a better model.
10:12 It's about a better system around the
10:13 model.
10:14 The update is simple.
10:16 You don't just need to know what's
10:17 running.
10:18 You need to know who is still awake to
10:20 watch it.
10:21 Real quick,
10:23 this channel is where I take dense
10:24 reports, papers, and engineering
10:26 write-ups,
10:28 and turn them into something you can
10:29 actually understand
10:31 and use.
10:32 That takes a genuinely huge amount of
10:34 time and resources.
10:36 The research, the scripting, and the
10:38 animation you're watching right now.
10:40 If this video saved you from a 2:47 a.m.
10:42 of your own,
10:44 the single best way to support it is to
10:46 hit that like button and subscribe.
10:48 And if you want to go a step further,
10:50 tap join
10:52 and become a channel member.
10:54 Membership directly funds these deep
10:55 dives, and honestly,
10:57 it's what lets me keep them this
10:58 thorough instead of chasing cheap hot
11:00 takes.
11:01 To everyone who already has, thank you.
11:04 I also package this whole blueprint into
11:07 a free
11:08 one-page supervision checklist.
11:10 The autonomy tiers, the supervisor
11:12 metrics,
11:13 the rotation cadence,
11:14 and those three Monday questions,
11:16 all on a page you can take straight to
11:18 your team.
11:20 Just comment the word watcher
11:22 and I'll send it to you.
11:23 Or grab it at the link below.
11:26 And if you build agentic systems
11:27 seriously,
11:28 my four guides on Claude Code, Codex,
11:32 selling with Claude, and certification
11:34 prep
11:35 go much deeper.
11:37 Links are in the description.
11:39 Subscribe here on YouTube and follow
11:41 Hyper Automation Labs on Instagram and
11:43 Facebook.
11:44 Because somebody has to stay awake and
11:46 read the fine print.
11:47 And I'm happy to be that person.
11:49 I'll see you in the next one.

</details>
