---
title: "New Era of AI Agents with Microsoft Foundry Hosted Agent Service"
channel: "Eddy"
channel_slug: "eddy"
channel_id: "UC860VdxDA2EKFW9ezm36MAw"
published: "2026-06-28"
duration_seconds: 452
video_id: "bvCjyj2YZT8"
url: "https://www.youtube.com/watch?v=bvCjyj2YZT8"
language: "en"
tags: [microsoft-foundry, hosted-agents, agent-service, voice-protocol, agent-optimizer]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-07-01"
---

# New Era of AI Agents with Microsoft Foundry Hosted Agent Service

**Channel:** Eddy  **Published:** 2026-06-25  **Duration:** 07:32  **Watch:** https://www.youtube.com/watch?v=bvCjyj2YZT8

## TL;DR

Microsoft Foundry Hosted Agent Service eliminates the AI production headache (containerization, security provisioning, state management, observability) with hypervisor-isolated sandboxes + automatic Entra ID. The killer detail: **two AZD commands** (`azd init` + `azd deploy`) ship code to a production-ready agent — no container registries, no curl commands, no token management. Also ships integrated content safety, real-time voice over WebSocket, and an automated agent optimizer that generates and ranks prompt configurations in minutes.

## Key Insights

- "Building AI agents is easy. Scaling them is a nightmare." — the source material's framing of the operational tax every AI developer faces (00:43).
- Foundry Agent Service handles: hypervisor-isolated sandbox, dedicated file system, automatic Entra ID provisioning, built-in OpenTelemetry. Removes containerization, security provisioning, state management, observability from the developer's plate (01:08).
- **Deploy code, not containers**: zip your Python or .NET project, upload directly. Platform either installs dependencies on the fly (remote build mode) or runs your pre-bundled output. Bypasses all heavy lifting with container registries (01:55).
- **AZD = 2 commands** to go from source code to fully active secure agent: `azd init` (configuration files) + `azd deploy` (packaging + upload + deployment). No curl, no token management (02:30).
- Built-in safety guardrails: integrated safety layer blocks harmful inputs and filters unsafe outputs in real time. Content safety is integrated directly into the runtime — every prompt in and every response out is evaluated on the fly (03:15).
- **WebSocket protocol for voice**: new triad (responses protocol for conversation + HTTP invocations for webhooks/JSON + WebSocket invocations). Persistent bidirectional connection eliminates HTTP handshake latency. Pairs with Pipe Cat, Live Kit, Voice Live for real-time agent voice (03:50).
- **Automated agent optimizer** (closed loop): (1) evaluate baseline against pass-fail criteria, (2) generate new candidate configurations, (3) evaluate candidates, (4) rank + recommend (showing token costs), (5) deploy winner with one click. Runs in minutes, zero model retraining, zero manual code changes (04:35).
- Optimizer targets 4 areas: rewrite system instructions, optimize skills (reusable troubleshooting steps), test different models for quality-to-cost ratio, refine tool descriptions for API accuracy (05:00).
- **Cold start solution**: `eval init` command generates a dataset and evaluation criteria straight from existing agent instructions (no pre-built eval set needed) (05:30).
- **Road to GA (June 2026)**: support for private Azure container registries inside own virtual networks, managed VNet, expanded regions for real-time voice, durable long-running agents that survive container crashes and persist state across multi-session turns (06:10).

## Notable Quotes

> "Building AI agents is easy. Scaling them is a nightmare." — 00:48

> "If you're using the Azure developer CLI, AZD, it now takes exactly two commands to go from source code to a fully active secure agent. You just run AZ init to get your configuration files, and then AZ deploy to handle the packaging, the upload, and the deployment. That's it." — 02:23

> "Live and production ready aren't the same thing, and the gap shows up quickly." — 04:34

## Tools and Resources Mentioned

- Microsoft Foundry Agent Service — the new hosted agent platform
- Entra ID — Microsoft's automatic identity provisioning
- OpenTelemetry — built-in observability standard
- Azure Developer CLI (AZD) — `azd init` + `azd deploy` deployment flow
- Pipe Cat / Live Kit / Voice Live — voice frameworks that pair with WebSocket invocations
- WebSocket invocations — bidirectional real-time protocol
- Vendor: Microsoft Foundry is a Microsoft Azure product.

## GitHub Repos and URLs Referenced

None referenced in this video.

## Action Items

- [ ] Migrate AI agent deployments from manual containerization to AZD's two-command flow (`azd init` + `azd deploy`)
- [ ] For real-time voice agents, adopt the WebSocket invocation protocol + Pipe Cat/Live Kit/Voice Live framework
- [ ] For agent prompt iteration, use the closed-loop optimizer instead of manual prompt tweaks
- [ ] If you don't have an eval set yet, run `eval init` to auto-generate criteria from existing agent instructions
- [ ] Plan for durable long-running agents — state persistence across container crashes is GA-bound in June 2026

## Open Questions

- How does the built-in content safety handle ambiguous cases where "unsafe" depends on context?
- What's the cost profile of AZD-deployed agents vs. self-managed container deployments?
- For the agent optimizer, how much historical production data is needed before it can generate reliable candidate configurations?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 07:32 transcript)</summary>

Full transcript saved to channels/eddy/transcripts/2026-06-25_new-era-ai-agents-microsoft-foundry-hosted.txt (click to expand for the full HH:MM:SS transcript). Length: 9,012 chars.

</details>