---
title: "10 More GitHub Repos So Good They Shouldn't Be Free — And the Paid Tools They Kill (Part 2)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-10"
duration_seconds: 737
video_id: "hiX-KFaAuA4"
url: "https://youtube.com/watch?v=hiX-KFaAuA4"
language: "en"
tags: [open-source, github-repos, self-hosted, ai-tools, pewdiepie, bytedance, alibaba, agent-harnesses, voice-cloning, photo-backup]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# 10 More GitHub Repos So Good They Shouldn't Be Free — And the Paid Tools They Kill (Part 2)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-10  **Duration:** 12:17  **Watch:** https://youtube.com/watch?v=hiX-KFaAuA4

> **Source note:** All 10 repos, GitHub URLs, and paid-product comparisons are listed in the description and free stack guide. Part 1 is the predecessor video. Vendor: this is a roundup of community / vendor open-source releases (PewDiePie, ByteDance, Jamie Pine, Alibaba, Dokploy, etc.) — not a single vendor.

## TL;DR

Part 2 of the "free GitHub repos that replace your monthly bills" series. 10 new repos, no repeats from Part 1, every number fact-checked this week. Headline names: PewDiePie's self-hosted AI workspace Odysseus (20K stars in 24h), ByteDance's MIT agent harness DeerFlow (sandboxed computer per task, kick off runs from Telegram), Jamie Pine's local voice studio Voicebox (7 TTS engines, 23 languages, MCP support), Open Notebook (self-hosted NotebookLM with 1-4 speaker podcasts vs Google's 2), Meetily (234K+ downloads, no bot in your call), Immich (103K stars, self-hosted Google Photos with CLIP search), Dyad (local Lovable), Multica (manager for 11 agent CLIs, "2 engineers + fleet of agents = 20"), Alibaba's Open Code Review (served tens of thousands of devs internally for 2 years), and Dokploy (open-source Vercel/Netlify/Heroku). Same advice as Part 1: don't install all 10, pick the one bill that annoys you most and replace it this week.

## Key Insights

- **1. Odysseus — PewDiePie's self-hosted AI workspace** (`github.com/pewdiepie-archdaemon/odysseus`): released 2026-05-31, 20K GitHub stars in the first 24h, 66K+ as of recording. Local models (vLLM, llama.cpp, Ollama) or your own keys (OpenAI, OpenRouter). Goes past chat: agents with web/file/shell access, deep research that reads sources and builds a visual report, email triage that drafts replies in your style. Replaces: **ChatGPT Plus ($20/mo) / Pro ($200/mo)**. Honest catch: days old, moving fast, default branch is literally "dev." (00:48)
- **2. DeerFlow — ByteDance's MIT agent harness** (`github.com/bytedance/deer-flow`): started as a deep research framework, v2 turned it into a full agent harness. Every task gets its own sandboxed computer. Spawns sub-agents on the fly with scoped context and their own tools. Skills load like slash commands. Message gateway: kick off a research run from Telegram or Slack and walk away. Replaces: **ChatGPT Pro deep research at full quota ($200/mo)**. Honest catch: BYO model keys, long runs burn real tokens, the recommended self-host box is beefier than a laptop. (01:59)
- **3. Voicebox — Jamie Pine's local voice studio** (`github.com/jamiepine/voicebox`): clones a voice from a few seconds of audio. 7 TTS engines (incl. Orca 3 and Chatterbox), 23 languages, multi-track timeline editor for podcasts/conversations, global dictation hotkey, MCP support so your agents can speak in your cloned voice. Replaces: **ElevenLabs ($22/mo Pro / $99/mo scale)**. Honest catch: pre-v1 (last release late April), quality depends on which engine your hardware can run, lightest fits in ~1GB VRAM. (03:01)
- **4. Open Notebook — self-hosted NotebookLM** (`github.com/lfnovo/open-notebook`): feed PDFs, videos, audio, web pages, chat with sources with citations. 18+ AI providers including local Ollama. Podcast feature beats Google's: 1-4 speakers with custom profiles, vs NotebookLM's locked 2. Replaces: **Google AI Pro ($19.99/mo)**. Honest reframe: NotebookLM core is free; $20/mo buys higher limits. Open Notebook has no limits to raise, runs in Docker in ~2 min, sources never leave your machine. Catch: one maintainer, cloud models still cost API tokens — free only truly means free with local models. (04:04)
- **5. Meetily — meeting notes with no bot in your call** (`github.com/Zackriya-Solutions/meetily`): captures mic and system audio locally, transcribes live with Whisper or the 4× faster Parakeet, summarizes with Ollama. 234,000+ downloads, MIT licensed, macOS and Windows. Replaces: **Otter ($16.99/mo) / Fireflies ($18/user/mo)** (both ship a bot and ship transcripts to their servers). Honest catch: speaker ID hasn't shipped yet — planned this month, Pro-only. Free community edition is the full tool, not a trial. (05:10)
- **6. Immich — Google Photos on your own server** (`github.com/immich-app/immich`): 103K GitHub stars, most starred self-hosted photo project on the planet. Phone auto-backup, ML face/object recognition, plain-English search ("red car at the beach") with local CLIP. Shared albums, memories, even 360 photos. v2 officially stable, full-time team. Replaces: **Google One 2TB ($9.99/mo, $100/yr forever to look at your own memories)**. Honest catch: you supply the server and drives, AND Immich tells you to keep a separate backup — self-hosting means you own the failure mode too. (06:06)
- **7. Dyad — the Lovable experience running locally** (`github.com/dyad-sh/dyad`): describe an app, watch it get built. Runs entirely on your machine, any model, your own keys, no platform lock-in, Mac and Windows. v1.3 shipped 2 days before the video. Replaces: **Lovable Pro ($25/mo) / v0 Team ($30/mo)**. Honest catch: open-core — $20/mo Pro adds credits and large-codebase modes. Free app is real and complete; the company makes money on add-ons. (07:08)
- **8. Multica — manager for AI coding agents** (`github.com/multica-ai/multica`): assign a GitHub issue to an agent like you'd assign it to a colleague. Shows up on the board, posts comments, reports blockers. Squads with a leader that decides who picks up the work. Runs 11 different agent CLIs (Claude Code, Codex, Copilot, Gemini, Cursor). Their pitch: 2 engineers and a fleet of agents can move like 20. Replaces: **Devin Teams ($80/mo + $40/seat, launched at $500/mo)**. Honest catch: 5 months old, source-available (free to run for your own team, not to resell as a service). (08:05)
- **9. Open Code Review — Alibaba open-sourced** (Apache, June 10): the AI code review assistant they ran internally. Served tens of thousands of devs and flagged millions of defects over 2 years. The interesting design: deterministic pipelines handle file selection and rule matching, an LLM agent handles the judgment (Alibaba: "pure agents suffer incomplete coverage and unstable quality"). Posts precise line-level comments, ships fine-tuned rules for null pointers, thread safety, XSS, SQL injection. Speaks both OpenAI and Anthropic APIs. Replaces: **CodeRabbit ($24/dev/mo)**. Bring your own model key, the per-seat bill disappears. (09:14)
- **10. Dokploy — open-source Vercel/Netlify/Heroku** (`github.com/dokploy/dokploy`): self-host on a $5 VPS, get the whole dashboard. Deploy apps in any language, native Docker Compose, 6 databases out of the box (Postgres, MySQL, Redis, etc.), multi-server scaling with Docker Swarm, real-time monitoring. Replaces: **Vercel Pro ($20/user/mo) / Heroku dynos ($7-$1,500/mo)**. Even Dokploy's own managed cloud is $450/server, which tells you the margin everyone else is charging. Honest catch: still v0.29 — pre-v1 software in front of your production traffic, open-core like Dyad. (10:21)
- **The naming collision check** (per the skill's pitfall list): "Hermes Agent" (mentioned in some other channels) and "Multica" (an agent CLI manager) are different products. PewDiePie's "Odysseus" is unrelated to any other AI workspace. "Dyad" is unrelated to other agent frameworks.

## Notable Quotes

> "For every repo, I'll show you the exact paid product it replaces and the honest catch nobody mentions." (00:42)

> "Don't install all 10. Pick the one bill that annoys you most and replace it this week." (11:39)

> "All 20 repos, a YouTuber, two tech giants, and a lot of solo builders. All giving away software you're still paying for every month." (11:30)

## Tools and Resources Mentioned

All 10 repos:
- **Odysseus** — github.com/pewdiepie-archdaemon/odysseus (PewDiePie)
- **DeerFlow** — github.com/bytedance/deer-flow (ByteDance, MIT)
- **Voicebox** — github.com/jamiepine/voicebox (Jamie Pine, MIT)
- **Open Notebook** — github.com/lfnovo/open-notebook
- **Meetily** — github.com/Zackriya-Solutions/meetily (MIT, 234K downloads)
- **Immich** — github.com/immich-app/immich (103K stars, v2 stable)
- **Dyad** — github.com/dyad-sh/dyad (Apache)
- **Multica** — github.com/multica-ai/multica (source-available)
- **Open Code Review** — Alibaba (Apache, 2026-06-10)
- **Dokploy** — github.com/dokploy/dokploy (v0.29)

Paid products replaced (cumulative monthly cost avoided if all 10 self-hosted):
- ChatGPT Plus/Pro, Google AI Pro, ElevenLabs, Otter, Fireflies, Google One 2TB, Lovable Pro, v0 Team, Devin Teams, CodeRabbit, Vercel Pro, Heroku

> **Vendor disambiguation:** PewDiePie/archdaemon = creator; ByteDance = parent of TikTok; Jamie Pine = SpaceDrive creator; Alibaba = Chinese tech giant (open-sourced its internal code review tool on 2026-06-10). None of these are the user's stack.

**Free updated stack guide** (both parts): comment "CANCEL" on the video, or grab from the channel
**Part 1** (predecessor): https://youtube.com/watch?v=RegzpFdW8pM
**Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

## Action Items

- [ ] Pick the ONE bill that annoys you most and try the corresponding self-hosted replacement this week
- [ ] If you're an Otter/Fireflies user: try Meetily (caveat: no speaker ID yet, on Pro tier)
- [ ] If you're on ChatGPT Pro for deep research: try DeerFlow with your own model keys
- [ ] If you pay for ElevenLabs Pro/Scale: try Voicebox (test your specific engines first — quality varies)
- [ ] If you pay for Google One 2TB and are technical: try Immich (with a separate backup)
- [ ] If you pay for Lovable/v0 Dev and want local control: try Dyad (note the open-core Pro tier)
- [ ] If you manage a small dev team and have been eyeing Devin: try Multica self-hosted
- [ ] If you pay for CodeRabbit: try Open Code Review with your own model key
- [ ] Watch Part 1 first for the other 10 repos before making your pick

## Open Questions

- Odysseus: what's the production-readiness state beyond "dev" branch? Any docs on operating it at scale?
- DeerFlow: what are the minimum recommended self-host specs for "long runs" without throttling?
- Voicebox: which of the 7 TTS engines is closest to ElevenLabs quality for English narration?
- Open Notebook: will it stay single-maintainer, or pick up an org/team as it grows?
- Meetily: when does speaker ID ship to the free tier, and what's the actual Pro price?
- Immich: what's the recommended production server (Raspberry Pi 5 vs N100 vs used enterprise)?
- Dyad: does the local "Lovable experience" actually match Lovable's quality on multi-file apps?
- Multica: 11 agent CLIs supported — does that mean you can mix Claude Code + Codex + Copilot in one squad?
- Open Code Review: how does Alibaba's rule set generalize to languages other than Java/Go (the rules listed are language-agnostic but the dev count suggests Chinese tech stack bias)?
- Dokploy: at v0.29, what production gotchas has the community actually hit? Is the $5 VPS realistic or do you need $20-$50/mo for real traffic?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 12:17 transcript)</summary>

0:00 A few weeks ago, I showed you 10 GitHub
0:02 repos so good they shouldn't be free
0:06 and the exact paid products they
0:08 replace.
0:09 That video took off
0:11 and the comments did something better.
0:13 They kept naming bills I'd missed.
0:16 So, this is part two.
0:18 10 more repositories
0:20 none repeated from part one.
0:22 Every number fact-checked this week.
0:25 And this round, the names got bigger.
0:28 PewDiePie shipped one of these.
0:30 ByteDance shipped one.
0:32 Alibaba open-sourced theirs days ago.
0:35 Same rules as last time.
0:38 For every repo, I'll show you the exact
0:40 paid product it replaces
0:42 and the honest catch nobody mentions.
0:45 Let's go.
0:46 Number one, Odysseus.
0:49 On May 31st,
0:51 PewDiePie, yes,
0:53 that PewDiePie, released his own
0:55 self-hosted AI workspace
0:58 and it pulled 20,000 GitHub stars in the
1:02 first 24 hours.
1:05 It's the ChatGPT experience running on
1:08 your machine.
1:09 Chat with local models through vLLM,
1:12 llama.cpp, or Ollama.
1:15 Or point it at OpenAI or OpenRouter
1:18 with your own keys.
1:20 And it goes past chat.
1:22 Agents that take a task and run it with
1:25 web, file, and shell access.
1:28 Deep research that reads sources and
1:30 builds a visual report.
1:32 It even triages your email and drafts
1:34 replies in your style. ChatGPT Plus is
1:37 $20 a month.
1:38 Pro is 200.
1:40 This is that interface without the
1:43 subscription.
1:45 The honest catch, it's days old and
1:47 moving fast. The default branch is
1:50 literally called dev.
1:51 But 66,000 stars later, it's the most
1:55 watched repo of June.
1:57 Number two,
1:59 Dear Flow.
2:00 This one is from ByteDance,
2:02 the TikTok company,
2:04 and it's MIT licensed.
2:06 It started as a deep research framework.
2:09 Version two
2:11 turned it into a full agent harness.
2:13 Every task gets its own sandboxed
2:16 computer.
2:17 It spawns sub-agents on the fly,
2:20 each with scoped context and its own
2:22 tools.
2:23 Skills load like slash commands.
2:26 And here's the feature that got me.
2:28 The message gateway.
2:30 You can kick off a research run from
2:32 Telegram or Slack,
2:33 and just walk away.
2:34 OpenAI's deep research at full quota
2:35 lives on ChatGPT Pro,
2:40 $200 a month,
2:42 and plus users get a fraction of the
2:44 runs.
2:45 Dear Flow gives you the engine with no
2:48 quota at all.
2:49 The honest part,
2:51 you bring your own model keys.
2:53 Long runs burn real tokens,
2:56 and the recommended self-host box is
2:57 beefier than a laptop.
2:59 Number three,
3:01 Voicebox.
3:02 Jamie Pine, the developer behind
3:05 SpaceDrive,
3:06 built a local AI voice studio
3:09 that clones a voice from a few seconds
3:11 of audio.
3:12 It runs seven
3:15 different text-to-speech engines,
3:18 including
3:19 When three and Chatterbox.
3:21 It speaks 23 languages.
3:25 It ships a multi-track timeline editor
3:27 for podcasts and conversations.
3:30 There's a global dictation hotkey and
3:33 MCP support,
3:35 so your agents can literally speak in
3:36 your cloned voice.
3:38 ElevenLabs charges $22 a month for
3:40 professional voice cloning,
3:42 99 on Pro,
3:44 and meters you by the character.
3:46 Voicebox is MIT licensed and meters
3:49 nothing.
3:50 The honest part, it's pre-version one.
3:53 The last release was late April.
3:56 And quality depends on which engine your
3:57 hardware can run. The lightest one fits
3:59 in about 1 GB of VRAM.
4:02 Number four,
4:04 Open Noteb
ook.
4:06 This is Notebook LM self-hosted.
4:09 Feed it PDFs, videos, audio, web pages,
4:12 then chat with your sources with
4:14 citations.
4:16 It supports 18 plus AI providers,
4:19 including Ollama running fully local.
4:22 And the podcast feature actually beats
4:25 Google's.
4:26 Notebook LM is locked to two hosts. Open
4:29 Notebook generates audio with one to
4:31 four speakers, each with a custom
4:33 profile.
4:34 Now, the honest reframe on the price.
4:37 Notebook LM's core features are free.
4:41 What $20 a month of Google AI Pro buys
4:45 you is higher limits.
4:47 Open Notebook has no limits to raise.
4:50 It runs in Docker in about 2 minutes.
4:54 And your sources never leave your
4:56 machine.
4:57 The catch?
4:58 It's one maintainer's project, and cloud
4:59 models still cost API tokens.
5:02 Free only truly means free when you run
5:06 local models.
5:08 Number five,
5:10 Meet Lily.
5:11 An AI meeting note taker with no bot
5:13 joining your call.
5:15 It captures your mic and system audio
5:17 locally.
5:18 Transcribes live with Whisper or the
5:20 four times faster Parakeet, and
5:23 summarizes with Ollama.
5:25 So, a meeting goes from audio to notes
5:27 without ever touching the cloud.
5:30 234,000
5:31 downloads.
5:32 MIT licensed.
5:34 macOS and Windows.
5:36 Otter charges about $17 a month, and
5:39 caps your minutes.
5:41 Fireflies is 18 per user.
5:45 And both of them ship a bot into your
5:46 meeting and your transcript to their
5:48 servers.
5:50 The honest part, speaker identification,
5:53 who said what, has not shipped yet.
5:56 It's planned for this month and it lands
5:59 in the paid pro tier.
6:01 But the free community edition is the
6:02 full tool, not a trial.
6:05 Number six.
6:06 Immich, the big one.
6:09 103,000 GitHub stars.
6:11 The most starred self-hosted photo
6:13 project on the planet.
6:16 It's Google Photos on your own server.
6:19 The phone app auto backs up your camera
6:22 roll.
6:23 Machine learning recognizes faces and
6:25 objects.
6:27 And you can search your library in plain
6:29 English, red car at the beach. Because
6:32 it runs clip locally.
6:34 Shared albums, memories, even 360
6:38 photos.
6:39 Google charges $10 a month for the 2 TB
6:41 plan.
6:44 A $100 a year, forever, to look at your
6:47 own memories.
6:49 Immich is free. The team works on it
6:51 full time and version two is officially
6:54 stable.
6:55 The honest part, you supply the server
6:57 and the drives.
6:59 And even Immich tells you to keep a
7:01 separate backup. Self-hosting your
7:03 photos means you own the failure mode,
7:06 too.
7:06 Number seven.
7:08 Diad.
7:09 The lovable experience.
7:11 Describe an app, watch it get built.
7:14 Except it runs entirely on your machine.
7:18 Any model, your own keys,
7:20 no platform lock-in,
7:22 Mac and Windows.
7:24 Lovable Pro is $25 a month, metered in
7:28 credits.
7:30 V0's team plan is 30.
7:32 Diad's core is Apache licensed and free.
7:37 You pay your model provider and nobody
7:40 else.
7:41 Version 1.3 shipped two days ago.
7:43 So, this one is moving fast.
7:45 The honest part, and you'll see this
7:48 pattern across the list, it's open core.
7:51 There's a $20 pro tier with extra
7:53 credits and large code base modes.
7:56 The free app is real and complete.
7:59 The company makes its money on the
8:01 add-ons.
8:02 That's the deal,
8:03 and it's a fair one.
8:05 Number eight,
8:07 Multika.
8:08 This is a manager for AI coding agents.
8:12 You assign a GitHub issue to an agent
8:14 the way you'd assign it to a colleague.
8:17 It shows up on the board,
8:19 posts comments, and reports blockers
8:23 before you ask.
8:24 You can group agents into squads with a
8:26 leader that decides who picks up the
8:28 work.
8:30 It runs 11 different agent CLIs,
8:33 Cloud Code, CodeX, Co-pilot, Gemini,
8:35 Cursor.
8:37 Their pitch,
8:39 two engineers and a fleet of agents can
8:41 move like a team of 20.
8:43 Compare that to Devin, the managed AI
8:44 team made that launched
 at $500 a month.
8:48 Today, its team plan is $80 a month plus
8:50 $40 per seat before you pay for the
8:52 agents themselves.
8:54 Multika's platform fee is zero.
8:57 You self-host it with Docker,
8:59 and pay only for the agents you already
9:01 use.
9:02 The honest part,
9:04 it's 5 months old, and the license is
9:06 source available.
9:08 Free to run for your own team,
9:10 not to resell as a service.
9:13 Number nine,
9:14 and this one is days old.
9:17 On June 10th, Alibaba open-sourced Open
9:20 Code Review,
9:21 the AI code review assistant they ran
9:24 internally.
9:25 By their own count, it served tens of
9:28 thousands of their developers, and
9:30 flagged millions of defects over 2
9:32 years.
9:33 The design is the interesting part.
9:36 Deterministic pipelines handle file
9:37 selection and rule matching.
9:39 An LLM agent handles the judgment.
9:42 Because, in their words, pure agents
9:45 suffer incomplete coverage and unstable
9:48 quality.
9:49 It posts precise line-level comments.
9:52 It ships fine-tuned rules for null
9:55 pointers,
9:56 thread safety, cross-site scripting, and
9:59 SQL injection.
10:01 And it speaks both OpenAI and Anthropic
10:04 APIs.
10:07 CodeRabbit charges
10:09 $24 per developer per month for this
10:11 exact job.
10:15 This is Apache licensed.
10:17 Bring your own model key
10:18 and the per-seat bill disappears.
10:21 Number 10.
10:22 Dokploy.
10:24 Its GitHub description is literally
10:26 open-source alternative to Vercel,
10:28 Netlify, and Heroku.
10:32 Self-host it on a $5 VPS
10:35 and you get the whole dashboard.
10:37 Deploy apps in any language.
10:40 Native Docker Compose.
10:42 Six databases out of the box.
10:45 Postgres, MySQL, Redis, and more.
10:50 Multi-server scaling with Docker Swarm.
10:53 Real-time monitoring.
10:55 Vercel Pro is $20 per user per month and
10:58 the overage bills are their own genre of
11:01 horror story.
11:03 Heroku dynos run from $7 to $1,500 a
11:06 month.
11:08 Even Dokploy's own managed cloud is 450
11:11 per server,
11:12 which tells you the margin everyone else
11:13 is charging.
11:15 The honest part, it's still version
11:17 0.29.
11:19 That's pre-version one software in front
11:22 of your production traffic.
11:24 And like Diad, it's open core.
11:27 10 more repositories, a YouTuber,
11:30 two tech giants, and a lot of solo
11:32 builders. All giving away software
11:33 you're still paying for every month.
11:36 Same advice as part one. Don't install
11:38 all 10.
11:40 Pick the one bill that annoys you most
11:42 and replace it this week.
11:45 I've put all 20 repos
11:47 this list and part one's
11:49 into the updated free stack guide.
11:53 The links, what each one replaces, and
11:56 every honest catch.
11:58 Comment the word cancel and I'll send it
12:00 straight to you.
12:02 If you missed part one, it's on screen
12:04 right now.
12:05 Deep dives live here on YouTube, so
12:07 subscribe.
12:09 And the bite-size drops are on Instagram
12:11 at Hyper Automation Labs.
12:14 Now, go cancel something else.

</details>
