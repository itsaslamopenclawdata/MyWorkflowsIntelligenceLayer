---
title: "Claude Mythos 5 Is Here — and You're Not Allowed to Use It"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-09"
duration_seconds: 748
video_id: "S-5BJwqpcdg"
url: "https://youtube.com/watch?v=S-5BJwqpcdg"
language: "en"
tags: [anthropic, claude-fable-5, claude-mythos-5, project-glasswing, model-tiering, classifiers, cybersecurity, biotech, pricing, swe-bench]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# Claude Mythos 5 Is Here — and You're Not Allowed to Use It

**Channel:** Hyperautomation Labs  **Published:** 2026-06-09  **Duration:** 12:28  **Watch:** https://youtube.com/watch?v=S-5BJwqpcdg

> **Naming note:** "Claude Fable 5" and "Claude Mythos 5" are the names Anthropic gave to the two publicly-announced tiers on 2026-06-09. "Project Glasswing" is Anthropic's name for the US-government collaboration tier. Vendor: Anthropic. This is independent analysis, not affiliated with Anthropic. The video's date claims and benchmark numbers should be verified against Anthropic's official announcement before relying on them.

## TL;DR

Anthropic launched two models on 2026-06-09 with the same underlying brain: Claude Fable 5 (public, free on paid plans through 2026-06-22, then metered) and Claude Mythos 5 (government / Project Glasswing — you will never touch it). The only difference is invisible classifiers sitting between you and the full model — cybersecurity, biology/chemistry, and distillation. The critical mechanism: **a blocked query doesn't error, it silently falls back to Opus 4.8** with no on-screen indicator. Filters trigger in <5% of sessions per Anthropic, but if you work in security or biotech, your sessions are the 5%. Pricing: $10/$50 per M tokens (exactly 2× Opus 4.8). Capability ceiling of the unfiltered tier: ~10× drug design speedup, 9/14 protein targets, week-long autonomous genomics run across 138 species. 1,000+ hours of external red-team testing produced zero universal jailbreaks.

## Key Insights

- **One model, two names, one mechanism**: Fable 5 = the same intelligence as Mythos 5 wrapped in three classifier systems. The frontier is officially two-tiered. (03:29)
- **SWE-bench Pro 80.3%** vs Opus 4.8's 69.2%, GPT 5.5's 58.6%, Gemini 3.1 Pro's 54% — a new tier, not an incremental bump. (01:30)
- **The receipts**: Stripe migrated 50 million lines of Ruby in a single day (Anthropic says a team would have taken ~2 months). Fable 5 beat Pokémon FireRed on raw screenshots alone (previous Claudes couldn't, even with extra scaffolding). 3× better Slay the Spire with simple file-based memory. Cursor, GitHub, and Perplexity CEO all call it state-of-the-art. (02:00)
- **Three classifier systems**: (1) cybersecurity / exploitation, (2) biology and chemistry ("broadly blocks most requests," not just weapons), (3) distillation (extracting capabilities to train competitors). (04:33)
- **The silent-fallback mechanism**: a blocked query does NOT return an error — it is silently answered by Opus 4.8, the older model, with nothing on your screen telling you the swap happened. This is the most important detail in the video. (05:09)
- **<5% filter trigger rate** per Anthropic's own reporting, with the honest caveat that tuning is conservative (some harmless requests get caught). For most people, most of the time, this changes nothing. But if you work in security, biotech, or chemistry, your sessions are exactly inside that 5%. (05:32)
- **Mythos 5 capability ceiling you don't get**: ~10× drug design speedup in Anthropic's protein design study, 9/14 protein targets produced strong drug candidates, scientists preferred Mythos's molecular biology hypotheses ~80% of the time in blind comparisons, an E. coli protein hypothesis was later independently corroborated, week-long autonomous genomics run assembled single-cell data for millions of cells across 138 animal species and built a custom ML model 100× smaller that beat a published science paper. (06:00)
- **Jailbreak wall**: 1,000+ hours of external bug-bounty testing, zero universal jailbreaks. External red teams also failed. One partner called these "the most robust safeguards of any model they have tested." Honest caveat: the UK AISI made progress toward one in an early testing window. Anthropic's own published chart shows attack success rates on offensive cyber tasks dropping sharply with classifiers on. Anthropic admits total prevention is "likely impossible" — the goal is to make jailbreaks slow and expensive enough to detect and patch. (07:10)
- **Pricing**: $10/M input, $50/M output — exactly 2× Opus 4.8 ($5/$25). Anthropic's framing ("less than half of Mythos preview") is technically true but flattering, since most people were using Opus 4.8 last week, not Mythos preview. 1M token context window is preserved at standard pricing. (08:14)
- **The June 23 deadline**: Fable 5 is free on Pro/Max/Team/Enterprise plans from June 9 through June 22. Starting June 23 it requires usage credits. Anthropic "hopes" to make it standard again once capacity allows — no date attached. (09:20)
- **30-day data retention on all Mythos-class models including Fable 5**: Anthropic says it won't be used for training, exists only for safety, with new privacy protections. It applies to you — know it exists before pasting anything sensitive. (09:56)
- **The 14-day test plan**: Day 1 = throw your single hardest task (the refactor you're avoiding, the migration nobody wants). Then test vision. Then re-run the same job on Opus 4.8 and compare cost vs quality — double price needs double proof on YOUR workload. If you work in security or biotech, test your real topics early in the free window to see if queries are silently falling back to Opus. (10:28)
- **The bigger shift**: in a two-tier AI world, the advantage is no longer access to intelligence. Everyone has the chat box. The advantage is knowing exactly which intelligence is answering you. (11:22)

## Notable Quotes

> "The question is no longer just how smart the model is. It is who decided what your copy of it is allowed to say. For the first time, the frontier is officially two-tiered." (04:17)

> "A blocked query does not return an error. It silently gets answered by Claude Opus 4.8. You ask Fable. Opus answers. And nothing on your screen tells you the swap happened." (05:09)

> "The moat is no longer the model. The moat is clearance." (07:05)

> "In a two-tier AI world, the advantage is no longer access to intelligence. The advantage is knowing exactly which intelligence is answering you." (11:22)

## Tools and Resources Mentioned

- **Claude Fable 5** (vendor: Anthropic) — public tier, free on paid plans through 2026-06-22, $10/$50 per M tokens after
- **Claude Mythos 5** (vendor: Anthropic) — unfiltered tier, government-only via Project Glasswing
- **Project Glasswing** (vendor: Anthropic + US government) — critical-software / cyber-defender collaboration
- **Claude Opus 4.8** (vendor: Anthropic) — the silent-fallback model
- **SWE-bench Pro 80.3%** — Fable 5's score; vs Opus 4.8 69.2%, GPT 5.5 58.6%, Gemini 3.1 Pro 54%
- **Cognition Frontier Code Evaluation** — Fable 5 highest among frontier models
- **Stripe** — early-access case study: 50M-line Ruby migration in one day
- **Cursor, GitHub, Perplexity** — early-access reviewer quotes
- **UK AISI** — early-window progress toward a jailbreak (caveat)
- **Free Decision Guide** from Hyperautomation Labs: https://hyperautomationlabs.co/free/fable-5-decision-guide
- **Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

## Action Items

- [ ] If on Pro/Max/Team/Enterprise, test Fable 5 between now and 2026-06-22 before the meter starts
- [ ] Day 1: run your single hardest task (the refactor you've been avoiding) — long-horizon is where this model separates
- [ ] Test vision (screenshots → working code, charts → exact numbers) if relevant to your work
- [ ] Re-run the same job on Opus 4.8 and compare cost vs quality — 2× price needs 2× proof on YOUR workload
- [ ] If you work in security, biotech, or chemistry, run your real topics early in the free window to detect silent Opus fallbacks
- [ ] Audit your prompt content for sensitivity — Mythos-class models now have 30-day data retention
- [ ] Comment "GLASSWING" or grab the Fable 5 Decision Guide before June 22
- [ ] Verify the June 9 2026 dates, pricing, and benchmark numbers against Anthropic's official announcement before relying on them for production decisions

## Open Questions

- How does the classifier fallback work technically — is it a routing layer at the API gateway, or a prompt-level substitution?
- Does the 30-day data retention apply to Fable 5 traffic on Pro/Max/Team plans, or only to Mythos 5?
- If you suspect silent fallback to Opus 4.8 mid-session, is there any observable signal (latency, response style shift, finish_reason) to detect it?
- Will the 1,000+ jailbreak hours of testing be published, and what does the "progress" the UK AISI made look like?
- Anthropic's "trusted access program for biology researchers" — what are the criteria, and when does it open?
- Is the 2× price vs Opus 4.8 inclusive or exclusive of the effort controls, batching, prompt caching, etc.?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 12:28 transcript)</summary>

0:00 On June 9th, Antropic launched two AI
0:03 models with the exact same brain. One is
0:06 called Claude Fable 5. You can use it
0:09 today and for the next 2 weeks it is
0:12 included free inside your Claude
0:14 subscription. The other is called Claude
0:18 Mythos 5. You will never touch it.
0:22 It ships through something called
0:24 Project Glasswing, a collaboration with
0:27 the US government because Anthropic says
0:30 it has the strongest cyber security
0:32 capabilities of any model in the world.
0:34 Same model, two names, and the only
0:38 difference is a set of invisible
0:40 classifiers that sit between you and the
0:42 full version, silently deciding which
0:44 answers you are allowed to get. I read
0:47 the entire announcement, the benchmark
0:49 tables and the fine print most people
0:51 will scroll straight past. There are
0:53 three hidden filters. One, new data
0:56 retention policy and one billing
0:59 deadline on June 23rd that you need to
1:01 know about. Let me decode the whole
1:03 thing. First, what actually shipped?
1:07 Anthropic calls Fable 5 a mythos class
1:10 model that has been made safe for
1:13 general use. Translation
1:16 This is the most capable model they have
1:20 ever released to the public. It is
1:22 state-of-the-art on nearly every
1:24 benchmark they tested. Software
1:27 engineering, knowledge, work, vision,
1:31 scientific research. On SW Bench Pro, it
1:35 scores 80.3%.
1:37 Claude Opus 4.8, the model that was the
1:41 king just weeks ago, sits at 69.
1:46 GPT 5.5 scores around 59.
1:49 Gemini 3.1 Pro around 54.
1:53 That is not an incremental bump. That is
1:56 a new tier and the early feedback
1:59 matches.
2:00 Cursor calls it the state-ofthe-art on
2:03 their benchmark. GitHub says its
2:05 autonomy exceeded previous benchmarks.
2:09 Perplexity's CEO says it works at the
2:12 level of a senior research scientist.
2:14 The headline is real, but the headline
2:17 is not the story. Here are the receipts
2:19 that made me sit up. Stripe got early
2:22 access and reported that Fable 5
2:25 compressed months of engineering into
2:27 days. In one case, the model performed a
2:30 migration across a 50 million line Ruby
2:32 codebase in a single day.
2:34 Anthropic says that same job would have
2:37 taken a whole team about two months by
2:39 hand. on Cognition's Frontier Code
2:42 Evaluation,
2:43 which tests whether code meets real
2:45 production standards. Fable 5 scores
2:47 highest among Frontier models. Then it
2:49 gets weirder. Fable 5 beat Pokémon Fire
2:53 Red using nothing but raw screenshots.
2:56 No maps, no helper tools, no navigation
2:59 aids. Previous Claw models could not
3:02 finish that game, even with extra
3:05 scaffolding bolted on. And with a simple
3:08 file-based memory, it played Slay the
3:11 Spire three times better than Opus 48,
3:14 reaching the final act three times more
3:16 often. The pattern in all of these is
3:19 the same. Long tasks, sustained focus,
3:23 no babysitting. Now, the part of the
3:26 announcement most coverage will skip.
3:29 Fable five and mythos five are the same
3:33 underlying model. Antropic says it
3:36 directly in writing. The difference is
3:40 not intelligence. The difference is
3:42 permission.
3:44 Mythos 5 is the version with safeguards
3:46 lifted in some areas. It launches inside
3:50 project Glass, a collaboration with the
3:52 US government where cyber defenders and
3:56 infrastructure providers use it to
3:58 secure critical software. Anthropic
4:00 states plainly that mythos 5 has the
4:04 strongest cyber security capabilities of
4:06 any model in the world. Fable 5 is that
4:09 same intelligence wrapped in classifiers
4:12 and handed to the rest of us. Think
4:14 about what that actually means. The
4:17 question is no longer just how smart the
4:20 model is. It is who decided what your
4:23 copy of it is allowed to say. For the
4:26 first time, the frontier is officially
4:30 two-tiered. So what exactly is in tha
t4:33 wrapper? Three classifier systems sit
4:36 between you and the full model. Filter
4:39 one, cyber security.
4:42 Anything that looks like exploitation or
4:44 offensive cyber work gets caught. Filter
4:47 two, biology and chemistry.
4:50 Anthropic says it broadly blocks most
4:53 requests related to these fields. Not
4:56 just weapons work, most requests. Filter
4:59 three, distillation.
5:01 Attempts to extract Fable's capabilities
5:04 to train competing models get flagged.
5:07 And here is the mechanism. The one
5:09 detail I want you to remember from this
5:11 video. A blocked query does not return
5:15 an error. It silently gets answered by
5:18 Claude Opus 4.8, the older model.
5:20 Instead, you ask Fable. Opus answers.
5:25 and nothing on your screen tells you the
5:28 swap happened. Now, the honest numbers.
5:32 Antropic says these filters trigger in
5:35 less than 5% of sessions and they admit
5:39 the tuning is conservative. So, some
5:41 harmless requests get caught. For most
5:44 people, most of the time this changes
5:46 nothing. But if you work in security,
5:50 biotech or chemistry, your sessions are
5:53 exactly the ones inside that 5%. So what
5:57 does the unfiltered tier actually do?
6:00 This is where the announcement starts to
6:02 read like science fiction. With MYOS 5,
6:05 Antropics internal protein design
6:07 experts accelerated parts of drug design
6:10 by around 10 times. Nine of the 14
6:13 protein targets in their study produced
6:16 strong drug candidates that they are now
6:18 investigating.
6:20 In blind comparisons, scientists
6:22 preferred Mythos's molecular biology
6:24 hypothesis about 80% of the time and one
6:29 of its hypothesis about an E.coli
6:32 protein was later backed up by an
6:34 independent study. It also ran an
6:37 autonomous genomics project for a full
6:39 week, assembling single cell data for
6:42 millions of cells across 138 animal
6:46 species and built a custom machine
6:49 learning model that beat a published
6:51 science paper while being 100 times
6:54 smaller. That is the capability ceiling.
6:57 And Anthropic says a trusted access
6:59 program for biology researchers is
7:01 opening soon. Read that again. The moat
7:05 is no longer the model. The moat is
7:07 clearance. Can you just jailbreak your
7:10 way to the full version?
7:12 Anthropic spent serious money making
7:14 sure you cannot. They ran an external
7:17 bug bounty and over 1,000 hours of
7:20 testing produced zero universal
7:22 jailbreaks. The external red teams they
7:25 hired failed too. Although the UK AI
7:28 security institute did make progress
7:30 toward one in an early testing window.
7:33 One partner called these the most robust
7:35 safeguards of any model they have
7:37 tested. Their own published chart shows
7:40 attack success rates on offensive cyber
7:43 tasks dropping sharply once the
7:46 classifiers are switched on. And to
7:48 their credit, Anthropic is honest about
7:51 the limit. They say it is likely
7:53 impossible to completely prevent
7:55 jailbreaks. The real goal is to make
7:58 them so slow and so expensive that they
8:02 get detected and patched before they
8:04 matter at scale. The wall is not
8:07 perfect, but it is the tallest one any
8:10 lab has built so far. Now the money
8:14 fable 5 costs $10 per million input
8:17 tokens and $50 per million output
8:20 tokens. That is exactly doubleclaw opus
8:23 4.8 8 which sits at 5 and 25.
8:28 Antropic frames the price as less than
8:30 half of Claude Mythos preview which is
8:33 true. It is also a very flattering
8:35 comparison because the model most of us
8:38 were actually using last week was Opus
8:41 not mythos preview. So the real question
8:44 is simple. When is double worth it? You
8:48 still get the 1 million token context
8:50 window at standard pricing. You still
8:53 get effort controls to dial spending
8:55 down on easy work. And on long horizon
8:59 tasks, a smarter model can finish in
9:02 fewer attempts, which sometimes makes
9:04 the expensive model the cheaper total
9:06 bill. But for everyday coding and
9:09 writing, Opus 48 at half the price did
9:12 not stop existing. Double the price
9:15 needs double the proof on your workload,
9:18 not on their benchmark. Here is the
9:20 deadline buried in the rollout section.
9:23 If you are on pro, max, team, or a
9:27 seatbased enterprise plan, Fable 5 is
9:30 included at no extra cost from June 9th
9:34 through June 22nd.
9:36 Starting June 23rd, it requires usage
9:40 credits.
9:41 Antropic says they hope to make it
9:43 standard again once capacity allows.
9:47 There is no date attached to that
9:48 promise.
9:50 So you have a 14-day free window and
9:52 then the meter starts. And one more
9:56 change that deserves daylight.
9:58 A new data retention policy. All traffic
10:01 on Mythos class models including Fable 5
10:04 is now retained for 30 days. Antropic
10:07 says it will not be used to train
10:09 models, that it exists only for
safety10:11 purposes, and that new privacy
10:13 protections sit around it. That may be a
10:16 fair trade for Frontier capability.
10:19 But it is a change. It applies to you
10:22 and you should know it exists before you
10:25 paste anything sensitive. So here is the
10:28 playbook for the next 14 days. Day one,
10:31 throw your single hardest task at it.
10:34 Not a toy prompt. The refactor you have
10:37 been avoiding. The migration nobody on
10:40 the team wants the 50 file bug. Long
10:43 horizon work is exactly where this model
10:46 is supposed to separate from opus. Then
10:49 if your work touches vision, test that
10:52 screenshots into working code charts
10:55 into exact numbers. Then run the same
10:58 job on Opus 48 and compare cost against
11:01 quality because double the price needs
11:04 double the proof. And if you work in
11:06 security or biotech, run your real
11:09 topics early in the free window. If your
11:11 queries are quietly falling back to
11:13 Opus, then Fable buys you nothing in
11:16 your field and now you know before you
11:19 ever pay for it. Because here is the
11:22 bigger shift. In a two-tier AI world,
11:25 the advantage is no longer access to
11:28 intelligence. Everyone has the chat box.
11:32 The advantage is knowing exactly which
11:35 intelligence is answering you. I
11:37 condensed all of this into a one-page
11:40 Fable 5 decision guide. What is free
11:43 until June 22nd, the three filters and
11:47 who they actually affect, the double
11:49 price math against Opus 4 and 8, and the
11:53 exact test plan for the free window.
11:56 Comment the word glasswing and I will
11:59 send it to you free. If this decode
12:03 saved you a trip through a 9,000word
12:05 announcement, subscribe.
12:08 I read these documents line by line so
12:10 you do not have to. And the next one is
12:13 already sitting on my desk. I drop
12:16 byte-size AI breakdowns every day on
12:18 Instagram and the full deep dives like
12:22 this one right here on YouTube. I will
12:25 see you in the next one.

</details>
