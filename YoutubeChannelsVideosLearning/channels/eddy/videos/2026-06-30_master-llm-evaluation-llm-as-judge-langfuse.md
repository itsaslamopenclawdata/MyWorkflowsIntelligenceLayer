---
title: "Master LLM Evaluation with LLM as a Judge using Langfuse"
channel: "Eddy"
channel_slug: "eddy"
channel_id: "UC860VdxDA2EKFW9ezm36MAw"
published: "2026-06-30"
duration_seconds: 524
video_id: "QhrLzKbYaGM"
url: "https://www.youtube.com/watch?v=QhrLzKbYaGM"
language: "en"
tags: [llm-evaluation, llm-as-judge, langfuse, observability, ai-engineering]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-07-01"
---

# Master LLM Evaluation with LLM as a Judge using Langfuse

**Channel:** Eddy  **Published:** 2026-06-30  **Duration:** 08:44  **Watch:** https://www.youtube.com/watch?v=QhrLzKbYaGM

## TL;DR

LLM-as-a-judge solves the impossible scaling problem of human evaluation — strong LLM judges achieve 80-90% agreement with human evaluators at 1-10 cents per assessment. Langfuse's implementation pivots from slow legacy "traces" to fast async "observations" (per-operation LLM calls), enabling compositional evaluation where toxicity, retrieval relevance, and accuracy can be scored simultaneously on the same data.

## Key Insights

- Traditional heuristic metrics (exact word matches, pattern matching) fail on nuance, helpfulness, tone, creativity, factual accuracy. Human review doesn't scale — "thousands of responses a minute" makes it impossible (00:55).
- LLM-as-a-judge anatomy = 4 components: evaluation criteria (rubric) + input context + output to evaluate + optional reference. Judge returns structured data (numeric, categorical, or boolean scores) (02:23).
- 80-90% agreement with human evaluators across quality dimensions = same level of agreement as between two human reviewers (03:23).
- Cost: 1-10 cents per assessment (vs. paying human domain experts to sit and rate hundreds of responses) (03:56).
- Data strategy shift: experiments (offline dev) → traces (legacy, slow, imprecise) → **observations** (gold standard for live production). Observations enable compositional evaluation (04:30).
- Observations enable evaluations that complete in seconds (not minutes) because they're asynchronous per-operation evaluations rather than full-workflow traces. Process thousands of evaluations per minute (05:05).
- Compositional evaluation: filter by observation type (just final response, or just a specific DB retrieval), run simultaneous evaluators (toxicity + retrieval relevance + accuracy) on the same data with stacked filters (user IDs, session tags) (05:27).
- 4-step Langfuse blueprint: (1) create evaluator with default model supporting structured output, (2) pick evaluator type, (3) target data (live observations for production), (4) map variables via JSON path expressions (06:05).
- Two evaluator paths: managed evaluators (built by Langfuse/Ragas, no prompt writing required) vs. custom evaluators (bring your own prompt, custom rubric for unique business logic) (06:34).
- Live prompt preview: pulls real historical data from last 24 hours matching your filters — click through real-world examples to see how your actual user data fills the judge's prompt before deploying (07:13).
- Full judge transparency: every judge execution creates its own trace with 100% visibility — debug prompt issues, inspect step-by-step reasoning, monitor token usage of the judge itself (07:48).

## Notable Quotes

> "If AI is building AI, who is evaluating yours? The bottleneck of slow, expensive human review? It is completely over. It's time to let the machines do the grading so you can get back to building." — 08:18

> "Strong LLM judges achieve 80 to 90% agreement with human evaluators across a ton of different quality dimensions. I mean guys, that is effectively the exact same level of agreement you'd see between two different human reviewers." — 03:23

> "This brilliantly asynchronous architecture, you can effortlessly process thousands of hyper-fast evaluations per minute on individual operations within your app." — 05:13

## Tools and Resources Mentioned

- Langfuse — open-source LLM observability + evaluation platform (recently acquired by ClickHouse)
- Ragas — partner platform providing managed evaluators (hallucination, helpfulness)
- LLM-as-a-judge — evaluation methodology using one model to assess another's outputs
- Structured output (JSON schema) — required for evaluators returning numeric/categorical/boolean scores
- Vendor: Langfuse is a third-party platform; not related to this user's stack.

## GitHub Repos and URLs Referenced

- Langfuse platform docs / API endpoints (referenced via product description, no specific URL given)

## Action Items

- [ ] Identify one high-volume LLM operation in production (e.g., retrieval step, final response) and wire it as an "observation" target
- [ ] Start with a managed evaluator (Langfuse hallucination or helpfulness) before investing in custom prompts
- [ ] Compose multiple simultaneous evaluators (toxicity + accuracy) on the same observation to catch different failure modes in one pass
- [ ] Use JSON path expressions to map nested app data to judge prompt variables
- [ ] Enable live prompt preview during dev — see real user data fill the judge's prompt before deploy
- [ ] Set up judge monitoring — every judge execution should be its own trace so you can debug judge prompts later

## Open Questions

- What's the right model for the judge itself? Is using a smaller/faster model for first-pass + a stronger model for second-pass more cost-effective than always using a top-tier model?
- How does LLM-as-judge hold up against adversarial prompts that try to game the rubric?
- For multimodal outputs (image generation, code with execution), what evaluation frameworks exist?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 08:44 transcript)</summary>

0:01 [snorts]
0:03 [music]
0:06 >> Welcome back to the Explainer. So, look,
0:08 right now, across the tech industry, AI
0:11 engineers are slamming into this
0:12 massive, completely unavoidable
0:15 bottleneck. Building an AI app, that's
0:17 actually easier than ever these days.
0:19 But scaling it up, yeah, that's where
0:20 the real nightmare begins. Because think
0:22 about it, once your AI is actually out
0:24 there in the wild, interacting with real
0:26 users, how on earth do you know if it's
0:28 doing a good job? You literally need a
0:30 bold, hyper-efficient solution. Today,
0:33 we're unpacking an absolute
0:34 game-changer. It's totally reshaping how
0:36 developers smash through this
0:37 bottleneck. We are talking about LLM as
0:40 a judge. It all really starts with one
0:42 wildly provocative question. How do you
0:44 actually grade an AI?
0:46 Think about it for a second. If you've
0:48 built a system to, say, generate code,
0:50 or summarize dense legal documents, or
0:53 act as your front-line customer support,
0:55 simple heuristic metrics, they are
0:57 completely dead. I mean, traditional
0:59 metrics looking for exact word matches
1:01 or basic patterns, they just completely
1:02 fail to capture the nuance of human
1:04 language, or helpfulness, or tone. You
1:07 just can't use some basic old-school
1:08 math formula to grade creativity or
1:10 factual accuracy. It doesn't work. So,
1:13 historically, the only way you could
1:15 actually get that nuance was by throwing
1:17 human annotators at the problem. But,
1:19 let's be real, human review is painfully
1:21 slow, and honestly, it is incredibly
1:23 expensive. It simply doesn't scale. Not
1:26 when your application is pumping out
1:28 thousands of responses a minute. The new
1:30 reality? LLM judges. They're blazing
1:33 fast, highly scalable, and just
1:35 relentlessly efficient. This right here
1:37 is the new secret weapon for engineering
1:39 teams.
1:41 Okay, let's lock down exactly what we
1:42 mean here. LLM as a judge is essentially
1:45 an evaluation methodology, where a
1:48 highly capable large language model, our
1:50 judge, is explicitly prompted to assess
1:53 the quality of outputs produced by
1:55 another LLM application. So, instead of
1:57 relying on a tired human staring at a
1:59 spreadsheet, you use a powerhouse model,
2:01 think GPT-4o or Claude Sonnet, to score
2:04 and actually reason about your app's
2:06 outputs based on really strict
2:07 predefined criteria.
2:10 It brilliantly combines the deep nuance
2:12 of human judgment with the relentless
2:14 automated massive scale of a machine.
2:17 So, let's dive into this. Let's look at
2:19 the actual anatomy of how this works.
2:21 Because look, a judge is only ever as
2:23 good as the prompt you give it, right?
2:25 There are four absolutely components you
2:27 need to wrap your head around. First,
2:29 the evaluation criteria. This is your
2:31 rubric. You're explicitly defining what
2:33 a good or bad response looks like.
2:35 Second is the input context, which is
2:38 just the user's original query. Third,
2:40 the output to evaluate, that's your
2:42 application's actual response. And
2:44 fourth is an optional reference. This
2:46 could be something like a ground truth
2:48 document the judge to compare against.
2:50 You feed those four pieces into the
2:51 judge and boom, it gets to work. Now,
2:53 for this to actually be useful at scale,
2:55 the judge can't just spit back a
2:57 rambling paragraph of feedback. It needs
2:59 to return structured data, data you can
3:00 actually track and analyze over time.
3:02 So, the judge model is configured to
3:04 return its internal reasoning alongside
3:06 a very specific output format. You might
3:08 go with numeric scores for continuous
3:10 judgments, like say a helpfulness scale
3:12 from zero to one. Or you could use
3:13 categorical scores for explicit labels,
3:15 like correct or partially correct, or
3:17 even boolean scores. Those are great for
3:19 rapid true or false decisions, like
3:20 instantly flagging a policy violation.
3:22 And this brilliantly illustrates exactly
3:24 why the entire industry is adopting this
3:26 so incredibly fast. 80 to 90%. That's
3:30 huge. Research has consistently shown
3:32 that strong LLM judges achieve 80 to 90%
3:34 agreement with human evaluators across a
3:36 ton of different quality dimensions. I
3:38 mean guys, that is effectively the exact
3:40 same level of agreement you'd see
3:42 between two different human reviewers.
3:45 By utilizing well-designed rubrics and
3:46 crystal clear criteria, you're
3:48 essentially getting human-level
3:50 accuracy, but at machine speed. And
3:52 then, we have to talk about the cost. A
3:55 typical LLM as a judge evaluation costs
3:57 somewhere between a single penny and 10
3:59 cents per assessment. Compare that to
4:02 paying a human domain expert to sit
4:03 there, read, and rate hundreds of
4:06 responses. Financially speaking, this
4:09 methodology is an absolute no-brainer
4:11 for scaling an AI app. You are getting
4:14 precise human-like monitoring literally
4:16 for pennies. Section one, data strategy,
4:20 where the judge sits. Moving right
4:21 along.
4:22 To build out your overall evaluation
4:24 strategy, there are three distinct data
4:26 targets you can essentially point your
4:28 judge at. At the bottom tier, we have
4:30 experiments. These are perfectly fine
4:32 for offline development and testing. In
4:34 the middle, we have traces, but notice
4:36 this is straight-up marked as legacy.
4:39 Tracing an entire massive workflow, it
4:41 takes minutes, it's really slow, and
4:42 honestly, it lacks precision. But at the
4:46 very top, we have the undisputed gold
4:48 standard for live production, and that
4:50 is observations. This is absolutely
4:52 where you want to be playing.
4:54 Let me heavily, heavily emphasize this
4:56 paradigm shift. Observations are the
4:58 absolute future of production
5:00 monitoring. When you target
5:01 observations, you are dramatically
5:03 speeding up your execution times. We're
5:05 talking evaluations that complete in
5:06 seconds, completely obliterating
5:08 bottlenecks and those massive evaluation
5:10 backlogs.
5:11 Because of this beautifully asynchronous
5:13 architecture, you can effortlessly
5:14 process thousands of hyper-fast
5:16 evaluations per minute on individual
5:17 operations within your app. No more
5:19 waiting around for massive clunky
5:21 workflows to finish up.
5:22 So, the really crucial point here is
5:24 that this unlocks what's called
5:26 compositional evaluation. You aren't
5:28 just giving your AI a single generic
5:30 overall grade anymore. You can filter by
5:32 observation type to look at, say, just a
5:35 final response, or maybe just a specific
5:37 database retrieval. And then, this is
5:39 the cool part. You can run simultaneous
5:41 evaluators. You could check the LLM's
5:43 output for toxicity, check its retrieval
5:46 step for relevance, and check its final
5:47 generation for accuracy. And do all of
5:50 that at the exact same time while
5:52 stacking filters like user IDs or
5:53 session tags. You are quite literally
5:55 grading specific isolated pieces of your
5:58 AI's brain simultaneously. Section two,
6:01 the blueprint implementation. Let's get
6:03 into the how-to. Here is your exact
6:05 four-step blueprint for wiring this up.
6:08 Step one, create the evaluator. You'll
6:10 set a default model here, making sure it
6:13 actually supports structured output.
6:15 Step two, pick the evaluator type. Step
6:18 three, target the data. And as we just
6:20 learned, that should ideally be live
6:22 observations for your production
6:23 environment. And finally, step four, map
6:25 the variables. This is where you connect
6:27 your app's live data to the judges
6:28 prompt. Let's quickly break down those
6:31 middle steps, starting with how you pick
6:32 your evaluator type.
6:34 Developers have just incredible
6:36 flexibility here. You basically have two
6:38 paths you can take. On one side, you
6:40 have managed evaluators. These are
6:42 completely out-of-the-box, ready-to-use
6:45 prompts built by platforms like LangFuse
6:47 and partners like Ragas. They capture
6:49 all the industry best practices for
6:51 evaluating things like hallucinations or
6:53 helpfulness, literally no prompt writing
6:55 required on your end. But, on the other
6:57 side, if you have a super specific use
6:59 case, you can build custom evaluators.
7:01 You literally bring your own prompt,
7:03 define your exact variables, and write a
7:04 completely custom evaluation rubric
7:07 tailored perfectly to your unique
7:08 business logic.
7:10 All right, once you've picked your
7:11 evaluator, you hit step four, mapping
7:13 your variables. Honestly, this is where
7:15 the magic really happens. To teach your
7:17 system which properties of your data
7:19 represent the inputs and the outputs,
7:21 you can use JSON path expressions to
7:23 precisely pinpoint nested data. But, the
7:26 absolute best part? LangFuse provides a
7:28 live prompt preview. It actually pulls
7:30 real historical data from the last 24
7:32 hours that matched your filters, so you
7:35 can literally click through real-world
7:36 examples and see exactly how your actual
7:38 user data is going to fill the judges
7:40 prompt before you ever even deploy it.
7:43 It's a total game changer. Now, if
7:45 you're sitting there worried about the
7:46 AI judge itself making a mistake, don't
7:49 be. Because the judge itself is fully
7:50 monitored. Every single execution of
7:52 your LLM as a judge creates its own full
7:55 trace that gives you total 100%
7:57 visibility. You can instantly debug
7:59 prompt issues. You can literally inspect
8:01 the model's exact step-by-step
8:02 reasoning. And you can even monitor the
8:03 token usage of the judge itself to keep
8:05 your cost strictly under control. The
8:07 whole shebang is entirely transparent.
8:09 We are rapidly entering an era where AI
8:11 is actively generating content, writing
8:13 complex code, and literally building
8:15 other AI. So, the main question you
8:17 really have to ask yourself, and frankly
8:18 your entire engineering team, is this:
8:20 If AI is building AI, who is evaluating
8:22 yours? The bottleneck of slow, expensive
8:25 human review? It is completely over.
8:28 It's time to let the machines do the
8:30 grading so you can get back to building.
8:32 Thanks for joining me on this explainer,
8:33 and I'll catch you on the next one.

</details>