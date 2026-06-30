---
title: "Build an AI Second Brain with Claude + Obsidian — Karpathy's LLM Wiki Method (Full Guide)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-29"
duration_seconds: 553
video_id: "HuREI6lks4s"
url: "https://youtube.com/watch?v=HuREI6lks4s"
language: "en"
tags: [second-brain, llm-wiki, andrej-karpathy, claude-code, obsidian, mcp, claude-desktop, routines, plaintext-vault, knowledge-management]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-30"
---

# Build an AI Second Brain with Claude + Obsidian — Karpathy's LLM Wiki Method (Full Guide)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-29  **Duration:** 00:09:13  **Watch:** https://youtube.com/watch?v=HuREI6lks4s

## TL;DR
A walkthrough for building a Karpathy-style "LLM Wiki" second brain using Claude Code + Obsidian. Three layers: (1) a plaintext Obsidian vault you own forever, (2) Claude Code reading, linking, and growing it via MCP, (3) overnight autopiloting via Routines — plus one rule: keys, not prompts. Every click and command spelled out for first-time Obsidian and first-time Claude Code users alike.

## Key Insights
- **The "LLM Wiki" framing (Andrej Karpathy).** A wiki-style vault where Claude — not you — does the linking, summarizing, and updating. The human writes; the model connects. (timestamp 0:45)
- **Layer 1 — Storage: a plain-text Obsidian vault.** Plaintext is durable forever (no lock-in, migrable, searchable). Obsidian adds backlinks, graph view, and a familiar editor. (timestamp 2:00)
- **Layer 2 — The Brain: Claude Code reading & linking via MCP.** MCP (Model Context Protocol) connects Claude to your vault. The agent can read, search, write, and link automatically. (timestamp 3:30)
- **Layer 3 — Autopilot: Routines files itself overnight.** Scheduled tasks (Routines) run when you sleep, summarizing new notes, finding patterns, surfacing contradictions. (timestamp 5:15)
- **THE RULE: keys, not prompts.** Don't keep retyping context — store reusable knowledge as keys (a Skills file, an AGENTS.md, a `claude.md`). Pull from the key on demand. The vault is your key store. (timestamp 7:00)
- **The compounding effect:** as the vault grows, Claude gets more context for everything. Each piece you write becomes a small upgrade to every future interaction.
- **Privacy-first by default:** everything lives in your filesystem. No cloud-vendor lock-in. You can rip out Obsidian or Claude and the vault survives as a folder of markdown.

## Notable Quotes
> "Keys, not prompts. Don't re-explain context — store it as a key and pull it when you need it." — 7:05
> "Plaintext lasts forever. Tools come and go. The folder of markdown doesn't care which editor you open it in." — 2:15

## Tools and Resources Mentioned
- **Obsidian** — local-first markdown vault editor
- **Claude Code** (vendor: Anthropic) — the agent that reads & writes the vault
- **Claude Desktop** (vendor: Anthropic) — alternative UI for non-terminal users
- **MCP — Model Context Protocol** (vendor: Anthropic) — connector pattern Claude uses
- **Routines** (vendor: Anthropic) — scheduled tasks (sandboxed, cannot touch local files — keep that in mind)
- **Andrej Karpathy** — origin of the "LLM Wiki" framing

## GitHub Repos and URLs Referenced
- None referenced directly. Companion PDF: https://hyperautomationlabs.co/free/second-brain (code "WIKI")
- The MCP server for Obsidian is referenced conceptually; no specific repo URL given in the transcript

## Action Items
- [ ] Create an empty Obsidian vault in a folder you control (e.g., `~/Documents/second-brain`)
- [ ] Wire Claude Code to the vault via MCP — start with read-only access, graduate to read/write
- [ ] Pick one Routine (e.g., nightly "summarize today's notes") and turn it on — measure the quality after 7 days
- [ ] Move reusable instructions (your coding conventions, your meeting cadence) into a `claude.md` so you stop pasting them every session

## Open Questions
- Which MCP server implementation does this build use — is there a community-accepted reference, or roll-your-own?
- How do you prevent the Routine from "drifting" — adding notes that subtly contradict your intent?
- What's the failure mode when the vault grows past ~10k notes — does the linking still scale, or do you hit context walls?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 00:09:13 transcript)</summary>

0:00 Your best ideas are scattered across notes apps, browser tabs, and Claude chats you'll never find again...
[...full transcript omitted; see .txt companion file...]
9:13 End of video.

</details>
