---
title: "I Checked Every Free Tool Hiding in Your NVIDIA GPU — 9 Replace Paid Apps (and 2 Are Dead)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-13"
duration_seconds: 1079
video_id: "VjHG8peizpo"
url: "https://youtube.com/watch?v=VjHG8peizpo"
language: "en"
tags: [nvidia, rtx, free-tools, broadcast, shadowplay, smooth-motion, g-assist, dead-software, chat-rtx, omniverse-launcher, nvidia-canvas]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# I Checked Every Free Tool Hiding in Your NVIDIA GPU — 9 Replace Paid Apps (and 2 Are Dead)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-13  **Duration:** 17:59  **Watch:** https://youtube.com/watch?v=VjHG8peizpo

> **Source note:** Every tool verified against NVIDIA's own pages the week of 2026-06-08. Two famous "free" names (ChatRTX, Omniverse Launcher) confirmed dead and called out by name. One (Canvas) flagged as a zombie (downloadable but frozen since 2023-10). All gate info is the channel's own runtime test, not a press release.

## TL;DR

9 free NVIDIA tools hiding in your RTX card that replace paid apps, plus a public funeral for 2 names articles still push and 1 zombie nobody talks about. The rent stack: Krisp $96/yr, VCam $48/yr, Bandicam $37/yr, Adobe Podcast ~$100/yr, Topaz Video AI $299/yr (perpetual killed fall 2025). The 9 keepers: NVIDIA Broadcast (kills Krisp + VCam + Adobe Studio Voice, RTX 2060+, v2.2 took Studio Voice out of beta in June 2026), ShadowPlay / NVIDIA App (8K30 / 4K HDR 120 recording, near-zero perf hit, login optional), RTX Video Super Resolution (watch-only, the catch NOBODY SAYS), Project G-Assist (local SLM in the NVIDIA App, 6GB VRAM), Smooth Motion (driver-level frame gen, RTX 40/50 only), plus RTX Remix, Studio Drivers, ICAT, FrameView. The graveyard: **ChatRTX deprecated 2026-01-21** (locked forum, archived GitHub), **Omniverse Launcher deprecated 2025-10** (dev kit only now), **Canvas = zombie, untouched since 2023-10, delisted from Studio Hub**. The hard catches: RTX Video Super Resolution is watch-only with no export (Restorers keep Topaz); typing artifacts in Broadcast on heavy keystrokes; Eye Contact filter "unblinking stare"; Smooth Motion = input lag doesn't drop, HUDs can smear. Strict savings ≈ $180/yr; loose math with partial replacements up to $580/yr.

## Key Insights

- **The premise**: if you bought an NVIDIA RTX card in the last few years, you also bought a software bundle nobody told you about. Real tools, not trials. A noise canceller people pay $96/yr for. A 4K recorder people pay $40 for. A video upscaler people now rent for $299/yr. All sitting inside the card you already own, switched off. (00:00)
- **The blog-list rot problem**: blog lists recommending these tools are full of corpses. NVIDIA quietly killed two of its most famous freebies. Articles ranking in search are still pushing them this week. The channel checked everything against NVIDIA's own pages in June 2026. 9 tools made the cut. 2 are dead. 1 is a zombie. (00:35)
- **The rent stack (June 2026, official pricing pages)**:
  - Krisp Core $96/yr (or $16/mo monthly)
  - VCam $48/yr (virtual backgrounds no green screen)
  - Bandicam $37/yr
  - Adobe Podcast ~$100/yr
  - **Topaz Video AI — perpetual licenses killed fall 2025; now $299 EVERY YEAR**
  - Stack: $180-$580/yr depending on how many you rent (01:28)
- **The one rule**: everything in this video is free because of the silicon you already bought. NVIDIA ships these tools to sell more GPUs. **Your RTX card is the subscription. You just paid it once up front. And unlike a subscription, it holds resale value.** (02:58)
- **Gate 1 — Windows only**: every consumer tool on this list is Windows-only. If you're on a Mac, this video is not for you. The channel says this at minute 3 to save your evening. (03:24)
- **Gate 2 — generations**: most tools run on any RTX card 20-series or newer. A few want 3060+. Exactly one big feature is locked to 40/50 series (will be flagged). VRAM will be called out where it matters. **Filter: only tools that NVIDIA's own pages confirm are alive and updated as of this month.** (03:40)
- **Tool 1 — NVIDIA Broadcast** (the biggest subscription killer):
  - Cancels mic noise + speaker noise + room echo in real time unlimited = **Krisp $96/yr gone**
  - Removes/replaces webcam background no green screen = **VCam $48/yr gone**
  - **v2.2 (June 2026) took Studio Voice out of beta** — cheap mic sounds studio grade live, not in post = **Adobe Podcast $100/yr gone**
  - Requirements: any RTX 2060+. Studio Voice and the new virtual key light want RTX 3060 desktop+
  - **Catches out loud**: heavy typing can make your voice sound briefly "underwater" (Krisp has the same weakness); on a laptop running it on GPU costs real battery (treat as a desk tool); **Eye Contact filter "terrifying" — works right up until it becomes an unblinking stare**. Try it, but watch a recording of yourself before trusting it on a client call. (04:21)
- **Tool 2 — NVIDIA App / ShadowPlay** (the recorder):
  - Manual recording up to **8K30 or 4K HDR 120**
  - Instant Replay (always recording, one hotkey saves last 30s)
  - Runs on the dedicated encoder chip on your card, performance hit close to nothing
  - Unlike old GeForce Experience, **login is optional now**
  - **Catches**: hard bitrate ceiling ~130 Mbps (real cap lower at 1080p), max-quality archival recording still belongs to OBS; no scenes, no overlays, no plugins — streamers still want OBS (same NVENC chip, OBS uses the same encoder); doesn't replace Camtasia's editing half
  - For gameplay, tutorials, and clean capture, flip it on tonight (06:01)
- **Tool 3 — RTX Video Super Resolution + HDR** (the one where every other video hides the catch):
  - Flip one switch, your card upscales and deblocks every video you watch in Chrome/Edge/Firefox/VLC
  - Sibling: **RTX Video HDR** converts standard video to HDR10 on an HDR display
  - People compare to Topaz (the upscaler now $299/yr)
  - **The catch. Read slowly.** **Super Resolution is watch-only. There is no export button.** It enhances pixels on their way to your screen. It cannot save a single upscaled frame to disk. The only way to export with this technology is inside paid editors that license NVIDIA's SDK, like DaVinci Resolve Studio.
  - **So: if you restore footage for clients, keep Topaz. You still need it.** If like most people you mostly watch video at your desk, you just stopped needing the subscription you were about to buy. **That distinction is the difference between an honest recommendation and a thumbnail.** (07:29)
- **The funeral — 2 dead tools, 1 zombie** (the part listicles won't tell you):
  - **Grave 1: ChatRTX** — NVIDIA's local chatbot that reads your own files. Articles still recommending it this month. **Dead. NVIDIA deprecated 2026-01-21, archived the code on GitHub, locked the forum.** Posted on NVIDIA's own developer forum. (09:01)
  - **Grave 2: Omniverse Launcher** — the consumer doorway into NVIDIA's 3D platform. **Deprecated 2025-10.** Omniverse itself lives on, but as a developer kit on GitHub, not a free app you click and install. (09:30)
  - **The zombie: NVIDIA Canvas** — the famous app that turns doodles into landscapes. The download still works today (the channel checked the actual installer). **But that file has not been touched since October 2023.** Canvas is quietly delisted from NVIDIA's own Studio Hub. Fun to play with. Just don't build anything on abandonware. (09:46)
  - **Why this matters beyond trivia**: every name in this graveyard is still sitting in search results. In lists that never say when they were verified. **If a list does not tell you its date, it is recycling 2024.** (10:13)
- **Tool 4 — Project G-Assist** (what replaced ChatRTX):
  - The most underrated thing NVIDIA ships right now. A small language model that runs entirely on your card, inside the NVIDIA App.
  - Press Alt+G. Ask it to optimize a game's settings, chart FPS/temps/latency, tune fan curves, or just explain what a setting actually does
  - Nothing goes to the cloud. No subscription. No account.
  - **Last summer NVIDIA cut its memory requirement in half** — now runs on any RTX with **6GB VRAM+**
  - Voice commands need RTX 30+
  - Plugin hub on mod.io — Spotify control, Discord, Stream Deck integration
  - **Honest framing**: doesn't kill a specific subscription. What it replaces is the hour of forum digging every GPU owner eventually does. And it's the clearest sign of where this is all going: **free AI living inside the driver**. If you tried it at launch and it felt heavy, that old 12GB requirement is gone. Try it again. (10:35)
- **Tool 5 — NVIDIA Smooth Motion** (the gaming one, strictest gate):
  - Driver-level frame generation. One toggle, your card inserts AI-generated frames into almost any DX11/12/Vulkan game, **including games that never added DLSS support**
  - Benchmarks show it close to doubling perceived frame rate
  - Gamers pay $7 on Steam for Lossless Scaling to do this
  - **The gate, loudly**: **RTX 40 and 50 series only**. Launched on 50s, reached 40s in 2025-08. If you're on 20 or 30, Lossless Scaling remains the $7 answer
  - **Catches**: generated frames do not reduce input lag (clicks still land on real frames — keep away from competitive shooters); driver can't see the game's interface separately, fast-moving HUD elements can smear
  - Where it shines: single-player, controller games, capped frame rates
  - DLSS 4's upgraded super resolution works on every RTX back to 20-series, and the app can force the new model per game (11:55)
- **Tools 6-9 — four quick ones to round out** (all verified alive):
  - **RTX Remix** — free open-source platform that remasters classic games with path-traced lighting, mod tools included
  - **Studio Drivers** — same download page you already use. Stability-tested branch of the driver built for Premiere, Resolve, Blender. Most creator crash fixes are one drop-down away, costs nothing
  - **ICAT** — NVIDIA's image and video comparison tool. Drag two clips in, wipe a slider between them, fastest way to see whether a setting actually matters
  - **FrameView** — benchmarking overlay that logs frame rate and power draw. **Works on AMD and Intel cards too** (13:40)
- **The footnote for non-NVIDIA users**:
  - **Team Red (AMD)**: FSR 4 upscaling is free and excellent; v4.1 reaches RX 7000 cards the month after recording. Adrenalin drivers include a free noise suppression feature
  - **Team Blue (Intel)**: XeSS frame generation now runs on other vendors' GPUs too, including older RTX cards — a genuine gift to 30-series owners (14:21)
  - **The real point of this video is not that NVIDIA is generous. It is that the software you already paid for, whoever made your card, is probably switched off.** (14:56)
- **Bonus — no GPU required**: build.nvidia.com gives free API access to 100+ hosted models (Llama, Nemotron, DeepSeek, Qwen) on an OpenAI-compatible endpoint. **No credit card, no expiry, rate-limited to ~40 req/min.** Older articles mention free credits that run out — that system is gone. NVIDIA staff confirmed it's pure rate limits now. License is for prototyping, not production. Treat as a free lab, not a free bill cut. (15:18)
- **The verdict**:
  - **Strict math (full replacements only)**: Broadcast kills Krisp + VCam. ShadowPlay kills Bandicam. ≈ $180/yr
  - **Loose math (if partial replacements fit)**: watch-only upscaling instead of Topaz, Studio Voice instead of Adobe Enhancer → near $580/yr (15:55)
  - **The one sentence that survives fact-checking**: if you own an RTX card and currently pay for any of these 5 jobs — noise removal, backgrounds, recording, upscaling for watching, or frame generation — **you are paying twice**. Flip the switches first. Keep a subscription only where the catch the channel read you actually bites. (16:38)
  - **Your card came with the software. Tonight, you switch it on.** (17:55)

## Notable Quotes

> "The blog lists recommending these tools are full of corpses. NVIDIA quietly killed two of its most famous freebies. And articles ranking in search are still pushing them this week." (00:35)

> "Your RTX card is the subscription. You just paid it once up front. And unlike a subscription, it holds resale value." (03:14)

> "The famous eye contact filter, the one that makes you look at the camera. Reviewers literally called it terrifying. It works right up until it becomes an unblinking stare." (05:46)

> "Super resolution is watch only. There is no export button. It enhances pixels on their way to your screen. And it cannot save a single upscaled frame to disk. So, if you restore footage for clients, keep Topaz. You still need it. But if like most people, you mostly watch video at your desk, you just stopped needing the subscription you were about to buy. That distinction is the difference between an honest recommendation and a thumbnail." (08:14)

> "Fun to play with. Just do not build anything on abandonware." (10:11)

> "The real point of this video is not that NVIDIA is generous. It is that the software you already paid for, whoever made your card, is probably switched off." (14:56)

> "If a list does not tell you its date, it is recycling 2024." (10:24)

> "If you own an RTX card and currently pay for any of these five jobs, you are paying twice. Flip the switches first. Keep a subscription only where the catch I read you actually bites." (16:44)

## Tools and Resources Mentioned

The 9 keepers (all NVIDIA, all free, all Windows unless noted):
- **NVIDIA Broadcast** — v2.2 June 2026, kills Krisp + VCam + Adobe Studio Voice, RTX 2060+ (Studio Voice / virtual key light need 3060 desktop+)
- **NVIDIA App / ShadowPlay** — 8K30 / 4K HDR 120, Instant Replay, RTX 20+
- **RTX Video Super Resolution + HDR** — watch-only upscale/HDR conversion, RTX 20+
- **Project G-Assist** — local SLM inside NVIDIA App, Alt+G, 6GB VRAM (Aug 2025 cut), voice needs 30+
- **NVIDIA Smooth Motion** — driver-level frame gen, RTX 40/50 only (Lossless Scaling $7 for 20/30)
- **RTX Remix** — open-source game remastering w/ path-traced lighting
- **NVIDIA Studio Drivers** — stability-tested branch for Premiere/Resolve/Blender
- **ICAT** — image/video comparison tool with wipe slider
- **FrameView** — benchmarking overlay (works on AMD/Intel too)

The dead / zombie list (verified June 2026):
- **ChatRTX** — DEPRECATED 2026-01-21, GitHub archived, forum locked
- **Omniverse Launcher** — DEPRECATED 2025-10, dev kit only now
- **NVIDIA Canvas** — ZOMBIE, untouched since 2023-10, delisted from Studio Hub

Bonus:
- **build.nvidia.com** — free API to 100+ models (Llama, Nemotron, DeepSeek, Qwen), ~40 req/min, no card, no expiry (prototype license only)
- **AMD FSR 4** (Team Red alternative) — free, RX 7000+ from July 2026
- **AMD Adrenalin** — free noise suppression
- **Intel XeSS frame gen** — now runs on AMD/Intel/older RTX
- **Lossless Scaling** (Steam, $7) — frame gen for non-RTX-40/50 users

> **Vendor disambiguation:** Topaz = Topaz Labs (Topaz Video AI, the paid upscaler the channel compares to). Lossless Scaling = the $7 Steam app for non-40/50-series users. AMD/Intel GPU alternatives are listed but the video is Windows-NVIDIA-focused.

**Free "RTX Vault" PDF** — every tool, exact requirements, generation gates, VRAM lines, every catch read out loud, the graveyard list, strict vs loose savings math: comment "RTX" on the video
**Predecessor videos in the series**: $0 AI Stack Parts 1-2, GitHub Repos Parts 1-2
**Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

## Action Items

- [ ] **Windows + RTX 20+ users**: install NVIDIA Broadcast v2.2 first (kills $144/yr of Krisp+VCam subscriptions)
- [ ] **Mac users**: skip this list entirely, watch the AMD/Intel footnote section only
- [ ] **Content creators**: flip on ShadowPlay Instant Replay, replace Bandicam
- [ ] **Watchers (not editors)**: turn on RTX Video Super Resolution in Chrome/Edge/Firefox/VLC — kills the Topaz subscription if you only watch
- [ ] **Video editors / restorers**: KEEP Topaz — RTX Video Super Resolution has no export button
- [ ] **Gamers on 40/50 series**: enable Smooth Motion in NVIDIA App for ~2× perceived FPS (avoid competitive shooters — input lag doesn't drop)
- [ ] **Gamers on 20/30 series**: buy Lossless Scaling on Steam ($7) — your only free-ish path to frame gen
- [ ] **Curious tinkerers**: try Project G-Assist (Alt+G in NVIDIA App) — 6GB VRAM is enough since 2025-08, voice needs 30+
- [ ] **Stop recommending ChatRTX and Omniverse Launcher in 2026 articles** — both are deprecated
- [ ] **Don't build on NVIDIA Canvas** — frozen since 2023-10, delisted
- [ ] **Bookmark dates on every "free NVIDIA tool" article you read** — if there's no date, it's recycling 2024
- [ ] **No GPU at all?** Use build.nvidia.com (free API, 100+ models, ~40 req/min, prototype license)
- [ ] **AMD users**: try FSR 4 + Adrenalin noise suppression
- [ ] **Intel users**: XeSS frame gen now works on older RTX cards too (gift to 30-series owners)

## Open Questions

- For NVIDIA Broadcast typing "underwater" artifacts — is there a setting/threshold to disable the typing-detection, or does it just get confused by any non-speech audio?
- For Eye Contact filter "unblinking stare" — does it have a smoothing/relaxation option, or is it binary on/off?
- For ShadowPlay's "~130 Mbps ceiling" — at what resolution? Is it 4K only, or applies at 1080p too?
- For G-Assist plugins (Spotify, Discord, Stream Deck) — are these official NVIDIA plugins or community? What happens to them when NVIDIA's plugin hub changes?
- For RTX Video Super Resolution — is there any way to capture the upscaled output short of screen-recording (which would defeat the purpose)?
- For Smooth Motion's HUD smearing — does the driver have a per-game whitelist, or is it true "any DX11/12/Vulkan"?
- For build.nvidia.com — what does "prototype license, not production" mean in practice? Per-user cap? Per-output license key? Branding requirement?
- For the dead tools: what was the actual reason for ChatRTX deprecation? Was it replaced by G-Assist + NIM, or simply abandoned?
- For the zombie Canvas: any open-source fork that picked up maintenance?
- The $299/yr Topaz pricing — is the perpetual grandfather clause for existing customers honored, or did they force-migrate everyone?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 17:59 transcript)</summary>

0:00 If you bought an Nvidia RTX card anytime
0:03 in the last few years
0:05 you also bought a software bundle
0:08 nobody told you about.
0:09 Real tools, not trials.
0:11 The kind people rent every month.
0:14 A noise canceller people pay $96 a year
0:17 for.
0:19 A 4K recorder people pay $40
0:22 a video upscaler people now rent for
0:24 $299 a year.
0:27 All sitting inside the card you already
0:29 own. Switched off.
0:31 And here is the twist that made me build
0:33 this video.
0:35 The blog lists recommending these tools
0:37 are full of copses.
0:39 Nvidia
0:41 quietly killed two of its most famous
0:43 freebies.
0:44 And articles ranking in search are still
0:46 pushing them this week. So I checked
0:49 everything against Nvidia's own pages.
0:52 This week, June 2026.
0:55 What is alive? What it replaces. What it
0:57 really requires.
0:59 And the fine print nobody reads out
1:01 loud. Nine tools made the cut.
1:04 Two are dead. And one is a zombie.
1:08 Still downloadable.
1:10 Frozen for almost 3 years.
1:12 By the end, you will know exactly which
1:15 switches to flip tonight.
1:16 And which famous names to skip.
1:19 And if your card is team red or team
1:21 blue instead, stay to the end because
1:24 there is a footnote for you, too.
1:26 Let's price the rental side first.
1:28 Because these numbers changed recently.
1:30 Krisp the noise cancelling app, their
1:33 core plan runs $96 a year billed
1:37 annually.
1:38 $16 a month if you pay monthly.
1:42 VCam
1:43 virtual backgrounds
1:45 without a green screen.
1:47 $48 a year.
1:50 Bandicam
1:51 the screen recorder
1:53 $37 a year.
1:56 Adobe's Podcast voice enhancer
1:58 About a hundred a year.
2:00 And the big one.
2:02 Topaz.
2:03 The famous AI video upscaler.
2:06 Used to be a one-time purchase.
2:09 Last fall, they killed perpetual
2:11 licenses.
2:13 It is now $299
2:15 every single year.
2:17 Stack those and you are somewhere
2:19 between 180 and 580 dollars a year.
2:23 Depending on how many you rent.
2:25 Now, I am going to be straight with you.
2:27 The way thumbnails on this topic usually
2:30 are not.
2:31 The free tools in your GPU
2:33 do not replace all of that perfectly.
2:36 One of them has a catch so big that most
2:38 videos hide it completely.
2:40 I will read every catch out loud.
2:43 But the strict defensible math
2:46 still lands around 180 dollars a year of
2:48 full replacements.
2:50 And up to 580
2:52 if the partial ones cover your use case.
2:55 That is the price.
2:57 Here is the rule.
2:58 One rule and two gates before the list.
3:02 The rule.
3:03 Everything in this video is free
3:05 because of the silicon you already
3:07 bought.
3:08 Nvidia ships these tools to sell more
3:11 GPUs.
3:13 Which means
3:14 your RTX card is the subscription.
3:18 You just paid it once up front. And
3:20 unlike a subscription, it holds resale
3:23 value.
3:24 Gate one, Windows.
3:27 Every consumer tool on this list is
3:29 Windows-only.
3:31 If you are on a Mac, this video is not
3:33 for you.
3:34 And I would rather tell you
3:36 that in minute three than waste your
3:38 evening.
3:39 Gate two,
3:40 generations.
3:42 Most of these run on any RTX card.
3:45 20 series or newer.
3:47 A few want a 3060 or better.
3:50 Exactly one big feature is locked to the
3:53 40 and 50 series,
3:55 and I will flag it loudly when we get
3:57 there.
3:58 I will also call out VRAM where it
4:00 matters.
4:02 And the filter
4:04 I only kept tools that Nvidia's own
4:06 pages
4:07 confirm are alive
4:10 and updated as of this month.
4:13 Two famous names failed that filter.
4:16 And they get their own funeral in the
4:18 middle of this video.
4:20 Tool number one
4:21 is the one that kills the most
4:24 subscriptions.
4:25 Nvidia Broadcast
4:27 one app, and it is the single biggest
4:30 subscription killer on this list.
4:32 It cancels your mic noise, your speaker
4:35 noise, and your room echo in real time
4:39 unlimited
4:40 which is exactly what Krisp charges $96
4:44 a year for.
4:45 It removes or replaces your webcam
4:46 background with no green screen
4:51 which is what VCam charges
4:52 $48 a year for.
4:55 And version 2.2
4:57 which shipped this month took Studio
5:00 Voice out of beta.
5:02 That filter makes a cheap mic sound
5:04 studio grade
5:05 the job Adobe charges about a hundred a
5:08 year for
5:09 except Broadcast does it live, not in
5:12 post.
5:13 Requirements
5:14 any RTX card from the 2060 up.
5:18 Studio Voice and the new virtual key
5:21 light want a 3060 desktop card or
5:25 better.
5:26 Now, the catches out loud.
5:29 In independent tests, heavy typing can
5:31 make your voice sound briefly
5:33 underwater, and Krisp has the same
5:35 weakness.
5:37 On a laptop
5:38 running it on the GPU costs real
5:40 battery, so treat it as a desk tool. And
5:43 the famous eye contact filter, the one
5:46 that makes you look at the camera.
5:48 Reviewers literally called it
5:49 terrifying. It works
5:52 right up until it becomes an unblinking
5:54 stare.
5:55 Try it, but watch a recording of
5:57 yourself before you trust it on a client
6:00 call.
6:01 Tool two,
6:02 the recorder.
6:03 The Nvidia app, the one that replaced
6:06 GeForce Experience,
6:08 ships with ShadowPlay built in.
6:11 Manual recording up to 8K at 30 frames
6:15 or 4K HDR at 120.
6:20 And instant replay,
6:22 which is always quietly recording.
6:24 So, you press one hotkey
6:26 and the last 30 seconds are saved.
6:28 The clip you could never recreate
6:31 captured after it happened.
6:33 Because it runs on the dedicated encoder
6:35 chip on your card,
6:37 the performance hit is close to nothing.
6:40 That is Bandicam's $37 a year gone.
6:44 And unlike the old GeForce Experience,
6:47 login is optional now. The catch is
6:50 there is a hard bitrate ceiling around
6:52 130 megabits
6:54 and users report the real cap sits lower
6:57 at 1080p. So, maximum quality
6:59 archival recording still belongs to OBS.
7:02 No scenes, no overlays, no plugins,
7:05 so streamers still want OBS, too.
7:08 And to be fair, OBS uses the very same
7:11 encoder chip on your card.
7:13 One more honesty line.
7:15 If you were eyeing Camtasia, ShadowPlay
7:17 replaces the recording half, not the
7:19 editing half. So, I am not counting that
7:21 money.
7:23 For gameplay, tutorials, and clean
7:24 capture, flip it on tonight.
7:27 Tool three,
7:29 and this is the one where every other
7:30 video hides the catch.
7:33 RTX video super resolution.
7:37 Flip one switch
7:39 and your card
7:40 upscales
7:41 and deblocks
7:43 every video you watch in Chrome, Edge,
7:46 Firefox, or VLC.
7:49 Old 720p uploads, compressed conference
7:52 streams, blocky sports feeds, cleaned up
7:55 toward 4K in real time.
7:58 Its sibling, RTX video HDR,
8:02 converts standard video
8:03 to HDR 10 on an HDR display.
8:07 People compare this to Topaz,
8:09 the upscaler that now costs $299 a year.
8:14 So, here is the catch.
8:16 Read slowly.
8:18 Super resolution is watch only.
8:21 There is no export button.
8:23 It enhances pixels on their way to your
8:25 screen.
8:27 And it cannot save a single upscaled
8:28 frame to disk.
8:30 The only way to export with this
8:32 technology
8:33 is inside paid editors that license
8:35 Nvidia's SDK, like DaVinci Resolve
8:38 Studio.
8:39 So, if you restore footage for clients,
8:41 keep Topaz. You still need it.
8:44 But if like most people, you mostly
8:46 watch video at your desk,
8:48 you just stopped needing the
8:49 subscription you were about to buy.
8:51 That distinction is the difference
8:53 between an honest recommendation and a
8:56 thumbnail.
8:57 Works on any RTX card, 20 series and up.
9:00 Now, the funeral.
9:02 Because this is the part the listicles
9:04 will not tell you.
9:05 Grave one.
9:07 Chat RTX.
9:09 Nvidia's local chatbot that reads your
9:11 own files.
9:13 Articles are still recommending it this
9:14 month.
9:15 It is dead.
9:17 Nvidia deprecated it on January 21st
9:19 this year,
9:20 archived the code on GitHub, and locked
9:23 the forum.
9:24 That is not a rumor.
9:26 It is posted on Nvidia's own developer
9:27 forum.
9:29 Grave two.
9:30 The Omniverse launcher, the consumer
9:32 doorway into Nvidia's 3D platform.
9:36 Deprecated it last October.
9:39 Omniverse itself lives on.
9:41 But as a developer kit on GitHub. Not a
9:44 free app you click and install.
9:46 And then the zombie.
9:48 Nvidia canvas. The famous app that turns
9:51 doodles into landscapes.
9:53 The download still works today. I
9:55 checked the actual installer.
9:57 But that file has not been touched since
10:00 October 2023.
10:02 And canvas is quietly delisted. From
10:05 Nvidia's own studio hub.
10:07 Fun to play with.
10:09 Just do not build anything on
10:11 abandonware.
10:13 Here is why this matters beyond trivia.
10:16 Every name in this graveyard is still
10:18 sitting in search results.
10:20 In lists that never say when they were
10:22 verified.
10:23 If a list does not tell you its date.
10:26 It is recycling 2024.
10:29 Everything still ahead of us passed the
10:31 check this week.
10:32 So what replaced chat RTX?
10:36 Tool four.
10:38 Project G assist.
10:40 The most underrated thing Nvidia ships
10:41 right now.
10:44 It is a small language model.
10:46 That runs entirely on your card.
10:49 Inside the Nvidia app.
10:52 Press all G. And you can ask it to
10:55 optimize a game's settings.
10:57 Chart your frame rate, your
10:59 temperatures, your latency.
11:02 Tune your fan curves. Or. Just explain
11:05 what a setting actually does.
11:08 Nothing goes to the cloud.
11:10 No subscription. No account.
11:13 And last summer. Nvidia cut its memory
11:15 requirement in half.
11:18 So it now runs on any RTX card with 6 GB
11:21 of VRAM or more.
11:23 Voice commands need a 30 series card or
11:26 newer.
11:27 There is even a plug-in hub.
11:29 And G assist installs plugins for you.
11:32 when you ask in plain English.
11:34 Spotify control, Discord, Stream Deck
11:36 integration.
11:37 The honest framing.
11:39 This one does not kill a specific
11:42 subscription.
11:43 What it replaces is the hour of forum
11:46 digging every GPU owner eventually does.
11:50 And it is the clearest sign of where
11:51 this is all going.
11:52 Free AI living inside the driver.
11:56 If you tried it at launch and it felt
11:58 heavy,
11:59 that old 12 GB requirement is gone.
12:02 Try it again.
12:03 Tool five, the gaming one.
12:06 And it carries the strictest hardware
12:08 gate on the list.
12:10 Nvidia
12:11 smooth motion.
12:13 Driver level frame generation.
12:15 One toggle in the Nvidia app and your
12:18 card inserts AI-generated frames into
12:22 almost any DirectX 11,
12:25 DirectX 12, or Vulcan game,
12:27 including games that never added DLSS
12:30 support.
12:32 Benchmarks show it close to doubling
12:34 perceived frame rate.
12:36 Gamers pay $7 on Steam for an app called
12:39 lossless scaling to do this.
12:42 Your driver now does it free.
12:44 The gate, loudly.
12:46 40 and 50 series cards only.
12:49 It launched on the 50s and reached the
12:52 40s last August.
12:54 If you are on a 20 or 30 series card,
12:57 lossless scaling remains the $7 answer.
13:00 And it is genuinely good.
13:02 The catches.
13:04 Generated frames do not reduce input
13:06 lag.
13:07 Your clicks still land on real frames.
13:10 So, keep it away from competitive
13:11 shooters.
13:13 And because the driver cannot see the
13:14 game's interface separately,
13:17 fast-moving HUD elements can smear.
13:20 Single-player games, controller games,
13:13 capped frame rates, that is where it
13:25 shines.
13:26 And while you are in there,
13:28 DLSS 4's upgraded super resolution model
13:31 works on every RTX generation
13:34 back to the 20 series.
13:36 And the app can force the new model per
13:38 game.
13:39 Four quick ones to round out the stack,
13:41 all verified alive.
13:43 RTX Remix, a free open-source platform
13:46 that remasters classic games with
13:49 path-traced lighting, mod tools
13:51 included.
13:52 Studio drivers, same download page you
13:55 already use.
13:57 A stability-tested branch of the driver
13:59 built for Premiere,
14:01 Resolve, and Blender.
14:03 Most creator crash fixes are one
14:06 drop-down away, and it costs nothing.
14:09 ICAT, Nvidia's image and video
14:12 comparison tool.
14:14 Drag two clips in, wipe a slider between
14:16 them, the fastest way to actually see
14:19 whether a setting matters.
14:21 And FrameView,
14:23 a benchmarking overlay that logs frame
14:25 rate and power draw.
14:28 And it works on AMD and Intel cards,
14:30 too.
14:31 Which brings me to the footnote I
14:33 promised.
14:34 Team Red,
14:35 AMD's FSR 4 upscaling
14:37 is free and excellent, and version 4.1
14:41 reaches RX 7000 cards next month.
14:44 The Adrenalin drivers also include a
14:47 free noise suppression feature.
14:49 Team Blue, Intel's XeSS frame generation
14:53 now runs on other vendors' GPUs, too,
14:56 including older RTX cards, which is a
15:00 genuine gift to 30 series owners.
15:03 Because the real point of this video is
15:05 not that Nvidia is generous.
15:08 It is
15:09 that the software you already paid for,
15:11 whoever made your card, is probably
15:14 switched off.
15:15 One bonus that needs no GPU at all, then
15:19 the honest math.
15:20 Nvidia's API catalog at build.nvidia.com
15:26 gives you free API access to over 100
15:30 hosted models. Llama, Nemotron,
15:34 DeepSeek, Quinn,
15:36 all on an OpenAI compatible endpoint.
15:39 No credit card,
15:41 no expiry,
15:42 rate limited to roughly 40 requests a
15:44 minute.
15:46 Older articles mention free credits that
15:47 run out.
15:49 That system is gone.
15:50 Nvidia staff confirmed it is pure rate
15:53 limits now.
15:55 The license is for prototyping, not
15:57 production.
15:58 So, treat it as a free lab for building
16:01 and testing agents,
16:02 not a free bill cut.
16:05 Now, the verdict.
16:07 Strict math, full replacements only.
16:10 Broadcast kills Krisp
16:12 and VCam.
16:14 ShadowPlay kills Bandicam.
16:17 That is about $180 a year.
16:20 Real and defensible.
16:22 Loose math, if the partial replacements
16:24 fit your use case,
16:26 watch only upscaling instead of Topaz,
16:29 Studio Voice instead of Adobe's
16:30 Enhancer,
16:33 and you are near 580 a year.
16:37 And here is the one sentence that
16:39 survives fact-checking.
16:41 If you own an RTX card and currently pay
16:45 for any of these five jobs,
16:47 noise removal, backgrounds, recording,
16:50 upscaling for watching, or frame
16:53 generation, you are paying twice.
16:56 Flip the switches first.
16:58 Keep a subscription only where the catch
17:01 I read you actually bites.
17:03 Everything verified in this video is in
17:06 one free PDF, the RTX Vault.
17:09 Every tool with its exact requirements,
17:12 the generation gates, the VRAM lines,
17:16 every catch read out loud.
17:18 The graveyard list.
17:19 So, you stop clicking dead links.
17:21 And the strict versus loose savings
17:24 math.
17:25 Comment the word RTX.
17:28 And I will send it straight to you.
17:30 If killing your software bills is the
17:32 mission,
17:33 the two videos on screen right now are
17:36 the rest of this series.
17:38 The free AI video stack.
17:40 And the GitHub repos that should cost
17:43 thousands.
17:45 Deep dives live here on YouTube. So,
17:47 subscribe.
17:49 Bite-size drops are on Instagram at
17:52 hyper automation labs.
17:54 Your card came with the software.
17:57 Tonight, you switch it on.

</details>
