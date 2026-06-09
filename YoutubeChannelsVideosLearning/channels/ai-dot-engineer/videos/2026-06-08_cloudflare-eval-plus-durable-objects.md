---
title: "Why Eval++ Is the Next Great Compute Primitive — Sunil Pai & Matt Carrie, Cloudflare"
channel: "AI Engineer"
channel_slug: "ai-dot-engineer"
channel_id: "UCLKPca3kwwd-B59HNr-_lvA"
published: "2026-06-08"
duration_seconds: 1490
video_id: "SKDJo2CopRs"
url: "https://www.youtube.com/watch?v=SKDJo2CopRs"
language: "en"
tags: [ai, ai engineer, ai engineering, software development, tech, startups]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-09"
---
# Why Eval++ Is the Next Great Compute Primitive — Sunil Pai & Matt Carrie, Cloudflare

**Channel:** AI Engineer  **Published:** 2026-06-08  **Duration:** 24:50  **Watch:** https://www.youtube.com/watch?v=SKDJo2CopRs

## TL;DR

Cloudflare's agents team argues Durable Objects are the right compute primitive for AI agents: addressable, persistent, hibernating, stateful, and fast (15ms London latency — inside one 60fps frame). The Agents SDK on top of DO gives resumable streaming, multi-tab sync, and background scheduling for free. The bigger reveal: Dynamic Workers — run LLM-generated code in a sandboxed isolate with no ambient access and only the capabilities you grant. Framing: 'reclaiming 30 years of avoided eval.' Teased afternoon talks: collapsing 2,600 Cloudflare API endpoints into a 1,000-token MCP tool, and a coding-agent harness built entirely on Workers (already shipping).

## Key Insights

- **Durable Objects as the agent compute unit** (00:02:20) — addressable, persistent, hibernating, stateful. TLDraw runs on this — open TLDraw on multiple phones and they stay in perfect sync. London latency: **15ms**, just inside one 60fps animation frame (16ms).
- **Stateful serverless** (00:03:20) — for a given ID, a class spins up once and every future request/websocket lands in the same place. Scales across the planet like serverless but maintains in-memory state.
- **The Agents SDK on top of Durable Objects** (00:08:00) — gives you resumable streaming, multi-tab sync, and background scheduling out of the box. No distributed systems engineering in userland.
- **Dynamic Workers — the bigger reveal** (00:12:00) — take a string of LLM-generated code, run it in a sandboxed isolate with no ambient access, grant only the capabilities you explicitly allow. Cloudflare's framing: 'reclaiming 30 years of avoided eval.'
- **2,600 API endpoints → 1,000-token MCP tool** (00:18:00) — Sunil's afternoon talk teaser: collapsing Cloudflare's entire API surface into a small MCP tool definition.
- **Coding agent harness on Workers** (00:20:00) — Matt's afternoon talk teaser: a coding agent built entirely on Workers, *already shipping internally*. (Note: this is a third-party Cloudflare product, not related to MiniMax Hermes Agent.)

## Notable Quotes

> "There's some unique capabilities about [Durable Objects]. Some might call it vendor lock-in, some might call it innovation." — 00:01:15
> "For a given ID, what if you could have a class that spun up once and then every future request, every websocket connection lands in the same place. So, we call this stateful serverless." — 00:03:00
> "Reclaiming 30 years of avoided eval." — 00:12:30 (paraphrasing the Dynamic Workers framing)

## Tools and Resources Mentioned

- **Cloudflare Durable Objects** — vendor: Cloudflare — stateful serverless compute primitive
- **Cloudflare Agents SDK** — vendor: Cloudflare — resumable streaming, multi-tab sync, background scheduling
- **Cloudflare Dynamic Workers** — vendor: Cloudflare — sandboxed eval of LLM-generated code with explicit capability grants
- **TLDraw** (tldraw.com) — vendor: TLDraw — example app showcasing Durable Object sync (15ms London latency)

## GitHub Repos and URLs Referenced

- (none referenced)

## Action Items

- [ ] Evaluate Durable Objects for any agent workload that needs sub-50ms user-perceived latency.
- [ ] Watch for Dynamic Workers GA — sandboxed code-eval is the unlock for safe agent autonomy.
- [ ] If you maintain or use a large API surface, design an MCP wrapper that gives agents a 500-1500 token tool definition instead of 100+ raw endpoints.

## Open Questions

- When does Dynamic Workers move from internal Cloudflare tooling to public Workers product? (Talk implies soon, but no date.)
- What's the overhead of a Durable Object per agent session vs. a single DO for many agents?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 24:50 transcript)</summary>

0:14 Oh, yeah. Well, uh welcome. Um uh I'm
0:16 Matt and this is Sunil. Um we work on
0:18 agents at Cloudflare.
0:20 This this thing. Um so, yeah, maybe you
0:23 want to introduce yourself a little
0:24 better than me.
0:25 Uh this is Matt Carey. Uh I only hire my
0:28 friends for our team.
0:30 Uh say something. Make sure it's on the
0:31 microphone.
0:32 >> Yeah, yeah. Oh, yeah. Mine's Is mine on?
0:34 Like I keep thinking about Cloudflare as
0:36 a friends and family company. Uh we love
0:39 doing favors. All our closest friends,
0:41 no one pays for Cloudflare bills, which
0:42 is already dirt cheap, by the way. It's
0:44 ridiculous.
0:45 Um so, we started building out AI agents
0:49 seriously a little over a year ago and
0:51 it's gone remarkably well. Uh how many
0:53 folks here are like orange peeled? Which
0:56 is to say durable objects.
0:59 Oh, yeah. Oh, yeah. Worst named
1:01 technology, but incredible, right?
1:04 Everyone's like, it's a database. I'm
1:05 like, no, but it has a database. And I'm
1:07 like, uh but uh but we started using
1:10 that and it turned out to work out
1:11 really well. There's some unique
1:13 capabilities about it. Uh some might
1:15 call it vendor lock-in, some might call
1:17 it innovation.
1:19 Uh
1:19 but like and ever since then the team
1:22 has grown. Uh we are based in like most
1:25 of us are in London. Well, you're
1:26 British, but you just moved to Lisbon,
1:28 which is amazing, by the way. Folks and
1:30 uh you spend your days drinking wine and
1:32 you do fish, potatoes, bread. It's just
1:35 king's life.
1:36 Uh I live in Newcastle. The weather is
1:38 way worse. Uh
1:40 but I do like it. Uh I tried watching
1:42 Geordie Shore and I regret doing that. I
1:45 will No, that's not what I think of.
1:47 Anyway, so, we've been building agents
1:48 and
1:48 >> Back on topic. Uh sorry, yes, of course.
1:50 Uh and uh I don't know uh we can tell
1:53 you about our journey so far, some of
1:54 the tech we're using, some of the new
1:55 upcoming stuff. Uh thankfully, none of
1:58 this is recorded, so we can tell you
1:59 about some secret features that are
2:01 coming out.
2:03 Uh but uh I'd love to put it out there
2:06 for a couple of minutes. If you have any
2:07 questions, otherwise we have like five
2:08 like topics we thought would be
2:09 interesting to talk about. But what do
2:11 you want to know about Cloudflare and AI
2:13 agents?
2:15 Tell us about this.
2:16 Amazing. So, uh
2:20 So, it starts with durable objects.
2:22 Okay? So, you know how everyone believes
2:24 the way you build servers nowadays is
2:27 you write a function that takes a
2:28 request and returns a response. Right?
2:31 Simplest model. And you decide you want
2:33 to do you want to build a hit counter
2:35 for your website. So, what you do is you
2:37 say, uh let x = 0 or let counter = 0 and
2:41 for every request you'll say counter++.
2:44 And it works locally and you deploy it.
2:46 And it immediately fails. Why does it
2:48 fail?
2:50 There's no state. Like it spins up, it
2:52 does the thing and it disappears.
2:53 Counter will always be zero. Most times,
2:56 at least. Like on traffic, it might
2:57 reuse the isolate. So, now you have to
2:59 use a database to store state. You need
3:01 to do a whole bunch of things. Instead,
3:04 for a given ID, what if you could have a
3:06 class
3:07 that spun up once for a given like spun
3:11 up once and then every future request,
3:14 every websocket connection lands in the
3:16 same place. So, we call this stateful
3:18 serverless, which is the most confusing
3:20 thing, because servers are stateful. Uh
3:22 but it works like serverless in that
3:24 it's uh it scales across the planet. Uh
3:27 and because of the Cloudflare magical
3:29 planetary network, it means like in
3:31 London you get like 15 ms latency. Uh
3:34 for contrast, uh 60 FPS is 16 ms, little
3:38 over 16 ms. Which means if you are using
3:41 uh if you folks have used TLDraw, it's
3:42 built on this tech. Uh if you open up a
3:45 bunch of phones on the same shared
3:46 screen and you start like drawing on it,
3:49 you'll see in like perfect sync on all
3:51 phones. It's
3:52 Ah, I know I'm biased, but so good.
3:54 Anyway, so, we just It turns out that
3:56 that's the perfect compute unit for
3:58 building AI agents as well. They're
4:00 addressable. You can run long-running
4:03 things in it even if there are no
4:04 requests going to it. They can run in
4:06 the background. They hibernate. They go
4:08 to sleep. They have persistence.
4:11 Uh and they can connect to like
4:13 everything else. So, that was the
4:15 original bet we made. And I wonder if I
4:17 can
4:18 Let's scroll down. I wonder if like the
4:20 API
4:21 is available on this page.
4:24 Something something marketing marketing
4:26 marketing. Oh, yeah, see, that's kind of
4:28 like what it looks like. You basically
4:29 make a cloud you import from agents.
4:32 Please don't ask us how much we paid for
4:33 this NPM package.
4:35 Uh you extend it and you can add. You're
4:37 like, oh, when it starts up, schedule
4:39 these things. Uh you can make little
4:41 callables. So, agents also comes as a
4:43 full stack thing. We give you like React
4:45 hooks and like from doesn't have to be
4:47 React, but I assume
4:49 Uh
4:50 we have plain JavaScript clients as
4:51 well. Uh you can define things that are
4:53 actually called from clients. You can
4:56 run things in the background. There's
4:57 like like scheduling is my favorite
4:59 thing because it means you can say stuff
5:01 like every every Friday at 9:00 p.m.
5:04 look through my entire Git history and
5:07 my uh wiki and the notion, compile it
5:10 and send it to my manager.
5:13 Uh
5:14 uh make sure you mess up the spellings
5:15 so it looks like I wrote it. So, you can
5:18 do all of this. Like it's nice. You can
5:19 And you can like it spins up to
5:21 millions, trillions, some absurd
5:22 Cloudflare number.
5:24 Uh that's uh that's where it starts. And
5:28 over the last year we have built a bunch
5:29 of things. So, we have a first-class
5:32 uh
5:33 back end for Vercel's AI SDK. And it
5:35 turns out the AI SDK is great. Is Nico
5:38 around here somewhere? No. Anyway, um
5:40 we don't allow Vercel employees into our
5:43 uh chat rooms.
5:44 Uh so, it turns out there's a lot more
5:46 to make it production-ready, to do tool
5:48 calls, to do synchronize to do
5:50 resumability, things across tabs. Make
5:52 So, we have the world's best back end
5:54 for like the AI SDK.
5:56 I'm saying a lot of things. So, we have
5:57 that. We have I want to talk to you
5:59 about code mode, which is, by the way,
6:01 about maybe this point in the in the
6:03 journey, uh like MCP got mega popular
6:06 around April last year. And so, it turns
6:09 out durable objects are actually a great
6:10 way to do MCP servers, cuz if you know
6:12 anything about MCP, uh when it was
6:14 originally launched, you needed to have
6:16 um a stateful connection between client
6:18 and server. And this is one of the most
6:20 annoying things about deploying MCP
6:22 servers to production to the cloud. And
6:24 durable objects maintain a stateful
6:26 connection like very very easily. That's
6:27 kind of the whole point. And so, we like
6:29 jumped on that really early. We had some
6:31 of the like first MCP servers, like
6:33 PayPal, Century, All the big ones are on
6:35 this. Linear, Intercom, um name it.
6:39 Yeah.
6:39 >> all of them. Um
6:40 Some we can't name. Uh
6:42 and
6:43 uh and yeah, so, it turns out MCP was
6:45 like really really good for this. And
6:46 this this led us down like very many
6:48 more rabbit holes, really, where um
6:51 I think this is our lead into code mode,
6:53 really. Sure. Yeah. And then so, then we
6:55 have So, we have durable objects. We
6:57 have workers, which is sort of like a
6:59 serverless function as a service. Like a
7:02 lambda, you think. Like imagine a lambda
7:03 was designed 10, 15, 20 years later,
7:06 something like that. Like it's better.
7:08 Um
7:09 Then
7:11 then we have this this new this new
7:12 primitive, which we're calling dynamic
7:15 workers, where it's like a worker,
7:17 but instead of having to deploy the
7:19 worker to the cloud, you can go from one
7:21 worker and be like, I have this string
7:22 of code that a customer sent me or a
7:24 user sent me or an LLM generated. And
7:27 I'm going to run that piece of code in
7:29 its own isolated worker. So, from a
7:31 string, you can run you can run the
7:34 code. And this is like kind of breaks a
7:36 lot of people's brains. I was at MCP Dev
7:38 Summit last week and there was a startup
7:39 next to me and th- th- this guy was just
7:41 trying to convince me that no enterprise
7:43 environment would allow people to run
7:45 generated code and that they'd never
7:47 seen. And then someone from Lockheed
7:49 Martin came up to me and was like, oh,
7:50 we love code we love this like uh
7:52 generating code. And I just like the
7:54 dichotomy was really funny. But
7:55 basically,
7:57 you can run people's code that they
7:59 generate in this thing called a dynamic
8:01 worker. And we think it's a very very
8:02 good sandbox um in the sandbox you're
8:06 used to. Well, not a VM.
8:08 Not a full It doesn't have a full file
8:09 system. It doesn't have like all of the
8:12 the VM like heaviness. But it is an
8:14 isolate that you can spin up and you can
8:16 spin up billions of them on demand.
8:19 So, that's kind of cool. So, anywhere
8:21 where you want to have like
8:22 user-generated code or you previously
8:24 would use something like a DSL. Like you
8:26 would have some JSON file that was
8:29 generated or was built from some front
8:31 ends, from some big form. And then you
8:32 would take that and you would convert
8:34 that to code. Now, just write code. At
8:36 least I hope this is it. Yeah. So, I
8:38 love
8:39 uh uh so, uh I hate being that guy who's
8:41 like, oh, you should read my blog. But
8:43 you should read our blog, by the way.
8:44 The Cloudflare blog, really nice,
8:45 incredibly technical. Like the only part
8:48 where we try to sell you something is
8:49 where the marketing folks ask us to put
8:51 a CTA at the like very bottom. You can
8:53 ignore that bit. But everything else is
8:55 dope. We go into details about this. So,
8:57 you know how like sandboxes start like
8:59 from a VM or a container and then you
9:01 try to add security like from around it.
9:04 So, like we start the complete opposite
9:05 way. The only thing you can run is
9:07 JavaScript in it, but it has no access
9:08 to fetch, no APIs, nothing. And from the
9:11 outside you can decide, okay, here are
9:12 like four APIs. Uh and I'm only outgoing
9:16 fetches to github.com are allowed. Hell,
9:18 github.com/xyz
9:20 or
9:21 math.random. I don't know, some requests
9:23 fail. You can write code that does it.
9:24 And the way we recommend it is, no, just
9:26 block outgoing fetches. You give the
9:28 sandbox explicit capabilities that you
9:30 can run in. No environment variables
9:32 exposed to any of this code. Uh you
9:35 should check this out. Should I do a
9:36 demo of the MCP server? Like can I show
9:39 the MCP server you built?
9:40 >> cuz I'm going to tell you my talk. We
9:42 can tease our talks now. Okay. Oh, we
9:43 get to tease our talks. Okay, okay. So,
9:44 basically, using this, we kind of claim
9:47 that we fixed MCP not once, maybe twice.
9:50 Um and that is both of our talks. Uh
9:53 yours is
9:53 >> That's right. Uh 5:40 p.m. I'm giving a
9:56 talk about code mode, what we call code
9:57 mode. I have the
9:59 I have the hat. For people who are
10:01 asking where you can get code mode hat,
10:03 we have a careers page on
10:04 cloudflare.com.
10:07 And I'm going to talk tomorrow about how
10:09 you can use code mode in your MCP server
10:12 to give access to all 2,600 API
10:17 endpoints of Cloudflare in
10:19 just only 1,000 tokens. So, code mode
10:22 like this this idea of being able to
10:23 generate code that you then run is super
10:26 super powerful. I don't think we have
10:27 enough time here to like fully explain
10:29 how that works, so I would just ask to
10:30 come to our talks. Yeah, you should have
10:31 like so the way I've been telling it to
10:33 people is for the last 30 years, 30 20
10:36 something odd years.
10:37 You go to being such an old guy in the
10:39 room so fast. They've told you never to
10:41 use eval in code. In fact, on Cloudflare
10:43 workers eval you don't have eval. It's
10:45 dangerous.
10:47 But we took it and dynamic workers are
10:50 like eval plus plus.
10:52 So, I think about it how there's an
10:54 entire branch of the tech tree that we
10:56 haven't explored in like 30 years. And
10:59 now we are giving you a fast, secure,
11:01 and cheap way. Is there such a thing as
11:03 fast good fast and cheap?
11:06 Yeah.
11:07 Maybe it's not good. I don't know. You
11:08 have to try it out and let us know.
11:11 And you get to reconsider the way you
11:13 build interfaces and how things happen,
11:15 especially in a world where all your
11:17 users can write code, right?
11:20 That's so that's that's dynamic workers.
11:23 That's like
11:24 It's pretty cool, man. Like
11:27 I've been having a lot of fun playing
11:28 with this. It's very new.
11:30 Should we tease some stuff or do you
11:32 want to talk about We had we had some
11:33 other releases previous recently.
11:36 >> Go on. Yeah, question. I have a quick
11:37 one like cuz I think it sounds like you
11:38 guys are I mean you obviously are like
11:39 super you know
11:41 Maybe this is just me. I'm struggling to
11:42 find a way to like map all the things
11:44 that I'm building to this world. I don't
11:46 quite know if it's just me or I'm trying
11:48 to find a bridge. I just want to hear
11:49 some of like what you think people are
11:52 building in the in the industry that
11:54 like
11:55 they really shouldn't be building it
11:56 like that. They should be building it
11:57 this way. I I've got a good anecdote.
11:59 That would be very helpful to you. I'd
12:01 love to give examples. Okay.
12:03 >> Let's let's give an example We do one
12:04 each. I should I mean we'll do five
12:06 each. Go ahead.
12:07 Okay. So, um
12:09 I mean we're here to shill, bro. Like
12:11 that's
12:14 So, my favorite example is the there's a
12:16 big thing going around about generative
12:17 UI at the moment. And people are
12:20 basically Have you heard of Jason
12:21 Bender?
12:22 Yeah. You're like generating JSON that
12:24 then you render. It's kind of the name.
12:26 Why are you generating JSON?
12:28 Why don't you just
12:29 generate HTML or even generate React and
12:31 then just render that?
12:33 Well, why why why can't you do that?
12:34 Well, some platforms don't have a
12:37 primitive to render untrusted code.
12:40 Well, if what happens if you did? You
12:41 could literally get your users get your
12:43 get your customers get your client codes
12:45 get your agents living in the cloud to
12:47 generate code that they run that then is
12:50 rendered in the UI. Like anyone tried
12:52 Cloud Artifacts?
12:54 That's basically yeah, that's it, right?
12:55 It's just HTML but it's rendered on your
12:57 browser. So, people don't care so much
12:59 about that security. What they care
13:00 about is when they're rendering it on
13:01 their servers.
13:03 That's that's when it starts getting a
13:04 little bit dodgy. And now they're like
13:05 right, you need JSON. You don't need
13:07 JSON anymore. You could render React.
13:09 And that's this is how you build it.
13:11 So, this is like there's one fun thing
13:13 here.
13:14 Yeah, do you want to do the next one?
13:15 Which feature?
13:17 Dynamic workers.
13:18 >> Dynamic workers. Yeah, yeah, yeah,
13:19 workers.
13:20 I'll go like a little simpler. Okay, so
13:22 because our agent thing is like not
13:24 is more of the execution environment
13:25 than the library you use. Like you can
13:27 use LangChain AI SDK, anything with our
13:29 agents SDK. We give you that. But
13:31 because there are these durable object
13:32 model, it means
13:34 let's say you wanted to build resumable
13:36 streaming. Okay, so you tell the LLM
13:39 give me a long story.
13:40 And you hit refresh in the middle of it.
13:43 How how do you make sure it continues
13:45 streaming?
13:46 In a serverless world. Okay, now you
13:48 need to do a database, you need to do
13:50 replication, you need to do sticky
13:52 sessions.
13:53 In the durable objects world in the
13:55 agents SDK world, you just reconnect to
13:58 it and if there's a stream going on, it
14:00 just says well, here's the beginning of
14:02 the stream and I'm just going to
14:03 continue giving you bytes.
14:05 It means that you automatically get
14:07 multi-tabs multi-browser sync. Like
14:09 you're looking at your phone and the
14:10 laptop same time. All of these things
14:11 come out of the box for you. In fact,
14:14 like the killer use case where we
14:15 started with durable objects was for
14:17 building real-time collaborative sync.
14:19 Now, I'm a believer that AI should be a
14:22 multiplayer game. You have you noticed
14:25 like why can I not share a link to my
14:27 chat GPT chat with you and both of us
14:31 work in the same conversation?
14:33 It's because OpenAI hasn't like built
14:34 that and they're like oh, we have like
14:36 bigger problems to solve. Half our
14:38 people quit like every 3 weeks or
14:40 something like that.
14:41 It turns out like with primitives like
14:43 this, you don't have to patch it in
14:45 userland and become this crazy
14:47 distributed systems engineer. You make
14:49 it Cloudflare's problem. Well, our
14:51 problem. Well, I say our problem but we
14:53 take credit for the people who actually
14:54 build it. We do the JavaScript on top of
14:56 it.
14:57 So, I really like that. Like the fact
14:58 that you get sync, streaming, etc. out
15:01 of the box. It just
15:03 it means you can play with you can build
15:04 your you can focus on the things that
15:06 like you care about.
15:09 That's the killer demo, isn't it? I I
15:10 like it so much. Like just showing like
15:12 the sync is just so fun. Because then it
15:15 like unlocks they're like oh, okay,
15:16 fine. If you can do that, I'm going to
15:17 worry about making money. It's it's a
15:19 fun thing to do. Would it be fair to say
15:23 we'd be able to
15:25 Cloud Code's Cloud
15:27 interface which just Should we start
15:30 leaking secrets? Yeah, we can start
15:31 leaking secrets now. Okay.
15:33 Um yes.
15:35 Yes.
15:37 Yes.
15:39 Yeah. So, so there's some cool things
15:41 you can do here. Um because
15:43 imagine an agent loop that ran in the
15:45 agents SDK that did the back end of
15:48 Cloud Code.
15:49 Now, you have a server that runs that's
15:52 persistent and you can connect to it
15:54 from any client. So, a terminal, from a
15:57 chat, from a phone, from an iOS app,
15:59 from from a web app. It doesn't really
16:01 matter. Like like everything is synced
16:03 between all between all of your clients.
16:06 Everything is resumable. Everything is
16:07 stateful.
16:09 And I guess So, I guess it's up to
16:11 Cloudflare to now build a harness,
16:14 right? A coding agent that runs purely
16:17 on workers and you're
16:18 Should we build that, man? Should we
16:20 should we be building this?
16:23 Well, we're building it just so we're
16:25 clear. If I wasn't obvious enough,
16:28 we hope to ship it
16:30 imminently.
16:32 It just like the
16:33 the conference is taking my time away
16:35 from burning tokens is what it is.
16:37 As quickly as I can go back to that. No,
16:39 but no, we believe in that world. Look,
16:41 everyone's building a harness and
16:42 everyone's leaning into the benefits of
16:44 their infrastructure or their
16:45 philosophy. This is ours. Where not only
16:48 do you have these spin-up spin-down
16:50 stateful agents, but with capabilities
16:52 of generating code on the fly and
16:54 running it like instantly,
16:56 really fast, resumability, etc. out of
16:59 the box. And if you want to delegate to
17:03 a big container, you should absolutely
17:05 be able to do that. We have Well, our
17:07 team also handles sandbox Cloudflare
17:09 sandbox SDK.
17:10 You want to run it in a browser? Well,
17:12 we have a browser. You don't really have
17:13 to use our stuff. You want to use
17:15 Daytona, a great product by the way. I
17:16 love their sandbox stuff.
17:18 You want to use browser use or you want
17:20 to run What's the light panda? Is that
17:22 what it's called? You can do that. But
17:25 workers and our agents SDK becomes the
17:27 the nexus of where like it connects all
17:30 of the things. That's the vision we
17:31 have. It's uh
17:33 It's happening sooner than later. How
17:36 would you then create a Cloudflare,
17:38 particularly one that can like create
17:40 its own skills? Cuz I think that for me
17:42 is the the thing I love the most.
17:44 You'd be able to just say like send it a
17:46 voice message and it says I've got a
17:48 cron that does really great thing now.
17:50 So, so we have um
17:53 we have a bunch of storage solutions. Uh
17:56 we have one in the durable object. So,
17:57 we have like SQLite directly in the
18:00 durable object. So, you can store stuff
18:02 there. You can store stuff in R2.
18:06 And all of that at the moment you have
18:07 to kind of wire up, but imminently you
18:10 won't.
18:11 All right. So, here's the thing. What is
18:13 open cloud? You want a thing that has a
18:14 heartbeat. You want a thing that has a
18:16 virtual file system. And you want a
18:18 thing that's connected to services.
18:22 Exactly. And you want extensions.
18:24 Which means you want to generate code
18:26 that's run in a safe sandboxed
18:27 environment.
18:30 I implemented extensions this morning.
18:33 It works really well
18:34 on our thing. By the way, I'm friends
18:36 like with Mario. Hi Mario.
18:39 And
18:41 yeah, 100%. We love Pi by the way, the
18:43 Pi coding agent. In fact, we want to run
18:44 Pi directly on workers as well. We've
18:46 been talking to him about it. Because
18:48 why not?
18:49 But
18:51 this is the future. Yes, we're we're
18:53 working I'm we're working non-stop on
18:55 this right now. If it wasn't for you
18:56 people, I'd be burning tokens.
18:59 Do you have any more questions? How much
19:00 time do we have? I don't even know how
19:01 long we have.
19:08 Would you like Python?
19:09 Amazing. So, we'll do Python as well.
19:11 The dynamic workers and workers itself
19:13 supports Python. You just need to spend
19:15 a little time like polishing the rough
19:16 edges.
19:18 Python is first class. JavaScript is
19:20 first class. Everything else is WASM.
19:22 The thing we've been playing with lately
19:24 is Zig.
19:25 Our boy here is one I think you're the
19:27 first person bring Zig into production
19:29 in Cloudflare workers
19:31 for a bunch of things that we actually
19:33 cannot talk about today. But Zig the
19:35 nice thing about Zig is the WASM bundles
19:37 are like tiny compared to like Go and
19:39 Rust.
19:40 So, other languages do we do WASM or if
19:43 it is that important to you to run it
19:45 like natively, you spin up a container
19:46 instead. Again, like we have a first
19:48 class SDK that lets you spin it up and
19:50 do things. That being said, brother,
19:52 your LLM is writing code at this point.
19:54 Like, why does it matter, right? Like,
19:56 whether it's JavaScript or not.
19:58 That's That's kind of my point as well.
19:59 Like, what
20:00 if if if you write whatever it was
20:03 Yeah.
20:04 Yeah, yeah. So, the infrastructure right
20:05 now, first class is JavaScript Python.
20:07 Uh and uh as you could tell, I'm a React
20:10 programmer, so I'm like, "Eh, Python too
20:11 hard." Uh but no, we'll polish off those
20:14 rough edges and we'll do that as well.
20:15 Hell, we have a thing which lets you run
20:17 a bundler inside a worker right now.
20:20 It's literally called worker bundler. It
20:22 pulls down dependencies from NPM, strips
20:24 out types, JSX, TypeScript, all of that,
20:27 and generates like the thing that you
20:28 would like run inside it. So fun,
20:30 because then it uses the Cloudflare
20:32 cache for dependencies instead of
20:34 worrying about NPM uh downtime. It's
20:36 quite nice.
20:40 All right. Uh when you said you have to
20:42 wire up the SQLite storage right now and
20:45 so you won't, what
20:47 What do you mean by soon? Um Oh, no, it
20:49 actually works. It's called
20:50 atcloudflair/shell.
20:52 Uh the APIs shouldn't break, uh but it's
20:55 usable today. Uh it gives you a full
20:57 file system inside uh layered on top of
21:00 both durable object SQLite and R2 for
21:02 like bigger files. I see.
21:04 It works today. You can use it today.
21:07 Actually, that's just it. I
21:08 I don't want to talk about the history
21:10 of that project. Uh anything else?
21:13 He searches his own name on Twitter,
21:14 you'll find the history of that project.
21:16 Yeah, it was a little dramatic.
21:18 Uh
21:19 anything else I can help you folks with?
21:21 Anyone want free credits and Like
21:23 I said, friends and family company, so.
21:27 Uh we I don't know if you wanted to talk
21:29 otherwise about the new CMS that we
21:31 launched last week. Uh it's called M-
21:35 Great name for a product in this day and
21:37 age. Uh it runs fully on Workers Durable
21:40 Objects, etc. And like, the nice thing
21:42 about M- is the plugin system is built
21:45 fully on dynamic workers. So, So, you
21:49 know how like WordPress has a bunch of
21:50 security incidents of its plugins? Well,
21:52 you just lock down where you run the
21:54 plugins, and it just works out of the
21:55 box. M- otherwise deploys actually
21:58 completely on any platform. It's not
22:00 Cloudflare specific, and we are working
22:01 on other platform support for this
22:04 dynamic worker bit that we that we have
22:06 right now.
22:08 Yeah. Uh other things is We Next. We
22:11 have a version of Next.js that runs
22:13 fully on Wheat, and it's so fun to use.
22:16 Uh
22:17 what else do we What do we do, bro? What
22:20 do we do?
22:21 Uh the problem is it's like next week is
22:23 our in one of our is our Agents Week, so
22:26 you'll be seeing a lot from us next
22:27 week. Oh, yeah. Like, twice a year we
22:29 have these announcement weeks where we
22:31 get really noisy, and next week's is
22:34 going to be particularly noisy, where we
22:36 announce a bunch of fun stuff. Yeah.
22:40 Any more questions? Go on.
22:41 >> going to come friends and family
22:42 questions for us today. Uh send account
22:44 ID and optionally bribes.
22:49 See, it's You can consider it a bribe or
22:51 protection money. Like, I'm trying to
22:53 also develop a little like mafioso vibe
22:55 around that.
22:57 Uh but no, dude. Like, we we
23:01 The way that Cloudflare is constructed,
23:03 the reason it's so cheap is because of
23:05 decisions made 10 years ago. We don't
23:07 build massive data centers. Instead, we
23:09 install hardware near ISPs. We buy
23:11 bandwidth in bulk from uh
23:14 level zero like top level ISPs, and we
23:17 do agreements where bytes that cross
23:19 boundaries, you don't really pay for it
23:21 and stuff. So, our free accounts aren't
23:23 marketing expenditure. It's just how the
23:25 business is constructed. Uh and I need
23:28 more people to know that. Like, I spent
23:30 a a bunch of time. I was like, "How do
23:31 they give it out for so cheap?" So,
23:34 it's otherwise $5 a month, and we know
23:36 people building multi-million dollar
23:38 like SaaS's on top of that. But, if you
23:40 want less than $5, well,
23:42 we can become friends friends with us.
23:47 That's cool. I think Uh other fun stuff
23:49 we have
23:51 >> Uh is that time? Oh, well, I guess we
23:53 are at time. How's no one knocking at
23:55 Oh, you are you are I'm so sorry. Uh
23:58 especially after we made a
23:59 thing about the previous session. Thank
24:01 you so much. We have a booth on the expo
24:03 floor. I'm speaking today at 5:40 p.m.
24:05 He's speaking tomorrow. You should watch
24:06 both talks. Uh like, look at us. Like,
24:10 uh I got a haircut for this, you guys.
24:12 Like,
24:12 like Uh it's going to be fun. Also, just
24:15 come hang with us. We love just like
24:16 chatting with people. Uh
24:19 agents.cloudflare.com or
24:20 developers.cloudflare.com/agents
24:22 for all the docs.
24:24 Uh
24:24 github.com/cloudflareagents,
24:26 you can file issues. We love That's just
24:28 it. Like, have your clan curl talk to
24:30 our clan curls. Uh and uh looking
24:33 forward to seeing what you build.


</details>
