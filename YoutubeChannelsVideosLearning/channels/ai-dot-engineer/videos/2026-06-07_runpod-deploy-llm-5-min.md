---
title: "Under 5 minutes to a deployed LLM endpoint — Audry Hsu, RunPod"
channel: "AI Engineer"
channel_slug: "ai-dot-engineer"
channel_id: "UCLKPca3kwwd-B59HNr-_lvA"
published: "2026-06-07"
duration_seconds: 806
video_id: "ILdE7FaAjVA"
url: "https://www.youtube.com/watch?v=ILdE7FaAjVA"
language: "en"
tags: [ai, ai engineer, ai engineering, software development, tech, startups]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-09"
---
# Under 5 minutes to a deployed LLM endpoint — Audry Hsu, RunPod

**Channel:** AI Engineer  **Published:** 2026-06-07  **Duration:** 13:26  **Watch:** https://www.youtube.com/watch?v=ILdE7FaAjVA

## TL;DR

RunPod started in 2022 with two failed crypto-mining GPUs in a basement, given away for free on Reddit in exchange for feedback. Now at $120M ARR and 500K developers. The live demo: pick a Hugging Face model, configure context window, deploy a serverless endpoint on H100s — under 5 minutes total. Cold start: 41 seconds. Warm requests: ~1.5 seconds. You pay only while a worker is handling a request.

## Key Insights

- **RunPod origin story** (00:01:50) — two failed crypto-mining rigs in a basement in 2022. Founders posted on Reddit offering the GPUs for free in exchange for feedback. Now at **$120M ARR, 500K developers, 30+ data centers**.
- **Two product lines** (00:04:20) — *Pods* (sandbox virtual environments, containerized GPU allocation, you bring Dockerfiles) and *Serverless* (auto-scaling, workers spin down when idle, you pay only while handling a request).
- **Demo: end-to-end deploy in under 5 minutes** (00:06:00) — pick a model from the Hub → configure context window → deploy serverless endpoint on H100s. Cold start: **41 seconds** for the first request while the container initializes and the model downloads. Subsequent requests: **~1.5 seconds**.
- **Pricing model** (00:05:00) — serverless bills per-request, per-second-of-worker-time. Container is always-on, serverless is bursty/batch.
- **GPU market context** (00:01:30) — RunPod's positioning: GPU access is slow/opaque due to global supply crunch (analogized to COVID toilet-paper hoarding). Expect recovery as customers get better at forecasting compute needs.

## Notable Quotes

> "The origin story of RunPod has always started with builders and getting feedback from the community, and that is still true today." — 00:03:10
> "Serverless: instead of being always on like a container is, serverless your workers spin down, and when they're idle..." — 00:04:45
> "First request queues for 41 seconds on cold start while the container initializes and the model downloads. Every request after that executes in about 1.5 seconds." — 00:06:30

## Tools and Resources Mentioned

- **RunPod** (runpod.io) — vendor: RunPod — serverless GPU endpoints, Pods, $120M ARR
- **Hugging Face Hub** (huggingface.co) — vendor: Hugging Face — model source for the demo
- **H100 GPUs** — vendor: NVIDIA — the deployed hardware tier in the demo

## GitHub Repos and URLs Referenced

- (none referenced)

## Action Items

- [ ] Try a free-tier serverless deploy on RunPod: pick a small HF model, set context window, hit the endpoint, measure cold start in your region.
- [ ] For any agent product: design for 30-60s cold start on first request; pre-warm on a cron if UX is latency-sensitive.
- [ ] Bookmark the GPU supply tracking — if you build on RunPod/Lambda/CoreWeave, capacity spikes will hit you first.

## Open Questions

- What's RunPod's pricing per-second for a serverless H100 worker? (Not given in the talk — would need to check runpod.io for current rates.)
- How does RunPod compare to Modal / Lambda / CoreWeave for agent-style bursty workloads? (Talk is purely self-positioned.)

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 13:26 transcript)</summary>

0:07 [music]
0:14 >> Audrey, um I am from RunPod. Um this is
0:18 an intro to RunPod. Can I just get a
0:20 quick hands to see how many people have
0:23 already heard of RunPod or maybe even
0:24 used RunPod before?
0:26 Okay, newbies for everybody. Great.
0:30 Um
0:30 So, RunPod, we are a cloud AI
0:33 infrastructure company. So, we have the
0:37 hardware, we have the GPUs, and we make
0:40 it easy for developers to deploy
0:43 um models. And that can be your own
0:44 private model, it can be an open-source
0:46 model from Hugging Face. Doesn't matter
0:48 to us. You bring your code and we'll
0:50 bring the rest.
0:53 Um just really quickly, what problems
0:56 does RunPod solve? Like, why are we even
0:58 here today?
0:59 Um infrastructure can be hard, managing
1:02 it.
1:05 I think about back in the day before we
1:07 had AWS, um Google Cloud, when everybody
1:11 would have to have on-prem servers and
1:14 manage those, maintain those. That
1:15 [clears throat] is something that we
1:16 don't want to have to do as developers.
1:18 Those are things that we happily
1:20 um have moved away from and given off to
1:23 DevOps, and now it's even it's even more
1:25 abstracted for us.
1:27 GPU access is slow and opaque. So, um
1:32 I don't know if you if anybody has tried
1:34 to buy a GPU recently, we're in a global
1:37 supply crunch. Um it's a bit like in
1:40 COVID when everybody went to the store
1:42 and bought all the toilet paper because
1:44 we didn't know how
1:46 how long they would need to be at home
1:47 for. We're a little bit in that right
1:48 now. Um but we expect the market will
1:51 recover um as customers, companies,
1:54 people figure out a little bit better,
1:56 uh get a little bit better at um
1:58 estimating what kind of compute they
2:00 need.
2:01 Um and then last, builder primary focus
2:04 should be building. So, again,
2:07 um
2:07 we want to build
2:09 we as software developers, uh we bring
2:12 bring the value through the applications
2:13 that we build, um not from managing the
2:16 infrastructure.
2:19 And I think RunPod has a pretty unique
2:21 story. These are These are our founders,
2:23 Zenon and Pardeep. Um so, they had a
2:26 couple of GPU rigs in their basement in
2:29 2022,
2:30 um failed crypto mining, and then so
2:32 they're like, "What are we going to do
2:33 with our GPUs now?"
2:35 Um so, they prototyped what is now the
2:38 foundations of RunPod. They posted on
2:41 Reddit and said, "Hey, anyone want to
2:43 use these GPUs for free? Just give us
2:45 feedback on it." And that is literally
2:48 how our company has started, and we have
2:51 been
2:52 um revenue generating ever since.
2:56 Um and the reason why I want to tell
2:57 this story is um not because it's it's
3:00 very like bootstrappy, but because um
3:03 the origin origin story of RunPod has
3:06 always started with uh builders and
3:08 getting feedback from the community, and
3:10 that is still true today.
3:13 So, I won't promise that we'll be
3:15 perfect, but um we are definitely very
3:17 engaged with um our users on on Reddit,
3:20 um on Reddit, on Discord. So,
3:22 um we're always trying to stay engaged
3:24 with y'all.
3:26 Um just at a glance to give you an idea
3:28 of RunPod, we have over 500,000
3:32 developers on our platforms, 30-plus
3:34 data centers across the world, including
3:37 um Europe and the EU.
3:40 Um and we've just passed a significant
3:43 revenue milestone for us, 120 million in
3:45 annual recurring revenue.
3:50 Uh
3:51 these are just a few of our customers.
3:53 Um
3:54 you might be surprised to see some of
3:55 the AI cloud-native companies on here,
3:57 too, but um they come to us for the same
4:00 reasons that most of our customers come
4:02 to us. It's
4:03 um because they need flexible and
4:06 reliable GPU infrastructure.
4:12 This is a really high-over high-level
4:14 overview of um different ways you can
4:18 build on RunPod. So, I would say our
4:22 core at our core, um pods, it's our
4:25 sandbox virtual environment. We spin up
4:27 a container for you, um allocate GPUs to
4:30 it, and we manage the rest. You just
4:33 bring your
4:35 um Dockerfiles, you bring your code.
4:38 Serverless, um it's our auto-scaling
4:41 product. So, when you're thinking more
4:44 about like bursty workloads or batch
4:46 workloads, um serverless is really great
4:48 because um instead of being always on
4:51 like a container is, serverless um your
4:53 workers spin down, and when they're idle
4:56 you don't pay for anything.
4:58 Clusters, um if you were doing some
5:01 heavy-duty training, there's a place for
5:03 you as well on RunPod. Um multi-node
5:06 clusters with high-speed networking.
5:08 And then the hub, which I'll I'll I'll
5:10 switch to in a second, um it's kind of
5:12 like our central repository for AI
5:14 repos.
5:15 Um these are already preconfigured,
5:18 pre-vetted. Um we have a couple of
5:20 examples of listings by RunPod for
5:23 popular models, but also our community
5:26 um contributes to them as well. So,
5:29 there's repos that you can fork, you can
5:32 watch, and then um you can star and
5:34 deploy on RunPod.
5:39 Um so, today we're going to be talking
5:41 mostly about serverless.
5:44 Um so, serverless is best for real-time
5:48 inference. I talked about the
5:49 auto-scaling that comes with it.
5:52 Um
5:52 why teams use it is mostly because they
5:55 don't need to um preempt and figure out
5:58 how much compute they need ahead of
6:00 time. Um
6:02 You can set you can configure the number
6:05 of max workers that you want to scale up
6:06 to. You can set limits for caps, for
6:08 spending caps. And you can also
6:10 configure workers that are always on, so
6:12 they're um
6:13 already have your models downloaded, and
6:16 they can respond to requests um
6:17 immediately.
6:19 For a lot of teams, serverless is the
6:21 fastest way um if you want to start
6:24 deploying a production-ready API.
6:30 And
6:32 now I'm going to switch over
6:35 and just show y'all really quick how
6:38 easy it is to get started and deploy
6:40 something.
6:45 Okay.
6:51 Where are we?
6:56 Okay. So, right now I'm um going to do
6:59 everything via the console so that it's
7:02 nice and pretty for you guys to see, but
7:04 we also have um CLI support. We have
7:07 skills um to help work with RunPod,
7:10 everything that's ready for your agent
7:12 so you don't have to read our documents,
7:13 but since we're all humans here today,
7:15 I'm going to show you via the console.
7:19 Um
7:21 we'll start in the hub, which is if
7:23 you're just trying to explore and see
7:25 what's out there, what is something that
7:26 you can get up and running right now,
7:29 the hub is a great place to start. So,
7:32 like I mentioned, these are already
7:33 vetted open-source listings for um AI
7:37 repos, and
7:39 I am going to pick the LLM,
7:43 um
7:44 and I'll just open the underlying
7:47 repository as well so you could guys can
7:49 see what
7:51 it is literally just a GitHub
7:53 um repo.
7:56 It tells you how to get set up for it.
7:59 Um
8:01 we can see there's already the
8:03 Dockerfile here. It's already
8:06 preconfigured for you. It's got some
8:08 defaults for you um depending on the
8:10 listing. You can um pass in different
8:13 environmental variables
8:15 um to configure it how you wish.
8:21 But I'm just going to go ahead and click
8:23 deploy.
8:25 And
8:28 I have a model that I wanted I
8:37 Let me see.
8:40 I was going to just pick one.
8:44 Looks well.
8:46 This is going to download it from
8:47 Hugging Face. I'm just expand
8:50 the advanced options and look for the
8:52 max model length, and I'm going to
8:55 bump this up for the context window,
8:58 and leave everything else as the
9:01 defaults, but there's settings for max
9:03 loras. Um all of these configuration
9:06 options get passed as um
9:11 as flags to the uh vLLM serve.
9:16 And
9:19 I'm going to spin it up as an endpoint
9:21 here.
9:25 This might take a minute since or two
9:27 since this is the very I just created
9:30 it. I've got to initialize my workers.
9:33 Let's check out.
9:35 So, the default configuration here is
9:37 it's going to deploy on some H100s,
9:40 and A100s are the backup here. I have my
9:43 pricing. This is
9:45 fraction of a cent per second. Um like I
9:49 mentioned before that this is only going
9:51 to be charged for a while the worker is
9:53 actually running and handling a request.
9:56 Max workers is where I can bump this up
9:59 if I want to have
10:02 my workload scale up up to 15 workers at
10:05 a time and I can set
10:07 um some active workers, ones that I want
10:09 always to be on that I don't want um the
10:11 container to ever spin down.
10:16 And I can save that.
10:22 Okay, so how do I how does one interact
10:24 with the serverless endpoint?
10:26 Um
10:27 this is just an API
10:29 uh HTTP endpoint right here. Um we
10:32 provision this endpoint for you. You can
10:34 send requests to this. Your customers
10:36 can send requests to this. If I just hit
10:38 run
10:39 and I'm going to
10:40 add a few Let's
10:44 Which which should we ask the LLM today?
10:48 Say one.
10:52 Okay.
10:54 How did I'm I'm American, so how did Bid
10:56 Then get its name? I don't know.
11:00 >> [clears throat]
11:02 >> Um okay, well these requests are queued.
11:05 Let me check on our workers.
11:08 Okay.
11:09 We have a handful that are in
11:11 initializing. Um this is the container's
11:14 being created. That's the model being
11:16 downloaded. Um getting ready and the
11:18 ones that are running, they've already
11:20 finished. These are probably going to be
11:22 the ones who are going to pick up those
11:23 requests that we just added. I've got
11:25 telemetry about
11:27 um
11:29 it's blank right now, but the number of
11:31 requests, execution time, delay time, so
11:33 you have observability into how your
11:36 endpoints are operating.
11:40 >> [snorts]
11:40 >> And
11:42 let's see. Okay, it's already done.
11:44 >> [snorts]
11:48 >> I got a request back and it sat in the
11:50 queue for about 41 seconds. Um that's
11:53 going to be a little bit longer than all
11:55 of the subsequent requests because of
11:57 some of the cold start time that I
11:58 talked about, like downloading the
11:59 model,
12:00 um initializing the first container, but
12:03 um execution time only about 1 and 1/2
12:06 seconds, so
12:08 yeah, that was probably less than 5
12:09 minutes to get started and get something
12:12 deployed
12:13 um on serverless from a hub listing.
12:22 Does anyone have any questions? This is
12:24 is a very short and sweet intro. Um we
12:27 have another session later today at 4:00
12:30 um and that one is going to be focused
12:32 on our Python um SDK and that one is
12:36 going to be completely via the terminal.
12:40 Um and I'm going to walk you through how
12:42 I can
12:43 spin up
12:44 uh and deploy my code on my code as a
12:47 remote remote function onto a GPU um and
12:52 uh deploy in the end and make it like a
12:55 production-ready endpoint here as well.
13:04 Okay. But that's all I got for today, so
13:07 yeah, thanks thanks for coming.
13:09 >> [applause]
13:18 [music]


</details>
