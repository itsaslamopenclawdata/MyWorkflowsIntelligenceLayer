---
title: "Top 10 Trending GitHub Repos This Week — 5 Are Secretly ONE Idea"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-23"
duration_seconds: 728
video_id: "VeNWtD_eN2s"
url: "https://www.youtube.com/watch?v=VeNWtD_eN2s"
language: "en"
tags: ["github", "trending-repos", "ai-agents", "agent-skills", "mcp", "open-source", "coding-agents", "claude-code", "cursor", "codex"]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-25"
---

# Top 10 Trending GitHub Repos This Week — 5 Are Secretly ONE Idea

**Channel:** Hyperautomation Labs
**Published:** 2026-06-23
**Duration:** 12 min 8 sec
**Watch:** https://www.youtube.com/watch?v=VeNWtD_eN2s

## TL;DR

GitHub's trending page this week is dominated by one concept: **agent skills** — reusable, shareable capability packs that turn AI coding agents from "eager intern" into "senior engineer." Of the top 10 fastest-growing repos (ranked by stars gained this week, not total stars), #1 (Matt Pocock's Skills, +11k stars), #2 (Agent Reach), #3 (Codebase Memory MCP), #5 (Addy Osmani's Agent Skills), and #7 (Nvidia's Skill Specter security scanner) are all pieces of the same emerging skills ecosystem — install, extend, secure. The remaining 5 are practical open-source replacements for paid SaaS (Voicebox for voice, Penpot for Figma, OpenCut for CapCut, TimesFM for forecasting, OpenMontage for AI video editing). Three concrete moves this week: steal Pocock's or Osmani's skills folder, run Skill Specter before you install anything, and pilot one open-source tool to kill a subscription.

## Key Insights

- **Trending = velocity, not fame.** The ranking is by *stars gained this week*, so a 50k-star repo can outrank a 140k-star repo if it's growing faster right now. This surface the actual signal the trending page is meant to show.
- **The "skills" era is replacing the "prompts" era.** For two years, getting more out of an AI meant writing cleverer prompts. The new unit is the **skill** — a reusable, shareable capability folder your agent invokes again and again. You don't build agents from scratch anymore, you assemble them from parts other engineers shipped.
- **A full skills ecosystem formed in ~7 days.** Five of the top 10 repos are interlocking pieces: Pocock + Osmani ship the *skills themselves*; Codebase Memory gives skills a persistent memory of your repo; Agent Reach gives skills eyes on the live web; Nvidia's Skill Specter keeps the whole thing safe to install. Install → extend → secure — that pattern is the marker of a maturing ecosystem.
- **Skills are code with your permissions.** A skill is just code that runs with your agent's credentials. Install a sketchy one and it can do real damage. Treat them with the same skepticism you'd give any downloaded executable. Always scan first.
- **Honest warning on stars.** A jump from 0 → 40k in 3 weeks with no issues, no forks, and no real discussion is almost certainly inflated. Check velocity *and* whether people are actually filing issues and building on top.
- **Most of the list replaces a paid SaaS with something you self-host.** Voicebox (AI voice studio, no per-word subscription), Penpot (Figma replacement, self-hostable, designer-and-dev friendly), OpenCut (browser video editor, no watermark, footage never leaves your machine). The creative-tool category on this list is unusually strong.
- **Forecasting just got a "just works" button.** Google Research's **TimesFM** is a foundation model for time-series that requires zero training — point it at sales, traffic, or demand data and it forecasts forward. This is the closest thing yet to replacing the "hire a data scientist to hand-build a model" path.
- **Agentic video editing is early but real.** OpenMontage (#4) lets you *describe the cut* and an agent assembles the edit. Not production-ready this week, but a clear signal that the agentic pattern coming for coding is now coming for media.

## Notable Quotes

- "The single fastest-growing repository on all of GitHub wasn't a new app, and it wasn't a new model. It was one engineer's folder of agent skills."
- "The trending page screamed one word: skills."
- "For two years, getting more out of an AI meant writing a cleverer prompt. That era is ending. The new unit is the skill."
- "Skills are becoming the new apps. You don't build your agent from scratch anymore. You assemble it from parts that other brilliant engineers already shipped."
- "A skill is just code that runs with your permissions. Install a sketchy one and it can do real damage."
- "By default, a model only knows the world up to its training cutoff. It's frozen in the past. Agent Reach lets it browse, read, and pull in live web pages."
- "When your AI agent works on a big project, it wastes huge amounts of time and money re-reading the same files over and over every single turn. Codebase Memory indexes everything once."
- "A blind agent is a guessing agent."
- "If something jumps from 0 to 40,000 in 3 weeks with no issues, no forks, and no real discussion, be skeptical."
- "Don't just watch the trend. Get 1% ahead of it this week."

## Tools and Resources Mentioned

**The 5 "Skills Ecosystem" repos (the secret unifying idea):**
- **#1 Skills (Matt Pocock)** — Pocock's personal `.claude/skills` directory open-sourced; +11,000 stars this week. Clone into `~/.claude/skills/`.
- **#2 Agent Reach** — Gives your AI agent live web browsing/reading capability. Closes the training-cutoff blind spot. +8,000 stars this week.
- **#3 Codebase Memory** — High-performance MCP server (written in C) that indexes your whole repo once so agents stop re-reading the same files every turn. Works with Claude Code and Cursor.
- **#5 Agent Skills (Addy Osmani)** — Curated, battle-tested production skills for Claude Code / Codex / Cursor. Osmani is the Chrome engineering lead; his name is the quality bar.
- **#7 Skill Specter (Nvidia)** — Security scanner for agent skills. Point it at any skill folder to detect malicious or dangerous code *before* you run it.

**The 5 "Kill a SaaS" repos:**
- **#10 Voicebox (Jamie Pine, SpaceDrive author)** — Open-source local AI voice studio. Studio-quality narration, characters, audiobooks, voice cloning. No per-word subscription. *Caveat: only clone voices you have permission to use.*
- **#9 Penpot** — Open-source Figma replacement. Runs in browser, speaks CSS/SVG, full self-host capability. The most mature item on the list; companies already run it in production.
- **#8 OpenCut** — Open-source CapCut. Browser-based timeline editor, no watermark, no subscription, footage stays local. Privacy-first design.
- **#6 TimesFM (Google Research)** — Foundation model for time-series forecasting. Zero training required. `pip install` and predict.
- **#4 OpenMontage** — Self-described "world's first open-source agentic video production system." Describe the cut; agent assembles the edit. Early/rough but directionally striking.

**Distribution / channel CTAs:**
- Free cheat sheet with all 10 repos, live star counts, one-line install commands, skills ecosystem map, and how to spot fake inflated stars — comment **"shipped"** on the video or grab the link in description.
- Creator's deeper guides: Claude Code, Codex Cloud for Sales, Certification Prep (links in description).
- Follow Hyperautomation Labs on Instagram and Facebook.

## GitHub Repos and URLs Referenced

| # | Repo / Project | Author | What it does | Install path |
|---|---|---|---|---|
| 1 | **Skills** (Matt Pocock) | Matt Pocock (TypeScript educator) | Open-sourced `.claude/skills` directory — senior-engineer skill pack | Clone into `~/.claude/skills/` |
| 2 | **Agent Reach** | (community) | Gives agent live web browsing/reading | Clone repo |
| 3 | **Codebase Memory** | (community) | High-perf MCP server, C implementation, persistent repo index | Add as MCP server to client config |
| 4 | **OpenMontage** | (community) | "World's first open-source agentic video production system" | Clone repo (experimental) |
| 5 | **Agent Skills** | Addy Osmani (Google Chrome eng. lead) | Curated production skills for Claude Code / Codex / Cursor | Clone into `~/.claude/skills/` |
| 6 | **TimesFM** | Google Research | Foundation model for time-series forecasting, zero-training | `pip install` |
| 7 | **Skill Specter** | Nvidia | Antivirus-style scanner for agent skills | Point at any skill folder and scan |
| 8 | **OpenCut** | (community) | Open-source CapCut replacement, browser editor | Self-host or use web app |
| 9 | **Penpot** | (community) | Open-source Figma replacement, CSS/SVG-native | `penpot.app` or Docker self-host |
| 10 | **Voicebox** | Jamie Pine (SpaceDrive author) | Local AI voice studio, narration/clone, no subscription | Clone repo and run studio locally |

- Video URL: https://www.youtube.com/watch?v=VeNWtD_eN2s
- Channel: https://www.youtube.com/@hyperautomationlabs (channel_id `UCiax-xbEI0P6Y8C8VwZGMgQ`)

## Action Items

- [ ] **Steal a skills folder today.** Clone either Matt Pocock's `Skills` repo or Addy Osmani's `agent-skills` repo into `~/.claude/skills/` and notice the difference in code quality within a session.
- [ ] **Scan before you trust.** Run Nvidia's **Skill Specter** against any skill folder (yours or someone else's) before installing it. Treat skills like any other code you download — because that's exactly what they are.
- [ ] **Pick one creative tool and kill a subscription.** Choose whichever replaces a bill you're already paying: OpenCut (video editing), Penpot (design), or Voicebox (voice generation). Pilot one this week.
- [ ] **Give your agent live web eyes.** Add **Agent Reach** so it can answer questions about brand-new libraries, current prices, breaking changes — instead of confidently hallucinating from stale training data.
- [ ] **Stop re-reading the same files.** Plug **Codebase Memory** (MCP server) into Claude Code / Cursor on your large repo. Measure the speedup on multi-turn work.
- [ ] **Try zero-training forecasting.** Install **TimesFM** and point it at one real series you care about (traffic, sales, demand). Compare to whatever you're currently using.
- [ ] **Audit your starred repos for fake velocity.** For any repo with rapid star growth, check issue activity, fork count, and discussion quality. Unstar anything that looks like an inflation campaign.
- [ ] **Watch OpenMontage closely.** Not production-ready, but worth tracking as the leading edge of agentic media editing.

## Open Questions

- **How will the skills ecosystem handle versioning and breaking changes?** When you `git pull` someone's skill folder, you're inheriting their evolving behavior. What's the equivalent of a `package.json` lockfile for skills? Pocock and Osmani both ship curated sets — but who arbitrates the canonical version?
- **Can Skill Specter keep up with skill obfuscation?** Static scanning is a starting point, but adversarial skill authors will eventually write skills that hide malicious intent from naive scanners. Does Nvidia have a roadmap for runtime sandboxing on top of static analysis?
- **Is "stars gained this week" actually a useful signal at this velocity?** A repo going from 0 → 11k in days is clearly newsworthy, but it also concentrates attention on whoever shipped first and got the front-page bump. Does the trending algorithm systematically favor established names with existing audiences (Pocock, Osmani, Nvidia) over genuinely novel work from unknown authors?
- **What's the unit-economics flip when agents stop re-reading files?** Codebase Memory's pitch is "agents waste huge amounts of time and money re-reading the same files." If that waste is real and pervasive, what's the magnitude on a typical long session — 30% of tokens? 70%? The video asserts it but doesn't quantify.
- **Does Penpot really replace Figma for teams that already standardized on Figma's plugin ecosystem?** The video frames it as a drop-in, but plugin parity, real-time multi-user performance at scale, and design-system integrations (Tokens Studio, etc.) are the usual sticking points.
- **OpenMontage and the "describe the cut" workflow — is this the future of all editing, or just B-roll assembly?** Creative editing depends on taste, timing, and emotional rhythm that current agents clearly don't have. Where exactly is the boundary?
- **TimesFM on real production data — how does it compare to ARIMA / Prophet / a hand-tuned LSTM when stakes are high (revenue forecasting)?** "Zero training" is a powerful claim but the real test is on noisy, regime-changing business data.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 12 min 8 sec transcript)</summary>

0:00 Every week, GitHub quietly publishes a
0:02 leaked memo about where software is
0:05 heading.
0:06 It's the trending page, and almost
0:08 nobody reads it.
0:10 This week, it screamed one word, skills.
0:15 The single fastest-growing repository on
0:17 all of GitHub wasn't a new app, and it
0:20 wasn't a new model.
0:22 It was one engineer's folder of agent
0:23 skills,
0:25 and it gained over 11,000 stars in just
0:27 days.
0:28 Right behind it, a tool that gives your
0:30 agent eyes on the live internet,
0:33 a memory server for your code base, and
0:35 a security scanner
0:36 built by Nvidia just to keep those
0:38 skills safe.
0:40 I pulled the real numbers and read every
0:42 single repo.
0:43 Here are the top 10 this week, ranked by
0:45 the stars they actually gained, counted
0:48 down with honest verdicts.
0:50 Let's go.
0:51 Quick ground rules, because this ranking
0:53 is different from every other best repos
0:55 list.
0:56 I am not ranking by total stars.
0:58 If I did, the same boring giants would
1:01 win every single week.
1:03 I'm ranking by stars gained this week.
1:06 Who is surging right now?
1:08 That is what trending actually means.
1:11 So, a project with 50,000 total stars
1:14 can outrank one with 140,000
1:17 simply because it's growing faster
1:19 today.
1:21 One honest warning before we start.
1:23 Stars can be gamed.
1:25 If something jumps from 0 to 40,000 in 3
1:28 weeks with no issues, no forks, and no
1:31 real discussion,
1:32 be skeptical.
1:34 Check the velocity.
1:36 Check whether people are actually filing
1:38 issues and building on it.
1:40 Watch the number,
1:41 but also watch whether the thing is
1:43 real.
1:44 Now, let's count them down from 10 to 1.
1:47 Number 10,
1:48 Voicebox
1:49 from Jamie Pine, the developer behind
1:52 SpaceDrive.
1:53 It's an open-source AI voice studio.
1:56 You can generate studio quality
1:58 narration,
1:59 characters, and audiobooks.
2:01 And even clone a voice, all running
2:03 locally with no per word subscription
2:05 bill.
2:06 For creators, that's a real unlock.
2:08 Voiceovers without a monthly meter
2:10 running.
2:11 One honest caveat, and it matters.
2:14 Only ever clone a voice you actually
2:16 have permission to use.
2:18 Used responsibly,
2:20 it replaces an expensive piece of the
2:22 content stack
2:23 with something you fully control.
2:25 To try it,
2:26 clone the repo
2:28 and run the studio on your own machine.
2:30 Number nine, Penpot.
2:32 This is the open-source answer to Figma.
2:35 A full design tool that runs in your
2:37 browser and speaks code.
2:40 Designers work in real CSS and SVG.
2:43 Developers get clean handoff. And your
2:45 whole team can self-host the entire
2:48 thing for free.
2:50 Of everything on this list, Penpot is
2:52 the most mature and battle-tested.
2:55 This is not a weekend project.
2:57 It's a genuine Figma replacement that
3:00 companies already run in production.
3:03 If your team is paying per seat for
3:04 design software, this is the one to
3:06 pilot.
3:07 Self-host it with Docker or just open
3:10 penpot.app and start for free. Number
3:12 eight, OpenCut, the open-source CapCut.
3:16 It's a real video editor that runs right
3:18 in your browser.
3:19 Timeline editing, no watermark, no
3:22 subscription, and your footage never has
3:24 to leave your machine.
3:26 For anyone who's felt nervous uploading
3:28 raw clips to a free online editor,
3:30 that privacy-first design is the whole
3:32 point.
3:33 It's young and moving fast, so expect a
3:36 few rough edges. But the direction is
3:38 exactly right.
3:40 Serious editing, no lock-in, and no
3:42 surprise paywall on export.
3:44 Self-host it or use the web app and
3:46 start cutting today. Number seven,
3:48 and this one is quietly important.
3:51 Skill Specter,
3:52 built by Nvidia.
3:54 As agent skills explode in popularity,
3:58 here's the uncomfortable truth.
4:00 A skill is just code that runs with your
4:02 permissions.
4:04 Install a sketchy one and it can do real
4:06 damage.
4:08 Skill Specter is the antivirus for that
4:10 problem.
4:11 It scans any agent skill
4:13 for malicious or dangerous code before
4:16 you ever run it.
4:17 The fact that Nvidia shipped this in the
4:19 very same week skills went viral
4:22 tells you exactly
4:24 how fast this ecosystem is maturing.
4:26 My verdict is simple.
4:29 If you install skills, run this first.
4:31 Point it at any skill folder and let it
4:33 scan.
4:34 Number six,
4:35 Times FM
4:37 from Google Research.
4:39 Almost everything on this list is about
4:40 coding agents.
4:42 This one is different and genuinely
4:43 special.
4:45 Times FM is a foundation model for time
4:46 series forecasting.
4:48 In plain English, you point it at your
4:50 sales numbers, your website traffic, or
4:52 your demand data and it forecasts what
4:55 comes next with zero training required.
4:58 For years, forecasting meant hiring a
5:00 data scientist to hand-build a custom
5:02 model.
5:03 This is the closest thing yet to a just
5:05 works button
5:06 for predicting the future from your own
5:07 data.
5:09 It's real research from Google
5:11 and you can install it today with a
5:12 single pip e command. Number five,
5:15 Agent Skills from Addy Osmani an
5:17 engineering leader at Google Chrome.
5:20 These are production-grade skills for
5:22 your coding agent.
5:23 A curated battle-tested set
5:25 that makes Claude Code, Code X, or
5:28 Cursor
5:29 behave less like an eager intern
5:31 and more like a senior engineer.
5:33 The value here is the curation.
5:35 Anyone can write a skill.
5:37 The hard part is knowing which ones
5:38 actually hold up under real work.
5:41 Osmani's name on the repo is the quality
5:42 bar.
5:44 You drop these into your agent skills
5:45 folder and you can feel the difference
5:46 immediately.
5:48 Tighter code, fewer dumb mistakes. Clone
5:50 it straight into your dot cloud skills
5:52 directory. Number four,
5:54 Open Montage,
5:56 which calls itself the world's first
5:58 open-source agentic video production
6:00 system.
6:01 The idea is wild.
6:03 Instead of editing a video yourself,
6:05 you describe the cut you want,
6:07 and an AI agent assembles the montage
6:09 for you, pulling clips,
6:11 sequencing them,
6:13 building the edit.
6:14 Now, let me be honest.
6:16 This is early and rough around the
6:18 edges.
6:19 It's not replacing a professional editor
6:21 this week, but as a glimpse of where
6:23 things are going, it's striking.
6:26 The same agentic approach that's
6:28 rewriting coding
6:29 is now coming for video editing.
6:31 Watch this space closely.
6:34 Clone the repo if you want to experiment
6:36 on the frontier.
6:37 Number three, code-base memory, a
6:40 high-performance MCP server.
6:43 Here's the problem it solves. When your
6:45 AI agent works on a big project, it
6:48 wastes huge amounts of time and money
6:49 re-reading the same files over and over
6:53 every single turn.
6:55 This gives your agent a fast, persistent
6:58 memory of your entire code base.
7:00 It indexes everything once, so tools
7:03 like Claude code and Cursor can recall
7:06 how your project fits together instead
7:09 of starting from scratch each time.
7:11 Written in C for speed, it plugs
7:13 straight into your editor as an MCP
7:15 server.
7:17 For anyone working in a large repo, this
7:19 is the kind of unglamorous plumbing that
7:21 quietly makes your agent dramatically
7:23 faster.
7:24 Add it to your client config and go.
7:27 Number two,
7:28 Agent Reach.
7:30 Give your AI agent eyes to see the
7:32 entire internet.
7:34 This closes
7:35 what is probably
7:37 your agent's single biggest blind spot.
7:40 By default, a model only knows the world
7:42 up to its training cutoff. It's frozen
7:44 in the past.
7:46 Agent reach lets it browse, read, and
7:48 pull in live web pages.
7:50 So, its answers reflect what's true
7:52 today,
7:53 not what was true a year ago.
7:55 Ask about a brand new library, a current
7:57 price, a breaking change, and instead of
7:59 confidently guessing, it actually goes
8:02 and looks.
8:03 It gained over 8,000 stars this week for
8:05 a reason.
8:06 A blind agent is a guessing agent.
8:09 Clone their repo to give yours real-time
8:11 sight. And number one, the single
8:14 fastest growing repository on all of
8:16 GitHub this week, Skills from Matt
8:19 Pocock.
8:21 Pocock is a well-known educator in the
8:23 TypeScript world, and he did something
8:24 simple and brilliant.
8:26 He open-sourced his entire dot Claude
8:28 Skills directory,
8:29 the exact set of skills he uses to turn
8:32 Claude code into a senior engineer.
8:35 And the internet went straight for it.
8:37 Over 11,000 stars in a matter of days.
8:40 This is the whole story of the week in
8:42 one repo.
8:44 You are no longer just prompting your
8:45 agent.
8:47 You're handing it a folder of reusable
8:49 skills.
8:50 And now you can copy a top engineer's
8:52 exact setup for free.
8:54 Clone it into your dot Claude Skills
8:55 directory,
8:57 and your agent levels up instantly. Step
8:59 back and look at this list because
9:01 there's a pattern hiding in plain sight.
9:04 Five of these 10 repos, including the
9:06 number one, two, three, five, and seven
9:10 spots, are all about one new idea,
9:13 skills.
9:15 For two years, getting more out of an AI
9:17 meant writing a cleverer prompt.
9:20 That era is ending.
9:22 The new unit is the skill, a reusable,
9:24 shareable capability you give your agent
9:26 that it can use again and again.
9:29 And look at what sprang up around it in
9:30 a single week.
9:31 Matt Pocock and Addy Osmani give you the
9:34 skills to install.
9:36 Codebase memory gives those skills a
9:38 memory of your project.
9:40 Agent reach gives them eyes on the live
9:41 web.
9:43 And Nvidia's skill inspector keeps them
9:45 safe.
9:46 That's an entire ecosystem.
9:49 Install, extend, and secure forming in 7
9:50 days.
9:53 The takeaway is huge.
9:55 Skills are becoming the new apps.
9:58 You don't build your agent from scratch
9:59 anymore.
10:00 You assemble it from parts that other
10:02 brilliant engineers already shipped. So,
10:04 what do you actually do with this?
10:07 Three concrete moves this week.
10:09 One, steal a skills folder.
10:12 Clone Matt Pocock's skills or Addy
10:15 Osmani's agent skills into your dot
10:17 cloud directory today
10:19 and let your agent inherit a senior
10:20 engineer setup in 5 minutes.
10:23 Two,
10:24 scan before you trust.
10:26 Anything you install, run Nvidia's skill
10:28 inspector over it first.
10:30 Skills run with your permissions, so
10:32 treat them like any other code you
10:34 download. Three,
10:36 pick one creative tool and kill a
10:37 subscription.
10:39 Open cut for video, pen pot for design,
10:41 or voice box for voice.
10:43 Choose the one that replaces a bill
10:44 you're already paying. Don't just watch
10:46 the trend.
10:47 Get 1 in ahead of it this week. Real
10:50 quick, an honest moment.
10:52 Most people watching this still haven't
10:54 subscribed.
10:55 I pull the live numbers, read every
10:57 repo, and build the free guide by hand.
10:59 And YouTube only shows this to more
11:01 people if you subscribe.
11:03 So, if it's helping,
11:05 subscribe here on YouTube and follow
11:07 Hyperautomation Labs on Instagram and
11:09 Facebook so the next one finds you.
11:11 Subscribe now
11:13 and never miss the tool that saves you
11:15 the most time and money. I packed all of
11:18 this into one free cheat sheet.
11:21 All 10 repos with their live star
11:23 counts,
11:24 the exact one-line install for each,
11:27 the skills ecosystem map, and how to
11:30 spot fake inflated stars.
11:34 To get it, just comment the word shipped
11:36 and I'll send it straight to you or grab
11:38 it at the link in the description.
11:40 If you want to go deeper, my four guides
11:42 on Cloud Code, Code X Cloud for Sales,
11:45 and Certification Prep go far beyond
11:48 this.
11:49 Links are below.
11:50 And quickly, if this saved you an
11:52 afternoon of research,
11:54 subscribe here on YouTube and follow
11:55 High Performance Labs on Instagram and
11:57 Facebook.
11:58 Because I do the boring reading, so you
12:00 get the honest version.
12:02 Pick one tool today.
12:03 Learn one concept this week.
12:05 Get years ahead. I'll see you in the
12:07 next one.

</details>