---
title: "The End of SaaS Just Got Open-Sourced — Builder.io's Agent-Native"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-26"
duration_seconds: 568
video_id: "IX6hCv5PGW0"
url: "https://youtube.com/watch?v=IX6hCv5PGW0"
language: "en"
tags: [agent-native, saas-disruption, builder-io, forkable, open-source, coding-agents, claude-code, codex, open-source-saas]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-27"
---

# The End of SaaS Just Got Open-Sourced — Builder.io's Agent-Native

**Channel:** Hyperautomation Labs  **Published:** 2026-06-26  **Duration:** 00:09:28  **Watch:** https://youtube.com/watch?v=IX6hCv5PGW0

## TL;DR
**Builder.io's Agent-Native** is a forkable open-source framework for building agent-native SaaS apps. Instead of renting software, you fork the repo, point Claude Code/Codex/Cursor at it, and run your own. The pitch: invert the 15-year SaaS deal — instead of "rent forever, own nothing," you own the code, the agent is built in (not bolted on), and the software adapts to you because the agent can change it. The two killer slash commands: `/visual-plan` (reviewable plan with diagrams before any code) and `/visual-recap` (PR-to-visual-summary with a shareable link).

## Key Insights
- **The pitch in one line:** "Stop renting your software. Start forking it." (timestamp 9:03)
- **The old SaaS deal, for 15 years:** "Rent the software. The vendor owns the code. The vendor controls the AI. And you adapt your business to fit the app." (timestamp 7:40)
- **Agent-Native inverts every part of that:** "You own the code. The agent is built in, not bolted on. And instead of you adapting to the software, the software adapts to you — because the agent can change it." (timestamp 7:50)
- **The two scaffold paths:** `npm create agent-native@latest` for a full app (UI mode with a visual canvas, or headless CLI mode that walks you through calling your first action and agent). Then `cd`, `install`, `run dev`. "A few minutes and you're running your own forkable agent-native SaaS app on your own machine." (timestamp 4:50)
- **The no-scaffold path: drop it in as a skill.** `npx @agent-native/core/skills/add visual-plan` adds two slash commands to the coding agent you already use (Claude Code, Codex, Cursor, Copilot, etc.) — **without writing a new app.** (timestamp 6:05)
- **`/visual-plan` — reviewable plans with diagrams, interface wireframes, and a file-by-file map.** "Before your agent writes any code, it opens a structured, reviewable plan with diagrams, interface wireframes, and a file-by-file map you can comment on and approve." (timestamp 6:25)
- **`/visual-recap` — PR-to-visual-summary.** "After the changes land, it turns the whole pull request into a high-level visual summary with a shareable link instead of a raw wall of diff." (timestamp 6:40)
- **The honest framing:** "This is early. It's version 0.79. It moves fast. And it is built for people who write code, not for total beginners yet. You bring your own database, your own host, your own model. It's a framework, not a magic button. And it does not delete every SaaS tomorrow." (timestamp 6:55)
- **What it doesn't do (and shouldn't pretend to):** "Plenty of tools you'll happily keep renting. But the direction is the thing. The moment your software is a folder of code you own, that an agent can read, run, and improve, the old deal where you rent forever and own nothing starts to look like a choice instead of the only option." (timestamp 7:18)
- **The "forkable today, free" promise:** "That future just became forkable today for free." (timestamp 8:17)

## Notable Quotes
> "The moment your software is a folder of code you own, that an agent can read, run, and improve, the old deal where you rent forever and own nothing starts to look like a choice instead of the only option." — 7:30
> "Stop renting your software. Start forking it." — 9:03
> "It's a framework, not a magic button. And it does not delete every SaaS tomorrow." — 7:00

## Tools and Resources Mentioned
- **Agent-Native by Builder.io** (vendor: Builder.io) — the open-source framework; not the same as Google's "Antigravity" (a Google product with a colliding name). Note: this is a *third-party* SaaS framework, not the user's MiniMax Hermes Agent.
- **`npm create agent-native@latest`** — full app scaffold (UI or headless mode)
- **`npx @agent-native/core/skills/add visual-plan`** — adds `/visual-plan` + `/visual-recap` to your existing coding agent
- **Claude Code** (vendor: Anthropic) — one of the supported coding agents
- **Codex** (vendor: OpenAI's coding agent — *not* the user's stack)
- **Cursor** — supported coding agent
- **GitHub Copilot** — supported coding agent
- **Free "agent native playbook"** — comment "fork" on the video for the six apps, the SaaS tools they replace, the create command, the skill, and the build-your-first checklist
- **"The complete Claude Code guide"** / **"the OpenAI Codex guide"** / **"Claude Co-work sales guide"** / **"Claude certified architect prep kit"** — paid guides linked in the video description

## GitHub Repos and URLs Referenced

- **Agent-Native** — https://github.com/BuilderIO/agent-native (or `npm create agent-native@latest`) — Builder.io's open-source framework for forkable agent-native SaaS apps. The companion skill package is `npx @agent-native/core/skills/add visual-plan` for adding the `/visual-plan` and `/visual-recap` slash commands to any existing coding agent (Claude Code, Codex, Cursor, GitHub Copilot).

## Action Items
- [ ] Run `npx @agent-native/core/skills/add visual-plan` in your Claude Code/Codex/Cursor setup this week. You don't need to scaffold an app to get the planning discipline.
- [ ] On your next feature, before any code is written, demand `/visual-plan` produce a reviewable file-by-file map. Compare to the agent's "I just did it" behavior.
- [ ] After your next PR, demand `/visual-recap` produce a shareable visual summary instead of dumping a diff. Compare to your team's current PR-review ergonomics.
- [ ] If you've been on the fence about whether to fork vs. rent any tool, treat Agent-Native as the proof that "forkable" is a real third option, not a pipedream. Audit the 1-2 most expensive SaaS bills on your stack — could a forkable open-source replacement + your coding agent get you 80% of the value?
- [ ] Don't adopt Agent-Native for anything customer-facing yet — v0.79 is explicitly "built for people who write code, not for total beginners." Treat it as a fork-and-shape primitive, not a SaaS-replacement turnkey.

## Open Questions
- Agent-Native is v0.79 as of 2026-06-26. What's the path to v1.0, and which features are gated behind that?
- "You bring your own database, your own host, your own model" — which models are first-class? Does the framework assume Anthropic, OpenAI, or is it provider-agnostic with adapters?
- The "fork" model is exciting for solo devs but raises questions for teams: how do you keep N forks of the same Agent-Native template in sync? Is there a fork-merge story?
- Six app templates are mentioned in the free playbook. Which six? The video doesn't list them.
- The "Co-work sales guide" / "certified architect prep kit" references suggest Anthropic itself is positioning a partner/cert ecosystem around Claude Code — how does that interact with Agent-Native being a parallel third-party framework?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 00:09:28 transcript)</summary>

[Full transcript stored at channels/hyperautomation-labs/transcripts/2026-06-26_end-of-saas-agent-native-builder-io.txt]

</details>
