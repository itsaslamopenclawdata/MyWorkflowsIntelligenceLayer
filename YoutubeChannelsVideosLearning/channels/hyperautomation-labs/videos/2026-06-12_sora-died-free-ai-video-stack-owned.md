---
title: "Sora Died and OpenAI Deleted Everything — The Free AI Video Stack Nobody Can Shut Down"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-12"
duration_seconds: 852
video_id: "6R5Rsv15adI"
url: "https://youtube.com/watch?v=6R5Rsv15adI"
language: "en"
tags: [sora-shutdown, openai, ownership, open-source, video-generation, wan-22, ltx-23, hunyuanvideo, ovi, comfyui, wan2gp, license-fine-print, region-bans]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# Sora Died and OpenAI Deleted Everything — The Free AI Video Stack Nobody Can Shut Down

**Channel:** Hyperautomation Labs  **Published:** 2026-06-12  **Duration:** 14:12  **Watch:** https://youtube.com/watch?v=6R5Rsv15adI

> **Source note:** Channel's own verification of the Wall Street Journal's Sora-shutdown numbers, every model license, hardware spec, and free-GPU lane. Recorded ~6 weeks after the 2026-04-26 Sora shutdown. All license claims read from each model's own LICENSE file the week of 2026-06-08.

## TL;DR

A 5-channel ownership stack that replaces the rent-economy of paid AI video, anchored by the 2026-04-26 Sora shutdown (WSJ: ~$1M/day burn, <500K active users, Disney's $1B partnership dead with <1h notice, all user content permanently deleted after export window, leftover paid credits now redeemable only in Codex). 4 open video models with their real licenses: Wan 2.2 (Alibaba, Apache), LTX-2.3 (Lightricks, community license w/ $10M/yr revenue cap), HunyuanVideo 1.5 (Tencent, **community license void in EU/UK/South Korea** + 100M user cap), Ovi (Character AI + Yale, joint audio+video, ~6GB VRAM). The cockpits: ComfyUI (standard) or Wan2GP ("AI video for the GPU poor", 6GB+ VRAM, one-click via Pinokio). Finishing kit: SeedVR2 (upscale), RIFE (interpolation), MMAudio (soundtrack). No-GPU lanes: HF ZeroGPU Spaces (5min GPU/day free), Google Colab T4, Kaggle (30 GPU hrs/week), Modal ($30/mo recurring), RunPod/Vast (24GB 3090 from 17-19¢/hr). The "trust check" trap: SEO articles pushing "Wan 2.7 open source" — Alibaba never open-sourced past 2.2. Decision rule: **own the pipeline, rent the peak**.

## Key Insights

- **The Sora death receipts (2026-04-26)**:
  - WSJ: burning ~$1M/day, active users <500K
  - Disney's $1B partnership died with <1 hour's notice
  - After the export window closes, **OpenAI permanently deletes everything users ever made**
  - Leftover paid credits? They now work in **Codex**. A coding tool. Months of creative work gone because the people who made it never owned any of it. (00:00)
- **The rent meter (June 2026 prices, from official pricing pages)**:
  - Runway $12/mo = **25 seconds of Gen-4.5 per month** (their own pricing page) — and the Unlimited plan was **retired 2026-06-01**
  - Kling top tier $180/mo, **up 41% since launch**, no annual discount tier
  - Google AI Ultra $249.99/mo
  - Realistic creator stack (Runway Pro + Kling Pro + Google AI Pro) ≈ $92/mo, $1,100+/yr
  - **Under the surface**: Runway and Luma now resell Veo and Kling inside their own subscriptions. Market is consolidating. Fewer real options, floating prices, plans vanishing mid-year. (01:28)
- **The rule this whole video runs on**: a model is only yours if the weights (the actual files) sit on your disk under a license that lets you use them. **Apache and MIT = free forever, commercial use allowed, nobody can revoke it.** Once downloaded, no shutdown announcement, no price hike, no IPO cleanup can touch them. Sora users lost everything in a single quarter. A model you downloaded last summer still works the same today, and will in 20 years. (02:44)
- **The trap most videos mislead you with**: not everything called "open" is actually open. Some licenses carry revenue caps. One is void across entire continents. Some so-called open-source models don't exist as downloads at all. (03:30)
- **Model 1 — Wan 2.2 (Alibaba, Apache 2.0)**: T2V + I2V at 720p. Two sizes: 5B = 5-second 720p clip in <9 min on RTX 4090. 14B = quality pick, quantized GGUF builds fit in 8-10GB VRAM, runs on a gaming laptop. **The trap**: Alibaba's newer models (Wan 2.5, 2.6, 2.7) were never open-sourced — they are API only, rent only. **SEO content farms are publishing articles right now claiming Wan 2.7 is an open download.** Go check Alibaba's actual GitHub — the newest open repo is 2.2 from last July. The free download those blogs promise does not exist. The newest Wan you can own is 2.2, and it is excellent. github.com/Wan-Video/Wan2.2 (04:03)
- **Model 2 — LTX-2.3 (Lightricks, 22B, March release, 2M+ downloads)**: the one that does what paid tools charge extra for. **Generates video and synchronized audio together in a single pass** (dialogue, lip sync, sound effects, stereo). First production-ready open model to pull that off. Full version goes up to 4K. **Catches**: (1) hardware — efficient FP8 build still wants 18-20GB VRAM, workstation or rented GPU, won't run on the free Colab card. (2) license — **community license, not Apache; free for research and commercial use while your company makes under $10M/yr; above that you pay Lightricks.** For basically everyone watching, that's effectively free. But that is exactly the kind of fine print this video exists to read out loud. (05:18)
- **Model 3 — HunyuanVideo 1.5 (Tencent, 8.3B)**: pound for pound, the best quality per GB in open video right now. Officially runs in 14GB VRAM; FP8 build pushes near 12GB. 5-second clip takes ~5 min on a 4090 (verified user numbers, not marketing). **The catch is a big one**: Tencent's community license **literally does not apply in the European Union, the United Kingdom, or South Korea**. If you are there, you are not licensed to use it at all. Also a 100M user cap and a required "powered by Tencent" credit line. (06:40)
- **Model 4 — Ovi (Character AI + Yale)**: open weights, generates audio and video jointly, like a miniature VO. Community builds run it in ~6GB. Quality sits below LTX, but it's the audio+video option for small GPUs. github.com/character-ai/Ovi (07:36)
- **The cockpit you fly it from**:
  - **ComfyUI** = industry standard, node-based, official support for Wan/Hunyuan/LTX. Looks intimidating for ~1 hour, then power tools for life.
  - **Wan2GP** = the underrated pick, tagline is literally "AI video for the GPU poor." One app that runs Wan/Hunyuan/LTX/Flux from as low as 6GB VRAM, with finishing tools already wired in. **Installs in one click via Pinokio.** (07:58)
- **The finishing kit** (the part Topaz charges hundreds for):
  - **SeedVR2** — upscales video with temporal consistency, no flicker
  - **RIFE** — interpolates frames for smooth slow motion
  - **MMAudio** — generates a soundtrack for silent clips
  - All free and open. Post-production pipeline = zero dollars. (08:46)
- **No GPU? The free lanes**:
  - **Lane 1 — HF ZeroGPU Spaces**: live public spaces running Wan 2.2 and LTX on 48GB Blackwell cards. Free accounts get ~5 min GPU/day = 2-5 clips. "Test drive, not a studio."
  - **Lane 2 — Google Colab free T4**: 16GB VRAM, no published weekly quota, floats 15-30 hrs. Quantized 480p clip takes ~13 min. 12-hr session caps and idle disconnects wipe loaded models.
  - **Lane 3 — Kaggle (the sleeper)**: published **30 GPU hours/week, double Colab**. 12-hr sessions, two T4s at once (32GB combined). Requires phone verification, internet off by default.
  - **Lane 4 — Nearly free**: **Modal gives every account $30 of credits every single month, recurring, not a one-time trial.** At their rates that's ~50 hrs on a T4 or ~12 hrs on an 80GB A100. Code-first deployment, no notebook UI. (09:14)
- **The marketplaces**: RunPod and Vast rent a 3090-class card (24GB) for **17-19¢/hr**, 4090 from ~35¢/hr. One coffee covers an evening of renders on hardware that beats everything in the free lane. (11:18)
- **Two traps before you reach for the big clouds**: Google Cloud's famous $300 trial **cannot attach a GPU at all** — blocked until you upgrade to paid. Fresh AWS and Azure accounts start with a **GPU quota of zero** until you file a manual request. Those free-credit headlines are not lying. They are just not for video. (11:41)
- **When does renting still win? 3 cases**:
  - Need cinema-grade shots on a client deadline: Veo via API metered at 5-40¢/sec, pay for exactly the peak you need
  - Want to taste the state of the art: Kling hands out 66 free credits/day
  - Work depends on the same character staying consistent across many shots: Runway's tooling still ahead of the open stack (12:08)
- **The decision rule — one sentence**: **Own the pipeline. Rent the peak.** Your daily driver (drafts, social clips, B-roll, experiments) runs on weights you own at $0/clip. (12:39)
- **The hardware ladder**:
  - 6-8GB = quantized Wan and Ovi
  - 16GB = 14B builds comfortably
  - 24GB ($700 used 3090) = everything in the video except full LTX
  - **Unlike a subscription, a GPU holds resale value. Owning compounds. Renting evaporates.** Sora proved it can also just disappear. (12:54)
- **The hard truth**: 10+ years from now, will Sora's deleted videos matter to anyone? Yes — to the people who made them. **Sora's videos are gone forever. Yours never have to be.** (14:06)

## Notable Quotes

> "Months of creative work gone because the people who made it never owned any of it." (00:48)

> "Apache and MIT licenses mean free forever. Commercial use allowed. And nobody can revoke it after the fact. Once those weights are downloaded, no shutdown announcement, no price hike, no IPO cleanup can touch them." (03:00)

> "The articles claiming Wan 2.7 just went open source. SEO content farms. Alibaba never open-sourced anything past 2.2. The GitHub issues are full of people calling them out. Verify before you download." (04:48)

> "Runway's $12 plan sounds cheap until you read the credit math printed on their own pricing page. 625 credits buys 25 seconds of their best model per month. 25 seconds. That is three short clips with zero retries." (01:34)

> "Wan2GP, whose literal tagline is AI video for the GPU poor. One app that runs Wan/Hunyuan/LTX/Flux from as low as 6GB of VRAM with the finishing tools already wired in. And it installs in one click through Pinokio." (08:20)

> "Own the pipeline. Rent the peak. Your daily driver, the drafts, the social clips, the B-roll, the experiments runs on weights you own at $0 a clip." (12:42)

> "Sora's videos are gone forever. Yours never have to be." (14:08)

## Tools and Resources Mentioned

All 4 owned-stack models:
- **Wan 2.2** (Alibaba, Apache 2.0) — github.com/Wan-Video/Wan2.2
- **LTX-2.3** (Lightricks, 22B, community license w/ $10M/yr revenue cap) — huggingface.co/Lightricks/LTX-2.3
- **HunyuanVideo 1.5** (Tencent, 8.3B, community license **void in EU/UK/South Korea**, 100M user cap) — github.com/Tencent-Hunyuan/HunyuanVideo-1.5
- **Ovi** (Character AI + Yale, joint audio+video, ~6GB VRAM) — github.com/character-ai/Ovi

Cockpits:
- **ComfyUI** — github.com/comfyanonymous/ComfyUI
- **Wan2GP** — "AI video for the GPU poor," 6GB+ VRAM, one-click via Pinokio

Finishing kit (all free/open):
- **SeedVR2** — temporal-consistent upscale
- **RIFE** — frame interpolation for slow motion
- **MMAudio** — soundtrack generator for silent clips

Free / nearly-free cloud lanes:
- **HF ZeroGPU Spaces** — 48GB Blackwell, ~5min GPU/day free
- **Google Colab free T4** — 16GB, 15-30 hrs/week (variable)
- **Kaggle** — 30 GPU hrs/week, two T4s (32GB combined)
- **Modal** — $30 credits/month recurring
- **RunPod / Vast** — 24GB 3090 from 17-19¢/hr, 4090 from 35¢/hr

> **Vendor disambiguation:** Sora = OpenAI's video product (shut down 2026-04-26, not reopenable). The "Wan 2.7" articles referenced are SEO content farms — Alibaba only released 2.2 as open weights. Disney's $1B Sora partnership is historical. Veo = Google's video model (rent via API, not owned). Kling = Kuaishou's video model (rent via API, not owned). None of these are the user's stack.

**Free "Owned Stack" PDF** — every repo and model link, license table with revenue caps and region bands, VRAM ladder, free cloud quotas, real render times: comment "OWNED" on the video
**Predecessor videos in the series**: $0 AI Stack Parts 1-2, GitHub Repos Parts 1-2
**Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

## Action Items

- [ ] **Verify before downloading**: if you see "Wan 2.7" or any later version, check Alibaba's actual GitHub — newest open is 2.2
- [ ] **EU/UK/South Korea users**: HunyuanVideo 1.5 is not licensed for you. Use Wan 2.2 (Apache) or LTX-2.3 (community, ≤$10M/yr) instead
- [ ] **$10M+/yr company**: LTX-2.3 community license caps you out. Plan to pay Lightricks or stay on Apache models only
- [ ] **Hardware audit**:
  - 6-8GB = quantized Wan/Ovi via Wan2GP
  - 16GB = Wan 14B comfortably
  - 24GB ($700 used 3090) = everything except full LTX
  - Full LTX 2.3 = 18-20GB VRAM or rent
- [ ] **No GPU?** Try HF ZeroGPU Spaces first (free, fast start), then Kaggle (30 hrs/week, double Colab), then Modal ($30/mo recurring)
- [ ] **Avoid the trap**: Google Cloud $300 trial = no GPU attach; AWS/Azure new accounts = 0 GPU quota until manual request
- [ ] **Decision rule**: own the pipeline for daily work (drafts, social, B-roll, experiments at $0/clip), rent the peak (Veo API at 5-40¢/sec for cinema-grade client deadlines)
- [ ] **Backup your old Sora work now** if you have an export window still open — OpenAI is permanently deleting everything after
- [ ] **Use leftover Sora credits in Codex** if you have them, before they expire
- [ ] **Pre-mix your stack**: Wan 2.2 + Wan2GP + ComfyUI + SeedVR2 + RIFE + MMAudio is the complete ownership chain for $0/clip

## Open Questions

- Sora's exact permanent-deletion date (after which no exports) — WSJ implies it has passed; is the actual date documented anywhere?
- Does the "credit rollover to Codex" work for accounts that didn't have a Codex account before?
- LTX-2.3 at $10M/yr revenue cap — what does the tiered pricing look like above $10M? Is it percentage, flat fee, or per-output-minute?
- HunyuanVideo 1.5's "powered by Tencent credit line" — what format, where does it need to appear?
- The Wan 2.2 5B "<9 min for 5s 720p" number — at what quality setting, with which quant? (RTX 4090 + bf16 vs fp8 quantized)
- Does ComfyUI have a built-in "storyboard" mode yet, or is the workflow still single-clip-at-a-time?
- Wan2GP via Pinokio — is Pinokio still maintained in 2026, or has it been deprecated? (Cited as a 1-click install)
- HF ZeroGPU Spaces quotas — is the "5 min GPU/day" per model or total? (Free users likely have both a daily and a per-Space cap)
- Does Google's $300 trial "blocked until paid upgrade" affect ANY GPU SKU, or just specific families (H100, A100)?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 14:12 transcript)</summary>

0:00 April 26th,
0:01 2026.
0:03 OpenAI pulled the plug on Sora,
0:06 the most hyped video AI product on the
0:08 planet.
0:10 According to the Wall Street Journal, it
0:12 was burning about a million dollars a
0:14 day,
0:15 while active users collapsed below
0:17 500,000.
0:18 Disney had committed 1 billion dollars
0:22 to the partnership.
0:23 The Journal reports Disney found out
0:25 less than an hour before the rest of us.
0:28 And here is a detail nobody
0:30 screenshotted.
0:32 After the export window closes,
0:34 OpenAI permanently deletes everything
0:37 users ever made.
0:39 Leftover paid credits?
0:41 They still work, but only in Codex, a
0:44 coding tool. Months of creative work
0:47 gone
0:48 because the people who made it never
0:50 owned any of it.
0:52 So, this video is the other path,
0:55 a video generation stack you own. Free,
0:59 open weights sitting on your disk where
1:02 no boardroom decision can delete it.
1:05 I verified every model, every license,
1:08 every catch,
1:09 including a fake open-source download
1:12 that half the blogs are pushing right
1:14 now.
1:15 And if you do not own a GPU, stay with
1:18 me because there is a free cloud link,
1:20 too.
1:21 Let's build the stack they cannot shut
1:24 down.
1:24 First, look at what renting costs now
1:28 because it changed after Sora died.
1:30 Runway's $12 plan sounds cheap until you
1:34 read the credit math printed on their
1:36 own pricing page.
1:38 625 credits buys 25 seconds of their
1:42 best model per month.
1:44 25 seconds.
1:46 That is three short clips with zero
1:48 retries.
1:50 And on June 1st, Runway retired its
1:52 unlimited plan entirely.
1:54 New subscribers get credits, full stop.
1:58 Kling's top plan is $180 a month.
2:01 Up 41% since launch. And it is the
2:04 one tier with no annual discount.
2:07 Google's ultra tier, the one with
2:09 serious video volume,
2:11 is
2:12 $249.99
2:13 a month.
2:15 A realistic creator stack,
2:16 Runway Pro plus Kling Pro plus,
2:19 Google AI Pro,
2:21 lands around $92 a month.
2:24 Over $1,100 a year.
2:26 And notice what is happening underneath.
2:29 Runway and Luma now resell Veo and Kling
2:32 inside their own subscriptions.
2:35 The market is consolidating.
2:37 Fewer real options,
2:38 floating prices, and plans that vanish
2:42 mid-year.
2:42 That is renting.
2:44 Now, the ownership side.
2:46 Here is the rule this whole video runs
2:48 on.
2:49 A model is only yours
2:51 if the weights, the actual files,
2:53 sit on your disk under a license that
2:56 lets you use them.
2:58 Apache and MIT licenses
3:00 mean free forever.
3:03 Commercial use allowed.
3:05 And nobody can revoke it after the fact.
3:08 Once those weights are downloaded,
3:10 no shutdown announcement, no price hike,
3:13 no IPO cleanup can touch them.
3:17 Sora users
3:18 lost everything in a single quarter.
3:22 A model you downloaded last summer still
3:25 works exactly the same today.
3:27 And it will in 20 years.
3:29 But,
3:30 and this is where most videos mislead
3:33 you,
3:34 not everything called open is actually
3:37 open.
3:38 Some licenses carry revenue caps.
3:41 One is void across entire continents.
3:45 And some so-called open source models do
3:48 not exist as downloads at all.
3:50 So, for each model in this stack, I will
3:52 give you three things.
3:54 What it does, what hardware it needs,
3:56 and what the license really says.
3:59 No marketing, just the file and the fine
4:02 print.
4:03 Model one.
4:04 One 2.2 from Alibaba.
4:07 True Apache license, the gold standard.
4:10 Text to video and image to video at
4:13 720p.
4:15 Two sizes matter.
4:18 The 5B version officially generates a
4:20 5-second 720p clip in under 9 minutes on
4:23 an RTX 4090.
4:25 The 14B version is the quality pick and
4:28 quantized GGUF builds squeeze it into 8
4:31 to 10 GB of VRAM.
4:34 Slower,
4:35 but it runs on a gaming laptop.
4:37 Now, the trap I promised in the hook.
4:40 Alibaba's newer models, One 2.5,
4:44 2.6, and 2.7,
4:47 were never open-sourced.
4:50 They are API only.
4:52 Rent only.
4:54 But SEO content farms are publishing
4:56 articles right now,
4:57 claiming One 2.7 is an open download.
5:01 Go check Alibaba's actual GitHub.
5:04 The newest open repo is 2.2 from last
5:07 July.
5:08 The free download those blogs promise
5:11 does not exist.
5:12 The newest One you can own is 2.2.
5:15 And the good news is it is excellent.
5:18 Model two.
5:20 LTX 2.3
5:22 from Lightricks.
5:24 22 billion parameters released in March.
5:27 Already passed 2 million downloads.
5:30 This is the one that does what paid
5:33 tools charge extra for.
5:35 It generates the video and the
5:37 synchronized audio together in a single
5:39 pass.
5:41 Dialogue, lip sync, sound effects,
5:44 stereo.
5:45 It was the first production-ready open
5:47 model to pull that off.
5:49 And the full version goes up to 4K.
5:52 Now, the two catches.
5:55 Hardware first, the efficient FP8.
5:59 Built still wants around 18 to 20 GB of
6:01 VRAM.
6:03 This is a workstation model.
6:05 Or a rented GPU model.
6:08 It will not run on the free collab card.
6:12 And I will show you the cheap workaround
6:14 in a few minutes.
6:15 Second, the license.
6:17 It is a community license, not Apache.
6:20 Free for research and commercial use.
6:23 While your company makes under $10
6:24 million a year.
6:27 Above that, you pay Lightricks.
6:29 For basically everyone watching this,
6:32 that is effectively free.
6:34 But that is exactly the kind of fine
6:36 print this video exists to read out
6:39 loud.
6:40 Model three.
6:41 When you want video.
6:43 1.5 from Tencent.
6:46 8.3 billion parameters.
6:48 And pound for pound. The best quality.
6:52 Per gigabyte in open video. Right now.
6:56 It officially runs in 14 GB of VRAM.
6:59 With offloading.
7:00 And the FP8. Built pushes that near 12.
7:05 A 5-second clip.
7:07 Takes about 5 minutes on a 4090.
7:10 Those are verified user numbers.
7:12 Not marketing slides.
7:14 The catch is the license. And it is a
7:16 big one.
7:18 Tencent's community license literally
7:20 does not apply in the European Union.
7:23 The United Kingdom. Or South Korea.
7:26 If you are there, you are not licensed
7:28 to use it at all.
7:29 There is also a 100 million user cap.
7:32 And a required powered by Tencent credit
7:35 line.
7:36 One more name before we move on.
7:38 Ovi.
7:40 Open weights from character AI and Yale.
7:43 It generates audio and video jointly.
7:46 Like a miniature VO
7:48 and community builds, run it in about 6
7:50 GB.
7:52 Quality sits below LTX. But it is the
7:55 audio video option for small GPS.
7:58 That is the stack. Now the cockpit you
8:00 fly it from.
8:02 You do not need nine subscriptions to
8:03 run these models. You need one of two
8:07 free cockpits. Comfy UI is the industry
8:09 standard, node-based with official
8:12 support for 1, 1U1, and LTX.
8:16 It looks intimidating for about an hour,
8:18 and then it is power tools for life.
8:21 But the underrated pick is 1 2 GP, whose
8:24 literal tagline is AI video for the GPU
8:28 poor.
8:29 One app that runs 1, 1U1, LTX, and flux.
8:34 From as low as 6 GB of VRAM
8:38 with the finishing tools already wired
8:40 in.
8:41 And it installs in one click through
8:43 Pinocchio.
8:44 The finishing kit deserves its own line
8:47 because this is the part Topaz charges
8:49 hundreds of dollars for.
8:51 Seed VR 2 upscales video
8:54 with temporal consistency, so no
8:56 flicker.
8:57 RIFE interpolates frames for smooth slow
9:00 motion.
9:01 MM audio
9:03 generates a soundtrack
9:05 for silent clips.
9:07 Every one of them free and open.
9:09 Your entire post-production pipeline
9:11 zero dollars.
9:12 Now the part for everyone shouting at
9:15 the screen. I do not own a GPU.
9:18 No GPU.
9:20 Lane one.
9:21 The genuinely free clouds.
9:24 The fastest start is
9:26 hugging face zero GPU spaces.
9:30 There are live public spaces running
9:32 1 2.2
9:34 and LTX right now on 48 GB Blackwell
9:37 cards you would never buy.
9:40 Free accounts get about 5 minutes of GPU
9:43 time a day.
9:42 That is two to five clips. Then a
9:47 countdown timer.
9:49 Call it what it is, a test drive,
9:52 not a studio.
9:53 Lane two,
9:54 Google Colab's free T4.
9:58 16 GB of VRAM and no published weekly
10:01 quota.
10:02 It floats usually somewhere between 15
10:05 and 30 hours.
10:06 A quantized one clip at 480p takes about
10:09 13 minutes there and the community
10:10 notebooks are ready to go.
10:13 The catch, 12-hour session caps and idle
10:17 disconnects that wipe your loaded model.
10:19 Lane three is the sleeper.
10:21 Kaggle.
10:23 A published 30 GPU hours per week,
10:26 double what Colab usually gives you.
10:29 12-hour sessions
10:31 and you can attach two T4s at once.
10:34 32 GB combined.
10:36 It does require phone verification and
10:39 internet access is off by default.
10:42 The free tier truth,
10:43 slow, capped, occasionally annoying, and
10:47 completely real.
10:49 Lane four,
10:50 nearly free.
10:51 And this is where it gets practical.
10:54 Modal gives every account $30 of credits
10:58 every single month.
11:00 Recurring,
11:01 not a one-time trial.
11:03 At their published rates, that is
11:05 roughly 50 hours on a T4
11:07 or about 12 hours on an 80-gigabyte
11:09 A100, which runs the big models
11:12 properly.
11:13 The catch, it is code first.
11:16 You deploy Python scripts, there is no
11:18 notebook UI.
11:19 Then the marketplaces.
11:22 RunPod and Vast
11:23 rent a 3090 class card,
11:24 24 gigs,
11:27 for 17 to 19 cents an hour
11:30 and a 4090 from around 35 cents.
11:34 One coffee
11:35 covers an evening of renders on hardware
11:37 that beats everything in the free lane.
11:41 And two traps before you reach for the
11:43 big clouds.
11:44 Google Cloud's famous $300 trial cannot
11:48 attach a GPU at all.
11:51 It is blocked until you upgrade to paid.
11:54 And fresh AWS and Azure accounts start
11:58 with a GPU quota of zero
12:01 until you file a manual request.
12:04 Those free credit headlines are not
12:05 lying. They are just not for video.
12:08 The honest verdict.
12:10 When does renting still win?
12:13 Three cases.
12:14 If you need cinema grade shots on a
12:16 client deadline,
12:18 Leo through the API is metered at 5 to
12:40 cents a second. So, you pay for
12:22 exactly the peak you need and nothing
12:24 else.
12:25 If you just want to taste the state of
12:27 the art,
12:28 Cling hands out 66 free credits a day.
12:31 And if your work depends on the same
12:32 character staying consistent across many
12:34 shots,
12:36 Runway's tooling is still ahead of the
12:37 open stack.
12:39 The decision rule is one sentence.
12:42 Own the pipeline. Rent the peak.
12:45 Your daily driver, the drafts,
12:47 the social clips, the B-roll, the
12:50 experiments
12:51 runs on weights you own at $0 a clip.
12:55 The hardware ladder.
12:57 6 to 8 GB runs quantized 1 and OV.
13:01 16 runs the 14B builds comfortably. 24
13:05 and a used 3090 is around $700 once.
13:08 Runs everything in this video except
13:10 full LTX.
13:12 And unlike a subscription, a GPU holds
13:15 resale value. Owning compounds.
13:18 Renting evaporates. Sora proved it can
13:20 also just disappear.
13:22 Everything in this video is in one free
13:24 PDF, the owned stack.
13:27 Every repo and model link,
13:29 the license table with the revenue caps
13:32 and the region bands,
13:33 the VRAM ladder,
13:35 every free cloud quota, and the real
13:38 render times.
13:40 Comment the word owned,
13:42 and I will send it straight to you.
13:44 If killing your AI bill is the mission,
13:47 the two videos on screen right now,
13:50 the $0 AI stack,
13:52 and the GitHub repos that should cost
13:54 thousands, are the rest of this series.
13:57 Deep dives live here on YouTube, so
13:59 subscribe.
14:01 Bite-size drops are on Instagram
14:04 at hyperautomationlabs.
14:06 Sora's videos are gone forever.
14:09 Yours never have to be.

</details>
