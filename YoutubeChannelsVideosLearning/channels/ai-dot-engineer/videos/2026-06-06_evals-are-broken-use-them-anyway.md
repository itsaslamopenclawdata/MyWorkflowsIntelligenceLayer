---
title: "Evals Are Broken, Use Them Anyway — Ara Khan, Cline"
channel: "AI Dot Engineer"
channel_slug: "ai-dot-engineer"
channel_id: "UCLKPca3kwwd-B59HNr-_lvA"
published: "2026-06-06"
duration_seconds: 1144
video_id: "QuuIywMG4s8"
url: "https://www.youtube.com/watch?v=QuuIywMG4s8"
language: "en"
tags: ["evals", "ai-engineering", "cline", "benchmarks", "terminal-bench", "anthropic", "codex", "gemini", "harness", "model-evaluation"]
transcript_status: "partial"
generated_by: "channels-youtube-content"
generated_on: "2026-06-07"
---

# Evals Are Broken, Use Them Anyway — Ara Khan, Cline

**Channel:** AI Dot Engineer  **Published:** 2026-06-06  **Duration:** 19:04  **Watch:** https://www.youtube.com/watch?v=QuuIywMG4s8

## TL;DR

Ara Khan (Cline) on why benchmark numbers aren't gospel AND vibes aren't a system — the truth is in the messy middle. Cline went from 43% on Terminal Bench by adjusting container CPU/memory, timeouts, and Anthropic-specific prompt engineering — not by switching models. The practical framework: after each eval run, portfolio-allocate failures by sending another agent through all the failure traces. Three zones of failures — obvious bugs (zone 1), nuance improvements (zone 2), overfitting to the benchmark (zone 3, which Ara explicitly warns against).

## Key Insights

- **Cline started at 43% on Terminal Bench.** [description]
- **The improvements came from harness tuning**, not model swapping: container CPU/memory settings, raised timeouts, and prompt engineering techniques specific to Anthropic model families. [description]
- **Anthropic-specific techniques don't transfer to Codex or Gemini** — the "best model" depends entirely on the harness. [description]
- **Benchmark numbers are not gospel** — you can game them with infrastructure tuning. [description]
- **Vibes are not a system** — gut feel alone won't find the right model. [description]
- **The truth is in between** — systematic evals + the right granularity of failure analysis. [description]
- **The practical framework: portfolio-allocate failures.** After a run, send another agent through ALL the failure traces to find which small levers actually move the score. [description]
- **3 failure zones**: [description]
  - **Zone 1**: Obvious bugs (fix and re-run)
  - **Zone 2**: Nuance improvements (why a model "everyone calls great" doesn't work for your specific harness)
  - **Zone 3**: Overfitting to the benchmark (which people do, and which Ara explicitly says NOT to do)
- **The anti-pattern**: chasing the highest score, not the most useful signal. [implied]
- **No transcript available** — note generated from description.

## Notable Quotes

- "Cline started at 43% on Terminal Bench. The improvements came from container CPU and memory settings, raised timeouts, and prompt engineering techniques specific to Anthropic model families that do not transfer to Codex or Gemini. Not from switching to a better model." [description]
- "Benchmark numbers are not gospel and vibes are not a system, and that the truth is inconveniently in between." [description]
- "Zone three is overfitting to the benchmark, which people do, and which Ara is explicitly telling you not to do." [description]

## Tools and Resources Mentioned

- **Cline** — the AI coding agent (Ara Khan's company). [description]
- **Terminal Bench** — the benchmark. [description]
- **Anthropic Claude** — one of the tested models. [description]
- **OpenAI Codex, Google Gemini** — the other tested models. [description]
- No specific tools named beyond the benchmark.

## GitHub Repos and URLs Referenced

- **https://x.com/arafatkatze** — Ara's X. [description]
- **https://www.linkedin.com/in/arafatkatze/** — LinkedIn. [description]
- **https://github.com/arafatkatze** — GitHub. [description]
- No specific repos or project URLs.

## Action Items

- [ ] **Watch the full 19:04 video** for the actual evals methodology + the agent-through-failure-traces pattern. [transcript_status: partial]
- [ ] **Audit your current model selection** — is it based on a benchmark, a gut feel, or systematic harness-aware testing? [implied]
- [ ] **Test the same model across different harness configs** before switching models. The Cline lesson: infrastructure changes beat model swaps. [description]
- [ ] **Build the "send an agent through all failure traces" loop** — this is the practical playbook for systematic improvement. [description]
- [ ] **Define your own failure zones** — copy Cline's 3-zone framework (bug / nuance / overfit) and apply it to your own evals. [description]

## Open Questions

- **Terminal Bench** — what's the actual benchmark measuring? Real-world terminal tasks, or synthetic?
- **"Send another agent through all failure traces"** — is this a separate agent or the same one with a different prompt? Cost matters here.
- **The 43% baseline** — was that on a specific Cline version? What date?
- **How does this apply to non-coding evals?** The lessons are general but the specific patterns (CPU/memory tuning) are coding-specific.
- **What does "overfitting to the benchmark" look like in practice?** Are there symptoms Ara names?

---

*Note: transcript was unavailable. Note generated from description, which provides a robust argument + 3-zone framework.*
