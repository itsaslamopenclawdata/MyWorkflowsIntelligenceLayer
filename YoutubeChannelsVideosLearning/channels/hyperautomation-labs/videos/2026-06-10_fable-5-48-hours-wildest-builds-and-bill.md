---
title: "Claude Fable 5 Has Been Out 48 Hours — The Wildest Things People Built (and the Bill Nobody Posts)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-10"
duration_seconds: 817
video_id: "VyntpHLY1so"
url: "https://youtube.com/watch?v=VyntpHLY1so"
language: "en"
tags: [claude-fable-5, builds, hacker-news, reddit, one-shot, marathon-builds, billing, token-cost, stripe]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# Claude Fable 5 Has Been Out 48 Hours — The Wildest Things People Built (and the Bill Nobody Posts)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-10  **Duration:** 13:37  **Watch:** https://youtube.com/watch?v=VyntpHLY1so

> **Source note:** Every build in this video was tracked to its source (HN, Reddit, blog, launch demo). The "burn math" uses Anthropic's published list price of $10/M input and $50/M output tokens (2× Opus 4.8). Vendor: Anthropic. The 48-hour-window frame is the channel's, not Anthropic's.

## TL;DR

A tiered catalog of the wildest Claude Fable 5 builds from the first 48 hours after launch, each with its actual cost. Tier 1 = one-shot toys (a horror game live, volumetric clouds, Ethan Mollick's "Balatro for coin flips"). Tier 2 = the impossible bugs (HN user bottlepalm's reverse-engineering problem solved in 30 minutes after stumping Opus 4.8 and GPT 5.5). Tier 3 = marathon builds (Mollick's 9.5-hour Concord research tool + isochrone map; Simon Willison shipped a real LLM library release he says Fable almost entirely wrote). Tier 4 = industrial scale (Stripe's 50M-line Ruby migration in one day; Canva engineer reports ~50% fewer tokens for better results). Then the bill nobody posts: one developer, one day, $210.15 of frontier compute at API rates (zero paid because the free window absorbed it). Plus the silent Opus 4.8 fallback if a classifier trips. 11-day playbook: bring a list of impossible things, not a chat box.

## Key Insights

- **Why the 48 hours exploded**: Fable 5 is free on Pro/Max/Team/Enterprise through 2026-06-22; from 2026-06-23 it requires usage credits. Thousands of people are holding the strongest model on the market with the meter unplugged. (02:05)
- **Tier 1 — One-shot toys**: r/singularity front page on launch day: "It's over. Claude Fable 5 one-shots horror game live" (one prompt → playable horror game). r/claudeai thread "Fable 5 is actually insane" — one-shot volumetric clouds, flight physics, water/waves, procedural islands. Wharton Prof Ethan Mollick with pre-release access: asked for "Balatro for coin flips" → fun little game where every visual is generated mathematically (no art assets, nothing downloaded). Same with a self-aware snake game, "descend into the depths," and a 10-page rhyming poem about a haircut where every word starts with S. Tier 1 receipt: r/vibecoding user sent ONE complex prompt and watched half their daily usage limit vanish. (02:13)
- **Anthropic's own demos** (Tier 1, vendor-polished): Fable 5 beat Pokémon Fire Red using nothing but raw screenshots (no maps, helper tools, or navigation aids) — previous Claudes could not finish it even with extra scaffolding. Autonomously played Factorio (factory building game). Derived planetary motion from physics first principles, built a working solar system simulator, then used it to predict real eclipses. Coded a fluid simulation synchronized to an EDM remix of classical music that the model itself composed in code. (03:32)
- **Tier 2 — The impossible bugs** (the favorite tier):
  - HN user **bottlepalm**: old console games reverse-engineering problem that stumped both Opus 4.8 and GPT 5.5, solved in 30 minutes
  - Another user: weeks of previous-model emulation work for PlayStation's Tomba, Fable finished the job
  - Third user: satellite map reprojection fixed by writing 1/4 of a coordinate library from memory in a different language
  - r/ClaudeAI: developer whose custom GPU physics engine had a bug no model could find — Fable 5 diagnosed it
  - Same subreddit: developer called it a "mature, calm, down-to-earth programmer" after it quietly solved a platform bug Opus had been circling for days
  - Pattern: not toys — specific gnarly weeks-of-your-life problems (04:37)
- **Tier 3 — Marathon builds** (hours, not minutes):
  - Mollick: 9.5-hour single run on a multi-page spec → built "Concord," a research tool that takes multiple datasets and calibrates human judgments against AI judgments. His verdict: "Researchers have needed this for years. It was just never profitable for anyone to build." Will run up to 12 hours on multi-page specs. (06:08)
  - Mollick's wildest: an isochrone map (how long to travel anywhere on Earth). Fable researched 2,200+ real flight routes, TGV and Shinkansen rail schedules, and per-country road speeds from academic papers. Spun up sub-agents to verify data while other agents wrote the code. (06:39)
  - Simon Willison shipped a real LLM library release he says Fable almost entirely wrote, then had it build the sandboxed Python system he'd wanted for ages. (07:04)
  - The marathon receipts cut both ways — Mollick is blunt: burns tokens at twice Opus prices, the conjuring happens somewhere he can't watch, and a software engineer still has to iron out remaining bugs at the end. 9.5 hours of frontier compute is not a rounding error. (07:22)
- **Tier 4 — Industrial scale**:
  - Stripe: 50M-line Ruby migration in a single day, vs Anthropic's estimate of ~2 months for a team by hand
  - Canva engineer: code diffs were surgical, used ~half the tokens of the previous model for better results, called it a "step change worthy of the 5 in the name"
  - Another early tester: 50-page PDF of dense interconnected specs → correctly mapped what was implemented, half-done, and missing entirely
  - This tier is happening quietly inside companies, doesn't show up in viral threads, but explains Anthropic's pricing. (07:43)
- **The meter — $210.15 in one day**: r/ClaudeAI developer set Fable 5 as their Claude Code default on launch day, metered every token. Day-one usage at API rates: **$210.15**. Amount actually paid: $0 (free window absorbed it). One developer, one day, $210 of frontier compute. (08:49)
- **The silent swap they don't show you**: Fable 5 ships with safety classifiers. When one trips (anything that smells like offensive security, broad biology, broad chemistry), the request does not return an error — it silently gets answered by Opus 4.8, the older model. Nothing on your screen tells you. Anthropic says <5% of sessions, conservative tuning. Mollick is less polite: filters trip at the faintest hint of a security problem, way too often. (10:12)
- **The 11-day playbook** (window closes 2026-06-22):
  - Day 1: your stuck bug, the one open for months. Tier-2 problem, might be 30 minutes now.
  - Next: your marathon. Write a multi-page spec for the tool you've always needed, let it run for hours while you sleep. Tier-3.
  - Meter everything like the r/ClaudeAI dev did, so on June 23 you know your workflow cost and whether 2× Opus is worth it for your work
  - If you work anywhere near security or biology, run your real topics now for free and find out whether you're even getting Fable. (11:16)
- **The bigger lesson**: the people winning this window did not show up with a chat box. They showed up with a list of impossible things. Mollick had a backlog of tools he wanted for years. Willison had a library feature he'd been circling for months. The HN testers had specific problems that already beat every other model. (11:21)

## Notable Quotes

> "The viral threads are not lying to you. They are just not showing you the meter." (10:05)

> "Molic is less polite. He says the filters trip at the faintest hint of a security problem, and that it happens way too often." (10:45)

> "The people winning this window did not show up with a chat box. They showed up with a list of impossible things." (11:41)

> "The window closes June 22nd. The people with the list are going to spend it very differently from the people with a chat box." (12:33)

## Tools and Resources Mentioned

- **Claude Fable 5** (vendor: Anthropic) — the model; $10/M input, $50/M output, free on paid plans through 2026-06-22
- **Ethan Mollick** (Wharton, oneusefulthing.org) — "What it feels like to work with Mythos"; Concord; isochrone map
- **Simon Willison** (simonwillison.net) — LLM library release "almost entirely written" by Fable
- **Hacker News testers** — bottlepalm, Gamemaster1379, moffkalast, dannyw, port11
- **Reddit threads** — r/singularity, r/ClaudeAI, r/vibecoding (direct links in the free guide)
- **Stripe** — 50M-line Ruby migration in one day
- **Canva** — engineer review
- **Parameter Golf / Pokémon Fire Red / Factorio / Slay the Spire** — Anthropic launch demos
- **Free "Wildest Builds Vault" guide from Hyperautomation Labs**: comment "WILDEST" on the video or grab from the channel
- **Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

## Action Items

- [ ] Day 1 of the free window: throw your stuck bug at Fable 5 (the one open for months)
- [ ] Then: write the multi-page spec for the tool you've always needed, let it run for hours while you sleep
- [ ] Meter every token like the r/ClaudeAI developer — know your workflow cost before 2026-06-23
- [ ] If you work in security, biology, or chemistry: run your real topics in the free window to detect silent Opus fallbacks
- [ ] Build a list of impossible things BEFORE opening the chat — that's the actual leverage
- [ ] Verify each build claim from the video against its source thread (links in the free guide)
- [ ] Plan for the 2× Opus pricing after the free window — decide on YOUR workload, not the benchmarks

## Open Questions

- For each Tier 4 (Stripe, Canva) build, what was the actual Fable 5 spend in dollars, not just the productivity claim?
- The "$210.15 in one day" — is that average or outlier? What's the median day-one spend for a normal Claude Code user?
- Does the silent Opus 4.8 fallback happen for Opus 4.8 subscribers too, or only for users explicitly on Fable 5?
- Mollick's "filters trip at the faintest hint" — is this just security work, or does it bleed into adjacent fields (CTF, bug bounty, open-source vuln disclosure)?
- The 12-hour "executing without supervision" claim — what guardrails did Mollick set, if any?
- The 50M-line Ruby migration in one day — what verification was done, and what's the rollback path if the diff is wrong?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 13:37 transcript)</summary>

0:00 48 hours. That is how long Claude Fable
0:03 5 has been in public hands.
0:05 In that time, someone one-shotted a
0:08 playable horror game from a single
0:10 prompt live.
0:12 The model beat Pokémon using nothing but
0:14 raw screenshots.
0:16 A Hacker News user watched it crack in
0:18 30 minutes, a reverse-engineering
0:21 problem that had stumped every other
0:23 frontier model.
0:24 And Stripe says it migrated 50 million
0:25 lines of code in a single day.
0:29 The internet is calling it magic.
0:32 So, I tracked down the wildest builds of
0:34 the first 48 hours.
0:37 Verified every single one back to its
0:39 source and ranked them in four tiers.
0:43 Because under every one of these demos,
0:45 there is a number that almost nobody is
0:48 putting in their viral threads.
0:50 What it actually burned.
0:53 Fable 5 is free inside Claude
0:55 subscriptions right now. And on June
0:57 23rd, the meter switches on.
0:59 So, here are the wildest things people
1:01 have already built tier by tier with the
1:04 receipts and the real bill.
1:06 And the last tier is the one that should
1:08 change what you do this week.
1:11 Quick context because it explains
1:13 everything you are about to see.
1:15 On June 9th,
1:16 Anthropic shipped Fable 5,
1:20 the public version of its Mythos class
1:22 model,
1:24 and the most capable thing it has ever
1:25 handed to ordinary users.
1:28 I decoded the full announcement in my
1:29 last video. So, here is the one
1:32 paragraph that matters today.
1:34 From launch through June 22nd, Fable 5
1:36 is included at no extra cost on Pro,
1:39 Max, Team, and Enterprise plans.
1:43 From June 23rd, it requires usage
1:45 credits.
1:46 And at API list prices, it runs $10 per
1:49 million input tokens and $50 per million
1:51 output tokens. That is exactly double
1:56 Opus 4.8. So, right now thousands of
1:59 people are holding the strongest model
2:02 on the market with the meter unplugged.
2:05 That is why the last 48 hours exploded.
2:08 Let's start the countdown.
2:10 Tier one, the one-shot toys.
2:13 On launch day, the front page of
2:15 r/singularity
2:17 was a clip titled It's over. Claude
2:19 Fable 5 one-shots horror game live.
2:23 One prompt goes in. Agent spin-up. A
2:26 playable horror game comes out the other
2:28 side.
2:29 Over on r/claudeai,
2:32 a thread called Fable 5 is actually
2:34 insane,
2:35 filled up with one-shot volumetric
2:36 clouds, flight physics, water, waves,
2:41 and procedural islands.
2:43 And Wharton Professor Ethan Mollick, who
2:45 had pre-release access, asked it for
2:47 Balatro,
2:48 but for the game of coin flips.
2:51 He got a genuinely fun little game where
2:54 every visual is generated
2:55 mathematically.
2:56 No art assets.
2:58 Nothing downloaded.
3:00 He did the same with a self-aware snake
3:02 game
3:03 and a game about descending into the
3:04 depths.
3:05 He even asked for a 10-page rhyming poem
3:07 about a haircut where every single word
3:10 starts with the letter S.
3:12 It did that, too,
3:13 in one
3:14 session.
3:15 But here is the tier one receipt.
3:18 Over on r/vibecoding,
3:20 a user sent one complex prompt.
3:22 One.
3:23 And watched half of their daily usage
3:24 limit vanish.
3:27 The toys are real.
3:29 They are just not free shipped.
3:31 They are subsidized.
3:32 To be fair, Anthropic started this.
3:35 The launch demos were built to melt the
3:37 internet.
3:39 Fable 5 beat Pokémon Fire Red using
3:41 nothing but raw screenshots.
3:43 
No maps,
3:45 no helper tools,
3:46 no navigation aids.
3:48 A game that previous Claude models could
3:50 not finish even with extra scaffolding
3:53 bolted on.
3:54 It autonomously played Factorio, the
3:57 factory building game, strategizing and
3:59 expanding on its own.
4:02 It derived planetary motion from physics
4:04 first principles,
4:05 built a working solar system simulator,
4:08 and then used that simulator to predict
4:10 real eclipses.
4:12 And it coded a fluid simulation
4:14 synchronized to an EDM remix of
4:15 classical music
4:17 that the model itself composed in code.
4:20 Now, those are vendor demos, polished,
4:23 hand-picked. Every launch has them.
4:26 The reason this one feels different is
4:29 that within hours
4:30 random people on the internet
4:33 were posting things in the same league.
4:35 Which brings us to tier two.
4:37 Tier two is my favorite tier.
4:39 The nothing else could do this tier.
4:42 On Hacker News,
4:43 a user called Bottle Palm threw an old
4:46 console games reverse engineering
4:48 problem
4:49 at Fable 5,
4:50 a problem that had already stumped both
4:53 Opus 4.8 and GPT 5.5,
4:57 solved in 30 minutes.
5:00 Another user had spent weeks on the
5:02 previous model
5:04 doing emulation work for the PlayStation
5:06 game Tomba.
5:08 Fable finished the job.
5:10 A third watched it fix satellite map
5:12 reprojection by writing a quarter of a
5:15 coordinate library from memory
5:17 in a different programming language than
5:19 the original.
5:20 And on r/ClaudeAI,
5:22 one of the top posts of day two was a
5:25 developer whose custom GPU physics
5:26 engine had a bug that no model could
5:30 find.
5:31 Fable 5 diagnosed it.
5:33 Same subreddit, another developer called
5:35 it a mature,
5:37 calm, down-to-earth programmer
5:5:40 after it quietly solved a platform bug
5:43 that Opus had been circling for days.
5:46 Notice the pattern here.
5:48 These are not toys.
5:50 These are specific, gnarly weeks of your
5:54 life problems.
5:55 This is the tier that made senior
5:57 engineers sit up.
5:59 But people kept pushing.
6:01 What happens if you give this thing not
6:03 minutes but hours?
6:04 Tier three,
6:06 the marathon builds.
6:08 Ethan Mollick handed Fable 5 a
6:10 multi-page specification and watched it
6:12 work alone for 9 and 1/2 hours.
6:16 It built a research tool called Concord
6:19 that takes in multiple data sets
6:21 and calibrates human judgments against
6:23 AI judgments.
6:25 His verdict,
6:26 "Researchers have needed this for years.
6:29 It was just never profitable for anyone
6:31 to build."
6:32 Across his testing, he says it would
6:34 keep executing for up to 12 hours on
6:37 multi-page specs.
6:39 His wildest experiment was an isochrone
6:41 map,
6:42 a map of how long it takes to travel
6:45 anywhere on Earth.
6:47 Fable researched over 2,200 real flight
6:49 routes,
6:50 TGV and Shinkansen rail schedules, and
6:53 per-country road speeds pulled from
6:55 academic papers.
6:57 And it spun up its own sub-agents to
6:59 verify the data
7:01 while other agents wrote the code.
7:03 Meanwhile,
7:04 Simon Willison,
7:06 one of the most respected developers in
7:08 open source,
7:09 shipped a real release of his LLM
7:11 library
7:13 that he says Fable almost entirely
7:14 wrote.
7:16 Then had it build the sandboxed Python
7:17 system he had wanted for ages.
7:20 But the marathon receipts cut both ways.
7:23 Mollick is blunt.
7:25 It burns tokens at twice Opus prices.
7:29 The conjuring happens somewhere he
7:30 cannot watch.
7:32 And a software engineer still has to
7:34 iron out the remaining bugs at the end.
7:37 9 and 1/2 hours of frontier compute is
7:39 not a rounding error. Hold that thought
7:41 for the meter.
7:43 Tier four,
7:44 industrial scale.
7:46 Stripe got early access, pointed Fable 5
7:50 at a 50 million line Ruby code base,
7:52 and ran a migration in a single day
7:55 that Anthropic says would have taken a
7:57 whole team about two months by hand.
8:00 An engineer at Canva
8:02 who tested it before launch reported
8:04 that the code diffs were surgical.
8:07 That it used roughly half the tokens of
8:09 the previous model for better results.
8:11 And called it a step change
8:14 worthy of the five in the name.
8:17 Another early tester
8:19 fed it a 50-page PDF of dense
8:22 interconnected specifications
8:24 and it correctly mapped
8:26 what was implemented,
8:28 what was half done, and what was missing
8:30 entirely.
8:32 You will not see this tier in the viral
8:34 threads because it is happening quietly
8:37 inside companies.
8:39 But this is the tier that explains why
8:41 Anthropic priced this model the way they
8:43 did.
8:44 Which brings us to the part of this
8:45 video nobody else is making.
8:48 The meter.
8:49 Here is the number underneath everything
8:52 you just saw.
8:53 On r/ClaudeAI,
8:56 one developer did exactly what I wish
9:00 everyone did.
9:01 They set Fable 5 as their Claude code
9:04 default on launch day, and they metered
9:07 every single token.
9:09 Day one usage,
9:10 priced at API rates, $210.15.
9:16 Amount actually paid, zero
9:18 because the free window absorbed all of
9:20 it.
9:21 One developer, one day,
9:24 $210 of frontier compute.
9:27 Now, run that math back across the
9:28 tiers. The vibe coding user lost half a
9:31 daily limit to a single prompt.
9:34 Molic ran 9 and 1/2 hours in one
9:36 sitting. And he never published the
9:38 bill.
9:39 At $10 in and $50 out per million
9:42 tokens, you can guess why almost nobody
9:45 is publishing this. So, here is the
9:48 honest frame for the last 48 hours. It
9:50 is not just that the model got smarter.
9:53 It is that for 2 weeks, the strongest
9:55 model on the market costs subscribers
9:57 nothing extra. And everyone is swinging
9:59 as hard as they can before June 23rd.
10:03 The viral threads are not lying to you.
10:05 They are just not showing you the meter.
10:08 And there is one more thing
10:10 they are not showing you, either.
10:12 Fable 5 ships with safety classifiers.
10:16 And when one of them trips,
10:18 anything that smells like offensive
10:19 security work,
10:20 and broad areas of biology and
10:23 chemistry,
10:25 your request does not return an error.
10:28 It silently gets answered by Opus 48,
10:31 the older model.
10:33 And nothing on your screen tells you the
10:35 swap happened.
10:36 Anthropic says this hits fewer than 5%
10:39 of sessions,
10:40 and admits the tuning is conservative.
10:43 Molic is less polite.
10:45 He says the filters trip at the faintest
10:47 hint of a security problem,
10:49 and that it happens way too often.
10:52 Why does that matter in a video about
10:54 wild bills?
10:55 Because if your version of the wildest
10:57 thing touches security research, or
11:00 reverse engineering, or biotech,
11:03 there is a real chance the model
11:04 answering you is not Fable at all.
11:07 And you would never know.
11:09 Test your real topics before the free
11:12 window closes,
11:11:13 which is exactly what the playbook is
11:15 for.
11:16 Because here is what the first 48 hours
11:18 actually teach. And it is not go one
11:20 shot a horror game.
11:23 Look at who got the most out of this
11:25 model.
11:26 Molic walked in with a backlog of tools
11:28 he had wanted for years.
11:30 Willison walked in with a library
11:32 feature he had been circling for months.
11:35 The Hacker News testers walked in with
11:37 specific problems that had already
11:39 beaten every other model.
11:41 The people winning this window did not
11:43 show up with a chat box.
11:45 They showed up with a list of impossible
11:47 things.
11:48 So, for the next 11 days, while the
11:51 meter is unplugged, here is the plan.
11:54 Day one, your stuck bug.
11:56 The one that has been open for months.
11:59 That is a tier two problem, and it might
12:01 be 30 minutes now.
12:03 Next, your marathon.
12:05 Write the multi-page spec for the tool
12:07 you have always needed, and let it run
12:09 for hours while you sleep. That is tier
12:12 three.
12:13 Meter everything like that Reddit
12:15 developer did,
12:16 so that on June 23rd,
12:18 you know exactly what your workflow
12:20 costs, and whether double Opus pricing
12:23 is worth it for your work.
12:25 And if you work anywhere near security
12:26 or biology,
12:28 run your real topics now for free, and
12:31 find out whether you are even getting
12:32 fable.
12:33 The window closes June 22nd.
12:36 The people with the list are going to
12:37 spend it very differently from the
12:39 people with a chat box.
12:41 I put all of it into a free guide.
12:44 Every build from this video, tier by
12:46 tier,
12:47 with direct links to every thread and
12:49 post, so you can verify each one
12:52 yourself.
12:53 The burn math,
12:54 the silent downgrade test,
12:56 and the 11-day playbook with the exact
12:59 prompts to start tonight.
13:01 Comment the word wildest,
13:04 and I will send it to you.
13:05 Free.
13:06 If this saved you a week of scrolling
13:08 threads, subscribe.
13:11 The free window ends June 22nd,
13:14 and I am testing
13:16 what this model can really do all the
13:19 way to the deadline.
13:21 I drop
13:22 bite-size AI breakdowns
13:24 everyday
13:25 on Instagram,
13:27 and the full deep dives
13:30 like this one
13:31 right here on YouTube.
13:33 I will see you in the next one.

</details>
