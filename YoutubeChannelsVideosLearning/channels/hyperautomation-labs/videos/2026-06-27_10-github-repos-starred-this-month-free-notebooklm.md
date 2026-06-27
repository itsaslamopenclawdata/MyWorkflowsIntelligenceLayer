---
title: "10 GitHub Repos Everyone Starred This Month (Free NotebookLM, 1.7B Free Tokens & More)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-27"
duration_seconds: 625
video_id: "9_0TTQAaS8M"
url: "https://youtube.com/watch?v=9_0TTQAaS8M"
language: "en"
tags: [ai-agents, ai-coding-tools, free-llm-api, github-trending, notebooklm-alternative, supermemory, ollama, local-llm, devtools, open-source]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-27"
---

# 10 GitHub Repos Everyone Starred This Month (Free NotebookLM, 1.7B Free Tokens & More)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-27  **Duration:** 00:10:25  **Watch:** https://youtube.com/watch?v=9_0TTQAaS8M

## TL;DR
Hyperautomation Labs curates the month's 10 most-useful trending GitHub repos after filtering out hype and previously-covered projects. The standout: **Open Notebook** (open-source NotebookLM, MIT, 33k stars), **Supermemory** (long-term memory API, 27k stars), **Ohmypie** (a serious terminal coding agent with 10k commits), **Herder** (tmux for AI agent swarms), and **Free LLama P** (stacks 16 free-tier providers behind one OpenAI-compatible endpoint for ~1.7B tokens/month at $0). All are weekend-testable with a one-line install.

## Key Insights
- **The selection heuristic:** filter out hype repos, star-gamed projects, and anything already covered in prior videos. Keeps the list to genuinely useful weekends. (timestamp 0:25)
- **Open Notebook (33k stars, MIT) — the open-source NotebookLM.** Drop in documents, get a podcast you can actually listen to on a walk. Talks to 18+ AI providers, so no Google lock-in. Setup: `git clone` + `docker compose up`. "Mature project, not a weekend toy." (timestamp 0:45)
- **Supermemory (27k stars, MIT, 1,700+ commits) — the memory API for the AI era.** Extracts facts from conversations, builds a profile, recalls the right thing next session. Claims #1 on the big memory benchmarks. Plugs into Vercel AI SDK, LangChain, OpenAI agents. One `curl` to run. (timestamp 1:44)
- **Ohmypie — a terminal coding agent built like a product, not a demo.** Wires into your editor via LSP, has a real debugger, persistent Python/JS kernels, sub-agents for parallel work, 40+ model providers. Hash-anchored edits cut token burn. 10,000 commits of real work. Install: `curl omp.st/install.sh` or `brew`. (timestamp 2:39)
- **Herder — tmux for AI agent swarms.** When you're running 3-4 coding agents in parallel, you need one place to watch them. Agent-aware terminal multiplexer with workspaces, tabs, panes, and a socket so agents can talk back. 7.5k stars and climbing fast. Dual-licensed: AGPL free, paid for commercial. (timestamp 3:26)
- **Free LLama P (13k stars) — stacks free tiers of 16 AI providers behind one OpenAI-compatible endpoint.** ~1.7B tokens/month at $0. Point any OpenAI client at it, no code change. **Honest catch:** stacking free tiers can bump into providers' ToS — fine for side projects and prototypes, not for production startups. (timestamp 4:15)
- **Stop Slope — strips the AI tails out of writing.** Scores text on five dimensions (directness, rhythm, trust, authenticity, density) and rewrites the robot out. 12k stars. Cloud skill: drop the folder in as a skill, no install. The five-dimension scoring is the part worth stealing. (timestamp 5:03)
- **PM skills — marketplace of 100+ product management skills for Claude Code.** Bakes the frameworks the best PMs actually use (Teresa Torres on discovery, Marty Cagan on product, Alberto Savoia on testing ideas) into slash commands like `/discover`, `/write-prd`, `/plan`. (timestamp 5:58)
- **The big trend: "modular coding"** — you snap together plugins to fit exactly what you need. A single dev with the right mods (per the source's quoted developer Robert, veteran coder since 1980) "20x's their output." The economic question lurking: how long is a flat-rate $200/mo subscription viable when devs are maxing out token usage at 20x? (timestamp 6:11)
- **The mind-blowing thought:** when a single dev can orchestrate, test, and ship at 20x, "how long until the tech industry simply runs out of code to write?" The upside framing: what new class of massive problems do we finally have the bandwidth to solve? (timestamp 6:45)

## Notable Quotes
> "Cheaper is a big part of that." — Adam Brakhane, on why codebase-memory-mcp matters (4:00, in the parent show, but reflected in this video's framing of repo selection)
> "Modular coding is the future. You just snap together plugins to fit exactly what you need." — 6:15
> "How long until the tech industry simply runs out of code to write?" — 6:55

## Tools and Resources Mentioned
- **Open Notebook** (github.com) — open-source NotebookLM with 18+ provider support
- **Supermemory** — long-term memory API for AI apps
- **Ohmypie** (`omp.st/install.sh`) — terminal coding agent with LSP integration
- **Herder** — agent-aware terminal multiplexer
- **Free LLama P** — OpenAI-compatible proxy stacking 16 free-tier providers
- **Stop Slope** — Claude Code skill that scores & rewrites AI-sounding prose on 5 dimensions
- **PM skills** — 100+ PM framework skills (Teresa Torres, Marty Cagan, Alberto Savoia) for Claude Code
- **Claude Code** (vendor: Anthropic) — referenced as the host for Stop Slope, PM skills
- **LangChain / Vercel AI SDK / OpenAI agents** — Supermemory's plug-in surface
- **Next.js, Supabase, Cloudflare** — fast-moving platforms where fresh docs matter (from related context)

## GitHub Repos and URLs Referenced

- (See 'Tools and Resources Mentioned' — this video is itself a curated roundup of ~10 trending GitHub repos. Top repos cited in the transcript: **free-notebooklm** (open-source NotebookLM alternative), **github-free-tokens** (1.7B-token free tier distributor). Other names referenced include open-source Anthropic Skills repos and various AI tooling repos — full repo list with descriptions in the Tools section above.)

## Action Items
- [ ] Clone Open Notebook this weekend; spend 10 min wiring your PDFs into a private NotebookLM.
- [ ] If you ship an AI app, add Supermemory as your memory backend — the 1,700-commit maturity + benchmark #1 means it's a real dependency, not a toy.
- [ ] For multi-agent workflows, install Herder as your cockpit before you spawn your 4th coding agent.
- [ ] Use Free LLama P for prototypes and learning only; read each provider's ToS before pointing production traffic.
- [ ] Steal Stop Slope's 5-dimension scoring (directness, rhythm, trust, authenticity, density) for your own writing QA.

## Open Questions
- Which of these 10 will still be actively maintained in 6 months? Star counts and recent commit velocity suggest all 10 are healthy now, but the GitHub graveyard is long.
- Does Free LLama P detect/respect per-provider rate limits per session, or does it hammer through them until the 429s start?
- What's the canonical PM skills entry point? The video names 3 frameworks but doesn't show a single worked example of `/discover` or `/write-prd` end-to-end.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 00:10:25 transcript)</summary>

[Full transcript stored at channels/hyperautomation-labs/transcripts/2026-06-27_10-github-repos-starred-this-month-free-notebooklm.txt]

</details>
