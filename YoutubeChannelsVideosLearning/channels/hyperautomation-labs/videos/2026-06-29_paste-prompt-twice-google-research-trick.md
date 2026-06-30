---
title: "Paste Your Prompt TWICE: Google's Free Trick to Make AI Smarter (New Paper)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-29"
duration_seconds: 499
video_id: "lty3CUhGD-Q"
url: "https://youtube.com/watch?v=lty3CUhGD-Q"
language: "en"
tags: [prompt-repetition, google-research, arxiv-2512-14982, non-reasoning-llms, prompt-engineering, llm-accuracy, lost-in-the-middle, context-rot]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-30"
---

# Paste Your Prompt TWICE: Google's Free Trick to Make AI Smarter (New Paper)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-29  **Duration:** 00:08:19  **Watch:** https://youtube.com/watch?v=lty3CUhGD-Q

## TL;DR
Google Research paper "Prompt Repetition Improves Non-Reasoning LLMs" (Leviathan, Kalman & Matias, arXiv:2512.14982, Dec 2025) — pasting the same prompt twice in non-reasoning models wins 47 of 70 internal tests with zero losses. The viral "76%" claim is one best-case 21%→97% jump on a single task; the honest average is meaningful but smaller. It does NOT help thinking / reasoning models. Why it works: repetition reduces "lost in the middle" — attention dilutes across long contexts, repeating the prompt re-weights the start and end, which models attend to most.

## Key Insights
- **The trick: paste the prompt twice, no model upgrade, no clever wording.** Works on non-reasoning models (base LLMs, early Gemini, non-thinking Claude). For reasoning models like Claude with Extended Thinking or o-series GPT, it does NOT help (or hurts). (timestamp 0:30)
- **The headline number is honest, not viral.** It won 47 of 70 tests with zero losses. The "76%" figure was one extreme before/after on a single task. Most wins are in the 5-15% accuracy range. (timestamp 1:20)
- **Why it works: it counters "lost in the middle."** Long contexts dilute attention. Models attend most to tokens at the start and end. Repeating the prompt doubles the signal at both anchors. (timestamp 3:15)
- **When it backfires:** reasoning models (the paper explicitly tested against them) — the second copy distracts from the chain-of-thought pattern the model uses internally. (timestamp 4:30)
- **The mechanism is more general than "twice."** The paper tested 2x, 3x, 4x — gains plateau around 2-3 copies. Beyond that is noise. (timestamp 5:10)
- **Companion techniques from the same research group:** "anchor the edges" (put the most important constraint at the top AND bottom of the prompt), "cut the clutter" (fewer-but-denser examples beats more-but-longer examples). All three ship together in the "Accuracy Pack" PDF (free with code "TWICE"). (timestamp 5:50)

## Notable Quotes
> "Paste your prompt twice. No new model, no paid upgrade, no clever wording." — 0:33
> "It won 47 of 70 tests with ZERO losses when reasoning is OFF." — 1:25
> "It does NOT help thinking/reasoning models." — 1:40

## Tools and Resources Mentioned
- **Anthropic Claude** (vendor: Anthropic) — non-reasoning baseline variants tested
- **Gemini** (vendor: Google) — Google's own model in the test set
- **Reasoning models** (Claude with Extended Thinking, OpenAI o-series) — explicitly excluded as beneficiaries
- **The "Accuracy Pack" PDF** — free companion (https://hyperautomationlabs.co/free/twice)
- **Hyperautomation Labs beginner's Claude Code guide** — paid companion playbook

## GitHub Repos and URLs Referenced
- https://arxiv.org/abs/2512.14982 — the paper itself ("Prompt Repetition Improves Non-Reasoning LLMs" by Leviathan, Kalman & Matias, Google Research)
- https://hyperautomationlabs.co/free/twice — companion cheat sheet PDF

## Action Items
- [ ] In your prompt templates, paste the user query twice for non-reasoning models — measure accuracy change on 5 of your own tests
- [ ] For reasoning models, do NOT use this trick — switch to "anchor the edges" + "cut the clutter" instead
- [ ] Audit your existing prompts for "lost in the middle" risk — long contexts with the key constraint in the middle are the worst case

## Open Questions
- Does the trick generalize to coding tasks, or only to Q&A / classification?
- Which non-reasoning model families show the biggest lift? Small models or any?
- Is there a clean pairing rule — when to use repetition vs. when to use "anchor the edges"?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 00:08:19 transcript)</summary>

0:00 A new Google Research paper found a dead-simple way to get better answers from AI for free...
[...full transcript omitted; see .txt companion file...]
8:19 End of video.

</details>
