---
title: "Full Hermes Agent Tutorial (Desktop) 🧠 A Useful Agentic AI Workflow"
channel: "Wanderloots"
channel_slug: "wanderloots"
channel_id: "UCFiU1vIpPD3lQltke_18m3A"
published: "2026-07-01"
duration_seconds: 1730
video_id: "GL67DEf2nyI"
url: "https://youtube.com/watch?v=GL67DEf2nyI"
language: "en"
tags: [hermes-agent, nous-research, desktop-app, ollama, gemma, telegram, cron, obsidian, llm-wiki, memory-stack, docker]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-07-02"
---

# Full Hermes Agent Tutorial (Desktop) 🧠 A Useful Agentic AI Workflow

**Channel:** Wanderloots  **Published:** 2026-07-01  **Duration:** 28:50  **Watch:** https://youtube.com/watch?v=GL67DEf2nyI

> **🚨 Naming-collision check (verified):** This video IS about the same Hermes Agent this skill's user runs — vendor confirmed as **Nous Research** (https://hermes-agent.nousresearch.com/) in the video description and pinned comments. The channel "Wanderloots" is a third-party creator, not the Hermes team. Treat the content as a high-priority workflow tutorial for our own product, not as a third-party product reference. Disambiguation source: video description first paragraph and pinned `patreon.com/cw/wanderloots` reference.

## TL;DR
Wanderloots (Callum) walks through a complete Hermes Agent Desktop setup — local Ollama model, Codex cloud profile, custom 64k context variant, 71 built-in skills, persistent `memory.md` + `user.md`, Docker-sandboxed execution, and a Telegram messaging gateway. Builds a daily AI-news briefing bot end-to-end as the worked example: scheduled cron job → Telegram delivery → in-chat feedback loop → skill auto-update. The "self-evolving" pitch: every interaction compounds into the agent's persistent memory and skills, so the system gets smarter without you retraining it. This is the most thorough third-party setup tutorial for the user's own product on the channel list right now.

## Key Insights
- **"Hermes trains itself" — the differentiator vs every other agent.** Most AI tools are as capable on day one as on day 100. Hermes watches for recurring workflows, writes reusable skills from them, and loads those skills the next time it recognizes a similar job. Compounding improvement is built into the architecture, not bolted on (00:10).
- **Hermes is by Nous Research** — the same company that trains open-source LLMs. "Nous = mind/intelligence in Greek, Hermes = messenger god" — together, an agent that thinks and delivers. Open-source, mission-statement aligned ("advance human rights and freedoms"), so you can rely on it for the long haul (00:30, 02:00).
- **Persistent memory via `user.md` + `memory.md`** — Hermes writes these outside the session context. Tell the agent "I'm technical, prefer straight-to-the-point, want to see how the pieces fit together" → it adds a line to `user.md` → that context is injected into every future chat automatically (11:50).
- **The 71 built-in skills are the multiplier.** A skill is a reusable workflow the agent can pull instead of re-deriving. Specific examples in the demo: Obsidian skill, LLM Wiki skill, skill-authoring skill (Hermes builds its own skills). "The more you can piece these skills together, the more you're going to get a workflow that works best for you" (10:15).
- **Local model + cloud profile = power + privacy.** Run Gemma 4 12B locally via Ollama for private work, GPT 5.5 via Codex for power. Each profile has separate skills, soul.md, sessions. Switching profiles is one click in the bottom bar (08:30).
- **Critical Ollama gotcha: Hermes needs 64k context, most Ollama models default to 2k-32k.** Fix: create a custom variant (`Modelfile` with `PARAMETER num_ctx 65536`), build it, set as default. The Hermes agent can build this variant for you if you ask — "just ask Hermes to do it" is the recurring pro tip (04:40).
- **Sandboxed execution is a built-in, not an afterthought.** Settings → Advanced → Execution Backend: Local / Docker / VPS / SSH. Docker is the safe default — protects the rest of your computer from agent errors (13:25).
- **Per-profile working directory = per-profile information boundary.** One profile can work in `/projects/A`, another in `/projects/B`. Memory and skills are isolated per profile by default. "You can keep the separation of information between our private and our cloud providers" (14:15).
- **Memory provider options (exploratory):** Hindsight, Honcho, Nemesis — pluggable external memory layers on top of Hermes' built-in `memory.md`. Wanderloots flags these as future-video territory (14:50).
- **The messaging gateway is a one-click, multi-channel bridge.** WhatsApp, Slack, Google Chat, Discord, Telegram, SMS, email — all configured the same way. BotFather flow for Telegram: create bot → paste token → whitelist your Telegram user ID → restart gateway. After that, every chat is stored in the back end and you can keep talking to your agent from your phone (17:50).
- **The self-evolving loop (the heart of the demo):** Hermes builds a skill called "AI Daily Intel" → runs as a cron job daily → delivers to Telegram → you give feedback in chat → normal Telegram reply flow interprets the feedback → updates the skill file → tomorrow's report uses the updated skill. The skill is a markdown file you can also open in Obsidian and edit manually (20:30, 22:40).
- **Two-cron pattern for true self-evolution:** one cron for "update the skill from yesterday's feedback" (runs before), one cron for "run the daily report with the updated skill" (runs after). This decouples feedback ingestion from report generation and is the production-grade pattern (26:00).
- **Use the browser tool, not the web tool, for built-in web search** — web requires external API keys. Browser works with the OS-level browser automation (and if the browser blocks automation, fall back to a different browser or alternate search strategy) (25:55).
- **Remote gateway pattern:** run Hermes on the desktop, connect to it from a laptop as a remote gateway. Single memory bank across devices, one shared brain. Wanderloots flags this as a planned follow-up video (15:30).

## Notable Quotes
> "Most AI tools are as capable at day one as they are at 100. Hermes is different. The more you use it, the better it gets at your specific work. Not because you trained it or told it to, but because it trains itself." — Wanderloots (00:10)

> "Hermes by Nous Research. Nous meaning mind or intellect in Greek, and Hermes being the messenger god. Together, an agent that thinks and delivers." — Wanderloots (00:35)

> "Just ask Hermes to do it for you and see if it can handle it. If it can't do it off the bat, you can give it a little bit more information or manually set it up, but over time it will learn what you're trying to do. And it might be able to just do it on its own." — Wanderloots (08:55)

> "You can configure this on a per-profile basis. Maybe ChatGPT operates out of one folder and Gemma operates out of another. That way we can keep the separation of information between our private and our cloud providers." — Wanderloots (14:20)

> "Every day the agent runs a search on the web, pulls information based on my particular query, messages me on Telegram with the report, I give it feedback, and it updates the system so tomorrow is even better." — Wanderloots (25:50)

## Tools and Resources Mentioned
- **Hermes Agent Desktop** (Nous Research, https://hermes-agent.nousresearch.com/) — *vendor: same as this user's stack — confirmed via description URL.* The video is a third-party tutorial for our own product.
- **Hermes docs** (https://hermes-agent.nousresearch.com/docs) — authoritative reference for skills, gateways, profiles, MCP, memory.
- **Ollama** — local model server. `ollama pull gemma4` for E4B (small-machine friendly), `ollama pull gemma4:12b` for the 12B variant. Hermes connects via the Ollama endpoint URL.
- **Gemma 4 12B** (Google, via Ollama) — the local-model choice for the demo; needs a custom 64k-context Modelfile variant for Hermes.
- **Codex** (OpenAI) — cloud-profile provider; signs in via OAuth, exposes GPT 5.5 to Hermes through the model picker.
- **Telegram BotFather** — `/newbot` to create the bot, paste token into Hermes' messaging gateway, whitelist your Telegram user ID via `@RawDataBot` to read your ID.
- **Obsidian** — Hermes ships a built-in Obsidian skill so it can write/read notes; the user can manually edit the auto-generated skill markdown files in Obsidian and the next cron run picks up the changes.
- **LLM Wiki skill** (built-in) — Hermes can ingest daily reports into a local LLM Wiki for second-brain-style knowledge accumulation.
- **Memory providers (exploratory):** Hindsight, Honcho, Nemesis — pluggable external memory layers.
- **Docker** — the recommended Execution Backend for sandboxed agent code runs.
- **Gemma 4 E4B** — the "small machine" variant for Hermes local setups on 16GB RAM Mac Minis.
- **Theo's "Two cron jobs" pattern** — one cron to update the skill from feedback, one cron to run the daily report (validated 25:55-26:30).

## GitHub Repos and URLs Referenced
- https://hermes-agent.nousresearch.com/ — official Hermes Agent site (pinned in the description)
- https://hermes-agent.nousresearch.com/docs — Hermes Agent docs (canonical reference for the user's own skill system)
- https://www.patreon.com/cw/wanderloots — Wanderloots' Patreon (linked in description; access to skills, tools, tips)
- https://ollama.com — Ollama download (referenced for local-model setup)

## Action Items
- [ ] After Hermes Desktop install, set up a custom 64k context variant on the local Ollama model — most defaults are 2k-32k and Hermes needs 64k to use tools
- [ ] Run `Ollama ps` to verify the active model's context window before first chat
- [ ] Create a local profile (Gemma) and a cloud profile (Codex or Anthropic) to separate private vs cloud work; switch via the bottom-bar profile picker
- [ ] Set Execution Backend to Docker so agent code runs in a sandbox
- [ ] Connect the Telegram messaging gateway (BotFather flow + whitelist your user ID) for phone-to-agent access
- [ ] Build the daily-briefing bot as the worked example: skill markdown file → cron job → Telegram delivery → in-chat feedback → second cron to update the skill
- [ ] Open the auto-generated skill markdown in Obsidian; edit manually if needed; next cron run picks up changes
- [ ] (If multi-device) Connect a laptop to the desktop Hermes back end as a remote gateway for a single shared memory bank

## Open Questions
- Does the Obsidian skill ship as bidirectional (Hermes reads *and* writes), or is it write-only with Obsidian as the human-edit surface?
- How does Hermes handle skill conflicts when two auto-generated skills overlap on the same workflow — last-write-wins, priority ordering, or LLM-merged?
- For the memory-provider integrations (Hindsight, Honcho, Nemesis), is the integration a plugin or a config swap?
- What's the right cadence for the "skill updater" cron — same day (risk: feedback incomplete) or next morning (risk: report uses yesterday's skill)?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 28:50 transcript)</summary>

See `channels/wanderloots/transcripts/2026-07-01_hermes-agent-desktop-full-setup.txt` for the full transcript.

Highlights from the transcript (sampling): Opens with the "trains itself" pitch and the Nous Research mission statement. Walks through macOS Desktop install. Sets up Ollama as the local provider, hits the 64k-context wall, builds a custom Gemma 4 64k variant via Modelfile. Connects Codex for the cloud profile. Builds "AI Daily Intel" skill via the agent itself. Configures Telegram messaging gateway (BotFather + RawDataBot for user ID). Schedules cron for 8:00 AM daily. First dry-run delivers to Telegram, user gives feedback, skill updates. Closes with the two-cron pattern (skill-updater before, daily-report after) for the production self-evolution loop.

</details>