---
title: "(Podcast) How a Non Technical Founder Built a Top iOS App with Claude Code"
channel: "Eddy"
channel_slug: "eddy"
channel_id: "UC860VdxDA2EKFW9ezm36MAw"
published: "2026-06-14"
duration_seconds: 1191
video_id: "Tc3zHU6ITUQ"
url: "https://www.youtube.com/watch?v=Tc3zHU6ITUQ"
language: "en"
tags: [ai-agents, claude-code, ios, no-code, multi-agent, project-management, respiro, anthropic]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-15"
---

# (Podcast) How a Non Technical Founder Built a Top iOS App with Claude Code

**Channel:** Eddy  **Published:** 2026-06-14  **Duration:** 19:51  **Watch:** https://www.youtube.com/watch?v=Tc3zHU6ITUQ

## TL;DR
A 10-year gaming project manager with zero coding experience shipped a real-time biometric stress app (Respiro) to the iOS App Store in 6 weeks using Claude Code — winning the Claude Opus 4.6 hackathon with a 72-hour MVP. The story reframes "non-technical" as a competitive advantage: PM skills (decomposition, role assignment, modularity) translate directly to multi-agent orchestration, and lacking traditional coding biases let him bypass overthinking. The friction in modern development is now deployment, not code generation.

## Key Insights
- **Non-technical is leverage, not liability.** Kostyantyn's decade of project management at Mythical Games (managing stakeholders, deadlines, team dynamics) translated directly to directing AI agents. His literal first prompt was: "Hey Claude, just give me an application that will make me less stressed." (timestamp 05:11)
- **Build a multi-agent architecture, not a monolith.** He orchestrated 15+ specialized sub-agents in parallel: TCA architect, Swift developer, Metal specialist (graphics/hardware acceleration), and code reviewer. Each ran in isolated silos, passing context like a relay race — not fighting over the same document. (timestamp 05:54)
- **TCA (Composable Architecture) forced modularity.** The TCA framework strictly separates app state, business logic, and UI — preventing the metal specialist from accidentally breaking core logic. This structural discipline is what made the rest of the multi-agent system work without constant breakage. (timestamp 06:47)
- **Pivot from React Native to native Swift in hours.** When he realized he couldn't test on Android, Claude Code rewrote the entire app from JavaScript-based React Native to compiled Swift in just a few hours — a project that traditionally takes a dedicated engineering team months. (timestamp 08:05)
- **Use vision capabilities for deployment friction.** The hardest part wasn't generating code — it was navigating Apple Developer Program, Sentry, and Amplitude dashboards. He fed Claude screenshots of confusing enterprise UIs instead of writing long text descriptions. (timestamp 09:59)
- **The CS degree becomes a liability if you can't let go of the wheel.** Engineers whose professional identity is tied to controlling every line of code face a "massive identity crisis" when AI takes over syntax. The premium shifts from syntax to architectural thinking and project management. (timestamp 15:30)
- **Daily routine proves the model is sustainable.** He works 70% on a MacBook, 5 browser tabs, cat on the desk, true-crime podcasts playing. From that low-friction environment he ships massive features (voice-guided practices, motion exercises) driven by a roadmap Claude helped him write. (timestamp 16:15)
- **Orchestration over syntax is the new definition of "technical."** The day-to-day work is moving from writing code to designing multi-agent systems, architecting better prompts, and critically verifying AI output. (timestamp 17:21)
- **Source: Anthropic's "Day Zero Founder Stories" blog (May 1, 2026).** Worth reading the original case study for the full prompt sequence and architecture diagram. (timestamp 01:16)

## Notable Quotes
> "Prompt engineering is essentially just the new middle management." — 04:13
>
> "He instantly hired an entire senior engineering department." — 06:14
>
> "The friction of creation is just gone. The era of needing a specialized technical co-founder to test a basic software hypothesis is effectively over." — 18:49
>
> "In an ocean of infinite perfectly coded applications, what idea are you currently holding back on simply because you've convinced yourself you weren't technical enough to build it?" — 19:31

## Tools and Resources Mentioned
- **Claude Code** (Anthropic) — the command-line tool Kostyantyn used to build Respiro. Now accessible to non-engineers.
- **TCA (Composable Architecture)** — a specific iOS framework that strictly separates state, business logic, and UI. The structural backbone that made the multi-agent system tractable.
- **Sentry** — error logging and monitoring platform. Required SDK installation and API key generation.
- **Amplitude** — user analytics platform. Same deployment friction.
- **Anthropic Day Zero Founder Stories** — the source blog post (May 1, 2026) the podcast deep-dives. https://www.anthropic.com (general; specific post URL not given in the podcast)

## GitHub Repos and URLs Referenced
- No GitHub repos referenced in this episode. The story is about a founder's process, not a tool release.

## Action Items
- [ ] Re-read the Anthropic "Day Zero Founder Stories" blog post for the full prompt sequence and architecture diagram.
- [ ] If you're a PM, project manager, or operations person: try building a small Claude Code project this week using strict role-based modularity (one agent per concern, isolated file ownership). The TCA pattern generalizes to any stack.
- [ ] If you're a trained engineer: deliberately practice letting the AI generate full modules while you only review and direct. Treat it as a "steering wheel release" exercise.
- [ ] For deployment friction: next time you hit a clunky enterprise dashboard, screenshot it and paste to Claude with vision instead of typing a long description. Validate the speedup.
- [ ] Audit your own product roadmap: are you still writing detailed specs by hand? Try having Claude draft a 4-week roadmap from a one-paragraph product vision.

## Open Questions
- How does the multi-agent architecture scale past 15 sub-agents? What coordination protocols emerge when 30+ agents share state?
- What does "critical verification" of AI output look like in practice for a non-technical founder who can't read the generated code?
- The "18-year-old with 30M ARR" and the "calorie photo app" examples from earlier in the show — what is the realistic distribution of solo-built apps hitting that scale? Survivorship bias is heavy.
- When 10 million non-technical people can build a 15-agent software architecture in 72 hours, what becomes the actual differentiator? Distribution? Taste? Audience trust?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 19:51 transcript)</summary>

0:00 [snorts]
0:03 [music]
0:06 >> Picture this. You are sitting at your
0:07 desk, right? And you're
0:11 uh maybe 15 minutes away from jumping
0:13 onto this massive high-stakes video
0:16 call.
0:16 >> Oh man, the worst feeling. The
0:17 pre-interview sweat.
0:19 >> Exactly. It's a huge interview, maybe
0:21 the most important one of your career.
0:23 You're running through your talking
0:24 points, hyper-focused, just staring at
0:26 the screen.
0:27 >> zoned in.
0:28 >> Right. And you don't even realize that
0:30 your heart rate has quietly skyrocketed.
0:33 Your breathing has gone completely
0:34 shallow. You are incredibly stressed,
0:37 but you're just too in your own head to
0:38 even notice it.
0:39 >> Because you're just, you know, you're in
0:40 survival mode at that point.
0:42 >> Completely. But suddenly your phone
0:44 buzzes on the desk. You glance down, and
0:46 it's a notification. And it says, "Mate,
0:48 you can just go and do a short box
0:50 breathing session." Box breathing has
0:51 previously helped you de-stress.
0:53 >> See that level of um immediate
0:56 contextual awareness from a piece of
0:58 tech is just wild. It completely shifts
1:00 the paradigm of wellness applications.
1:02 >> It really does.
1:03 >> We are moving away from those, you know,
1:05 scheduled passive reminders and moving
1:07 toward active real-time biometric
1:08 intervention.
1:11 >> And that notification is actually from
1:13 an app called Respiro.
1:15 So, for this deep dive, we're looking at
1:16 a blog post from May 1st, 2026. It's
1:20 from Anthropic's Day Zero Founder
1:23 Stories.
1:24 >> They are a great series, yeah.
1:26 >> Yeah, it's fascinating. We are exploring
1:28 the story of Respiro and its creator,
1:29 Kostyantyn Flosenco.
1:31 Our mission today is to unpack this like
1:34 fundamental [snorts] shift in how
1:36 technology is actually being created
1:37 right now.
1:38 >> Right, because the old rules just don't
1:39 apply anymore.
1:40 >> Exactly. We are seeing traditional
1:42 project management skills rapidly
1:43 replacing traditional coding skills. And
1:45 Kostyantyn is basically the ultimate
1:46 case study for this.
1:49 >> He really is.
1:49 >> a project manager from Ukraine who had
1:52 absolutely zero programming experience.
1:54 I mean, he had never written a single
1:55 line of code in his life.
1:57 >> None. Zero.
1:58 >> Yet he built and shipped this highly
1:59 complex real-time stress management app
1:03 to the iOS App Store in just 6 weeks
2:05 using Claude code.
2:07 >> Which is just I mean, it's mind-blowing.
2:09 To understand the magnitude of shipping
2:11 a native iOS application in 6 weeks with
2:13 zero programming background, we really
2:15 have to look at his day job.
2:16 >> Right. Mythical Games.
2:17 >> Yeah. Exactly. He spent 10 years as a
2:20 project manager there in Kyiv.
2:22 And uh project management in the gaming
2:24 industry is notoriously high-pressure.
2:27 >> Oh, I can only imagine.
2:29 The deadlines in gaming are brutal.
2:32 >> Yeah, you are constantly managing
2:33 stakeholder expectations. You're
2:35 navigating these tricky team dynamics,
2:38 and you're just racing against this
2:39 relentless pace of product releases.
2:42 >> So, dealing with that kind of daily
2:44 pressure means you obviously need a
2:46 rock-solid coping mechanism.
2:48 >> You have to, or you burn out.
2:49 >> Right. And Kostyantyn relied heavily on
2:52 breathing techniques and mindfulness.
2:55 But he ran into this massive frustration
2:57 with the existing tools on the market.
2:59 >> issue.
3:00 >> Exactly. The mindfulness apps out there
3:02 would just like ping him to do deep
3:04 breathing at 10:00 p.m.
3:05 >> Which is I mean, that is practically
3:07 useless if the actual moment of acute
3:09 stress happened at 2:00 p.m. during some
3:12 chaotic product meeting.
3:14 >> Totally useless. The apps just didn't
3:15 understand when he was actually stressed
3:16 in the moment.
3:17 >> Right. So, he was on vacation in the
3:19 mountains of Western Ukraine when the
3:21 concept for Aspiro finally, you know,
3:23 crystallized for him.
3:25 >> epiphany.
3:25 >> Yeah. Exactly. He wanted to build an app
3:28 that reads real-time stress signals from
3:30 personal devices and intervenes exactly
3:33 when the user needs it. He just um he
3:35 lacked the technical capability to
3:36 physically write the software.
3:39 >> But he did know how to manage work.
3:41 I mean, it at his day job, he'd already
3:44 been using Claude to automate his
3:46 project management tasks, right?
3:48 >> Right. Like updating Jira tickets and
3:49 posting meeting notes into Slack. Normal
3:51 PM stuff.
3:52 >> Exactly. And he had recently started
3:55 playing around with the Claude code
3:56 command line interface. He was watching
3:59 how his engineering team used Claude to
4:00 write code, and he realized that his
4:02 decade of managing real people
4:04 translated perfectly to managing AI
4:06 agents inside a development environment.
4:09 >> huge mindset shift.
4:11 >> Okay, let's unpack this for a second
4:12 because it sounds like prompt
4:13 engineering is essentially just the new
4:14 middle management.
4:16 >> That is a great way to put it, yeah.
4:17 >> It's like It's like being a seasoned
4:19 head chef who suddenly gets a fully
4:21 automated robotic kitchen. You don't
4:24 need to know how to physically chop the
4:26 onions or sear the steak yourself, you
4:27 know? You just need to know exactly what
4:30 the final dish should taste like and how
4:32 to direct the kitchen to achieve it.
4:34 >> What's fascinating here is that his lack
4:36 of traditional coding experience meant
4:38 he completely bypassed all the usual
4:40 friction points.
4:41 >> Oh, like overthinking the code.
4:43 >> Exactly. A trained engineer often gets
4:45 bogged down in the syntax or, you know,
4:47 they start debating specific programming
4:49 languages or agonizing over the minutia
4:51 of code structure.
4:53 >> Or I think it lost in the weeds.
4:55 >> But Kostyantyn viewed the AI not as a
4:57 tool, but as a team of workers. He was
5:00 just doing what he'd always done, which
5:02 is managing a team to execute a vision.
5:05 >> And his literal first prompt reflects
5:07 that perfectly. He actually jokes that
5:09 he essentially just typed uh "Hey
5:11 Claude, just give me an application that
5:13 will make me less stressed."
5:14 >> I love that. It's so simple.
5:15 >> Right. He conceptualized something in
5:17 his head, described it, and just began
5:20 generating a functional prototype.
5:21 >> And the timeline of that initial build
5:24 is just staggering. He built the first
5:27 version of Respiro in just 72 hours for
5:30 the Claude Opus 4.6 hackathon.
5:33 >> Which he ended up winning, by the way.
5:35 >> Yeah, he won it. Three days to go from a
5:37 blank screen to a functional real-time
5:39 biometric application.
5:41 >> But I mean, he didn't achieve that by
5:43 just asking one single AI to do
5:45 everything in one massive block of text.
5:47 >> No, no, that would never work.
5:49 >> Because he was thinking like a project
5:50 manager, he researched how agent systems
5:52 work.
5:54 >> Mhm.
5:54 >> And then he used Claude to build out
5:56 this really complex multi-agent
5:58 architecture.
5:59 >> Yeah, the source mentions he had 15 or
6:01 more specialized sub-agents all running
6:03 in parallel.
6:04 >> 15. He spun up like a TCA architect
6:07 agent, a dedicated Swift developer
6:09 agent, a metal specialist for the
6:11 graphics and hardware acceleration, and
6:13 even a code reviewer.
6:14 >> He instantly hired an entire senior
6:16 engineering department.
6:17 >> Okay, here's where it gets really
6:19 interesting though, and I have to push
6:20 back a little on this whole frictionless
6:22 narrative.
6:22 >> Okay, sure.
6:23 >> Because managing 15 distinct AI agents
6:25 sounds like absolute chaos to me. I
6:28 mean, surely he hit a wall.
6:30 How does a system that complex not just
6:32 constantly break the build or overwrite
6:34 each other's work or get hopelessly
6:36 confused?
6:37 >> Well, they avoid chaos through strict
6:39 modularity and defined roles, which
6:41 Konstantin orchestrated beautifully.
6:44 >> Okay, how so?
6:45 >> You mentioned the TCA architect agent
6:47 earlier, right? TCA stands for the
6:49 composable architecture.
6:50 >> Right.
6:51 >> It is a specific framework for building
6:53 iOS applications that strictly separates
6:55 the state of the app, the business
6:57 logic, and the user interface.
6:59 >> Oh, I see. So, it forces them into
7:00 lanes.
7:01 >> Exactly. By forcing the AI to use TCA,
7:04 Konstantin ensured that the agents were
7:06 working in completely isolated silos.
7:09 So, the metal specialist who's dealing
7:10 with Apple's hardware-accelerated
7:12 graphics is only touching the rendering
7:14 code. It literally cannot accidentally
7:16 break the core logic.
7:17 >> Okay, so they aren't all just like
7:19 fighting over the same document.
7:21 >> No, they're passing contexts like a
7:23 relay race.
7:24 The Swift developer agent writes a
7:26 module, and then the code reviewer
7:28 agent, which is specifically prompted to
7:30 check against Apple's human interface
7:32 guidelines and performance standards,
7:34 reviews it.
7:35 >> And if there's a bug?
7:36 >> If there is an error, the reviewer kicks
7:39 it back to the developer agent to fix,
7:40 all without Konstantin having to read a
7:42 single line of the output.
7:44 >> Wow. So, he's just watching the
7:46 terminal.
7:46 >> Yeah, just monitoring the workflow and
7:48 ensuring the final feature matches his
7:50 overarching product requirement.
7:52 >> And that structural discipline is
7:54 actually what saved him when he had to
7:57 execute this massive technical pivot.
7:59 Because, you know, he initially built
8:02 this minimum viable product using a
8:03 framework called React Native.
8:05 >> Right, for the hackathon.
8:06 >> Yeah. But, he didn't actually own an
8:08 Android phone to test it on. So, he had
8:10 Claude code rewrite the entire
8:12 application from scratch into Swift in
8:15 just a few hours.
8:16 >> Which is wild.
8:17 >> It sounds like sci-fi.
8:19 For anyone listening who isn't, you
8:20 know, deep into mobile development,
8:22 React Native is a web-based framework.
8:25 It uses JavaScript components to
8:27 basically simulate an app so it can run
8:30 on both Apple and Android devices.
8:32 >> Right, it's very different from native
8:33 code.
8:34 >> Exactly.
8:35 Because Swift is Apple's native compiled
8:38 programming language. They have
8:40 completely different syntax, totally
8:42 different memory management, and
8:43 different structural paradigm.
8:44 >> Yeah, they don't map one-to-one at all.
8:46 >> Right. So, in traditional software
8:48 development, a full language rewrite
8:50 from React Native to native Swift is a
8:52 nightmare project. It takes a dedicated
8:54 engineering team months of planning, QA
8:57 testing, and debugging.
8:58 >> And he did it in a few hours.
9:00 >> A few hours. Doesn't the AI ever get
9:02 confused when things get that complex?
9:04 >> Well, the fact that he accomplished a
9:05 full rewrite in a few hours proves that
9:08 generating the raw logic of the
9:09 application is practically solved. The
9:11 actual friction in modern development
9:13 lies in deployment now.
9:15 >> Getting it out of the real world.
9:16 >> Exactly, getting that code out of the
9:18 editor.
9:19 Kostyantyn had never navigated the Apple
9:22 developer program to actually ship an
9:24 app. He had never set up complex
9:26 third-party platforms.
9:27 >> Right, which are always a headache.
9:29 >> The source highlights his use of Sentry,
9:31 which is a tool for error logging, and
9:32 Amplitude for user analytics.
9:35 Integrating these platforms requires
9:37 installing specific software development
9:39 kits or SDKs.
9:41 >> And usually navigating those notoriously
9:43 clunky, confusing enterprise dashboards
9:46 to generate API keys.
9:48 >> Ugh.
9:49 >> Yeah, the dashboards are always the
9:50 worst part. But when he got stuck on
9:52 those enterprise interfaces, he didn't
9:54 try to type out a long explanation of
9:56 his problem.
9:57 >> No, he did something much smarter.
9:59 >> He leveraged Claude's vision
10:00 capabilities. He literally just took a
10:01 screenshot of the confusing interface
10:04 and pasted it into the chat.
10:05 >> Wow.
10:07 >> I mean, that is a such a simple hack
10:09 that everyone listening to this can
10:10 implement right now.
10:11 >> Absolutely. Yeah.
10:12 >> And honestly, the most underrated
10:14 thing about vision models is using them
10:16 to navigate complex enterprise software.
10:18 >> Right, because often the the setting
10:21 you need is three layers deep in a
10:23 sidebar, and it's almost impossible to
10:25 describe in text. But a picture just
10:27 says a thousand words.
10:28 >> And after about six weeks, the app was
10:30 live on the iOS App Store with hundreds
10:32 of users.
10:33 >> Wow.
10:34 >> So, let's just break down that timeline
10:36 again because it is just so important.
10:37 He started with an idea, a fleeting
10:39 thought on a mountain vacation, and
10:40 turned it into a live product in 6
10:42 weeks.
10:44 >> The first 72 hours produced a
10:45 functional prototype. The next six weeks
10:47 were basically just navigating
10:48 deployment, third-party integrations,
10:49 and the App Store submission process.
10:53 >> And he's not the only one shipping
10:55 this fast. There is a real sense that
10:57 software development itself has
10:59 fundamentally bifurcated. There is
11:01 development and there is deployment.
11:03 >> Hmm.
11:05 >> And AI excels at the first one, the
11:07 raw logic generation, the raw code
11:09 writing. But the second one,
11:10 deployment, requires a totally different
11:12 skill set.
11:14 >> So, when people say AI is making
11:16 coders 10 times more productive, that
11:18 is usually only true for the first 50%
11:19 of the project.
11:21 >> Right, the first 50% is the code
11:23 writing, the code generation, the
11:24 building. But the second 50% is the
11:26 deployment, and that's where it still
11:28 kind of falls apart.
11:29 >> And it's not falling apart because the
11:31 AI can't do it. It's falling apart
11:32 because the tooling around deployment
11:33 is genuinely terrible.
11:36 >> The dashboards are terrible. The API
11:36 generation is terrible. The SDK
11:37 installation is terrible. The App Store
11:39 submission is terrible. All of that
11:41 friction.
11:42 >> Which is why I think the next massive
11:44 wave of startups isn't going to be
11:46 another AI coding tool. It's going to be
11:48 AI deployment tools. AI agents that
11:50 specifically do the boring deployment
11:52 work.
11:53 >> Absolutely. So, what does this story
11:55 mean for you, the listener? And more
11:57 importantly, what does it mean if you
11:59 are a trained software engineer
12:00 listening to this?
12:02 >> Right, because what does this all mean
12:04 for the listener who, you know, just
12:06 spent four years getting a rigorous
12:07 computer science degree? Are deep,
12:09 granular coding skills actually becoming
12:11 a liability if the engineer cannot learn
12:13 to let go of the steering wheel and
12:14 abstract their thinking?
12:16 >> It's a tough pill to swallow. A deep
12:18 understanding of computer science
12:19 principles like how data structures
12:21 work, how systems scale, how security
12:23 protocols function, that will all remain
12:25 incredibly valuable.
12:27 >> But the day-to-day work is changing.
12:29 >> Yes. The definition of what it means
12:30 to be technical is fundamentally
12:32 shifting up a level. It is moving from
12:34 writing syntax to orchestrating
12:35 systems.
12:36 >> Orchestration over syntax.
12:38 >> Exactly. The engineers who thrive will
12:40 use their deep expertise to architect
12:42 better prompts, design more robust
12:43 multi-agent systems, and verify the
12:44 AI's output with a highly critical
12:46 eye.
12:48 >> But if an engineer's only value
12:49 proposition is knowing where the
12:50 semicolons go,
12:52 >> they will face a very difficult
12:53 transition. The premium is now on
12:55 architectural thinking and project
12:56 management, which is exactly why a PM
12:58 like Kostyantin could leapfrog the
13:00 traditional development process.
13:02 >> So, to bring this deep dive to a close,
13:04 let's just look at the massive paradigm
13:06 shift we've just unpacked here.
13:08 The historical barrier between having a
13:10 great idea and actually shipping a
13:12 functional product has essentially been
13:14 leveled.
13:16 >> We just walked through how Kostyantin
13:17 Placentko took a fleeting idea he had
13:19 while on a mountain vacation, a stress
13:20 app that actually read your biometrics
13:22 and knows when you're stressed, and
13:24 turned it into a live App Store product
13:26 with hundreds of users in just 6 weeks.
13:28 >> Not by learning to code, but by
13:30 learning to manage AI like a team of
13:31 human experts.
13:33 >> Right. He used multi-agent
13:34 architecture to build the code. He used
13:36 vision capabilities to navigate the
13:38 deployment and marketing platforms.
13:40 And he used his human vision to keep
13:41 the whole project on track.
13:42 >> Yeah.
13:43 >> And the tools he used are available
13:44 to you right now on the exact same
13:45 laptop or phone you use every day.
13:47 >> The friction of creation is just
13:48 gone. The era of needing a specialized
13:50 technical co-founder to test a basic
13:52 software hypothesis is effectively
13:54 over.
13:55 >> For decades, the tech industry has
13:56 told us that building software is an
13:58 exclusive club. That if you don't speak
14:00 the language of code, you just can't
14:01 participate. As we've seen today, that
14:03 narrative is obsolete.
14:05 >> It's a new world.
14:06 >> But this leaves us with an entirely
14:08 new challenge to mull over as you go
14:10 about your day.
14:11 If execution is now functionally free,
14:13 if a non-technical project manager can
14:15 build a 15-agent software architecture
14:17 in 72 hours, what happens when 10
14:19 million people do exactly that?
14:20 >> Yeah, what's the differentiator then?
14:22 >> Exactly. When the barrier to creating
14:24 perfect software drops to zero, the
14:26 simple ability to build will no longer
14:28 make you special. So, in an ocean of
14:30 infinite perfectly coded applications,
14:32 what idea are you currently holding
14:33 back on simply because you've convinced
14:35 yourself you weren't technical enough
14:37 to build it?
14:40 >> [music]

</details>
