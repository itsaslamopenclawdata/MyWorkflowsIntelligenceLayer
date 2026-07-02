---
title: "Sonnet 5 vs Opus: the pricing twist nobody expected."
channel: "The Next New Thing"
channel_slug: "the-next-new-thing-ai"
channel_id: "UCNZEktrsM5oJZ-MK4jKPMOQ"
published: "2026-07-01"
duration_seconds: 1628
video_id: "osawfmJzzFE"
url: "https://youtube.com/watch?v=osawfmJzzFE"
language: "en"
tags: [claude, sonnet-5, opus-4-8, anthropic, pricing, tokenizer, ai-agents, glm-5-2]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-07-02"
---

# Sonnet 5 vs Opus: the pricing twist nobody expected.

**Channel:** The Next New Thing  **Published:** 2026-07-01  **Duration:** 27:08  **Watch:** https://youtube.com/watch?v=osawfmJzzFE

## TL;DR
Andrew Warner and Justin Brooke roundup the first wave of Claude Sonnet 5 reviews and land on a contrarian read: Sonnet 5 is *not* the "cheaper Opus" anymore — it's the most expensive model ever put through Theo's benchmark ($6,000 to run, beating even Fable 5 at $5,600). The reason is the new Opus 4.7 tokenizer, which inflates token counts ~30-35%, partially offsetting Anthropic's launch price cut (intro pricing through Aug 31: input $2, output $10 vs Sonnet 4.6's $3/$15). The duo's playbook: use Opus 4.8 as the senior-dev "sidekick" for research/specs/skills, then hand off execution to Sonnet for cheap loops — and `/model`-switch in the middle of a chat when the cheap model can't crack it.

## Key Insights
- **Sonnet 5 switches to the Opus 4.7 tokenizer, which tokenizes the same text 1.0×-1.3× (up to 35%) more aggressively** depending on content. Anthropic is also fighting for HTML instead of markdown in code outputs, which adds even more tokens. Net: the launch price cut is partially an illusion (02:45).
- **Intro pricing through Aug 31 is $2 input / $10 output vs Sonnet 4.6's $3 / $15.** After Aug 31, pricing returns to normal Sonnet rates *with the heavier tokenizer* — Mo Bitar's analogy: "your landlord kept rent the same but started counting months in dog months" (03:30).
- **Theo's "Artificial Analysis" benchmark cost: Sonnet 5 = $6,000 to run the full suite; Opus 4.8 = ~2× cheaper in real-world work. Sonnet 5 was even more expensive than Fable 5 at $5,600** (07:10).
- **Theo frames it as "junior dev that keeps going until it gets an answer"** — if a task is within the model's capability it solves fast, but if it's not, the junior loops until the cost is enormous. Sonnet 5 inherits this profile. Senior (Opus) → think, organize, spec. Junior (Sonnet) → execute the steps (20:00).
- **Justin Brooke's daily-driver rule:** Sonnet 5 is a writing/knowledge-work model — it shines for "blogging, scripting, reports, analysis" (Anthropic's own positioning). It is *not* a 3D-rendering model, and it is *not* a one-shot prompt model (02:00, 13:00).
- **GLM 5.2 has no vision** — and that's a real obstacle for game dev, image-fed agents, and any workflow that pipes screenshots or UI mocks into the model. Theo's workaround: use a fallback model for images. Andrew's workaround: route images through a different model in his Hermes agent (11:00).
- **Real-world game build comparison (Theo, head-to-head, same prompt, "extra mode"):**
  - Opus 4.8 — 26 min, ~$0.25, ship-able output, good economy balance, "thinking" strategy
  - GLM 5.2 — cost $8.30 (separate run), no vision, weird economy, choppy movement
  - Sonnet 5 — 2+ hours, ~$0.13, no hotkeys, "well it got the job done" (12:30)
- **Zapier's enterprise-workflow benchmark:** Opus 4.8 = 15.4% success rate, Sonnet 5 = 13.5%; cost: Sonnet 5 = 2.0¢ vs Opus 4.8 = 2.36¢. Sonnet 5 is "more capable but not dramatically cheaper" on multi-tool/multi-step tasks (15:30).
- **Justin Brooke's actual production pattern:** Opus 4.8 as the "sidekick" — big research, instructions, skill design — then Sonnet goes and does all the cheap loop work. "I don't want my junior dev just going and going and going trying to figure out the problem. I want to use a senior dev" (20:50).
- **AI Code King's flag:** Sonnet 5 in Open Code writes into `/tmp` instead of the project working directory, asks for permission constantly, and "doesn't follow system instructions well." Sonnet 5 in Open Code is "even more weird" than in Claude Code (22:30).
- **Andrew's Mind Studio profiler comparison (SVG BMW M4 side-view, identical prompt):** Sonnet 5 ~23s / 4¢, Opus 4.8 ~27s / 6¢, Gemini 3 Pro 68s / 0.3¢ but failed. Sonnet 5 isn't the "cheaper alternative" anymore — it's "the tool for certain jobs" (25:00).
- **Cost-per-task is the right metric, not cost-per-token.** Peter Steinberger (creator of OpenClaw, now at OpenAI): "Watch out, price per token does not equal cost per task" (05:30).

## Notable Quotes
> "Your landlord kept rent the same, but started counting the months in dog months." — Mo Bitar on Sonnet 5's new tokenizer (04:10)

> "Watch out — price per token does not equal cost per task." — Peter Steinberger (OpenClaw creator, now at OpenAI) (05:30)

> "I use Opus 4.8 as my sidekick. It helps me come up with the big research, the instructions, the skills. Then Sonnet goes and does all the work because it's cheaper to do all the little steps with Sonnet than with Opus." — Justin Brooke (14:50)

> "Sonnet 5 isn't the cheaper alternative anymore. We have to think of it as the tool for certain jobs, not the mini version of Opus 4.8." — Andrew Warner (26:40)

## Tools and Resources Mentioned
- **Claude Sonnet 5** (Anthropic) — flagship writing/knowledge-work model; new Opus 4.7 tokenizer; intro pricing $2/$10 through Aug 31, then reverts.
- **Claude Opus 4.8** (Anthropic) — "senior dev" model; 15.4% on Zapier multi-tool benchmark; ~$0.25 for a 26-min game build.
- **GLM 5.2** (Zhipu / Z.AI) — Chinese open-source; ~5× cheaper than Opus; **no vision** (must fallback model for images).
- **Hermes Agent** (Nous Research, hermes-agent.nousresearch.com) — Andrew and Justin both daily-drive it; supports `/model` mid-chat to switch senior/junior. *Same product as this user's stack — confirmed via description URL and vendor disambiguation.*
- **Mind Studio** — agent-builder with a "profiler" head-to-head tool for same-prompt multi-model cost/time comparison (23:50).
- **Zapier** — sponsor; runs the multi-tool agent benchmark that puts Opus 4.8 ahead of Sonnet 5 on enterprise workflows (15:30).
- **Open Code** — terminal coding agent that integrates Sonnet 5 with documented quirks (writes to `/tmp`, ignores system instructions) per AI Code King review (22:30).
- **DGX Station** (NVIDIA) — 750GB unified-memory workstation; can run GLM 5.2 2-bit quant (~250GB); ~$85,000. Mentioned as the local-hosting escape hatch (10:10).

## GitHub Repos and URLs Referenced
- https://www.youtube.com/watch?v=uU0RFxGv-Ks — Alex Finn's Sonnet 5 review ("Claude Sonnet 5 just dropped")
- https://www.youtube.com/watch?v=VuodSALTF9w — WorldofAI's Sonnet 5 review ("Worst Model By Anthropic EVER?")
- https://zapier.com/ — sponsor; enterprise workflow benchmark source
- https://hermes-agent.nousresearch.com/ — Hermes Agent docs (Andrew and Justin's daily driver)

## Action Items
- [ ] Audit your current Sonnet 4.6 spend and re-budget for Sonnet 5 + Opus 4.7 tokenizer math — intro pricing ends Aug 31
- [ ] Adopt the senior/junior split: route big-research/spec/skill-design prompts to Opus 4.8, hand off execution loops to Sonnet 5
- [ ] If you use GLM 5.2, set up an explicit image-fallback model — GLM has no vision, so any screenshot/UI-mock pipeline needs a different model downstream
- [ ] Build your own head-to-head profiler for your top 3 tasks (using Mind Studio or a homegrown equivalent) before re-pricing your AI stack — vendor benchmarks lie, your benchmarks don't
- [ ] Reconsider Sonnet 5 as a default for resource-intensive coding tasks (3D, multi-file builds); the time + token multiplier exceeds the price-per-token savings

## Open Questions
- After Aug 31, what does the real-world Sonnet 5 cost-per-task curve look like vs the intro-pricing window — is the launch discount enough to lock in pilots?
- Does the Opus 4.7 tokenizer get retrofitted into Claude Code's default model picker, or do you have to opt in?
- Will Anthropic ship a "Sonnet 5.5" within 90 days to fix the junior-dev-loop problem Theo identified, or is this the new normal?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 27:08 transcript)</summary>

See `channels/the-next-new-thing-ai/transcripts/2026-07-01_sonnet-5-vs-opus-pricing-twist.txt` for the full transcript.

Highlights from the transcript (sampling): Opens with Alex Finn's 3D boat test (Sonnet 5 renders, GPT 5.5 can't move camera/ship/water). WorldofAI's flag: Sonnet 5 uses the Opus 4.7 tokenizer (~30-35% more tokens). Mo Bitar's "dog months" analogy. Justin: "Sonnet is for writing. Anthropic calls it knowledge work." Theo's benchmark: Sonnet 5 = $6,000 to run, Opus 4.8 = ~2× cheaper in real work. Justin's daily-driver rule: Opus 4.8 senior / Sonnet 5 junior via `/model` mid-chat. AI Code King flags Sonnet 5 writing to `/tmp` and ignoring system instructions. Mind Studio profiler: Sonnet 5 ~23s/4¢, Opus 4.8 ~27s/6¢ for an identical SVG prompt. Andrew's closing: "It's the tool for certain jobs, not the mini version of Opus 4.8."

</details>