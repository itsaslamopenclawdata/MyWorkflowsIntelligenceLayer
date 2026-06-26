---
title: "The Best Claude Code Mods That Change Everything"
channel: "Eddy Says Hi"
channel_slug: "eddy"
channel_id: "UC860VdxDA2EKFW9ezm36MAw"
published: "2026-06-25"
duration_seconds: 352
video_id: "CO5LJLEh260"
url: "https://www.youtube.com/watch?v=CO5LJLEh260"
language: "en"
tags: [claude-code, mods, subagents, context-loading, get-shit-done, simonex, agentic-coding, anthropic]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-26"
---

# The Best Claude Code Mods That Change Everything

**Channel:** Eddy Says Hi  **Published:** 2026-06-25  **Duration:** 5:52  **Watch:** https://www.youtube.com/watch?v=CO5LJLEh260

## TL;DR

Short tour of four Claude Code mods that meaningfully change the dev-loop: (1) `.claude/skills/` for per-project reusable skills, (2) auto-loaded instruction files so you don't retype conventions each session, (3) subagent delegation so the main thread stays lean and focused, (4) the **GSD ("Get Shit Done") mod** — a multi-phase planning + execution framework that maps directly to Anthropic's recommended best practices. Also covers Simonex as a comparison tool.

## Key Insights

- **Why mods at all?** Vanilla Claude Code is great as a coding partner but on the long side, ad-hoc. Mods let you customize Claude Code to your exact workflow without rebuilding the agent. (0:00–0:30)

- **Mod #1 — `.claude/skills/` for per-project skills.** Inside the `.claude/skills/` directory, you create individual folders containing skill definitions scoped to the project. Instead of typing the same prompts in every Claude Code session, you turn them into permanent project-specific tools. (0:30–1:15)

- **Mod #2 — Auto-loaded instruction files.** These are files in the project that Claude Code automatically pulls into context when it spins up. Stop retyping "use the new API endpoint" or "always run tests before committing" every session — Claude Code finds and reads these files automatically. (1:15–2:00)

- **Mod #3 — Subagent delegation.** Hand off smaller subtasks to subagents so the main thread doesn't get cluttered. Keeps the primary context clean and focused, lets complex work happen in parallel without breaking your flow. (2:00–2:30)

- **Mod #4 — GSD ("Get Shit Done").** The flagship mod discussed: a full multi-phase planning + execution framework inside Claude Code. Aligns closely with Anthropic's official Claude Code best practices (context, subagents, verification). The vibe: instead of one continuous loop, GSD forces you through explicit phases — brainstorm, spec, plan, build, verify. (2:30–4:00)

- **Simonex as comparison.** Mentioned in passing as another community mod worth comparing against GSD. Not deep-dived; useful as a second data point if you're evaluating one vs. the other. (4:00–4:30)

- **The real benefit of adopting a mod.** The video's framing: vanilla Claude Code is generic. A mod is "Claude Code tailored exactly to your coding style and your project." The cost-of-context-per-session drops dramatically because the auto-loaded files and per-project skills carry the conventions forward. (4:30–5:52)

## Notable Quotes

> "You're able to customize Claude Code to your exact workflow without rebuilding the agent." — 0:20

> "Stop retyping the same instructions every single time you open up Claude Code." — 1:50

> "Instead of just one continuous loop, it's a multi-phase approach to building things." — 3:30

## Tools and Resources Mentioned

- **Claude Code (Anthropic)** — the IDE agent being modified throughout. *vendor: Anthropic product.*
- **`.claude/skills/`** — folder convention for per-project skills.
- **Claude Code Mods** — community ecosystem of customizations to vanilla Claude Code.
- **GSD ("Get Shit Done") mod** — multi-phase planning + execution framework. The most prominently featured mod in the video.
- **Simonex mod** — alternative community mod mentioned for comparison.
- **Anthropic's official Claude Code best practices** — GSD's design is explicitly aligned with these.

## GitHub Repos and URLs Referenced

- (The GSD mod repo is implied as the install target but not pasted in transcript.)
- (No specific URLs or repos in this short video.)

## Action Items

- [ ] Set up a `.claude/skills/` folder in your most active repo and convert the prompt you re-type every session into a skill.
- [ ] Add an auto-loaded instruction file (CLAUDE.md or similar) carrying your project's standing conventions so Claude Code reads them at session start.
- [ ] Try delegating one subtask to a subagent and confirm the main thread stays focused and readable.
- [ ] Install GSD and run it on one project end-to-end; compare the result against vanilla Claude Code on the same project.

## Open Questions

- The video names four mods but the install steps for each are not walked through — viewers are pointed at "the community." Which specific GitHub repos / marketplace install commands are the canonical entry points today?
- GSD vs. Simonex: which fits which workflows? The video says "compare" but doesn't characterize the difference.
- Are there any known interactions between auto-loaded instruction files and per-project skills — e.g., can both be active at once, and which wins on conflict?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 5:52 transcript)</summary>

0:00 Vanilla Claude Code is great, but it's
0:02 pretty long. It's pretty ad hoc.
[...]
5:50 (closing)

(Full 6,127-character transcript saved to channels/eddy/transcripts/2026-06-25_claude-code-mods-change-everything.txt)

</details>