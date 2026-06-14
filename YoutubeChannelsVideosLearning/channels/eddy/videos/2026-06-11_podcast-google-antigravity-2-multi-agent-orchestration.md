---
title: "(Podcast) Google Antigravity 2.0 and the Future of Multi-Agent Orchestration"
channel: "Eddy Explainer"
channel_slug: "eddy"
channel_id: "UCZ_4HvkkWlRdM8t5nOiOiYA"
published: "2026-06-11"
duration_seconds: 1027
video_id: "kI5DB_UNFUg"
url: "https://www.youtube.com/watch?v=kI5DB_UNFUg"
language: "en"
tags: [google-antigravity, antigravity-2, multi-agent, orchestration, gemini-flash, gemini-cli, interactions-api, scheduled-tasks, review-driven-development, parallel-agents, session-ttl, varun-mohan, doom, eddy, podcast]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
source_article: "Google Antigravity 2.0, The Complete Developer Guide — Ria Bansal / Analytics Vidia (May 2026)"
---

# (Podcast) Google Antigravity 2.0 and the Future of Multi-Agent Orchestration

**Channel:** Eddy Explainer  **Published:** 2026-06-11  **Duration:** 17:07  **Watch:** https://www.youtube.com/watch?v=kI5DB_UNFUg
**Companion:** This is the long-form 17-min **podcast** version of the 8-min short explainer `8I5ZmNZXqEU` (same channel, same day). The short note covers the same product and the same deadline at a high level; this note goes deeper on the Google I/O Doom-on-OS-core demo, the desktop-plus-CLI/SDK/managed-API/enterprise five-touchpoint split, the session-TTL and parallel-isolation gotchas, and the schedule/voice/parallel-agent paradigm shift.

> **Vendor disambiguation (this video is full of third-party name collisions, read carefully):**
> - **"Google Antigravity"** is Google's product. It is **NOT** MiniMax, NOT Anthropic, and NOT this Hermes agent stack.
> - **"Gemini 3.5 Flash"** is Google's model. Not to be confused with Anthropic's Haiku or any third-party "Flash" branding.
> - **"Gemini CLI"** is Google's old command-line tool, being hard-cut on 2026-06-18.
> - **"Interactions API"** is Google's API surface for managed agents. It is **NOT** any third-party "interactions" SDK.
> - The source article is by **Ria Bansal / Analytics Vidia** (Eddy is summarizing it, not authoring it).

## TL;DR
A 17-min deep-dive podcast built around Ria Bansal's May 2026 Analytics Vidia guide on Google Antigravity 2.0. The framing: 1.0 was "a really fast typist looking over your shoulder" inside the IDE; 2.0 is "a standalone multi-agent workforce" that breaks out of the editor entirely. The hard deadline (June 18, 2026) is the same as the short, but the long-form adds the I/O keynote meat: Varun Mohan (noted in the short as "Varun Mohan"; the long-form sometimes mishears him as "Varun Nohria") standing on stage, spinning up Antigravity's parallel agents, and building a working OS core from scratch for under $1,000 in compute, then running a live Doom clone on top. The podcast also sharpens the five touchpoints (desktop app is the "control room"; the Go-based CLI, SDK, managed APIs via the Interactions API, and the enterprise platform are where the real work happens), dives deep on the **"review-driven development"** model (agent halts before destructive code changes and raises its hand for approval), and makes the parallel-isolation problem visceral with the **"soundproof rooms" + "conveyor belts"** analogy: every agent lives in its own persistent isolated Linux box, cannot natively see its peers, and you have to deliberately architect a common routing layer to coordinate them. The **"AI building AI"** detail is the new headline: Google used Antigravity's own multi-agent workflows to co-develop Gemini 3.5 Flash, the very engine that powers the platform. Closing provocation: if AI can already write the code, build the apps, manage the servers, and build its own next-gen models, is the developer of the future just a **diplomat** who negotiates routing paths between completely isolated, superintelligent digital workers?
The core lesson remains: **the developer of 2026 stops being a typist and becomes a manager of soundproof rooms.**

## Key Insights
- **The expert and the source.** Eddy's framing credits Ria Bansal's "phenomenal breakdown" at Analytics Vidia — "Google Antigravity 2.0, The Complete Developer Guide." The whole episode is a conversation-style unpacking of that single article, so the "voice" is editorial, not first-person. The hosts add color and analogies; the technical claims are sourced from Bansal. (0:59–1:31)
- **The piano analogy: from typist to conductor.** 1.0 was "a really fast typist looking over your shoulder" — a prediction engine inside your IDE, limited to the single open file. 2.0 is a "standalone multi-agent workforce" that breaks out of the editor entirely. The framing: you used to play a piano one key at a time, now a single chord summons an entire symphony. "You are no longer prompting a single engine to finish a sentence. You are now directing a team of independent agents." (0:06–2:35)
- **Scheduled tasks = the cognitive-load unlock.** "Before, an AI just sat there static waiting for you to hit enter. But with scheduled tasks, you can give an agent a goal, tell it to run in the background every hour or every day, and it becomes this continuous autonomous process." This is the shift from "tool you poke" to "coworker who runs" — the developer becomes an approver of milestones, not a producer of keystrokes. (2:35–3:01, 3:57–4:14)
- **Review-driven development = the safety net.** The new default mode: agent takes your high-level objective, generates intermediate artifacts (task lists, planning documents, architectural diagrams, code diffs) asynchronously, then **halts before doing anything destructive** and asks "Here is my plan, and here is the exact code I'm going to inject to execute that plan. Do you approve?" It does the heavy legwork, but the human holds the keys. (3:01–3:57)
- **The desktop app is the "control room" — the actual work is back-end.** What you're looking at in the UI is the front-end of the operation. The heavy lifting happens through **managed agents in the Gemini API**: with a single API call, a developer spins up an agent inside an isolated Linux environment (a tiny virtual computer in the cloud), and crucially it's **persistent** — close your laptop, come back 3 hours later, the files and state are exactly where the agent left them. Zero reset. (3:57–5:23, 12:14–12:30)
- **The "soundproof rooms" problem (parallel isolation).** "Every single agent gets its own persistent isolated Linux box." The hosts push on this: if agent A is writing the database back-end and agent B is building the UI, don't they step on each other's toes? Answer: "but only because they literally can't." Parallel agents are totally isolated **by design** — "think of them as working in completely separate soundproof rooms. They cannot natively see, touch, or edit what the other agent is doing." (5:23–6:57)
- **The "HR communication department" complaint.** The cynical developer reaction: "I'm a developer, I barely have time to write my own application logic, and now you're telling me I have to build an entire HR communication department just so my AI agents can talk to each other and share files. How is that saving me time?" Eddy's answer: "the alternative is absolute chaos. If you have five super fast autonomous agents all trying to edit the same core file simultaneously, your code base corrupts in seconds." Isolation is the cost of parallel speed. (6:29–6:57)
- **The "conveyor belt" / routing layer.** The mechanism for inter-agent coordination: a **shared database** the agents all have read-permission to, OR a **message broker** that takes a message from agent A, queues it, and securely delivers it to agent B when B is ready. "The point is the developer has to build the conveyor belts between these isolated rooms." You're not just writing features anymore — you're "architecting communication bridges between AIs." (7:00–7:40)
- **The latency compounding wall — and why Gemini 3.5 Flash exists.** If 10 agents are constantly pinging each other through a custom routing layer, message-passing creates a massive computational bottleneck. "Latency becomes your absolute worst enemy in this setup. And that computational wall is exactly why Google had to build Gemini 3.5 Flash." 3.5 Flash is ~4x faster than other frontier models and beats Google's own Gemini 3.1 Pro on most benchmarks. (7:40–8:37)
- **The accounting-department analogy for compounding delay.** 200ms per call feels instant in a 1:1 chat. But imagine 10 agents doing sequential hops: agent A emails accounting, waits 5 min; accounting emails legal, waits 5 min; legal emails back — a basic decision takes all afternoon. "In software orchestration, a 20-second lag means the system is effectively unusable. It's just broken at that point. If the model isn't blazingly fast, the whole multi-agent symphony grinds to a halt." (8:38–9:45)
- **The dog-food detail: AI built the AI.** The killer new fact the long-form surfaces: "Gemini 3.5 Flash wasn't built in a vacuum by engineers just typing away. It was actually co-developed using Antigravity's own agentic workflows. The AI was basically used to build the next faster version of itself. Google used the very same multi-agent system they're releasing to the public to optimize the latency of the model that powers it." This is "incredibly powerful proof of viability" — if Antigravity 2.0 is robust enough for Google to use it to architect Gemini 3.5 Flash, it's robust enough for whatever a normal company throws at it. (9:45–10:30)
- **The hard deadline: June 18, 2026, for the old Gemini CLI.** "This is not a gentle phase deprecation. It's a hard stop. If your team has continuous integration pipelines built on the old CLI, they will break on June 18th. Those pipelines run unattended, so if they're calling the old Gemini CLI to run tests or build code, they're going to hit a brick wall." Eddy adds a complication the short version doesn't emphasize: **migration isn't a copy-paste job** — the underlying syntax and dependencies change when you move to a new CLI built on a completely different language (Go). (10:30–12:14)
- **Session TTL = the "AI lifespan" gotcha.** The persistent Linux environments for managed agents "actually have a TTL, a time to live. You cannot just spin up an agent, give it a task, and leave it running in the background for 6 months. Those isolated sessions will eventually expire. The server will shut them down to free up resources." If you have a 3-day refactor and the session expires after 1 day, "the agent just dies mid-thought, and you lose any uncommitted progress. That is brutal." (12:14–12:53)
- **The "bookmark and switch desks" pattern.** Developers must manually build session expiry logic into long-running workflows: monitor the TTL clock, and when the environment is close to expiring, force the agent to **save its state, export files to permanent storage, request a brand-new Linux environment, re-import everything**, and pick up exactly where it left off. "You're managing its literal lifespan." (12:53–13:23)
- **The to-do app walkthrough (end-to-end in 3 minutes).** Open the desktop app → start conversation → switch to plan mode → request a FastAPI back-end + HTML/JS front-end → agent generates an **implementation plan artifact** (the blueprint) → you click approve → you watch `main.py` and `index.html` populate in real time in the editor → grab the **walkthrough artifact** (not a text summary — an executable container that bundles the Python code with server software and binds it to a network port) → it runs on `localhost:8000` → you open your browser and interact with a live, functioning app that didn't exist 3 minutes ago. "You acted as the manager, reviewing the plan, and the agents laid the bricks, wired the electricity, and turned on the lights." (13:23–15:08)
- **The I/O keynote: Doom on a freshly built OS core.** Varun Mohan (Eddy occasionally mishears as "Varun Nohria" — same person, the Codeium/Windsurf CEO turned Google exec) stood on stage, spun up Antigravity's parallel agents, and built a working operating system core from scratch — "building an OS core used to take teams of highly specialized senior engineers years of grueling work. And he did it live. And he did it for under a thousand dollars in raw compute costs." Then, to prove the architecture actually worked, "he ran a live clone of the video game Doom on top of it. Of course he ran Doom. It's always Doom." (15:08–15:52)
- **The "ceiling just got raised to the stratosphere."** Connect the dots: persistent environments + blazing 3.5 Flash speed + free desktop-accessible multi-agent orchestration harness = "the ceiling of what a single developer can accomplish has just been raised to the stratosphere." (15:52–16:18)
- **The closing provocation: developer as diplomat.** "The guide constantly emphasizes that parallel agents are totally isolated. They cannot natively see each other's code unless a human explicitly designs a common routing layer to connect them. If AI can now write the code, build the web apps, manage the servers, and even build its own next generation models, will the developer of the future simply be a **diplomat**? Someone whose only job is to negotiate routing paths, set up communication protocols, and resolve disputes between completely isolated, superintelligent digital workers?" Bookend callback: "We used to play the piano. Now we're just making sure the players are in the same room." (16:18–17:07)

## Notable Quotes
> "Anti-gravity 1.0 was a really fast typist looking over your shoulder. Two point O is a standalone multi-agent workforce." — ~2:04 (the paradigm shift in one line)

> "You are no longer prompting a single engine to finish a sentence. You are now directing a team of independent agents." — 2:31

> "The agent generates all of this asynchronously. But, and this is vital, it halts before doing anything destructive." — 3:39 (review-driven development in a sentence)

> "It does all the heavy legwork, but you hold the keys." — 3:55

> "Parallel agents are totally isolated by design. Think of them as working in completely separate soundproof rooms. They cannot natively see, touch, or edit what the other agent is doing." — 6:18 (the central architectural gotcha)

> "You aren't just writing features, you're architecting communication bridges between AIs." — 7:08

> "The AI was basically used to build the next faster version of itself. They eat their own dog food at the highest possible level of computer science." — 10:06 (Gemini 3.5 Flash co-developed by Antigravity)

> "In software orchestration, a 20-second lag means the system is effectively unusable. It's just broken at that point." — 9:38

> "If your team has continuous integration pipelines built on the old CLI, they will break on June 18th. Those pipelines run unattended, so if they're calling the old Gemini CLI to run tests or build code, they're going to hit a brick wall." — 11:24 (the hard deadline, podcast-length emphasis)

> "You aren't just telling the AI what to code, you are managing its literal lifespan." — 13:22 (the session-TTL reality)

> "It's like forcing the AI to bookmark its page and switch desks before the lights turn off in the office." — 13:18 (the TTL pattern)

> "Of course he ran Doom. It's always Doom." — 15:50 (the keynote payoff, with a wink)

> "The ceiling of what a single developer can accomplish has just been raised to the stratosphere." — 16:14

> "Will the developer of the future simply be a diplomat? Someone whose only job is to negotiate routing paths, set up communication protocols, and resolve disputes between completely isolated, superintelligent digital workers?" — 16:46 (closing provocation)

## Tools and Resources Mentioned
- **Google Antigravity 2.0** — Google's standalone multi-agent orchestration desktop app. ⚠️ **Google's product, NOT this stack (MiniMax / Hermes).**
- **Gemini 3.5 Flash** — Google's default model for the Antigravity 2.0 ecosystem. ⚠️ **Google's model, not Anthropic, not a third-party "Flash."**
- **Antigravity CLI (Go-based)** — Google's replacement for the old Gemini CLI. Migration deadline: 2026-06-18. ⚠️ **Google's CLI.**
- **Gemini CLI (legacy)** — the old Google CLI being hard-cut on June 18, 2026. ⚠️ **Google's tool, not Anthropic's.**
- **Interactions API** — Google's API surface for managed agents (persistent isolated Linux envs, custom skills via markdown). ⚠️ **Google's API, not a third-party SDK.**
- **Ria Bansal's "Google Antigravity 2.0, The Complete Developer Guide"** — the Analytics Vidia article this entire podcast is built around.
- **Varun Mohan** — the engineer (Codeium/Windsurf alumnus, now Google) who delivered the I/O keynote demo (built an OS core live with parallel agents, ran Doom on it, under $1,000 compute).
- **FastAPI** — the Python web framework used in the to-do-app walkthrough artifact.
- **Continuous Integration (CI) pipelines** — the unattended automation that the June 18 deadline most directly threatens.

## GitHub Repos and URLs Referenced
- (No specific GitHub repos are cited by URL in this podcast; the entire technical spine is the Ria Bansal article on Analytics Vidia, summarized conversationally. The earlier short video `8I5ZmNZXqEU` covers the same topic in 8 min and is the companion note for this repo.)

## Action Items
- [ ] **Before 2026-06-18**, audit every CI pipeline, cron job, and shell script that calls the old Gemini CLI. Treat migration to the Go-based Antigravity CLI as urgent and top-tier — it is a hard stop, not a rolling deprecation. Remember the syntax and dependencies change (Go vs. the old language), so this is a real port, not a copy-paste.
- [ ] **For any long-running Antigravity workflow**, read the Interactions API session-TTL documentation and explicitly build session-expiry handling into your code: monitor the TTL clock, force the agent to export state and files to permanent storage before expiry, spin up a fresh environment, and re-import. Do not assume a multi-day refactor survives on a single session.
- [ ] **For any multi-agent fan-out over the same codebase**, design the routing layer up front. Pick a shared database (read-permission) or a message broker (queue-based) and document the contract between agents. Do not assume parallel agents see each other's file changes — they don't, by design.
- [ ] **Default to "review-driven development" mode** for any production work. Use **plan mode** for multi-file projects. Treat the agent's artifacts (task lists, implementation plans, code diffs) as the unit of review, not raw generated code.
- [ ] **For latency-sensitive orchestration**, benchmark on Gemini 3.5 Flash, not 3.1 Pro. The 4x speed advantage is the difference between a 20-second system (unusable) and a 5-second system (responsive). Speed is structural, not cosmetic.
- [ ] **Track Google's pattern of dog-fooding Antigravity to build Gemini 3.5 Flash** as a credibility signal — but also as a tell that Google is heavily invested in the multi-agent story, so the ecosystem will keep evolving fast. Don't over-build on top of unstable primitives.

## Open Questions
- **What is the actual session TTL on Interactions API managed sessions?** Both Eddy and Ria Bansal gesture at it but never quote a number. Until you know, assume short and design for the worst case.
- **The Doom-on-OS-core demo is the headline, but is it reproducible?** Did Varun Mohan use a public recipe, or was the <$1,000 compute figure cherry-picked for the keynote? An open reproduction recipe would convert the demo from spectacle to engineering reference.
- **What is the recommended pattern for the "routing layer" between soundproof-room agents?** Eddy's article mentions shared databases and message brokers, but doesn't pick a winner. Is there a Google-recommended reference architecture, or is every team rolling their own conveyor belt?
- **What is the actual migration path from old Gemini CLI to new Go-based Antigravity CLI?** The podcast says "the syntax and dependencies change" but doesn't give a side-by-side. Is there a published porting guide, or is the June 18 cutoff going to break CI pipelines on a known unknown?
- **What is the actual scope of the "enterprise platform" touchpoint?** The desktop app, CLI, SDK, and managed APIs are all well-sketched. The enterprise platform (full Google Cloud integration) gets a single mention. Is this a rebrand of an existing Google Cloud product, or genuinely new?
- **Where does the "scheduled tasks" primitive live in the Interactions API?** Is it a feature of the API itself, or do you roll your own cron-on-serverless pattern? The headline feature of the paradigm shift is under-specified in both the short and the long-form.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 17:07 transcript)</summary>


```
0:01 [snorts]
0:03 [music]
0:06 >> You know, usually um
0:08 when we talk about software development,
0:09 there is this expectation of direct,
0:12 almost mechanical input, right?
0:14 >> Right, yeah. Like a one-to-one thing.
0:15 >> Exactly. You sit at a piano, you press a
0:17 key, and a specific note plays. Or, you
0:21 know, you type a line of code, and the
0:23 computer just executes exactly that one
0:25 command.
0:25 >> Yeah, it's very predictable. Human
0:27 thought directly translating into like a
0:30 single machine action. The machine
0:32 doesn't anticipate the melody. It just,
0:34 well, it just waits for you to strike
0:35 the next key.
0:36 >> But imagine if you sat down at that
0:38 piano, played a single chord, and
0:40 suddenly the piano stood up, grabbed a
0:43 cello and a violin, composed an entire
0:45 symphony on the spot, and then turned to
0:47 you and asked,
0:48 uh, "How did you like the second
0:50 movement? Should we make the tempo a
0:51 little faster?"
0:52 >> Which sounds completely absurd.
0:54 >> It does. But that is the level of
0:56 unreality we are stepping into today.
0:58 It's Monday, May 25, 2026, and we are
1:01 unpacking an absolute monster of a
1:03 release that just dropped at Google I/O.
1:05 >> Yeah, monster's the right word for it.
1:07 >> We're pulling our insights today from a
1:09 phenomenal breakdown from Analytics
1:11 Vidia, and it's titled Google
1:13 Antigravity 2.0, The Complete Developer
1:16 Guide, written by Ria Bansal.
1:19 And the mission for this deep dive is to
1:21 figure out what is actually happening
1:22 here, because this isn't just a software
1:24 update. It's um it's a complete
1:27 reimagining of how humans and AI build
1:30 things together.
1:31 >> Reading through her analysis, it becomes
1:33 abundantly clear that Google didn't just
1:35 push an update. They completely tore up
1:36 the floorboards of how developers work.
1:38 >> Yeah, so whether you are an engineering
1:41 lead prepping for a strategy meeting, or
1:43 you are just insanely curious about the
1:45 future of work, we are going to break
1:47 down this shift, and we're going to do
1:48 it without the jargon overload.
1:51 Okay, let's unpack this. Back in
1:53 November 2025, we had Antigravity 1.0.
1:56 >> Right.
1:57 >> And that was basically a really fast
1:58 typist looking over your shoulder. You
2:00 were still writing the code in your
2:01 normal environment. It was just
2:02 predicting your next few words. But 2.0
2:04 is a standalone multi-agent workforce.
2:07 >> What's fascinating here is that
2:08 anti-gravity 1.0 lived entirely inside
2:11 your integrated development environment,
2:12 you know, your IDE.
2:13 >> The place where you write the code.
2:15 >> Exactly. Its entire universe was limited
2:17 to the single file you had open.
2:20 But anti-gravity 2.0 breaks out of that
2:22 completely. It is now a standalone
2:25 desktop application built from the
2:27 ground up.
2:28 >> Oh, wow.
2:29 >> Yeah, so you are no longer prompting a
2:30 single engine to finish a sentence. You
2:32 are now directing a team of independent
2:34 agents.
2:35 >> And directing is the operative word
2:37 there, I think, because Rhea's Guide
2:39 highlights a feature called scheduled
2:40 tasks, which really struck me.
2:41 >> Oh, yeah, that's a big one.
2:42 >> Because before an AI just sat there
2:45 static waiting for you to hit enter. But
2:47 with scheduled tasks, you can give an
2:50 agent a goal, tell it to run in the
2:52 background every hour or every day, and
2:54 it becomes comes this continuous
2:56 autonomous process.
2:57 >> Which fundamentally alters the cognitive
2:59 load on the user.
3:01 We have to look at what Google calls
3:02 review-driven development.
3:04 >> Review-driven development, okay, what is
3:06 that?
3:06 >> It's the new default mode. So, in the
3:08 old model, you did the manual labor,
3:10 right? Now, the agent takes your
3:12 high-level objective and starts
3:13 generating all the intermediate
3:15 artifacts on its own just running in the
3:16 background.
3:17 >> By artifacts, you mean like the building
3:19 blocks of a project. Things like a task
3:21 list or a blueprint of how it plans to
3:24 build a feature.
3:24 >> Exactly. The planning documents, the
3:27 architectural diagrams, and crucially,
3:29 the code diffs.
3:30 >> The actual code changes.
3:32 >> Right. The actual line-by-line changes
3:34 it intends to make to your project. The
3:36 agent generates all of this
3:38 asynchronously. But, and this is vital,
3:40 it halts before doing anything
3:42 destructive.
3:43 >> So, it doesn't just overwrite everything
3:44 blindly.
3:45 >> No, not at all.
3:46 It basically raises its hand and says,
3:49 "Here is my plan, and here is the exact
3:51 code I'm going to inject to execute that
3:53 plan. Do you approve?
3:54 >> It does all the heavy legwork, but you
3:56 hold the keys.
3:56 >> Precisely.
3:57 >> I want you to just imagine for a second
3:59 how your daily workflow would change if
4:00 you operated this way. Imagine if you
4:03 only had to approve milestones rather
4:05 than write every single line of an email
4:07 or every block of code or, you know,
4:09 every weekly project update. You are
4:11 just reviewing and saying yes, no, or
4:13 tweak this.
4:14 >> It frees the developer up to focus
4:16 entirely on architecture, system logic,
4:19 and overarching business goals rather
4:22 than getting bogged down in syntax and
4:23 boilerplate code.
4:25 >> I mean, that sounds amazing. But if my
4:27 entire job shifts to just reviewing and
4:30 approving these massive blocks of work,
4:32 I have to wonder where this work is
4:34 actually happening. Because this isn't
4:36 just taking place in a little chat
4:37 window anymore. We're moving from the
4:39 front-end interface to the back-end API.
4:42 >> Yeah, the desktop app you're looking at
4:44 is just the control room. The heavy
4:46 lifting is done through what the guide
4:48 refers to as managed agents in the
4:50 Gemini API.
4:51 >> Okay, unpack that for us.
4:53 >> What happens is with a single API call,
4:55 a developer can spin up an agent inside
4:58 an isolated Linux environment.
5:00 >> Linux being the operating system that
5:01 runs most of the internet's servers,
5:03 yeah.
5:03 >> Right.
5:04 >> So, it's basically spinning up a tiny
5:05 virtual computer in the cloud for this
5:08 agent to live in.
5:09 >> Exactly. And it's not just a temporary
5:11 sandbox that disappears when you close
5:13 the window. That's a huge point from the
5:14 guide. These are persistent isolated
5:17 environments.
5:18 Every time you interact, the files in
5:20 the state stay completely intact between
5:23 turns. There's zero reset.
5:24 >> Oh, wow. So, they remember everything.
5:26 >> Let's say your agent downloads a
5:28 specific Python library, writes a
5:30 script, and saves a configuration file.
5:32 You can close your laptop, come back 3
5:35 hours later in a follow-up call, and
5:37 everything is exactly where the agent
5:38 left it.
5:39 >> Wait, hold on. Here's where it gets
5:40 really interesting, but also where I get
5:42 completely stuck.
5:43 >> Okay, lay it on me.
5:45 >> I am trying to picture the architecture
5:47 of this.
5:48 If every single agent gets its own
5:50 persistent isolated Linux box,
5:54 what happens when you have multiple
5:55 agents working on the same project?
5:57 >> Uh
5:58 >> Like if agent A is writing the database
5:59 back end and agent B is building the
6:01 user interface, don't they end up
6:03 stepping on each other's toes or
6:05 overriding each other's files?
6:07 >> but only because they literally can't.
6:09 >> What do you mean they can't?
6:10 >> This is a massive constraint that
6:12 Re-Abigail specifically warned about in
6:14 the developer guide.
6:16 Parallel agents are totally isolated by
6:18 design. Think of them as working in
6:20 completely separate soundproof rooms.
6:22 >> Soundproof rooms?
6:23 >> Yeah. They cannot natively see, touch,
6:26 or edit what the other agent is doing.
6:28 >> Wait, really? Because I'm a developer, I
6:30 barely have time to write my own
6:32 application logic, and now you're
6:33 telling me I have to build an entire HR
6:35 communication department just so my AI
6:37 agents can talk to each other and share
6:38 files. How is that saving me time?
6:41 >> Because the alternative is absolute
6:43 chaos.
6:43 >> Chaos?
6:44 >> Yeah, think about it. If you have five
6:46 super fast autonomous agents all trying
6:48 to edit the same core file
6:49 simultaneously, your code base corrupts
6:52 in seconds. They would constantly
6:53 override each other's work.
6:55 >> Oh, I see.
6:56 >> So yes, you, the human, must explicitly
6:58 design a common routing layer for their
7:00 outputs. This raises an important
7:02 question about how developers actually
7:04 build things now. You aren't just
7:06 writing features, you're architecting
7:08 communication bridges between AIs.
7:10 >> A routing layer? Let's break that down
7:13 cuz it sounds a bit abstract. What does
7:14 a routing layer actually look like in
7:16 practice?
7:17 >> Well, it could be a shared database that
7:18 they all have permission to read from,
7:20 or it could be a message broker system,
7:22 which is basically a piece of software
7:24 specifically designed to take a message
7:26 from agent A, put it in a queue,
7:29 and securely deliver it to agent B when
7:32 agent B is ready for it.
7:33 >> Okay, so it's a conveyor belt.
7:34 >> Exactly. The point is the developer has
7:36 to build the conveyor belts between
7:38 these isolated rooms.
7:39 >> Wow. But, if these agents are in totally
7:42 isolated soundproof rooms and they can't
7:44 collaborate natively, they rely entirely
7:46 on this conveyor belts you just
7:47 mentioned.
7:47 >> Right.
7:48 >> But, the second you have 10 agents
7:49 constantly pinging each other through
7:51 that custom routing layer, sending
7:53 messages back and forth just to
7:54 coordinate basic tasks, you run into a
7:56 massive computational wall, don't you?
7:58 >> Mhm.
7:58 >> Passing messages back and forth like
8:00 that has to create a huge bottleneck.
8:02 >> Oh, absolutely. Latency becomes your
8:05 absolute worst enemy in this setup. And
8:07 that computational wall is exactly why
8:09 Google had to build Gemini 3.5 Flash.
8:12 >> Which is the new default engine running
8:14 this entire ecosystem.
8:16 >> Yes.
8:16 >> The guide has a staggering metric on
8:19 this, actually. Gemini 3.5 Flash is
8:22 roughly four times faster than previous
8:24 frontier models. It actually beats
8:26 Google's own Gemini 3.1 Pro on most
8:29 benchmarks.
8:31 But, why the obsession with sheer speed
8:33 over, say, just making the model a
8:35 little bit smarter?
8:37 >> Let's look at the underlying mathematics
8:38 of latency in an agentic workflow.
8:41 We can use, um, a corporate email chain
8:44 as an analogy.
8:45 >> Okay.
8:45 >> Imagine you need a simple yes or no
8:47 decision to move forward with a project.
8:50 But, to get it, you have to email the
8:51 accounting department and wait 5 minutes
8:53 for a reply.
8:54 >> Always waiting on accounting.
8:55 >> Right. Then, accounting has to email
8:57 legal and wait another 5 minutes. Then,
8:59 legal emails you back. Suddenly, a basic
9:01 decision takes all afternoon.
9:03 >> Right, because the delays compound with
9:05 every single hop.
9:06 >> Exactly. Now, compress that to
9:08 milliseconds.
9:09 When you are chatting with an AI
9:10 one-on-one, a delay of 200 milliseconds
9:13 is basically a blink. You don't even
9:14 notice it.
9:15 >> It feels instant.
9:16 >> But, when you are running 10 agents at
9:18 the same time,
9:19 and they are constantly evaluating
9:20 subtasks, passing data through those
9:23 routing layers, and checking each
9:24 other's work,
9:25 well, those API calls stack up by the
9:27 thousands.
9:28 >> So, a tiny 200 millisecond delay on one
9:31 end compounds rapidly into 10, 20
9:34 seconds of lag across the entire system.
9:37 >> And in software orchestration, a
9:38 20-second lag means the system is
9:40 effectively unusable.
9:41 >> It's just broken at that point.
9:43 >> Yeah.
9:44 If the model isn't blazingly fast, the
9:46 whole multi-agent symphony grinds to a
9:48 halt. And there's a brilliant detail in
9:50 the guide about how Google actually
9:52 achieved this speed.
9:53 >> Oh, yeah, this blew my mind.
9:55 >> Gemini 3.5 Flash wasn't built in a
9:56 vacuum by engineers just typing away. It
9:58 was actually co-developed using
10:00 Antigravity's own agentic workflows.
10:02 >> The AI was basically used to build the
10:04 next faster version of itself.
10:06 >> Yes. Google used the very same
10:07 multi-agent system they're releasing to
10:09 the public to optimize the latency of
10:11 the model that powers it. They eat their
10:13 own dog food at the highest possible
10:15 level of computer science.
10:17 >> That is an incredibly powerful proof of
10:19 viability. I mean, if Antigravity 2.0 is
10:22 robust enough for Google to use it to
10:23 architect Gemini 3.5 Flash, it's robust
10:26 enough for whatever enterprise app a
10:28 normal company might throw at it.
10:30 >> Without a doubt.
10:30 >> But relying on this much automated speed
10:33 and orchestration means developers have
10:35 to clean house immediately, right?
10:37 Because this isn't backwards compatible
10:39 with everything.
10:40 >> Yeah. The tone of the guide shifts
10:41 dramatically when it gets to a section
10:43 called "Things Worth Knowing Before You
10:46 Build."
10:47 Because with this incredible power comes
10:49 immediate, unavoidable responsibility.
10:52 >> Yeah, there's a hard deadline in there.
10:53 >> There is an absolute hard cutoff date of
10:55 June 18th, 2026 for the old Gemini CLI.
10:59 >> And for anyone who might not be a
11:01 back-end engineer,
11:02 >> Yeah.
11:02 >> a CLI, a command line interface, is
11:04 basically that stripped-down text-based
11:06 window where you type commands directly
11:08 to your computer. There are no buttons,
11:10 no graphics, just pure text commands.
11:12 >> It's the primary way automated systems
11:14 and developer tools talk to the
11:15 underlying operating system.
11:17 And Re-Avanse all makes it crystal
11:19 clear. This is not a gentle phase
11:21 deprecation.
11:22 >> It's a hard stop.
11:23 >> If your team has continuous integration
11:25 pipelines built on the old CLI,
11:27 they will break on June 18th.
11:29 >> Continuous integration pipelines,
11:30 meaning um the automated scripts that
11:33 companies use to test and deploy their
11:35 software every time a developer makes an
11:37 update.
11:37 >> Precisely. Those pipelines run
11:39 unattended. So, if they're calling the
11:41 old Gemini CLI to run tests or build
11:43 code, they're going to hit a brick wall.
11:46 >> Yikes.
11:46 >> You must treat the migration to the new
11:48 Go-based Antigravity CLI as an urgent,
11:52 top-tier priority.
11:54 And migrating isn't always just a
11:56 copy-paste job. The underlying syntax
11:58 and dependencies change when you move to
12:00 a new CLI built on a completely
12:02 different programming language like Go.
12:04 >> So, that is a hard deadline hovering
12:06 right around the corner. But, the guide
12:08 also brings up another constraint
12:09 developers need to manage, which is the
12:11 reality of time within these systems.
12:13 >> Time management is huge now.
12:14 >> Because we talked earlier about those
12:16 persistent Linux environments for the
12:17 agents, they actually have a TTL, a time
12:19 to live.
12:20 >> You cannot just spin up an agent, give
12:22 it a task, and leave it running in the
12:24 background for 6 months. Those isolated
12:26 sessions will eventually expire. The
12:28 server will shut them down to free up
12:30 resources.
12:31 >> How does a developer actually deal with
12:32 that? If I have an agent working on a
12:34 massive code refactoring task that takes
12:37 3 days, and the session expires after 1
12:39 day, doesn't the agent just die
12:41 mid-thought?
12:42 >> It absolutely does, and you lose any
12:44 uncommitted progress.
12:45 >> Oh, man, that's brutal.
12:47 >> It is. That is why developers must
12:49 manually build session expiry logic into
12:52 their long-running workflows.
12:53 >> Okay, so how does that work?
12:55 >> You essentially have to teach your
12:56 application to monitor the TTL clock.
12:59 >> [snorts]
12:59 >> When the environment is getting close to
13:01 expiring,
13:02 your system needs to force the agent to
13:04 save its state, export its files to a
13:06 permanent storage location, request a
13:08 brand new Linux environment, and then
13:10 re-import everything so the agent can
13:12 pick up exactly where it left off.
13:14 >> It's like forcing the AI to bookmark its
13:16 page and switch desks before the lights
13:18 turn off in the office.
13:19 >> Exactly that.
13:20 >> That is a huge technical reality check.
13:23 You aren't just telling the AI what to
13:24 code, you are managing its literal
13:26 lifespan. But, let's ground all this
13:28 theory in reality, because the guide
13:31 gives this fantastic hands-on example of
13:33 building a to-do app from scratch, and
13:35 it perfectly illustrates how all these
13:37 mechanics come together.
13:38 >> It's a great example of review-driven
13:40 development in action.
13:41 >> So, imagine you open the anti-gravity
13:43 2.0 desktop app. You start a
13:45 conversation and switch the interface
13:47 into plan mode. You type in a very
13:49 standard request. You want a FastAPI
13:53 back end, which is just a a fast modern
13:55 framework for building the server side
13:57 of the app in Python, and you want a
13:59 standard HTML and JavaScript front end.
14:02 >> Instead of just spitting raw code into a
14:03 chat window, the agent analyzes the
14:06 request and generates an implementation
14:07 plan artifact.
14:08 >> Right, the blueprint. So, you review the
14:10 blueprint, you click approve, and then
14:12 you literally watch the main.py file for
14:14 the server and the index.html file for
14:17 the interface populate in real time in
14:19 your editor.
14:20 >> It's mesmerizing to watch.
14:21 >> And then and I love this detail, you use
14:23 something called the walkthrough
14:24 artifact to execute the app.
14:26 >> The walkthrough artifact is fascinating,
14:28 because it's not just a text summary,
14:30 it's an executable container.
14:31 >> An executable container, meaning it runs
14:33 the code.
14:34 >> Yeah, it takes the Python code the agent
14:36 just wrote, bundles it with the
14:37 necessary server software, and
14:39 automatically binds it to a network port
14:41 on your local machine.
14:42 >> Which is why the guide says it runs on
14:44 localhost:8000.
14:46 It turns your own computer into a
14:47 temporary web server, so you can open
14:49 your normal web browser, type in
14:51 localhost:8000,
14:53 and suddenly you are interacting with a
14:55 live, functioning application that
14:57 didn't exist 3 minutes ago, just like
14:59 that.
14:59 >> You acted as the manager, reviewing the
15:01 plan, and the agents laid the bricks,
15:04 wired the electricity, and turned on the
15:06 lights.
15:06 >> So, what does this all mean? We have
15:08 background agents, completely isolated
15:10 Linux environments, complex routing
15:12 layers, AI building its own AI.
15:16 Where is this actually heading?
15:17 >> We just have to look at the I/O keynote
15:19 demo that Ria highlights at the end of
15:20 her guide.
15:22 Varun Nohria stood on stage and using
15:24 these parallel agents inside
15:25 anti-gravity 2.0, he built a working
15:28 operating system core from scratch.
15:30 >> Building an OS core used to take teams
15:32 of highly specialized senior engineers
15:34 years of grueling work.
15:36 >> And he did it live.
15:37 >> Mhm.
15:38 >> And he did it for under a thousand
15:39 dollars in raw compute costs.
15:41 >> That is just unreal.
15:42 >> And just to prove that the architecture
15:44 actually worked, he ran a live clone of
15:46 the video game Doom on top of it.
15:49 >> Of course he ran Doom. It's always Doom.
15:51 >> Always Doom.
15:52 But if we connect this to the bigger
15:54 picture,
15:55 you might not be building an operating
15:57 system today, but the underlying
15:59 infrastructure that made that keynote
16:01 demo possible, the persistent
16:03 environments, the blazing speed of
16:04 Gemini 3.5 flash, the multi-agent
16:07 orchestration harness that is now freely
16:09 available on your desktop,
16:10 >> is crazy.
16:11 >> the ceiling of what a single developer
16:13 can accomplish has just been raised to
16:15 the stratosphere.
16:16 >> It really has.
16:18 Which leaves me with a final thought I
16:19 want you to mull over as we wrap up this
16:21 deep dive. The guide constantly
16:23 emphasizes that parallel agents are
16:25 totally isolated. They cannot natively
16:27 see each other's code unless a human
16:29 explicitly designs a common routing
16:31 layer to connect them. If AI can now
16:34 write the code, build the web apps,
16:36 manage the servers, and even build its
16:38 own next generation models, will the
16:40 developer of the future simply be a
16:42 diplomat? Someone whose only job is to
16:44 negotiate routing paths, set up
16:46 communication protocols, and resolve
16:48 disputes between completely isolated,
16:50 superintelligent digital workers? We
16:53 used to play the piano. Now we're just
16:55 making sure the players are in the same
16:56 room. Thank you for joining us on this
16:57 deep dive and keep questioning the
16:59 evolving digital world around you.
17:02 >> [music]
```

</details>
