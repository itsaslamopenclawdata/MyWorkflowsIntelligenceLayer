---
title: "No Fable. No Sol. Use GLM 5.2!"
channel: "The Next New Thing"
channel_slug: "the-next-new-thing-ai"
channel_id: "UCNZEktrsM5oJZ-MK4jKPMOQ"
published: "2026-06-29"
duration_seconds: 1065
video_id: "Cm1REvnij4A"
url: "https://youtube.com/watch?v=Cm1REvnij4A"
language: "en"
tags: [glm-5-2, z-ai, claude-code, vs-code, open-source, ai-coding, hermes-agent, local-models]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-07-02"
---

# No Fable. No Sol. Use GLM 5.2!

**Channel:** The Next New Thing  **Published:** 2026-06-29  **Duration:** 17:45  **Watch:** https://youtube.com/watch?v=Cm1REvnij4A

## TL;DR
Andrew Warner and Adam Brakhane react to OpenAI's GPT 5.6 being inaccessible to them, then evaluate GLM 5.2 (Zhipu's open-source model) as the practical alternative for high-token workflows. The verdict: GLM 5.2 is ~5× cheaper than Opus 4.8, ~3-4× faster on a real website-design task (3:59 vs 14:59), and "really solid" for most tasks that don't require heavy reasoning. They install it into Claude Code via a 5-line `settings.local.json` env-var patch and run it through Hermes Agent and Claude Code in parallel. The "skip" reason for not going all-local: GLM 5.2 is a "chunky boy" — ~250GB at 2-bit quant, needs ~25GB RAM minimum, $85k DGX Station for the full-speed version.

## Key Insights
- **OpenAI has scaled back what Anthropic and OpenAI ship to consumers.** "This is really bad. All of us don't get the Frontier model right when it drops" — Andrew's frustration (00:15). The strategic response: install open-source alternatives from China (GLM 5.2) and route around the gate.
- **Don't over-weight benchmarks; weigh what solves your problems fast and cheap.** Adam: "The easiest things for any of us like consumers out here picking a model are the ones that are fast and cheap. You can compare token price, you can compare speed. Take it on a trial for a day or a week" (01:40).
- **GLM 5.2 is "5× cheaper" than Opus 4.8 in real work.** On a website-design task: GLM 5.2 done in 3:59, Opus 4.8 done in 14:59. GLM used fewer tokens AND cheaper per-token (04:40).
- **For design work, GLM 5.2 outputs a *fresher* perspective than Opus.** Opus designs have started to look "stale" because everyone's been prompting Opus the same way. The slight visual differentiator on the GLM output ("a couple of little differences that Opus just wouldn't do by default") is a real vote for open-source variety (03:00).
- **On a real coding test (Opus-judged), GLM 5.2 was "good but not as precise"** — agent 2 (Opus) caught duplicate-records edge cases (`true` vs `1` vs `1.0`) that GLM missed. The meta-take: "GLM 5.2 is really solid and quick for most tasks that don't require heavy reasoning" (05:30).
- **The /memory.md secret for matching Opus's design output:** Andrew's pattern — give any model *your own* design style as a system prompt context ("use my design style"). Eliminates the "stale Opus look" problem without paying for Opus (03:40).
- **The local-hosting reality check (Andrew's 2-bit quant demo):** GLM 5.2 2-bit = ~250GB. Needs ~25GB RAM, so technically runs on a 256GB Mac Studio. Adam's reality: "I tap out the RAM on that machine using a model, I get maybe one token every five seconds" — unusable for anything longer than a LinkedIn post (07:30).
- **The real local option: DGX Station** — 750GB unified memory, ~$85,000. Adam: "If you're spending $60 to $200k, you could have pretty good performance. I'm not going to put that on a machine today. I would much rather pay the API rates" (10:15).
- **The pragmatic stack Andrew lands on:** GLM 5.2 Light plan = $16.20/mo, includes API access + monthly credits. Use it as the cheap fallback inside Hermes Agent and Claude Code, swap to Opus for the heavy-reasoning tasks. Adam: "You get API access on the plans. That's banked up — you get a bunch of credits every month" (11:30, 13:00).
- **The 5-line `settings.local.json` swap pattern:** paste the env-vars into settings, drop in the Z.AI API key, restart Claude Code. Andrew: "I'm a wuss when it comes to this stuff. I don't want to mess around with anything called settings.local. And now I was able to do it easily" (14:00).
- **Pro tip from Adam:** "People feel stuck. They feel afraid. Just ask. This thing is sitting here right now ready to help already on your screen. Ask Claude to set up the file for you" — Claude handles the settings.local.json write, you just supply the API key (16:50).

## Notable Quotes
> "GLM 5.2 is really solid and quick for most tasks that don't require heavy reasoning. At the end of the day, Opus 4.8 is a better model. It's closed source, but it does seem like it is better. It does have its place." — Andrew Warner (05:30)

> "If you're spending $60 to $200k, you could have pretty good performance. I'm not going to put that on some machine today. I would much rather pay the API rates." — Adam Brakhane (10:35)

> "I'm a wuss when it comes to this stuff. I don't want to mess around with anything called settings.local. And now I was able to do it easily." — Andrew Warner (16:40)

## Tools and Resources Mentioned
- **GLM 5.2** (Zhipu / Z.AI, `z.ai`) — open-source Chinese model; 2-bit quant ~250GB; ~5× cheaper than Opus; **no vision**; pricing $1.4 input / $4.4 output per million tokens.
- **Z.AI plans** — Light $16.20/mo, Pro $64/mo, Max $144/mo; include API access + monthly credits. Andrew's recommendation for solopreneurs.
- **Claude Code** (Anthropic) — installs GLM 5.2 via 5-line env-vars in `settings.local.json`; Claude writes the file for you.
- **Hermes Agent** (Nous Research) — Andrew's daily driver; uses GLM 5.2 Light plan as the cheap fallback model. *Same product as this user's stack — confirmed via description URL.*
- **OpenAI GPT 5.6** — referenced as the frontier model Andrew/Adam can't access (the trigger for evaluating GLM 5.2).
- **Anthropic Opus 4.8** — benchmark comparison; ~$200/mo Claude subscription = ~$10k equivalent API credits.
- **Mac Studio (256GB RAM)** — can technically run GLM 5.2 2-bit but yields ~1 token / 5 seconds per Adam.
- **DGX Station** (NVIDIA, 750GB unified memory, ~$85k) — the "real" local option for full-speed GLM 5.2.
- **Codex** (OpenAI) — used as the judge to grade the GLM-vs-Opus coding test (avoiding cross-contamination).

## GitHub Repos and URLs Referenced
- https://z.ai — Z.AI landing page; free chat playground for GLM 5.2 (landing pages, 3D modeling, mini-apps)
- https://thenextnewthing.ai/Resources — Andrew's Resource Vault (settings.local.json snippet for GLM 5.2)

## Action Items
- [ ] Go to z.ai and try the free chat playground for GLM 5.2 on a non-trivial design task to baseline output quality
- [ ] Sign up for Z.AI Light plan ($16.20/mo) for API access + monthly credits
- [ ] Install GLM 5.2 into Claude Code via `settings.local.json` env-vars (ask Claude to write the file — don't hand-edit)
- [ ] Add GLM 5.2 as the cheap fallback in Hermes Agent; route heavy-reasoning prompts to Opus, cheap loops to GLM
- [ ] Add *your own* design style as a system-prompt context for any model you use (kills the "stale Opus look" without paying for Opus)

## Open Questions
- Does GLM 5.2 gain vision in a near-term release, or is it permanently a text-only model? (Huge for screenshot-driven workflows.)
- For coding tasks specifically, what's the gap between GLM 5.2 Light plan output and Opus 4.8 on real production codebases (not contrived tests)?
- What's the cost-vs-quality crossover point for a solo founder — at what monthly AI spend does the $85k DGX Station actually pencil out vs API rates?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 17:45 transcript)</summary>

See `channels/the-next-new-thing-ai/transcripts/2026-06-29_no-fable-no-sol-use-glm-5-2.txt` for the full transcript.

Highlights from the transcript (sampling): Andrew opens frustrated about OpenAI scaling back frontier model access. Adam grounds it: "As a regular person, you probably shouldn't care all that much about benchmarks." Website-design head-to-head: GLM 5.2 done in 3:59 / cheaper per-token; Opus 4.8 done in 14:59 / stale design. Codex-judged coding test: GLM 5.2 missed duplicate-records edge cases (`true` vs `1` vs `1.0`); Opus 4.8 caught them. Local-hosting math: GLM 5.2 2-bit = ~250GB, needs ~25GB RAM, "one token every five seconds" on Adam's 64GB Mac Mini. The escape hatch: DGX Station at ~$85k, 750GB unified memory. Andrew's actual move: Z.AI Light plan at $16.20/mo, drops into Claude Code via settings.local.json, runs as the cheap fallback in Hermes Agent.

</details>