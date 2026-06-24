---
title: "7 Hermes Desktop Hacks That Will Change Your Life"
channel: "Sharbel A."
channel_slug: "sharbel"
channel_id: "UCxLzvFAUbpdNUIh0hGsEH0w"
published: "2026-06-21"
duration_seconds: 1503
video_id: "6kGXn-j16QM"
url: "https://www.youtube.com/watch?v=6kGXn-j16QM"
language: "en"
tags: [hermes-desktop, hermes-agent, sessions, skills, profiles, webhooks, gateway]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-24"
---

# 7 Hermes Desktop Hacks That Will Change Your Life

**Channel:** Sharbel A.  **Published:** 2026-06-21  **Duration:** 25:03  **Watch:** https://www.youtube.com/watch?v=6kGXn-j16QM

## TL;DR
Sharbel's seven concrete workflows for turning Hermes Desktop from a chat app into a command center: (1) make the agent interview you with embedded questionnaires before executing taste/budget/location-dependent tasks; (2) pin frequently-used sessions as recurring workspaces; (3) build skills — reusable operating procedures with explicit "when to use, what to check, what mistakes to avoid, what output looks like"; (4) wire webhooks to trigger workflows from external events; (5) keep files/tools/skills in dedicated project folders so the desktop UI surfaces the actual operating layer; (6) create separate specialist profiles (e.g., Nova for YouTube) with isolated memory, skills, sessions, soul files, and per-profile model choices; (7) point the desktop client at a remote gateway (Mac mini / VPS) so a 24/7 machine runs the agent while you operate from any laptop.

## Key Insights
- Hack #1 — Interview prompt: "Help me find homes in France. Use ask user question until you reach clarity." The desktop UI renders embedded questionnaires, forcing the agent to extract budget/purpose/location/deal-breakers before acting (1:55)
- "A good assistant does not just run with a bad brief. A good assistant asks the right questions until the brief is worth acting on" (5:20)
- Hack #2 — Pin sessions. Each pinned session is a workspace with its own decision trail (YouTube channel, home purchase, investments, email triage). You stop re-explaining context every morning (5:45)
- Hack #3 — Skills. Sharbel's recurring YouTube-upload checklist became a skill: "use vidIQ before tags, no m-dashes, no generic AI descriptions, label evidence, verify before claiming done" (7:55)
- Skill format: tell the agent **when** to use it, **what** to check, **what workflows** to follow, **what mistakes** to avoid, **what the output** should look like (8:20)
- Skills are version-controllable like code — Sharbel iterates them, the agent loads the latest version, no prompt drift (10:30)
- Hack #4 — Webhooks. Real-world examples he runs: Notion card moves to "Film" → research + validation; new GitHub PR → risk review; YouTube upload → performance tracking + title/click-through-rate review + edit suggestions (15:00)
- "The system reacts the moment I upload a video — it sees, it tracks, it suggests edits" — that's what makes the desktop feel like infrastructure, not a chatbot (17:35)
- Hack #5 — Project folders. Files, tools, skills, cron jobs, webhooks, sessions are surfaced as actual folders in the desktop UI; you navigate the agent the same way you navigate your OS (12:50)
- Hack #6 — Specialist profiles. Nova (YouTube) has its own role, memory, skills, sessions, soul file, and model choice. Sharbel can switch profiles instantly without context bleed (18:00)
- The "dentist vs. heart surgeon" analogy: forcing one agent to do every job produces mediocre output everywhere; profiles isolate roles so each agent does its job at the right level of seniority (20:25)
- Hack #7 — Remote gateway. Point the desktop client at a Mac mini / VPS running the agent instance 24/7. Sharbel's main Hermes lives on a Mac mini, his laptop is just the UI (21:15)
- Gateway setup: settings → gateway → choose local vs. remote → input URL → test → save. Different agents can connect to different gateway instances under one UI (22:50)
- The through-line: Desktop isn't interesting because it prettifies chat. It's interesting because it makes agent infrastructure (projects, sessions, skills, crons, webhooks, profiles, gateways) **visible and operable** — turns Hermes from "something you prompt" into "something you operate" (24:00)
- "If you connect it to a machine that stays on all the time — Mac mini, VPS, anything — that is when it starts to feel like a real AI employee. Not because it's magic, because it finally has somewhere to live." (24:30)

## Notable Quotes
> "A good assistant does not just run with a bad brief. A good assistant asks the right questions until the brief is worth acting on." — 05:20
> "Pin sessions turn Hermes from random chats into recurring workspaces." — 07:10
> "More agents does not automatically mean better. More focused agents means better." — (companion video)
> "Profiles let you separate those jobs instead of forcing one messy assistant to do all the different jobs." — 20:25
> "Hermes Desktop is not interesting because it makes your chat interface prettier. It is interesting because it makes agent infrastructure easily understandable." — 24:00

## Tools and Resources Mentioned
- **Hermes Desktop** — GUI client that makes agent infrastructure (files, tools, sessions, skills, crons, webhooks, profiles, gateways) navigable (the entire video topic)
- **Hermes Agent** — the underlying agent platform Hermes Desktop is a client for (third-party product, see vendor note)
- **Notion** — content board, triggers webhooks on column changes (15:00)
- **YouTube Data API** — powers the post-upload performance tracking webhook (16:55)
- **vidIQ** — YouTube tag/SEO tool referenced inside the YouTube-upload skill (8:00)
- **Mac mini / VPS** — physical 24/7 host machines for the remote-gateway pattern (21:30)
- **Vendor disambiguation:** "Hermes Agent" and "Hermes Desktop" in this video are a THIRD-PARTY product (Sharbel's stack), NOT the user's MiniMax Hermes Agent. The architectural patterns (profiles, sessions, skills, webhooks, gateways, project folders) are domain-portable. If you operate on the user's MiniMax Hermes, look for the equivalent profile/skill/cron/webhook concepts in that platform's own CLI/TUI rather than expecting a "Hermes Desktop" GUI.

## GitHub Repos and URLs Referenced
- Sharbel's GitHub — open-source agent definitions (Nova, Sage, and others) referenced in companion videos; same author
- Note: this specific video does not link a unique repo beyond the recurring specialist-agent drop

## Action Items
- [ ] Rewrite your 3 most-repeated prompts as interview prompts ("ask user questions until clarity, then act")
- [ ] Pin your 3 most-used sessions; never start from scratch on those again
- [ ] Pick one repeatable checklist (YouTube upload, blog publish, deploy, invoice) and convert it to a skill with the "when/what/mistakes/output" structure
- [ ] Wire ONE webhook today — start with Notion column change → research loop, or GitHub PR open → risk review
- [ ] Create a specialist profile for your highest-leverage recurring domain (YouTube, sales, code review) with isolated skills + memory
- [ ] If your agent runs on a laptop you close, set up a remote gateway on a Mac mini / VPS and connect your desktop client to it

## Open Questions
- How do you version and rollback skills once they become load-bearing for production workflows?
- Does pinning too many sessions dilute the value of each pin — what's the right ceiling?
- What's the failure mode when the remote gateway goes offline while your desktop client is connected?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 25:03 transcript)</summary>

# Transcript: 7 Hermes Desktop Hacks That Will Change Your Life
# Channel: Sharbel A.
# Duration: 1503s
# Video ID: 6kGXn-j16QM

0:00 Hermes Desktop looks like a cleaner way
[...full 24,106-character transcript saved in matching .txt file...]
25:01 I'll see you there.

</details>
