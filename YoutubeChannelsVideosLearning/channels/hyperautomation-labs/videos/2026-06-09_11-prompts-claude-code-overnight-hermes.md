---
title: "11 Prompts That Run Claude Code While You Sleep (Meet Hermes — The Honest Overnight Setup)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-09"
duration_seconds: 804
video_id: "-d7AExggxKI"
url: "https://youtube.com/watch?v=-d7AExggxKI"
language: "en"
tags: [claude-code, overnight-agents, hermes, headless, cron, routines, self-check, scope-drift, unattended-ai]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# 11 Prompts That Run Claude Code While You Sleep (Meet Hermes — The Honest Overnight Setup)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-09  **Duration:** 13:24  **Watch:** https://youtube.com/watch?v=-d7AExggxKI

> **Naming note:** The "Hermes" in this video is a custom name the channel gives to their own Claude Code overnight agent — it is NOT the third-party "Hermes Agent" product referenced in some other channels, and it is NOT the user's MiniMax Hermes Agent. It is a Claude Code instance (Anthropic) running an agent persona named Hermes. Vendor: Anthropic (Claude Code).

## TL;DR

A practical, no-hype blueprint for running Claude Code as an unattended overnight agent named "Hermes." Two runner paths (Routines cloud-scheduled vs `claude -p` + local cron — note the June 15 2026 billing change moves headless to a metered credit pool), 11 prompts split into scope (Mission Brief), fence (deny/allow settings + PreToolUse hook), self-check (re-read, run test, quote proof or mark BLOCKED), 7 night-shift jobs (inbox drafts, janitor, PR review, morning digest, competitor scan, content drafts, "Tomorrow's First Move"), and a 3-bucket standup report (DONE/BLOCKED/SKIPPED). The three places it breaks: cost (uncapped loop burns a budget), trust (self-grading is the worst grader), scope drift (polite instructions evaporate under context compaction — only permanent files survive).

## Key Insights

- **Two runner paths, different cost models**: Routines = Anthropic cloud, runs with laptop closed, stays on your normal subscription, hourly minimum. `claude -p` + local cron = local control, but starting **June 15 2026** moves to a separate metered credit pool with no auto-overflow. Rule: scheduled and gentle → Routines; heavy and custom → `claude -p` and watch the meter. (01:03, 09:08)
- **Prompt 1 — The Mission Brief, in `CLAUDE.md` not chat**: scope the agent to one task, restrict to specific folders, demand it stop and ask on ambiguity, demand it never claim work it can't prove. Critically: put this in the project's `CLAUDE.md` because over a long run the conversation gets compressed and early instructions get forgotten. (02:11)
- **Prompt 2 — The Fence**: deny list for destructive ops (delete files, force-push, touch secrets/prod) + narrow allow list of only the commands tonight's job needs. Add a PreToolUse hook that physically blocks dangerous commands no matter what the model decides. Deny rules win over everything else. (03:24)
- **Prompt 3 — The Self-Check, not optional**: the agent that wrote the code is the worst judge of whether it works. Before marking anything DONE, re-read the original request, run the test, quote the proof. If no evidence → mark BLOCKED, not DONE. (03:24)
- **Prompt 4 — Inbox triage that drafts but never sends**: anything needing a real decision goes to a `decisions.md` file with the agent's recommended answer. Newsletters: ignore. You wake to a stack of drafts, not a mess. (04:37)
- **Prompt 5 — Codebase Janitor**: the strongest overnight use case. Fix only low-risk stuff (failing tests, lint errors, dead imports, missing coverage on files you touched today). One small commit per branch. If any test goes red → stop. (04:37)
- **Prompt 6 — PR reviewer that never merges**: for every open PR, write a structured review to its own file (summary, risky changes, missing tests, three sharp questions). A human still pulls the trigger. (04:37)
- **Prompt 7 — Ranked morning digest with sources**: 10 bullets, ranked, each with a source link + one line on why it matters to you. Anything unverified gets labeled, not stated. (05:57)
- **Prompt 8 — Competitor scan with honest "no change"**: check specific pages (changelogs, pricing, landing), show actual before/after. If nothing changed, say "no change" — do not pad. (05:57)
- **Prompt 9 — Content drafts tagged [VERIFY]**: from your notes, draft the post, match voice, tag anything uncertain so you check it before publishing. (05:57)
- **Prompt 10 — Tomorrow's First Move**: read calendar + open tasks + what the agent did overnight, then output the single highest-leverage thing to do first + three things to safely ignore. You wake to a decision with reasoning, not a pile of output. (07:14)
- **Break #1 — Cost**: real teams blew through annual AI budgets in months and had to hard-cap each engineer. Use `--max-turns`, watch usage, and start on Routines to stay on the flat subscription. (08:24, 09:40)
- **Break #2 — Trust**: the agent will with total confidence tell you it fixed something it never touched. Permanent rule: the agent that did the work is never the only one allowed to grade it. (09:40)
- **Break #3 — Scope drift**: a small fix at midnight becomes a sprawling refactor by 3am. The narrow mission and deny rules survive **only** because they live in permanent files. (09:40)
- **Prompt 11 — Standup Report (DONE / BLOCKED / SKIPPED)**: one screen in three buckets, evidence attached, exact question for blockers, reason for skips. The line "I would rather see I wasn't sure than a confident wrong answer" flips the agent's personality. (10:54)
- **Rollout rule**: start with one job (the janitor) for a week. Build the trust. Then add the next prompt. (12:03)

## Notable Quotes

> "Two people can set up the exact same night shift and get opposite results. One uses it to move faster on work they deeply understand. The other uses it to avoid understanding their work at all. Hermes cannot tell the difference. You can." (12:36)

> "An agent will, with total confidence, tell you it fixed something it never touched." (09:44)

> "The expensive part of running an agent overnight is not writing the code — it's the running. A loop left alone can rack up a serious bill while you're asleep." (08:31)

> "I would rather see I wasn't sure than a confident wrong answer." (11:21)

## Tools and Resources Mentioned

- **Claude Code** (vendor: Anthropic) — the runtime; `claude -p` headless mode + Routines cloud scheduler + PreToolUse hooks + `CLAUDE.md` for permanent instructions
- **`--max-turns`** flag — hard cap to prevent infinite loops
- **`--allowedTools`** flag — narrow command allow-list
- **Anthropic Routines** — cloud-scheduled runs, runs with laptop closed, stays on normal subscription (hourly minimum)
- **macOS/Linux cron** — local scheduler for `claude -p` path
- **June 15 2026 billing change** — `claude -p` headless moves to separate metered credit pool, interactive sessions unaffected
- **Hyperautomation Labs free Hermes Night-Shift Prompt Pack** — all 11 prompts, copy-paste ready: https://hyperautomationlabs.co/free/hermes-overnight-prompts
- **Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

## Action Items

- [ ] Copy the Mission Brief template into a `CLAUDE.md` in your project before any overnight run
- [ ] Generate a deny/allow settings file (and optionally a PreToolUse hook) before leaving any agent unattended
- [ ] Always include the self-check: "re-read the request, run the test, quote the proof — else mark BLOCKED"
- [ ] Start with one job only (the codebase janitor is the safest) and run it for a week before adding the next
- [ ] If using `claude -p` instead of Routines, set a hard `--max-turns` cap and watch usage — headless moves to a metered pool on 2026-06-15
- [ ] Adopt the DONE / BLOCKED / SKIPPED standup report format with evidence attached

## Open Questions

- How does the metered pool for `claude -p` actually throttle when it runs out — does it pause, fail, or charge overage?
- What is the actual cost-per-hour for typical Routines jobs in production, vs. the flat subscription they run on?
- Does Routines respect custom `--allowedTools` and `CLAUDE.md` rules, or does it run in a sandboxed profile?
- The June 15 2026 billing change is presented as a fact — is this confirmed from Anthropic's official changelog or is it the channel's reporting?
- How do you build a PreToolUse hook that works both on Routines and on local `claude -p` runs?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 13:24 transcript)</summary>

0:00 Open any feed right now and someone is
0:02 selling you the dream. AI that works
0:05 while you sleep. You go to bed and a
0:08 swarm of agents builds your company by
0:10 morning. Here's the part they leave out.
0:14 Most of those overnight demos either
0:17 fake the result or quietly fall apart
0:21 around 2:00 in the morning when the
0:23 agent runs out of money or confidently
0:27 does the wrong thing for 6 hours
0:29 straight. So I built the honest version.
0:33 I gave Claude Code a night shift. a
0:37 single agent I call Hermes.
0:39 And I figured out exactly which prompts
0:43 make it actually finish real work by
0:45 sunrise and which ones just burn tokens
0:48 in the dark. In this video, I'll hand
0:51 you all 11 prompts, the exact setup that
0:55 makes them safe to leave running, and
0:58 the three places this still breaks. No
1:01 hype. Let's wire up Hermes. First, the
1:05 thing nobody explains. There isn't one
1:07 way to run clawed code while you sleep.
1:11 There are two. And picking the wrong one
1:14 is how people get a surprise bill. Path
1:17 one is routines. This runs Hermes on
1:19 Anthropic's own servers on a schedule
1:23 even with your laptop closed. The big
1:25 advantage, it stays on your normal
1:28 subscription, so a nightly run won't
1:30 blow up your bill. The catch, the
1:33 shortest schedule is once an hour. Path
1:35 two is the classic one. You write a tiny
1:38 script with the claud-b command, the
1:40 headless mode, and you let your
1:42 computer's built-inuler chron wake it up
1:46 at night. More control runs locally. But
1:49 starting June 15th, 2026,
1:53 that headless path moves to a separate
1:56 metered credit pool. Your interactive
1:59 sessions are untouched. So the rule is
2:01 simple scheduled and gentle on the
2:04 wallet use routines heavy and custom use
2:08 cla and watch the meter. Now the prompts
2:12 every prompt from here lives inside one
2:15 of those two runners. Prompt one is the
2:18 most important one in the whole video
2:20 because it's the difference between an
2:23 agent that helps and an agent that
2:24 wanders off. I call it the mission
2:27 brief. You do not say go improve my
2:30 project.
2:32 An unsupervised agent told to improve
2:34 things will refactor your entire
2:36 codebase by dawn.
2:38 Instead, you write something like this.
2:41 You are Hermes, my overnight agent.
2:44 Tonight, your only mission is this one
2:47 task. Work only inside these folders. If
2:52 anything is ambiguous or risky, stop and
2:55 write me a question instead of guessing.
2:59 Never claim you did something you can't
3:01 prove. And critically, you put this in
3:04 your project's claude MD file, not just
3:08 the chat.
3:10 Here's why that matters. Over a long
3:12 run, the conversation gets compressed
3:15 and early instructions can get
3:16 forgotten. The clawude MD file survives
3:20 that. Your guardrails have to live
3:22 somewhere permanent. Prompt
3:25 two builds the fence. Before you ever
3:29 leave Hermes alone, you run this once.
3:32 Read my project and propose a settings
3:34 file with two lists. A deny list for
3:37 anything destructive. deleting files,
3:40 force pushing to gate, touching secrets
3:43 or production, and a narrow allow list
3:47 for only the commands tonight's job
3:49 actually needs. Show me before you write
3:52 it. Those deny rules are the real seat
3:56 belt because they win over everything
3:58 else. You can even add a hook, a little
4:02 gate that physically blocks a dangerous
4:04 command before it runs, no matter what
4:06 the model decides. Prompt three is the
4:09 one that separates a useful agent from
4:11 an expensive liar. The selfch check. The
4:15 agent that wrote the code is the worst
4:16 judge of whether it works. So you tell
4:19 Hermes before you mark anything done,
4:22 reread the original request, run the
4:25 actual test and quote the proof. If you
4:28 can't show evidence, mark it blocked.
4:31 Not done. Without that one line, your
4:34 loop just generates confident mistakes
4:36 faster. Now the night shift itself, the
4:40 jobs prompt four, inbox triage. Go
4:44 through the last day of unread mail.
4:47 Draft replies, but never send them.
4:50 Anything that needs a real decision,
4:52 drop into a decisions file with your
4:55 recommended answer. Newsletters, ignore.
4:59 You wake up to a stack of drafts. Not a
5:02 mess. Prompt five, the codebase janitor.
5:07 This is where overnight agents genuinely
5:10 shine. Fix only the boring low-risk
5:13 stuff. Failing tests, lint errors, dead
5:17 imports, missing test coverage on the
5:19 files I touched today. One small commit
5:22 each on a separate branch. And if any
5:26 test goes red, stop. Prompt six, the
5:29 pull request reviewer. For every open
5:32 request, write a structured review to
5:34 its own file, a summary, the risky
5:37 changes, the missing tests, and three
5:41 sharp questions, but it never approves
5:44 and never merges. A human still pulls
5:47 the trigger. Three jobs, all framed the
5:51 same way, narrow, reversible, and they
5:55 hand the final call back to you. Three
5:57 more and these are the ones that feel
6:00 like having a research team on staff.
6:04 Prompt seven, the morning digest. Search
6:07 the web for anything new in the last day
6:09 on the topics I care about. 10 bullets
6:13 ranked each with a source link and one
6:17 line on why it matters to me. And
6:20 anything unverified gets labeled, not
6:24 stated as fact. Prompt eight, the
6:28 competitor scan.
6:30 Check these specific pages, change logs,
6:33 pricing, landing pages for anything that
6:37 changed since yesterday.
6:39 Show me the actual before and after. And
6:42 if nothing changed, just say no change.
6:46 Do not pad it to look busy. That one
6:49 honest instruction saves you from a
6:52 daily wall of fake updates. Prompt nine,
6:56 the content drafts. From my notes this
6:59 week, draft the post match the voice in
7:02 these examples and tag anything you're
7:05 not certain is factually mine so I can
7:07 check it before it goes out. Notice the
7:09 pattern.
7:11 Every single one of these has a built-in
7:13 honesty valve. Prompt 10 ties the whole
7:16 night together, and it's my favorite.
7:19 Tomorrow's first move. Look at my
7:21 calendar, my open tasks, and everything
7:24 you did tonight. Then tell me the single
7:27 highest leverage thing to do first in
7:29 the morning and why. Plus the three
7:34 things I can safely ignore today. Think
7:37 about what that actually does. You don't
7:40 wake up to a pile of raw output you now
7:43 have to sort through. You wake up to a
7:46 decision already made with the reasoning
7:48 attached. That's the real dream. Not a
7:52 thousand agents. One agent that did the
7:55 boring work and then pointed at the one
7:57 thing that matters. But, and this is
8:00 where I have to be honest with you,
8:03 everything I just described assumes
8:06 Hermes behaves all night. It won't, not
8:11 perfectly. So before you go set this up,
8:14 you need to know the three places this
8:17 breaks because they will cost you real
8:20 money and real trust if you ignore them.
8:24 Break number one, cost. This is the plot
8:28 twist nobody puts in the tutorial. The
8:31 expensive part of running an agent
8:34 overnight is not writing the code, it's
8:37 the running.
8:39 A loop left alone can rack up a serious
8:42 bill while you're asleep. And the
8:45 failure everyone in production fears is
8:48 the agent that never stops. Real teams
8:51 hit this. When big companies rolled
8:54 these tools out, some blew through their
8:56 entire annual AI budget in just a few
8:59 months and had to cap each engineer with
9:02 a hard monthly limit per tool. And
9:05 remember that June 15th change,
9:08 if you're using the headless claw-p
9:11 path, those overnight runs draw on a
9:15 separate metered credit pool with no
9:18 automatic overflow. When it's gone, the
9:21 job just fails. So you never leave
9:23 Hermes uncapped. You set a maximum
9:26 number of turns so it physically cannot
9:29 loop forever. You watch your usage and
9:33 honestly this is the single best reason
9:36 to start on routines where you stay on
9:38 your flat subscription. Break number
9:41 two, trust. An agent will with total
9:44 confidence tell you it fixed something
9:48 it never touched. It can read a file,
9:51 assume what's inside, and build on top
9:54 of a thing that isn't even there. This
9:57 is exactly why prompt three, the selfch
10:00 check, is not optional. The rule is
10:03 permanent.
10:05 The agent that did the work is never the
10:07 only one allowed to grade it. You verify
10:10 against reality or you don't trust the
10:13 result. Break number three, scope drift.
10:18 The longer an agent runs unattended, the
10:21 more it wanders.
10:23 A small fix at midnight becomes a
10:25 sprawling refactor by 3 in the morning.
10:28 And here's the subtle part. Over a long
10:31 run, the context gets compressed and the
10:34 polite instruction you typed into the
10:36 chat can quietly vanish. The narrow
10:39 mission and the deny rules survive only
10:42 because you put them in permanent files.
10:44 So the pattern is the whole game. Scope
10:47 it tight, cap it hard, and make it prove
10:50 its work. Do that and the night shift is
10:53 real. Which brings us to the morning and
10:56 the 11th prompt, the standup report.
11:00 When you wake up, you don't want a
11:02 transcript of everything Hermes thought
11:04 about for 8 hours. You want one screen
11:07 in three buckets, done with the evidence
11:10 attached, blocked with the exact
11:14 question it needs you to answer, and
11:16 skipped with the reason why. and you
11:19 tell it plainly, "I would rather see I
11:22 wasn't sure than a confident wrong
11:25 answer."
11:26 That one sentence changes the agent's
11:29 whole personality overnight. It stops
11:32 performing progress and starts reporting
11:34 reality. That's the report that makes
11:38 this trustworthy. You sip your coffee,
11:40 you read 11 lines, and in 2 minutes, you
11:43 know exactly what got done, what needs
11:46 you, and what to ignore.
11:48 The agent worked the night shift. You
11:51 just approved the morning. That's the
11:54 entire system. 11 prompts. One that
11:57 scopes it, two that fence it, seven that
12:00 work, and one that reports back. So,
12:04 should you actually build this? Here's
12:06 the honest decision tree. If you just
12:09 want scheduled, hands off tasks and a
12:12 calm bill, use routines on your
12:15 subscription. If you need heavy custom
12:17 local control, use claude-b with
12:20 youruler and respect the meter. And
12:24 whatever you do, start with one job, not
12:27 11. Run the codebased janitor for a
12:30 week. Build the trust, then add the next
12:33 prompt. Here's the part nobody says out
12:36 loud. Two people can set up the exact
12:39 same night shift and get opposite
12:41 results. One uses it to move faster on
12:45 work. They deeply understand. The other
12:47 uses it to avoid understanding their
12:50 work at all. Hermes cannot tell the
12:53 difference. You can. So build the night
12:56 shift, but stay the engineer who reads
12:59 the morning report. I put all 11 prompts
13:03 ready to copy and paste into one free
13:06 pack. Just comment the word night shift
13:09 and I'll send it straight to you. I drop
13:12 by bite-size AI breakdowns every day on
13:14 Instagram and the full deep dives right
13:16 here on YouTube. Subscribe and I'll keep
13:19 building the systems everyone talks
13:21 about but nobody actually ships.

</details>
