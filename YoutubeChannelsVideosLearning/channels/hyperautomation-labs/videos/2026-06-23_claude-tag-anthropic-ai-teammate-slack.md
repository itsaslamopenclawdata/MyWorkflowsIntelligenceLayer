---
title: "Claude Tag: Anthropic Put an AI Teammate in Your Slack — Build Your Own"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-23"
duration_seconds: 603
video_id: "T3gtaijgdrc"
url: "https://www.youtube.com/watch?v=T3gtaijgdrc"
language: "en"
tags: [claude-tag, anthropic, slack, mcp, bolt, n8n, make-com, vector-db, ambient-mode, opus-4, ai-teammate, rpa, hyperautomation, agentic-ai]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-25"
---

# Claude Tag: Anthropic Put an AI Teammate in Your Slack — Build Your Own

**Channel:** Hyperautomation Labs
**Published:** 2026-06-23
**Duration:** 10m 03s
**Watch:** https://www.youtube.com/watch?v=T3gtaijgdrc

## TL;DR

Anthropic just launched **Claude Tag**, a shared Claude instance that lives inside Slack channels and is invoked by `@`-mentioning it like a coworker. Anthropic reports 65% of their internal product team code is now produced by an internal version of this pattern. It's currently gated to Enterprise/Tier customers, but the design is fully reproducible with public tools. The video gives a four-pillar blueprint: (1) the Bolt mention-to-reply loop, (2) MCP tool/data integration, (3) tiered memory (channel history → vector DB → Claude's memory tool), and (4) ambient mode via scheduled jobs that let the bot speak unprompted. Both a developer path (Python/JS Bolt + Anthropic SDK) and a no-code path (n8n or Make) are shown.

## Key Insights

- **AI is shifting from "chatbot you visit" to "teammate that lives where the work happens"** — Slack is the deployment surface, not a separate URL. This is a category shift, not a feature launch.
- **Four design behaviors make a bot a teammate, not a chatbot:** multiplayer (one shared Claude visible to the whole channel), learning over time (channel/thread context), initiative (ambient mode that flags issues and follows up), and asynchronous work (hand off a task and walk away).
- **The 65% code stat is the headline business signal:** Anthropic's product team now ships the majority of their code through an internal Claude-in-Slack. Use cases extend beyond engineering to product metrics, support tickets, and root-cause bug analysis.
- **The four-pillar DIY architecture** (each maps to a Claude Tag superpower):
  1. **Code loop** — Slack app + Bolt (JS or Python) listening for `app_mention`, two scopes (read mentions, post replies), Anthropic SDK call, post back to thread. Socket Mode for local testing; Events API for production.
  2. **Tools via MCP** — Model Context Protocol is the open standard. Honest caveat: Slack's official MCP server is gated to published/internal apps, so hobbyist bots need to read channel history through Slack's normal APIs and wire MCP only for tools you control (GitHub, DB, etc.).
  3. **Memory in three tiers** — (a) pull recent channel/thread history per mention (free, very effective), (b) vector DB for long-term RAG retrieval, (c) Claude's native memory tool with a writable folder. Start at (a), graduate as needed.
  4. **Ambient mode** — scheduled cron-style job that wakes on its own, asks Claude "is there anything the team should know?", and posts a digest. Can also watch for silent threads and schedule self-follow-ups. **Hard cap spend from day one — this is not optional.**
- **No-code path is real:** n8n = Slack trigger → Anthropic chat model in AI agent node → Slack reply block. Make.com has equivalent modules. Drag, drop, wire with lines — no terminal required.
- **Three things are genuinely hard to replicate** and worth being honest about: shared identity with permission-aware context blending, reliable always-on ambient loops, and security/scope discipline on broad tokens.
- **The 30-day migration window is real** for admins running the old "Claude in Slack" app — note this if you have a Claude enterprise seat.

## Notable Quotes

- "65% of their product team's code is now written by an AI that lives inside their Slack." — on Anthropic's internal usage
- "You don't open a chat window. You just mention it. Like a co-worker." — defining the UX shift
- "It's not a separate chatbot you visit. It lives where the work already happens."
- "A teammate that reads everything and speaks up on its own is burning tokens around the clock. So put a hard cap on your spending from day one. That part is not optional. It's survival."
- "Your do-it-yourself version trades a bit of that polish for one huge thing. You actually own it and you can start building it tonight."
- "The real story here isn't one product launch. It's a shift. AI is moving from a chatbot you go and visit to a teammate that lives inside the place your team already works."

## Tools and Resources Mentioned

- **Claude Tag** — Anthropic's new Slack-resident Claude (Enterprise/Tier beta, Opus 4 model, 30-day migration window from old Claude-in-Slack app).
- **Claude (Anthropic SDK)** — model used under the hood; Opus 4.8 referenced for the code path.
- **Slack Bolt** — official Slack SDK for building mention-to-reply bots. Both JavaScript and Python versions shown.
- **Socket Mode** — Slack mode for local development (no public server required).
- **Events API** — Slack's web-based event delivery for production deployments.
- **MCP (Model Context Protocol)** — open standard for wiring Claude to real tools/data (GitHub, databases, etc.). Note: Slack's official MCP server is gated to published/internal apps.
- **Vector database** — for long-term memory / RAG (any vendor; not named specifically).
- **Claude Memory Tool** — Claude's native long-term memory feature with a writable folder.
- **n8n** — free open-source no-code automation platform; three blocks (Slack trigger → Anthropic chat model → Slack reply) build the whole teammate.
- **Make.com** — alternative no-code platform with native Slack + Claude modules following the same pattern.
- **Free one-page blueprint** — comment "sidekick" on the video or use the link in description to get all four pillars, exact Slack permissions, and the no-code recipe on a single sheet.

## GitHub Repos and URLs Referenced

- https://www.youtube.com/watch?v=T3gtaijgdrc — source video
- Slack Bolt (JS): https://slack.dev/bolt-js
- Slack Bolt (Python): https://slack.dev/bolt-python
- Anthropic SDK: https://github.com/anthropics/anthropic-sdk-python (and JS equivalent)
- Model Context Protocol: https://modelcontextprotocol.io
- n8n: https://n8n.io
- Make.com: https://make.com
- Channel socials: Hyper Automation Labs on Instagram and Facebook (links in description)
- Author's paid guides mentioned (not downloaded here): "Cloud Code", "Codex", "Cloud Code Work for Sales", and a certification prep kit — all linked in video description.

## Action Items

- [ ] **Decide on a use case** before building — pick one channel and one recurring pain point (code reviews? support triage? product metrics digests?) so memory and ambient triggers have a target.
- [ ] **Create a Slack app** at api.slack.com, subscribe to `app_mention` event, grant scopes `app_mentions:read` and `chat:write` (minimum).
- [ ] **Build the Bolt mention-loop first** (Python or JS) — confirm reply works in a test channel using Socket Mode before adding anything else.
- [ ] **Add MCP tool integrations** for one external system (start with GitHub or your DB). Skip Slack's official MCP server for hobby builds; use Slack's Web API for channel history.
- [ ] **Implement tier-1 memory** (pull recent channel/thread history per mention) before touching a vector DB.
- [ ] **If going no-code:** spin up n8n, add Slack trigger → Anthropic chat model node (Claude) → Slack reply block; test the same flow.
- [ ] **Set a hard spend cap on the Anthropic API key** *before* enabling ambient mode. Use Anthropic console usage limits.
- [ ] **Scope Slack bot token tightly** — request only the channels and scopes the bot actually needs; review monthly.
- [ ] **Grab the free one-page blueprint** by commenting "sidekick" on the video (or using the description link).
- [ ] **Migrate off the old "Claude in Slack" app within 30 days** if your org is a Claude enterprise customer.

## Open Questions

- Which specific vector DB does the video creator recommend? (None named explicitly — Qdrant, Pinecone, Weaviate, Chroma are all viable; needs a follow-up pick.)
- What's the actual cost profile of a "Claude teammate" running 8h/day with ambient mode on? The video warns to cap spend but doesn't give a real number — worth benchmarking.
- How does Anthropic handle permission-aware context blending in Claude Tag's "one shared Claude" — i.e., how does it know not to leak a private-DM fact into a public channel? The video flags this as "real engineering" but doesn't unpack the mechanism.
- Is the "65% of product team code" figure self-reported by Anthropic and does it include review/merge time, or just generation? Worth verifying against Anthropic's published sources.
- For n8n/Make builds, how do you handle the long-running async tasks ("hand it a task, walk away for hours") — are they polling, streaming, or true push? Bolt path is clearer; automation-platform path needs verification.
- Does Slack's gated MCP server policy loosen over the beta, or will hobby/community apps need a wrapper layer long-term?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 10m 03s transcript)</summary>

0:00 Anthropic just quietly admitted
0:02 something a little wild.
0:04 65% of their product team's code is now
0:07 written by an AI that lives inside their
0:10 Slack.
0:11 You don't open a chat window.
0:12 You just mention it. Like a co-worker.
0:14 Type what you need in plain English and
0:17 walk away while it does the work.
0:19 It's called Claude Tag. And it launched
0:21 today.
0:23 There's just one catch. It's locked to
0:25 big enterprise customers.
0:27 So, I spent today figuring out how to
0:29 build the same thing yourself.
0:31 With tools you can actually get your
0:32 hands on.
0:33 By the end of this, you'll have the full
0:35 blueprint for your own AI teammate in
0:37 Slack.
0:38 First, what Anthropic actually shipped
0:41 because the design is the whole lesson.
0:43 Claude Tag lets Claude join your Slack
0:46 as a team member.
0:47 You give it access to specific channels.
0:50 And you connect it to whatever tools,
0:52 data, and even code bases you choose.
0:55 Then, anyone in that channel can tag it
0:57 with a request in plain in terms.
1:01 And it breaks that request into stages,
1:03 works through them one by one using the
1:06 tools it has access to, and replies
1:09 right there in a Slack thread with
1:11 whatever it created.
1:13 It's not a separate chatbot you visit.
1:15 It lives where the work already happens.
1:18 And it runs on Anthropic's top model,
1:20 Opus 42 neat.
1:21 Here's what turns it from a chatbot into
1:24 a teammate.
1:26 Anthropic lists four behaviors.
1:29 First, it's multiplayer.
1:31 There's one shared Claude in the
1:33 channel. So, anyone can see what it's
1:35 working on and pick up the conversation
1:37 right where the last person left off.
1:40 Second, it learns over time.
1:42 As it follows the channel, it builds
1:44 context. So, you stop explaining the
1:46 same things over and over and it will
1:48 not read your private channels.
1:51 Third,
1:52 it takes initiative.
1:54 Switch on
1:55 what they call ambient mode
1:57 And it proactively flags things you
1:59 might need to know.
2:01 And follows up on threads that went
2:03 quiet.
2:04 And fourth, it works asynchronously.
2:07 Hand it a task, go do something else,
2:10 and it can even schedule work for itself
2:12 over hours or days.
2:13 Now,
2:14 why should you care if you can't even
2:16 use it yet? Because of that number.
2:19 Anthropic says 65% of their product
2:21 team's code is now created by the
2:23 internal version of this
2:25 And it's spreading well beyond
2:27 engineering. They're tagging Claude to
2:29 chase down product metrics, work through
2:31 support tickets, and even find the root
2:34 cause of tricky bugs.
2:35 They literally call it the next
2:36 evolution of Claude code.
2:38 The real story here isn't one product
2:40 launch.
2:41 It's a shift.
2:42 AI is moving from a chatbot you go and
2:45 visit to a teammate that lives inside
2:47 the place your team already works.
2:49 So, here's the wall you're going to hit.
2:52 Claude tag is in beta, and it's only for
2:55 Claude enterprise and team customers.
2:57 Administrators have a 30-day window to
2:59 migrate off the old Claude in Slack app.
3:01 There are introductory launch credits,
3:03 and it runs on Opus for domain.
3:06 Translation,
3:07 if you're a solo builder, a creator, or
3:10 a small scrappy team,
3:11 you can't just switch it on.
3:13 But here's the good news, and it's the
3:15 whole point of this video.
3:17 Nothing about the idea is locked.
3:19 Every single piece you need to build
3:21 your own version is public and available
3:23 right now.
3:24 Let me show you exactly how.
3:26 Here's what we're actually building.
3:28 A bot that lives in your Slack,
3:32 that you mention like a co-worker,
3:34 that calls Claude
3:35 under the hood,
3:36 uses real tools,
3:39 remembers your channel, and can even
3:41 speak up on its own.
3:43 I'm going to break it into four pillars,
3:45 and each one maps directly onto a Claude
3:48 tag superpower.
3:50 And there are two paths through this.
3:53 A developer path with a little code
3:56 and a no-code path
3:58 if you have never opened a terminal in
3:59 your life.
4:00 I'll show you both.
4:02 Every command and setting stays up on
4:04 screen.
4:05 So, you can pause,
4:06 read it, and copy it exactly.
4:09 Pillar one is the code loop.
4:11 You mention it, it replies.
4:13 You create a Slack app and use Slack's
4:16 own official toolkit called Bolt.
4:19 There's a version for JavaScript and one
4:22 for Python, both on screen.
4:25 You subscribe to a single event that
4:27 fires whenever someone mentions your
4:28 bot.
4:29 And you grant it just two permissions.
4:32 One to hear those mentions and one to
4:34 post replies.
4:35 When a mention comes in, you take the
4:37 text, send it to Claude using
4:38 Anthropic's library with the Opus 4.8
4:41 model, and post the answer straight back
4:44 into the same Slack thread.
4:46 For testing on your own laptop,
4:49 you turn on Socket Mode, so you don't
4:50 even need a public server.
4:52 For real production use, Slack
4:55 recommends the Events API over the web
4:57 instead.
4:58 That loop
4:59 right there is your teammate's
5:01 heartbeat.
5:02 A teammate that can only talk is
5:04 useless.
5:05 Pillar two is tools, and this is exactly
5:07 what MCP,
5:09 the Model Context Protocol, was built
5:11 for.
5:12 It's the open standard that lets Claude
5:13 actually use your tools and data, your
5:15 GitHub, your database, even Slack
5:17 itself, instead of just chatting about
5:19 them.
5:20 Now, here's an honest catch most videos
5:22 skip.
5:23 Slack did ship an official MCP server,
5:26 and it's powerful,
5:28 but it's gated.
5:30 Only published or internal apps can use
5:31 it. So, a quick unlisted hobby app can't
5:34 just plug in.
5:35 So, the realistic move is this.
5:37 Wire up MCP servers for the tools you
5:39 control and for Slack's own messages,
5:42 read the channel history
5:44 through Slack's normal API tools
5:46 are what turn your bot from talking
5:48 about the work
5:49 to actually doing it.
5:51 Pillar three is memory.
5:53 The learns over time part.
5:56 Out of the box, your bot forgets
5:58 everything the moment it replies.
6:01 There are three ways to fix that, and
6:03 I'll go simplest first.
6:05 Option one.
6:06 Every time it's mentioned,
6:08 pull the recent channel
6:10 or thread history
6:11 and feed it back in as context.
6:14 That costs you nothing extra
6:15 and it's shockingly effective.
6:17 Option two.
6:19 For real long-term recall,
6:21 save messages and short summaries into a
6:23 vector database,
6:24 then pull back only the relevant pieces
6:26 for each question.
6:28 That's retrieval
6:29 and it's the closest
6:31 do-it-yourself version of it learned our
6:32 whole channel.
6:34 Option three.
6:35 Claude's own memory tool,
6:37 where you hand it a memory folder it can
6:39 read from and write to.
6:41 Start with option one.
6:43 You can always graduate later.
6:45 Pillar four is the one that feels like
6:46 actual magic and it's the hardest.
6:49 Ambient mode. Speaking up without being
6:52 asked.
6:54 The secret is realizing that being
6:56 mentioned
6:57 isn't your only possible trigger.
6:59 You run a scheduled job,
7:00 a simple time task that wakes up on its
7:03 own,
7:04 asks Claude, "Is there anything the team
7:07 should know?"
7:08 and posts a short digest.
7:10 You can watch channel activity so it
7:12 notices a thread that went silent.
7:15 You can even let it schedule its own
7:16 follow-ups.
7:18 But be honest with yourself here.
7:19 A teammate that reads everything and
7:21 speaks up on its own is burning tokens
7:24 around the clock.
7:25 So put a hard cap on your spending
7:27 from day one.
7:29 That part is not optional.
7:31 It's survival.
7:33 Never opened a terminal?
7:34 You can still build this today
7:36 with zero code.
7:38 Use a free open source tool called N8N.
7:42 The whole recipe is three building
7:44 blocks.
7:45 One,
7:46 a Slack trigger that fires when someone
7:48 messages or mentions your bot.
7:50 Two,
7:51 the Anthropic chat model block dropped
7:54 into N8N's AI agent node and set to
7:56 Claude.
7:58 That's your brain.
7:59 Three,
8:00 a Slack block that sends the reply back.
8:03 You literally drag them onto a canvas
8:04 and connect them with lines. No code at
8:06 all.
8:08 And if you prefer make.com, it has its
8:11 own Slack and Claude modules that follow
8:13 the exact same pattern.
8:15 So, whether or not you write code, an AI
8:16 teammate is genuinely within your reach.
8:20 Now, let me be completely straight with
8:22 you because hype helps nobody.
8:24 A few things about Claude tag are
8:27 genuinely hard to copy.
8:30 That shared identity,
8:32 one Claude that blends everyone's
8:33 context,
8:34 but still respects who is allowed to see
8:36 what is real engineering.
8:39 True ambient behavior
8:40 means running a reliable, always-on loop
8:43 that actually knows what's still
8:44 unresolved.
8:46 And security matters a lot.
8:48 A bot with a broad access token
8:51 can quietly read far more of your
8:52 workspace than you intended.
8:54 So, scope its permissions tight
8:56 and keep watching the bill.
8:59 Anthropic runs all of that hard part for
9:01 you.
9:02 Your do-it-yourself version trades a bit
9:03 of that polish for one huge thing.
9:06 You actually own it and you can start
9:08 building it tonight.
9:10 Okay, quick honest moment.
9:12 Most of you watching this right now are
9:14 not subscribed.
9:15 The analytics are genuinely
9:17 a little brutal.
9:19 So, if any of this was useful to you,
9:21 take one second
9:22 and hit subscribe here on YouTube and
9:24 follow Hyper Automation Labs
9:26 over on Instagram and Facebook, too.
9:28 Because I do the boring reading, so you
9:30 get the honest version.
9:31 Now,
9:32 I package this entire build into a free
9:35 one-page blueprint.
9:36 All four pillars, the exact Slack
9:37 permissions, and the no-code recipe on a
9:42 single sheet.
9:43 Just comment the word sidekick
9:45 and I'll send it straight to you or grab
9:47 it at the link below.
9:49 And if you build with this stuff
9:50 seriously,
9:51 my four guides on Cloud Code, Codex,
9:54 Cloud Code Work for Sales, and the
9:56 certification prep kit
9:57 go much deeper.
9:59 The links are all in the description.
10:01 I'll see you in the next one.

</details>
