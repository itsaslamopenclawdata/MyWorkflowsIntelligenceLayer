---
title: "Building an App with Zero Coding Skills — Kostyantyn Vlasenko's 6-Week Respiro Story"
channel: "Eddy Explainer"
channel_slug: "eddy"
channel_id: "UCZ_4HvkkWlRdM8t5nOiOiYA"
published: "2026-06-14"
duration_seconds: 400
video_id: "e53ubwpu2Oo"
url: "https://www.youtube.com/watch?v=e53ubwpu2Oo"
language: "en"
tags: [claude-code, no-code, multi-agent, orchestration, respiro, mindfulness, eddy, case-study]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# Building an App with Zero Coding Skills — Kostyantyn Vlasenko's 6-Week Respiro Story

**Channel:** Eddy Explainer  **Published:** 2026-06-14  **Duration:** 06:40  **Watch:** https://www.youtube.com/watch?v=e53ubwpu2Oo

## TL;DR
Case study of Kostyantyn Vlasenko, a non-technical project manager from Kyiv, who shipped a live iOS app (Respiro — a stress-detecting mindfulness app) to the Apple App Store in 6 weeks with zero lines of code written by hand. His unlock: treating Claude Code agents inside his IDE exactly like the stakeholder-and-team-management work he'd done for a decade at Mythical Games. He built a multi-agent architecture to orchestrate the AI engineering team. The key insight is that PMs have the right instinct for managing agent teams because it's the same job — and the missing market is "real-time stress detection from personal devices" which standard mindfulness apps are blind to.

## Key Insights
- **The setup.** Kostyantyn Vlasenko, project manager at Mythical Games in Kyiv. Zero lines of code written in his entire life. Not a hobbyist, never dabbled in Python. His expertise: stakeholder pressure and team dynamics. (0:15–0:50)
- **The result.** Six weeks from blank screen to live, fully functional iOS app on the App Store. "In the traditional tech world, six weeks is barely enough time to hire a single developer." (0:54–1:10)
- **The unserved problem.** Standard mindfulness apps gently remind you to breathe at a scheduled time (say 10pm) but are "entirely blind to when you actually need the help. They just couldn't detect real-time stress signals from personal devices to jump in when it mattered most." The app's own demo: right before Kostyantyn's interview, the app detected elevated anxiety and proactively suggested a box breathing session. (1:18–1:58)
- **The mindset shift.** "I realized this was the same thing, only managing agents inside my IDE." He didn't treat AI as fancy autocomplete. He leveraged his actual superpower (PM experience) to orchestrate an AI engineering team. (2:00–2:30)
- **The architecture.** "He called his app Respiro, and he structured it using a remarkably sophisticated multi-agent architecture. He didn't just casually ask Claude to build the app." (2:30–2:50)

## Notable Quotes
> "Zero. None. That is the exact number of lines of code Kostyantyn had written in his entire life before he decided to build his own software." — 0:34

> "His mindset shift was brilliant. As he put it, 'I realized this was the same thing, only managing agents inside my IDE.'" — 2:13

## Tools and Resources Mentioned
- **Claude Code** — the AI tool Kostyantyn used to build Respiro. Used as an orchestrated team of agents, not a single autocomplete.
- **Respiro** — the resulting iOS app; a real-time stress-detecting mindfulness app.

## GitHub Repos and URLs Referenced
- (No specific GitHub repos or URLs cited in this video.)

## Action Items
- [ ] If you have PM / coordination / team-management experience and zero coding background, study this case as proof that the "I'm not technical enough" objection has a known workaround. Try Claude Code on a real internal tool this week.
- [ ] The unserved problem framing is the actual product insight — "scheduled reminders vs. real-time stress detection" — and it should generalize: most "X for mindfulness / focus / habits" apps are blind to biometric or context signals. Find a niche where a low-friction, signal-driven trigger beats a calendar trigger.
- [ ] Treat any AI coding tool as a team to be managed, not a thing to be prompted. Apply PM best practices: scope, decomposition, dependency tracking, verification gates, kill switches.

## Open Questions
- What's the actual multi-agent architecture Respiro uses? The video teases it ("remarkably sophisticated") but doesn't enumerate the agents or their roles.
- The "managing agents like people" framing is clean. What specific PM rituals (standups, retros, gantts) translate to agent orchestration, and which are dead weight?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 6:40 transcript)</summary>

0:01 [snorts]
0:03 [music]
0:06 >> All right, let's dive right into this
0:07 explainer. Today, we are unpacking an
0:10 absolutely wild, completely true story
0:12 about a guy named Kostyantyn Vlasenko.
0:15 He's a non-technical project manager
0:17 from Ukraine who completely defied all
0:19 traditional odds to launch a really
0:21 sophisticated tech startup. Seriously,
0:23 if you've ever thought that lacking a
0:25 computer science degree meant you
0:27 couldn't build a complex product, well,
0:29 this story is absolutely going to change
0:30 your mind. Zero. None. That is the exact
0:34 number of lines of code Kostyantyn had
0:36 written in his entire life before he
0:38 decided to build his own software. He
0:40 wasn't some weekend hobbyist programmer,
0:42 and he didn't even dabble in Python. As
0:44 a project manager at Mythical Games in
0:46 Kyiv, his real expertise was in managing
0:48 stakeholder pressure and team dynamics,
0:50 definitely not writing syntax.
0:54 But here's the crazy part. Six. Six
0:57 weeks. That's all the time it took him
0:59 to go from a totally blank screen to a
1:01 live, fully functional iOS app on the
1:03 Apple App Store. Now, in the traditional
1:05 tech world, six weeks is barely enough
1:07 time to hire a single developer. But
1:09 Kostyantyn completely bypassed all those
1:11 traditional hurdles using an AI tool
1:13 called Claude Code. Part one, the
1:16 unsolved stress problem.
1:18 So, to understand his motivation,
1:20 Kostyantyn was basically scratching a
1:22 deeply personal itch. His decade in
1:24 project management was incredibly
1:26 demanding, and he relied really heavily
1:28 on breathing techniques.
1:30 But he noticed this massive flaw in the
1:32 market. Standard mindfulness apps might
1:35 gently remind you to breathe at, say,
1:37 10:00 p.m., but they are entirely blind
1:39 to when you actually need the help. They
1:41 just couldn't detect real-time stress
1:43 signals from personal devices to jump in
1:45 when it mattered most. Actually, get
1:47 this. Right before his interview for the
1:48 article we're exploring today, his own
1:49 app detected elevated anxiety and
1:51 proactively suggested a box breathing
1:53 session. How cool is that?
1:58 Part two, managing agents like people.
2:00 He's on vacation up in the
2:02 stunning Ukrainian mountains, and he
2:04 just decides he's going to build this
2:06 solution himself. But he didn't treat AI
2:08 as some fancy autocomplete tool. His
2:10 mindset shift was brilliant. As he put
2:12 it, "I realized this was the same thing,
2:15 only managing agents inside my IDE."
2:18 Instead of trying to learn how to type
2:19 out code, he leveraged his actual
2:21 superpower, his project management
2:23 experience, to literally orchestrate an
2:25 AI engineering team. He called his app
2:27 Respiro, and he structured it using a
2:30 remarkably sophisticated multi-agent
2:32 architecture. He didn't just casually
2:33 ask Claude to buil

</details>
