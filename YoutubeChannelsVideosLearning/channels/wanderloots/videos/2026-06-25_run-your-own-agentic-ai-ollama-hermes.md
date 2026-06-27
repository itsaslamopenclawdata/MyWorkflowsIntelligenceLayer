---
title: "Run Your Own Agentic AI? 🦙 Full Ollama Setup + Hermes Workflow"
channel: "Wanderloots"
channel_slug: "wanderloots"
channel_id: "UC5JVXy7ucMCVChAOmjVsEPw"
published: "2026-06-25"
duration_seconds: 957
video_id: "4KXLW9Y1r4c"
url: "https://youtube.com/watch?v=4KXLW9Y1r4c"
language: "en"
tags: [ollama, gemma-4, hermes-agent, open-claw, local-llm, agent-harness, privacy, context-window, custom-endpoint, gcp]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-27"
---

# Run Your Own Agentic AI? 🦙 Full Ollama Setup + Hermes Workflow

**Channel:** Wanderloots  **Published:** 2026-06-25  **Duration:** 00:15:57  **Watch:** https://youtube.com/watch?v=4KXLW9Y1r4c

> ⚠️ **Vendor disambiguation:** This video demonstrates running local Ollama models with **"Hermes Agent"** (a third-party product referenced by Wanderloots on screen) and also mentions **"Open Claw"** and **"Agent Harness"** as separate tools in the same ecosystem. **These are NOT the user's MiniMax Hermes Agent** (the user's own stack) or any of its sub-tools. Treat this video as a generic "run a local LLM and point a third-party agent at it" tutorial.

## TL;DR
Wanderloots walks a 100% local / 100% private AI setup: install **Ollama** (CLI or desktop), pull **Gemma 4** in the E4B "effective-parameter" variant (8 GB RAM minimum), create a **64K context variant** (Hermes Agent and similar tools require 64K context — most Ollama defaults are only 2,048–32K), and point a third-party agent (Hermes, Claude Code, Codex, Open Claw, etc.) at the local Ollama endpoint. The "endpoint" string is what makes the agent talk to the local model instead of ChatGPT. The whole loop: install → pull → variant for 64K context → set custom endpoint in agent → chat with full privacy.

## Key Insights
- **The 100% privacy promise:** "Every single message I send to Gemma 4 stays entirely on my computer. It's full privacy." (timestamp 7:15)
- **The install path:** `ollama.com` → desktop app (which installs the CLI in terminal as a byproduct) or CLI directly. (timestamp 0:30)
- **E4B / E2B = "effective parameters" — smaller parameter counts that operate like bigger models via per-layer embeddings.** "E2B, you probably want to run on a low-end laptop with only maybe 4 GB of RAM, or on a phone. This is good for running on a mobile device. The E4B can handle something with 8 GB of RAM, which should be almost everyone's laptop. And then if you're getting into the 31, that's where you need a much bigger RAM." (timestamp 5:00)
- **The pull command:** `ollama pull gemma4:e4b` — pulls manifest, writes, installs. Verify with `ollama list`. (timestamp 6:00)
- **Run it standalone:** `ollama run gemma4:e4b` — instant local chat in the terminal. "That just took from start to finish maybe 1 minute or so to get a local model running on my computer." (timestamp 7:05)
- **The killer gotcha: most Ollama models default to a 2,048–32,768 token context window.** "A lot of Ollama models use a 2048 token context limitation and [the third-party] Hermes requires 64,000 to give your agent tools." (timestamp 9:00) Without solving this, your agent harness can't actually use the model.
- **Fix 1 — per-model variant:** Pull the model, set the context to 64K, save as a new variant name (e.g. `gemma4:e4b-64k`). "It's just a different way of launching the same underlying model." Doesn't duplicate the 10GB base weights. (timestamp 9:13)
- **Fix 2 — system-level default in Ollama settings:** Bump "context length" to 64K and every new model launches at 64K. Use this if you want all your local models at 64K; use the per-model variant if you only want one model at 64K. (timestamp 10:18)
- **The endpoint string — the bridge from agent to local model:** "It's just a string of numbers that is an address based on what's running or can run locally on our computer. This is an Ollama native endpoint, and then if we add a v1, it makes it compatible with what's called an OpenAI endpoint. So, that's what a lot of platforms use." (timestamp 11:24)
- **The integration step:** In the third-party Hermes Agent, go to Models → Custom Endpoint → paste the endpoint string → click Connect. The model now shows up in the model's list. (timestamp 11:43)
- **The "spawning an agent inside Ollama" pattern:** "What Hermes is doing is it's spawning a little agent inside of Ollama, a locally running model. And then once I get that started up, it's warmed up, I'll be able to have a conversation, and it can run for a few minutes before it goes back to sleep." (timestamp 12:22)
- **"Always on" tweak:** Modify Ollama settings so the model doesn't unload after a few minutes. You can then leave the agent running 24/7. (timestamp 13:15)
- **The cross-machine pattern (teased, not full tutorial in this video):** "If you have a more powerful system, like a desktop computer with bigger RAM, for example, I can potentially run a bigger parameter model on my desktop and then connect to it from my laptop, so I can leverage the power of a local model running on one computer, but then access it from another one." (timestamp 13:35)

## Notable Quotes
> "Every single message I send to Gemma 4 stays entirely on my computer. It's full privacy." — 7:18
> "A lot of Ollama models use a 2048 token context limitation and Hermes requires 64,000 to give your agent tools." — 9:00
> "It's just a different way of launching the same underlying model... it doesn't duplicate it." — 9:25 (on variants)
> "That's why this is called an agent harness." — 13:02

## Tools and Resources Mentioned
- **Ollama** (vendor: Ollama, open-source) — the local model runner; CLI + desktop app
- **Gemma 4** (vendor: Google DeepMind, open-weights) — the model family; the E4B variant is the practical sweet spot
- **Ollama variants** — per-model context-window config without duplicating weights
- **"Hermes Agent"** (third-party, as shown by Wanderloots) — agent tool with custom-endpoint support. **NOT the user's MiniMax Hermes Agent.**
- **"Open Claw"** (third-party) — mentioned as another compatible agent harness in the same ecosystem
- **Claude Code** (vendor: Anthropic) — mentioned as compatible via the OpenAI-compatible endpoint
- **Codex** (vendor: OpenAI's coding agent) — also compatible via the OpenAI-compatible endpoint
- **OpenAI-compatible endpoint pattern** — adding `/v1` to the Ollama native endpoint for compatibility with any OpenAI-API-compatible client

## GitHub Repos and URLs Referenced

- None referenced in this video. (The video covers concepts, vendors, and pricing but does not cite specific GitHub repositories.)

## Action Items
- [ ] **Decide your own privacy threshold.** If "100% local, no data leaves my machine" is a real requirement for your work (legal, medical, financial, IP-sensitive), the Ollama + Gemma 4 path gets you there in ~10 minutes.
- [ ] **Right-size the model to your RAM budget.** E2B (4GB) for phones/low-end laptops, E4B (8GB) for most laptops, 31B+ (32GB+) for desktops. Don't try to run 31B on 16GB and wonder why it crawls.
- [ ] **Don't skip the 64K context variant** if you're connecting to an agent harness. The 2,048 default will silently break your agent's tool use. Either set the system-level default to 64K in Ollama settings, or create a per-model variant.
- [ ] **Use the OpenAI-compatible endpoint (`http://localhost:11434/v1`)** if you're connecting multiple agents. Most agents (Claude Code, Codex, Open Claw, the third-party Hermes Agent) accept OpenAI-format endpoints out of the box.
- [ ] **Tune the model-unload timeout** in Ollama settings if you want a 24/7 local agent. Default is "a few minutes then sleep"; for a daemon-style agent, set to always-on.
- [ ] **Consider the cross-machine pattern** if you have a beefier desktop. Run the bigger model on the desktop, connect from the laptop via the same endpoint.

## Open Questions
- **Vendor confusion to clarify:** "Hermes Agent" in this video is a third-party product (used by Wanderloots), NOT the user's MiniMax Hermes Agent. The endpoint pattern shown (custom endpoint + Ollama URL) is generic and would work with the user's MiniMax stack if/when the user's Hermes supports custom endpoints — but the video is not demonstrating that. Treat this as a "local Ollama + any compatible agent" tutorial, not a "use your Hermes like this" tutorial.
- Gemma 4 E4B at 64K context on 8GB RAM — what's the real tokens-per-second throughput? The video doesn't benchmark it; the "agent harness warmup time" suggests it's slow enough to matter.
- The "Open Claw" mention — vendor name is intentionally punny / unclear. Worth a dedicated search before recommending.
- The cross-machine setup is teased as "another video" — not in this one. For anyone building a multi-machine local agent farm, that follow-up is the one that matters.
- Gemma 4 (vs Gemma 3): how does quality compare for code-agent tasks specifically? The video doesn't run code tasks; just chat identity confirmation ("I'm Gemma 4 by Google DeepMind").

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 00:15:57 transcript)</summary>

[Full transcript stored at channels/wanderloots/transcripts/2026-06-25_run-your-own-agentic-ai-ollama-hermes.txt]

</details>