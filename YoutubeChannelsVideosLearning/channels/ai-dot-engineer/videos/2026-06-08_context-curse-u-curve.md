---
title: "Why More Context Makes Your Agent Dumber and What to Do About It — Nupur Sharma, Qodo"
channel: "AI Engineer"
channel_slug: "ai-dot-engineer"
channel_id: "UCLKPca3kwwd-B59HNr-_lvA"
published: "2026-06-08"
duration_seconds: 1587
video_id: "EcqMYoIV57A"
url: "https://www.youtube.com/watch?v=EcqMYoIV57A"
language: "en"
tags: [ai, ai engineer, ai engineering, software development, tech, startups]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-09"
---
# Why More Context Makes Your Agent Dumber and What to Do About It — Nupur Sharma, Qodo

**Channel:** AI Engineer  **Published:** 2026-06-08  **Duration:** 26:27  **Watch:** https://www.youtube.com/watch?v=EcqMYoIV57A

## TL;DR

Larger context windows do NOT make agents smarter. Models exhibit a U-curve: they focus on the start and end of the context and quietly drop the middle. Nupur Sharma from Qodo moved from 'dump everything' to strategic context optimization (iterative retrieval, hierarchical summarization, self-correction) and split their architecture 80/20 between a high-reasoning model for open-ended discovery and a lighter deterministic model for validation. Code review agent uses context collector → specialized agents → judge node → PR-history-weighted recombiner, with weights updated by every accepted/rejected suggestion.

## Key Insights

- **The U-curve pattern** (00:01:55) — give an agent your whole codebase, it attends to the *start* and *end* of the input and *quietly drops the middle*. Bigger context ≠ smarter agent; context *quality* > context *size*.
- **Multi-agent loops don't auto-fix this** (00:02:00) — each handoff still produces a long stitched context that pays the U-curve tax. More agents also introduce clashing interpretations of the same instructions.
- **The orchestration paradox** (00:08:30) — for capable models, most tokens are spent *deciding how to solve* a problem, not solving it. Qodo's fix: 80/20 split — high-reasoning model for open-ended discovery, lighter deterministic model for validation.
- **Qodo's code review architecture** (00:14:00) — context collector → specialized agents (security, review, coding-fix) → judge node recombines → suggestions weighted against PR history → every accept/reject shifts weights for the next run (explicit learning loop).
- **Iterative retrieval > bulk dump** (00:05:00) — feed the model's prior outputs back as anchors and re-query in steps. Trades latency for attention quality.
- **Hierarchical summarization** (00:06:00) — collapse older context into summaries, keep recent context raw. Working memory vs long-term memory.
- **Self-correction** (00:07:30) — let the model critique its own output before finalizing. Cost: 2x tokens. Worth it when the alternative is silent context loss.

## Notable Quotes

> "Context is not a problem. Day by day the models are coming where you can dump a lot of context. But does that make sure that the results you are getting is smart enough to give you everything?" — 00:02:40
> "Agents look at the starting point, end point and try to provide you the results. This is like a U curve where some of the things from the start, some of the things from the end make sense but whatever you are providing in between that is not taken up." — 00:03:15
> "We see that whenever we start working with the initial prompt or the initial goal — that is in focus. If we give something at the end as an input that is in focus. But all between context — Jira, MCPs, can you look into that — the LLMs try to get rid of those things and purge them." — 00:04:10

## Tools and Resources Mentioned

- **Qodo** (qodo.ai) — vendor: Qodo — agentic code review platform; production example of the architecture described
- **OpenTelemetry / Otel** (opentelemetry.io) — vendor: CNCF / open-source — referenced as the agent audit-record pattern
- **Anthropic managed agents paper** — referenced as a session-level observability pattern (cross-reference with Dat Ngo's Arize talk in this same batch)

## GitHub Repos and URLs Referenced

- (none referenced)

## Action Items

- [ ] Audit any current agent: dump 5 random context items, ask the agent to recall all 5 — measure how many from the middle get lost. That's your U-curve tax.
- [ ] Replace 'dump everything' prompts with iterative retrieval: feed prior outputs as anchors and re-query in steps.
- [ ] For multi-step tasks, split the model: one strong reasoning model for 'decide what to do,' one cheap deterministic model for 'validate the output.'
- [ ] If running a review/eval loop, persist accept/reject signals as weights for the next run — explicit learning > implicit.

## Open Questions

- How does the U-curve behave with structured vs unstructured context? (e.g., is it worse for code than for prose?)
- What's the optimal context *replenishment* frequency? Qodo's answer seems to be 'iterate until convergence,' but the cost curve isn't drawn.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 26:27 transcript)</summary>

0:14 I'm Nupur. I work with Kodo. Uh at Kodo
0:18 we do agentic reviews. Uh I have a
0:21 background in dev sec ops. So I'm coming
0:23 from an industry where everything was
0:26 deterministic. The pipelines they run
0:28 they crash. If they crash, we fix them.
0:31 Uh to a place where we are doing agents
0:35 where nothing is deterministic.
0:38 So in my last few years I have learned
0:42 where and how agents fail, what are the
0:45 learnings and today I'll be sharing some
0:48 of my learnings with you.
0:52 So um if you see the evolution of
0:57 agents, it started with static prompts
0:59 where it was a 4K context window and we
1:03 tried to put whatever was important or
1:05 whatever we deemed important and the AI
1:08 models will process it and provide you
1:10 with a result. Right? When we started
1:13 with that that means that it was on us
1:15 to tell LLMs what do they should they
1:18 should look into. That means if we
1:20 provide wrong inputs, we might not get
1:22 proper results. And then we thought
1:25 maybe if the context window grows, if
1:27 the context size grows, we can do
1:29 better. We can have more inputs. And uh
1:32 we started with agentic workflows. So we
1:34 created an agent. We get that get them
1:37 tools like search tool to go into search
1:40 into documents and do something uh as a
1:43 command. then again look into the search
1:45 and do something which again created
1:47 kind of a loop where the tool does not
1:50 know where to stop. It thinks like I
1:52 need more inputs again going back and
1:54 back. It's a loop
1:58 to improvise on that. Uh nowadays multi-
2:01 aents is becoming more popular. Create
2:04 multi- aents do a lot of stuff together.
2:07 When we see it like that we have a lot
2:10 of agents working for you. a security
2:12 agent trying to figure security
2:14 concerns, a review agent trying to
2:16 review the tool, a coding agent trying
2:18 to fix things. Now again, the more the
2:21 tools, the more issues you have. Not
2:24 every agent understands and they have
2:26 clash in their understandings where you
2:28 don't get into the results.
2:34 So what do we learn from here? What uh
2:38 we see is context is not a problem. Day
2:41 by day the models are coming where you
2:43 can dump a lot of context, a lot of
2:47 data. But does that make sure that the
2:49 results you are getting is smart enough
2:52 to give you everything or smart enough
2:54 to decide what's important? If you see
2:57 the current LLM models, we see a pattern
3:00 where it takes the initial inputs you
3:04 provide, it takes the last inputs, but
3:06 the in between context is basically
3:10 removed. So they don't focus on the in
3:13 between context. Agents look at the
3:15 starting point, end point and try to
3:17 provide you the results. This is like a
3:20 U curve where some of the things from
3:23 the start, some of the things from the
3:24 end make sense but whatever you are
3:26 providing in between that that is not
3:29 taken up. Yeah.
3:30 >> How do you know this?
3:31 >> This is something which we are working
3:33 on and we are actually benchmarking
3:35 things. So when we create agents we try
3:37 to see this is the context we provide to
3:40 the agents. Does it take this context
3:43 into effect and also give us the
3:45 results. So we are working with
3:46 multi-agentic architecture where for
3:48 each of the task we do do for code
3:50 reviews we give the task to an agent and
3:53 say okay give us a result. Now every
3:56 time we for example code reviews we try
3:59 to see can we give all the context can
4:01 we give the whole codebase for example
4:03 and see if we can get a results but we
4:06 see that that whenever we start working
4:08 with that the initial prompt or the
4:10 initial goal which we start with that is
4:12 in focus. If we give something at the
4:15 end as an input that is in focus but all
4:17 between context like I have Jira I have
4:20 MCPS can you look into that the LLMs try
4:23 to get rid of those things and purge
4:26 them to get make sense by themsel.
4:31 So to have this or to make a way out of
4:36 this how we deal with is creating
4:39 strategic solution for context
4:40 optimization
4:42 rather than dumping everything to the
4:44 models and asking them to be smart
4:46 enough to find out what is more
4:48 important. Uh we usually try to see okay
4:51 what we can do to make it uh better
4:54 context for the model. There are lots of
4:57 solutions in place if you see currently
5:00 and context engine is a buzz word like
5:02 everybody wants to create context engine
5:04 and everybody wants to uh provide that
5:07 but context engine is like a bouncer
5:10 right so your high-speed car is going
5:13 and it acts as a bouncer and tells you
5:15 this is more important now if you have a
5:18 large messy code base it makes sense to
5:21 create a context engine because it
5:23 creates a search pattern it creates
5:25 ranking logic so that whenever you ask
5:28 for a task it looks for those rankings
5:30 and say this is more important for you
5:32 take it and work with it. The problem is
5:36 the indexing part takes moderate effort
5:39 but the scaling is a challenge. Like if
5:42 you start talking about 600 repositories
5:44 or 700 repositories the mapping and the
5:47 indexing starts to slow down and it
5:50 becomes again unpredictable to find or
5:53 create a context engine if you are not
5:56 actually into making context engine
5:58 only. There are lots of areas where
6:01 agent can get more context instead of
6:04 investing highly on context engine
6:07 hierarchal summarization where instead
6:09 of creating or going through everything
6:12 a summary is created for each file and
6:15 folder so that when the agents try to
6:17 find they can try to read the summary
6:19 and see if that is more important to us
6:22 or not can be a good one. The only thing
6:25 is that you need a lot of LLM
6:27 processing. every time a file is created
6:29 or changed some of the agents need to go
6:32 and create a mapping for that. So it's a
6:35 high upfront um context of uh LLM
6:39 processing that is needed. Another way
6:41 is knowledge graph. Now knowledge graph
6:44 is complex but it works wonder when you
6:47 have logical dependencies. For example,
6:50 you have one file which impacts another
6:52 file which again impacts other file. You
6:55 can create a graph DB hosting. It is the
6:59 initial input needed by the developer is
7:01 very high. It takes a lot of time to
7:03 create that. But if you have complex
7:05 logics or you have dependencies on
7:08 multiple repos that works wonder
7:11 for me. I think for most of the task if
7:14 you're not a product company but if
7:15 you're building agents for yourself or
7:17 your processes iterative retrieval works
7:20 really good because instead of even
7:23 creating a summary it creates kind of an
7:25 index. So it's like a library card which
7:28 you give to your agents and say this is
7:30 the topic if that is relatable to you.
7:33 You can look deep into the code uh and
7:35 uh look for the results. Again it has
7:39 quite uh cost impacts but you do not
7:43 have to invest a lot of energy. The
7:46 input uh required by the developers to
7:48 provide to the LLM is low and it
7:51 provides better results. There is also
7:53 option of selfcorrection where you ask
7:57 uh the LLM to do something and there is
8:00 a critic node which looks and say if
8:02 that is relevant to your initial goal or
8:05 not. In that case if the context is lost
8:09 uh you can again ask the agent to do it
8:11 again retry it again because the critic
8:14 note said this is not the right way. It
8:16 takes a little bit more time because it
8:18 adds a latency of running the agents and
8:21 again but it does not require a lot of
8:24 input initially from the developers to
8:27 create something.
8:31 Another challenge uh which I have seen
8:34 people getting into when they create uh
8:37 these um agents is the orchestration
8:41 paradox. Now what it does is that now
8:44 LLMs are becoming more and more smart.
8:47 So when you give them the task they
8:48 think like okay I should use this tool
8:51 uh maybe I can do better I should
8:52 research more on what should I use. It
8:55 goes into a loop that instead of
8:57 actually looking into solve the problem,
8:59 they look for the method to solve the
9:01 problem. They hop on from one method to
9:04 one another method and most of the API
9:07 tokens are wasted on finding a way to do
9:11 it rather than doing it. So you will
9:13 just go on the research mode. For
9:15 example, if you use Opus latest and
9:18 greatest, they will try to see what is
9:20 the best method to do it and challenging
9:23 themsel again and again. Maybe not this,
9:25 another way, another way. And it just
9:27 goes into a loop of doing trying to do
9:30 something rather than doing something.
9:34 To resolve this uh we worked with 80/20
9:39 hybrid approach. I think this is one of
9:41 the most interesting uh outcomes I have
9:44 seen or the way to in resolve this
9:47 infinite loop. What our teams are doing
9:50 is giving the latest and the greatest
9:52 models or giving the agents power to
9:55 research 80% of the time. So you give
9:57 them the goal and say okay try to do
10:00 whatever you can but the 20% of the task
10:04 where you need final validation you want
10:06 summarization
10:08 that are not something which is free
10:10 flowing that is more restricted those
10:13 are more hard gates for example if I get
10:16 X results I want Y it's more
10:19 deterministic so that the research which
10:21 is coming from the 80% can be lowered
10:24 down now when you see you can always say
10:27 that the 80% tool can still go on and go
10:30 into infinite loops. We have mechanisms
10:34 to work on that. For some organization
10:36 do they do counter mechanism where after
10:40 four or five counters you have to work
10:42 with whatever was the last results. For
10:45 some of them they have timeout counters
10:47 that after 5 minutes whatever is the
10:49 last tool or whatever is the last
10:51 decision you work with that and then go
10:53 back if the results are not good. But
10:56 you can restrict that 80%. But in short,
10:59 if you are using anything like discovery
11:02 or you're trying to see which tool to
11:04 use, you're trying to plan those 80% uh
11:08 research models are really good. But if
11:11 you are again trying to create a
11:12 summarization, you're trying to see okay
11:14 this is the research I have got. Now I
11:16 have to make a result out of it. The 20%
11:19 works really well. Now for 80% usually
11:22 you use uh high reasoning models latest
11:26 and the greatest but you don't need a
11:29 high reasoning model for the 20% because
11:32 those 20% things are doing
11:33 deterministing they you are actually
11:35 telling them what is needed for example
11:38 the critic node which we talked about
11:40 they don't need to research they don't
11:42 need to find out what is the best thing
11:43 to do they just need to see what was
11:45 your goal what was the result you are
11:47 trying to achieve and uh how to provide
11:49 or how to summarize ize that for that
11:52 also things like if you think about what
11:56 would be the next possible action I have
11:57 this result what should I go and look
11:59 for that are things can be done by the
12:02 80% dynamic models whereas I have all
12:06 the results from the 80% models but what
12:09 is the proper way or what is the proper
12:11 uh results the the user is looking into
12:15 those kind of decisions can be taken by
12:17 the 20% model.
12:22 Finally, uh this is again an interesting
12:25 failure which we have seen where as the
12:29 context grows, teams think okay we can
12:31 do everything with one agent because the
12:33 context window is quite great right we
12:35 can put everything we can ask an agent
12:38 to uh do uh the testing part we can ask
12:41 that agent to do review part we can ask
12:43 the agent all the kind of things because
12:45 the context is same and they can provide
12:47 us the results that make sure that the
12:50 when the agent is going forward ward it
12:52 get overwhelmed with the inputs and
12:54 again it tries to start losing uh what
12:57 was the original task. So maybe you give
13:00 four tasks to the agent and somewhere
13:02 down the line it focuses on two tasks.
13:04 So you get great results for the two
13:06 task but the other two just just get
13:09 lost in the middle. For those particular
13:11 purpose,
13:14 we have something called mixture of
13:16 agents. And that's that's where you hear
13:18 a lot of buzz about multiple agents or
13:21 multi-agent tech architecture where you
13:23 create instead of one big agent, we
13:27 create issue expert agents. We create
13:29 small small agents which are doing great
13:32 in a specific task which they have
13:34 provided. Now to build on top of that
13:38 each of the agent come up with their own
13:40 interesting ideas or results. How to
13:43 make sure those results combine and make
13:46 sense together. Because for example I am
13:49 trying to search for a vacation. I give
13:51 an agent to find the best hotel. Another
13:54 agent to find the best location. Another
13:56 agent try to find best flights. But all
13:59 three of them gives me different result.
14:01 The uh hotel is in Greece. uh the flight
14:05 is from Amsterdam to um maybe Portugal
14:10 and everything just doesn't make sense
14:12 right so for that particular purpose
14:14 there's a concept called a judge agent
14:16 what it does it it tries to get all the
14:19 results and see if they can make sense
14:21 together so now you are doing all the
14:25 greatest things from different agent
14:27 getting the best results from their part
14:30 but a judge agent help us to combine
14:32 these and make one sense out of it
14:34 instead of getting so many things which
14:36 doesn't make sense together.
14:41 Something similar is implemented by us.
14:44 So this is our architecture uh codos
14:47 architecture where for the code reviews
14:50 we are using the same uh formula. So as
14:54 part of a PR review we have a context
14:57 collector which actually goes and
14:59 collect context from the PRs it could
15:01 collect context from the context engine.
15:04 it uh collect context from the tools but
15:07 then it does not start working and uh
15:09 giving you the reviews. It actually
15:12 bifocates all the context it has
15:14 provided and pass it on to different
15:16 agents. Now what these agents do is
15:20 basically specializing in what they are
15:22 supposed to. For example, there will be
15:24 a security agent trying to find security
15:26 flaws. There might be a agent trying to
15:29 code. There might uh code differences.
15:31 There might be an agent trying to find
15:32 the Jira issues. Once all these agents
15:36 give us back, a judge agent actually
15:39 looks for the results and say okay these
15:41 are interesting enough but is it
15:43 relevant to you? They can again go back
15:45 in the context engine look into the PRs
15:48 and see out of the 10 things which is
15:50 provided by you how many of them
15:52 actually make sense for your thing. So
15:55 again refining the results uh to make
15:58 sense to you.
16:01 Yeah, I think that was it from my side.
16:05 Uh,
16:08 any questions?
16:10 >> Yes. Um, in practice, how do you let the
16:14 swarm communicate with each other?
16:17 >> Uh, you are talking about the agents.
16:20 >> So, you have agent A and agent B and the
16:22 judge. I can imagine they write to a
16:24 file system or they have some kind of
16:26 tool proprietary.
16:28 uh we ch we use uh longchain at the
16:32 bottom uh and that is being used to
16:35 communicate and build the infrastructure
16:37 for uh different agents.
16:38 >> Do you know what lang chain uses for
16:40 that like just collects the responses
16:44 and then shs it back into the prompt of
16:46 the next agent?
16:47 >> Yes. Yes. Yes. Yes. that that's what so
16:50 what we do is we try to uh get the
16:53 results and create a prompt for the next
16:55 agent and if it's multiple things again
16:58 there is an agent just to collect the
17:00 results and create a better prompt uh
17:02 which is refined for the next agent
17:06 >> have you thought about a calibration
17:08 step for each agent
17:10 >> when you say the calibration can you
17:12 tell me more
17:12 >> calibration right so when you do a code
17:15 review with an agent right need At
17:19 least what I heard today is doing some
17:23 calibration
17:25 that you actually tell them what is good
17:26 and what is bad.
17:28 >> Yes. So when you say it like that uh and
17:32 let me know if that makes sense for your
17:34 question or not. We do calibration in a
17:37 form we check what we have as a context.
17:40 So for example uh when we get the code
17:43 reviews LLM does not know what is
17:46 important for you or how do you work. So
17:49 for example an LLM when they gets input
17:51 they get input from healthcare industry
17:53 they get from retail industry they get
17:55 from finance industry and all of them
17:58 can use same Java framework in different
18:00 ways or different uh things are
18:03 important for them the rest of them
18:05 doesn't make sense. So what we do is we
18:08 give you two different options to tell
18:11 the agents how to perform or what to
18:14 work on. One part is we give them the PR
18:17 history. So we index all your PR and see
18:21 when was the last time something like
18:23 this was identified and compare the
18:26 current version if that is
18:28 >> you do that in the context standpoint.
18:30 >> Yes. Yes. Yes. Yes. We do that. So the
18:33 changes we you make to the code we look
18:35 into if we can see something similar in
18:38 the past that again is uh transfer to
18:41 the context twice. First is when we are
18:44 actually giving context to the sub
18:45 agents to find things for you and
18:48 another time to the judge agent. So that
18:50 when I get 15 different recommendations
18:53 for a code review, my judge agent can
18:55 look into what was there before, how did
18:58 your reviewer commented, how your
19:00 developers commented and based upon that
19:02 decide if that is worth providing to
19:04 your developers or not. And the other
19:06 part is
19:07 >> and this happens for every agent.
19:09 >> For every agent yes,
19:14 right, you don't share the context
19:16 between the agent, right? So you have
19:20 a specific context by the way.
19:22 >> Yes, we are trying to resolve that U
19:25 part that instead of dumping everything
19:27 to the LLM, we uh take the part which is
19:30 more important, we use a context engine
19:32 for that. We take the part which is more
19:34 important and only provide that
19:36 particular part to that particular
19:37 agent.
19:43 >> But but then for me it's not clear how
19:45 you bridge the gap rather than say you
19:48 have
19:50 quality agent and you have agent
19:59 framework specific coding radio agent
20:03 right and then you basically you only as
20:06 I understood
20:09 >> you only share the specific information
20:11 to each agent right and then basically
20:14 each agent runs
20:16 atomic autonomously Yeah.
20:18 >> Right.
20:22 And doesn't have a full picture,
20:24 >> right? At least when let's say as a
20:26 human, right? And if you do code
20:28 reviews, it's always good if you have a
20:31 full prospect, right? I would say like
20:34 that kind of methodology would it works
20:37 for simple things like does it use
20:39 linting? Does it use I don't know are
20:42 tests implemented? But when you think
20:44 about at least I think when you think
20:46 about architecture for example to make
20:49 architecture decisions um that covers
20:53 security because everything is a balance
20:56 and and uh
20:58 >> you have to wait that somehow so
21:01 >> how do you solve
21:02 >> yes so I think if you look into the
21:04 older version of code reviews you should
21:08 have you used to have a senior engineer
21:10 who knows your code who knows what kind
21:12 of packages you're using and they can
21:14 comment on if the developer has done
21:17 something uh similar to what you're used
21:19 to or did something uh totally weird,
21:22 right? Then you used to have a security
21:25 person who used to see if you are
21:27 providing all kinds of security, you are
21:29 not hard- coding your APIs or you are
21:32 not putting any SQL injection. So all
21:34 those kind of things the security
21:35 experts know. On the other hand, if you
21:38 are working with ISO compliance or sock
21:40 to compliance, there might be an auditor
21:41 who might ask the uh team lead or the
21:45 senior engineer is your code uh being um
21:49 you know logged is it logging the
21:51 changes and so on. So previously as well
21:53 there were lots of people having
21:55 specialized knowledge looking into those
21:57 kind of areas specifically. Now when the
22:00 context is provided it's always like
22:02 these are my security concerns which I
22:04 always have to look into. These are my
22:06 architectural concerns. An architect
22:08 might look from the architecture
22:09 perspective. We can do that something
22:12 similar uh with the agents as well
22:14 because for example architecture
22:16 security concerns we have a web portal
22:18 where architects can provide their
22:20 guidelines pro uh compliance people can
22:22 provide their guidelines and an agent
22:24 can look into all those guidelines and
22:26 say is it validated or not. So if you
22:29 see the
22:31 initial uh picture the context collector
22:35 knows everything and then it provides
22:38 relevant context to the agents. So you
22:40 you enforce basically your customer to
22:42 upload these kind of documents, right?
22:45 Is that a kind of a requirement then or
22:49 >> because I mean the system will have
22:52 completely let's say different result
22:54 right if you don't share them
22:55 >> exactly so that's something which
22:57 depends upon organization there are some
23:00 people who say we don't work with any
23:01 rules or regulations so just give me out
23:03 of the box that also means that don't
23:06 expect the agents to find something very
23:08 specific to your working until and
23:11 unless we have certain PR history
23:13 because then again the PR history kicks
23:15 in and tells you what is relevant even
23:17 though when you don't provide
23:19 >> I'm not sure if the the PR history is
23:22 really the best source but I think it
23:26 >> it can be one it can be one of it can so
23:29 that's why there are various uh sources
23:31 right so it's PR history it's your
23:33 resource it's your
23:35 and somebody's cooking food at my home
23:38 yeah but it it can be uh one of the
23:40 source and that's why
23:42 >> and my question is like yeah I mean of
23:43 course It can it can be right but yeah
23:46 at the end you need to decide
23:48 >> let's say also in the jury right how
23:50 much you weigh right so like the new
23:53 documents for let's say the engineering
23:56 principles architecture principles and
23:59 compare compare them to let's say your
24:03 your mer
24:04 >> yeah yeah
24:05 >> right they could be completely out of
24:07 balance right
24:10 >> um it depends it depends so again uh I
24:13 think It's if you look into from one
24:15 perspective it's difficult to decide but
24:17 if you're getting the context from many
24:19 angles for example PR history that's one
24:21 part but when you do the compliance and
24:23 you tell in the compliance portal this
24:25 is really important. So we have various
24:28 uh segments of it's an error, it's an uh
24:30 a recommendation. All those kind of
24:33 things adds weight to a feedback to say
24:36 if it's good or not. And every time your
24:39 developer expect accepts a suggestion,
24:41 it gets more weighted for the next one.
24:44 If it does not uh uh accept the
24:46 suggestion, it gets a less weight. So
24:48 it's all about indexing and making sure
24:51 those weights are managed somewhere.
24:54 >> Uh two ways. One is uh by when you when
24:57 you give your recommendations does your
24:59 developer actually accept it or not we
25:02 uh index that. Another way is uh from
25:06 the past PRs we try to find out similar
25:08 issues identified and if your developer
25:10 actually implemented them. So for
25:12 example some people are used to hard-
25:14 coding their uh API keys and I literally
25:18 had a tough um argument with the
25:21 developer but this is how we do it. No
25:22 this is should this should not be the
25:24 way. Yeah but nice thing
25:27 nicely match also what I meant right so
25:29 if you look in the in the history that
25:32 happened doesn't mean it's it's good
25:34 >> it's yeah and and that's the way where
25:37 the system tries to tell you this is not
25:39 good this is not good and then it's up
25:41 to you
25:41 >> only if you provide the guidance right
25:44 >> no it so there is something called bug
25:46 fixes and there is something called
25:48 rules so if you provide them as a rule
25:52 it will get uh highlighted doesn't
25:54 matter if you want it or not. And then
25:56 there are bugs where agent tried to tell
25:57 you there's something wrong and if the
25:59 reviewer also agrees with it and did not
26:01 implement a 10 times the reviewer might
26:04 get it less weighted and give you
26:09 >> cool. Thank you so much.
26:11 >> Thank you.


</details>
