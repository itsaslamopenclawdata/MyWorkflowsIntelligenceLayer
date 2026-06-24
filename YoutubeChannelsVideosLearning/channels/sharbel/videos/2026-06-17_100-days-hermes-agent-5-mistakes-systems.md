---
title: "100 Days With Hermes Agent in 21 Minutes"
channel: "Sharbel A."
channel_slug: "sharbel"
channel_id: "UCxLzvFAUbpdNUIh0hGsEH0w"
published: "2026-06-17"
duration_seconds: 1279
video_id: "sCa3BtpkziQ"
url: "https://www.youtube.com/watch?v=sCa3BtpkziQ"
language: "en"
tags: [hermes-agent, hermes-desktop, sub-agents, crons, webhooks, telegram, mission-control]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-24"
---

# 100 Days With Hermes Agent in 21 Minutes

**Channel:** Sharbel A.  **Published:** 2026-06-17  **Duration:** 21:19  **Watch:** https://www.youtube.com/watch?v=sCa3BtpkziQ

## TL;DR
After 100 days using Hermes Agent, Sharbel distills the gap between "smarter search box" usage and a real operating system into five architectural upgrades: (1) turn manual decisions into repeatable loops + crons, (2) split Telegram into per-context topics as workspaces, (3) deploy specialist sub-agents instead of one overpowered assistant, (4) add webhooks as event triggers alongside time-based crons, (5) build a "mission control" dashboard (live Vercel site behind Google auth) for visibility beyond chat. The core insight: don't ask "what can Hermes answer?" — ask "what decisions do I keep making manually?" The answer to that question is your loop. His open-source specialist agents Nova (YouTube) and Sage (X/content) are linked in the description.

## Key Insights
- Mistake #1: Treating Hermes as a search box — "summarize this PDF" doesn't compound. The upgrade is asking "what decisions do I keep making manually?" and turning THAT into a loop (0:50, 2:25)
- A loop example: YouTube ideation — check posted videos, rejected ideas, Notion board, current demand, competitor outliers, then return ONE next video to film with proof needed + first-30-sec hook (1:30)
- Manual-first rule: prove the loop works manually (Hermes can fetch every piece individually + apply rules correctly) BEFORE scheduling it as a cron (3:05)
- Cron = time-based trigger ("every morning do X"); Webhook = event-based trigger ("when Notion card moves to 'film,' do X") (13:00)
- Mistake #2: One giant junk-drawer chat. Fix = Telegram topics as workspaces: one per context (YouTube, X, general admin, React opportunities). Each topic has its own operating rule (5:40)
- "Every workspace starts having a job" — the agent no longer guesses what mode it's in because context is pre-loaded by the topic (7:00)
- Mistake #3: One agent doing everything. Fix = sub-agents. Main agent coordinates; specialists (e.g., "check my pipeline," "check competitors," "check demand") return clean reports; main agent decides (8:25)
- The "plumber vs. dentist" rule: don't make one agent do everything. Each agent needs its own memory, permissions, skills, lane (11:00)
- Sharbel's specialist agents: **Nova** (YouTube — checks posted videos, uses VidIQ, knows his title/retention/thumbnail preferences) and **Sage** (X/content strategy), both open-source on his GitHub (11:25)
- Mistake #4: Time triggers only. Webhooks are where "Hermes starts to feel alive" — Notion card moves to "film" tab triggers research + validation; GitHub PR opens triggers risk review; form submit triggers lead research; customer payment triggers daily summary (13:30)
- If a tool doesn't support webhooks natively, use a polling cron (check every 5 min, compare what changed, only act when the right thing happened) (15:50)
- Mistake #5: Chat is bad for visibility. Build a "mission control" — live Vercel website connected to workflows, behind Google/Gmail auth, mobile-accessible (17:10)
- Mission control gives confidence to let agents do more because you can see what's running, what's queued, what failed (18:45)
- Sharbel's build order from scratch: one boring loop → one Telegram workspace → one specialist agent → one scheduled cron → one event trigger → mission control last (19:05)
- Open-source links: Nova + Sage agents on his GitHub; mission control template also free (20:25)
- The meta-lesson: "Do not just ask Hermes to help. Teach it how your work runs. That is the leverage." (20:55)

## Notable Quotes
> "Don't ask what can Hermes answer for me. Ask what decisions do I keep making manually? Because that is usually where the loop is." — 02:25
> "Every workspace starts having a job. When I message Hermes in the YouTube topic, Hermes does not need to guess what mode it's in." — 06:55
> "More agents does not automatically mean better. More focused agents means better." — 11:00
> "Cron handles time. Webhooks handle events. Webhooks is where Hermes starts to feel alive." — 13:05
> "Mission controls give you the confidence to let Hermes do more because you can actually see what it is doing." — 18:45

## Tools and Resources Mentioned
- **Hermes Agent** (third-party product, NOT MiniMax Hermes) — Sharbel uses this as his primary agent platform; topic of his 100-day retrospective
- **Hermes Desktop** — desktop GUI client that makes Hermes' files, tools, sessions, skills, crons, webhooks visible and switchable
- **Telegram topics** — used as per-context workspaces (YouTube, X, general, React)
- **Notion** — content board that fires webhooks when cards move between columns
- **Vercel** — hosts Sharbel's mission-control dashboard
- **Google/Gmail auth** — gates the dashboard so it's not publicly accessible
- **Cron + webhook polling fallback** — covered as a pattern for tools without native webhook support
- **Vendor disambiguation:** "Hermes Agent" and "Hermes Desktop" in this video refer to a THIRD-PARTY product, NOT the user's MiniMax Hermes Agent (this skill's host platform). Sharbel's channel is a generalist creator who happens to use a similarly-named product. The architectural patterns (specialist agents, Telegram topics, webhooks, mission control) are domain-portable, but the product stack itself is unrelated to the user's stack.

## GitHub Repos and URLs Referenced
- Sharbel's GitHub — links in description for the **Nova** (YouTube specialist) and **Sage** (X/content specialist) agent definitions, open-source
- Sharbel's GitHub — link for the **mission control** template (Vercel + Gmail auth), open-source

## Action Items
- [ ] List 5 manual decisions you make more than once a week — pick the most repeatable and write a loop prompt for it
- [ ] Set up 3 Telegram topics (main work, content, admin) with one operating rule each
- [ ] Build or fork one specialist sub-agent profile (start with the task you loop most often)
- [ ] Add ONE webhook trigger to your most-used tool (Notion column move, GitHub PR open, form submit) — run the loop on the event
- [ ] If you're at 5+ crons/webhooks already, build a single-page mission control dashboard (Vercel + auth) listing run history
- [ ] Read Sharbel's open-source Nova and Sage agent definitions and copy the structure even if you don't use his stack

## Open Questions
- What's the right threshold for splitting one specialist agent into two? Sharbel implies "different job = different memory" but doesn't quantify
- For the polling-cron fallback pattern, what cadence is too aggressive (YouTube rate-limits? Notion API quotas?) before you give up and migrate to a webhook-native tool?
- Does the mission-control pattern hold up when you have 30+ sub-agents across 10+ tools, or does it collapse into a notification overload problem?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 21:19 transcript)</summary>

# Transcript: 100 Days With Hermes Agent in 21 Minutes
# Channel: Sharbel A.
# Duration: 1279s
# Video ID: sCa3BtpkziQ

0:00 You see people online using Hermes to
[...full 19,952-character transcript saved in matching .txt file...]
21:13 So,
21:15 I'll see you there.

</details>
