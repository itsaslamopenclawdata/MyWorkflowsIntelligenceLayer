---
title: "OpenAI Codex: Build Apps That Work For You 24/7"
channel: "Greg Isenberg"
channel_slug: "greg-isenberg"
channel_id: "UCPjNBjflYl0-HQtUvOx0Ibw"
published: "2026-06-04T18:11:16+00:00"
duration_seconds: 1483
video_id: "tUeSxXHmE9w"
url: "https://www.youtube.com/watch?v=tUeSxXHmE9w"
language: "en"
tags: ["codex", "openai", "codex-sites", "autonomous-apps", "vibe-coding", "agentic-engineering", "startup-tools"]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-06"
---

# OpenAI Codex: Build Apps That Work For You 24/7

**Channel:** Greg Isenberg
**Published:** 2026-06-04
**Duration:** 24:43
**Watch:** https://www.youtube.com/watch?v=tUeSxXHmE9w

## TL;DR

OpenAI Codex Sites lets you build a hosted app from inside Codex using the `/sites` plugin, then have Codex keep operating it for you over time via four primitives: **memory** (persistent storage), **safe actions** (named, gated API mutations instead of raw SQL), **skills** (reusable instruction manuals so future chats know how to use the app), and **save gates** (versioned checkpoints). The live build in this episode produces a 5-column "Startup Ideas OS" kanban in 6 prompts, then proves the loop by opening a brand-new chat and having Codex add a card via the skill + safe action. Compared to Replit/Lovable, Codex Sites feels more technical but wins on autonomous, agent-driven updates and tight Codex-ecosystem integration (plugins, FAL, Hugging Face, Convex, D1). The current ceiling: no custom domains and no public deploys — internal apps only, for now.

## Key Insights

- **Codex Sites is a plugin you invoke**, not a separate product — you start a chat, type `sites`, and describe the app. Access is rolling out and is "probably coming really soon for plus plus people". [05:30–06:00]
- **Replit/Lovable beat Codex Sites on one-shot simplicity** (editor + database + server + hosting + domain in one prompt), but Codex Sites wins on autonomous updates if you already live in Codex. Codex Sites is "missing off, missing databases, missing payments, missing email sending, missing analytics, missing a vault for secrets" out of the box — those have to be prompted in. [01:30–04:30]
- **Greg's four primitives for a useful Codex Site**: (1) memory / persistent storage, (2) safe actions for agent-callable mutations, (3) skills so future chats can use the app, (4) save gates as versioned checkpoints. Without these, "the app saves data, but without this it's just a demo". [20:30–22:30]
- **The memory prompt is non-obvious**: ask for "persistent storage" and tell it to "show me the data model and which records/actions the app needs" *before* writing code. In this build Codex chose Cloudflare D1 as the durable store with one `ideas` record (full card content, current column, owner email) and 7 actions: list, add, update, move, score, archive, seed. [09:30–11:00]
- **Safe actions are the agent's hands**: Codex tightened the worker to only call named mutations rather than arbitrary SQL, so the agent can only do "approved buttons" — this is what lets you ping-pong in a normal Codex chat and have `@add-idea` actually update the live app safely. Non-technical users should just ask Codex "what should the safe actions be?" [11:00–12:30]
- **Skills are the unlock most people are skipping**: a Codex skill is a "reusable instruction manual" stored in your local skill directory so future chats know how to operate the app. Greg's skill "Startup Ideas Admin" covered read board, add/update/move/score/archive ideas, plus 5 example commands. [13:30–14:30]
- **Codex Sites does not auto-save** — explicit save gates are required, framed like video-game checkpoints. The save prompt confirms build status, storage choice, access setting, and the exact version to review, all without deploying. [15:00–16:00]
- **Proving the loop = open a brand-new chat and invoke the skill**: Greg prompted "use Startup Ideas admin to add: AI agent SEO grader for local businesses. Put it in inbox with a first pass score and next step" — Codex opened a fresh thread, loaded the skill, used only the safe board API (no raw SQL, no generic DB writes, no deploy), and the card appeared in the published site. [16:30–18:00]
- **Current limitations as of recording**: cannot publish to your own domain (URLs are a "crazy" auto-generated Codex URL), apps are internal/team-share only, and the UI comes out "clean, minimalistic — not the most beautiful". Greg predicts custom domains "very, very, very, very, very soon". [04:30–05:00, 18:30–19:30]
- **Plugins turn a Codex Site from a static page into a product**: Figma, Canva, HeyGen, Remotion, FAL AI (image gen), Hugging Face (open-source models) are all available from the get-go. Game Studio is Greg's underrated pick — build a small fun game as a top-of-funnel attention engine, then route players into the core product (works best for consumer apps; example: a "Paper Boy competitor" that newsjacks topics). [07:00–09:00]

## Notable Quotes

- "The more I dug into it, the more I realized it's actually worth understanding how to use it and how to get the most out of it." [00:00]
- "What's the coolest part about Codex sites is it updates your app autonomously." [02:30]
- "I think it's a really good tip is to save for review, do not deploy… this basically unlocks building a real product service, not a homepage." [06:30]
- "You're starting to see that Codex it does feel a little more technical than your Lovable or your Replit or your Bolt, but if you can stay with it the output I think is super, super valuable." [13:00]
- "A website is a living and breathing entity. It isn't something you hit publish and walk away forever. We're now in this era 2026 where the agents are actually doing the updating, the editing, the removing." [21:30–22:00]
- "The real unlock here is to make products that Codex can keep operating for you… it can create ideas and apps and websites that are automatically updated, automatically get better, are autonomous." [23:00–23:30]
- "A lot of people are sleeping on this idea that you can go and create little apps that could bring them into the core experience." [08:30]
- "You might not know what safe actions to create… you might as well just ask Codex and it'll give it to you right there. So for non-technical people especially." [12:00]

## Tools and Resources Mentioned

- **OpenAI Codex** (Codex Sites plugin) — primary tool, OpenAI's coding agent with a `/sites` invocation for hosted apps. [05:30]
- **Anthropic ecosystem / Claude Code** — Greg notes he still lives in Anthropic but now also uses Codex as part of his daily driver. [01:30–02:00]
- **Cloudflare D1** — the durable store Codex chose for this build ("OpenAI has D1 DB data model"). [10:30]
- **Convex** — Greg flags this as the database a lot of people are starting to use with Codex Sites; worth looking into. [20:30]
- **Replit** — competitor framing; one-prompt app building with editor/DB/server/hosting/domain. [01:30]
- **Lovable** — competitor framing; same one-prompt simplicity. [01:30]
- **Bolt** — mentioned alongside Replit/Lovable as a one-prompt competitor. [13:00]
- **Figma plugin** — design assets inside Codex Sites. [07:30]
- **Canva plugin** — design assets inside Codex Sites. [07:30]
- **HeyGen** — avatar video plugin. [07:30]
- **Remotion** — programmatic video plugin. [07:30]
- **FAL AI** — image generation plugin. [13:00]
- **Hugging Face** — open-source model plugin, "all built in from the get-go". [13:00]
- **Game Studio (Codex plugin)** — Greg's underrated pick; build small fun games as a top-of-funnel attention engine. [07:30]
- **Riley Brown** (podcast guest, ~one month prior) — convinced Greg to try Codex. [01:30–02:00]
- **"Startup Ideas OS"** (the example app Greg builds in the episode) — kanban with columns Inbox / Researching / Validated / Building / Killed, and per-card fields: idea, buyer, pain, proof, next step, score. [05:00]
- **"AI agent SEO grader for local businesses"** — the test card Greg's loop-adds in a new chat to prove the autonomous flow. [16:30]

## GitHub Repos and URLs Referenced

- **OpenAI Codex / Codex Sites** — https://openai.com (or in-product Codex chat). No explicit URL given on screen; access via the Codex app's `plugins` section, invoked with the `/sites` keyword. [05:30–06:00]
- **Codex app Plugins section** — in-product UI path: click `plugins` to browse Figma, Canva, HeyGen, Remotion, FAL AI, Hugging Face, Game Studio, etc. [07:00–08:00]
- No external GitHub repos, documentation URLs, or third-party product pages were shown on screen in this episode. Greg promised to "include all these prompts in the show notes in the description" for download, but no URL was rendered. [15:30]

## Action Items

- **Open Codex and invoke `/sites`** with a one-line description of the app you want to build. Always include the phrase **"save for review, do not deploy"** in your first prompt, and ask for **realistic sample data**. [05:30–06:30]
- **Add memory in prompt #2** with this exact framing: "Add persistent storage so ideas [things] saved between visits stay saved between visits. Before coding, show me the data model and which records/actions the app needs." [09:30–10:00]
- **Define safe actions next** — ask Codex: "Create safe actions for [list operations]. Tighten the worker so the agent can only call named mutations rather than arbitrary SQL." If you don't know what the safe actions should be, literally ask "what should the safe actions be?" [11:00–12:30]
- **Create a Codex skill** for the app: "Create a Codex skill called [App Name] Admin. It should explain how to read state, how to do the main mutations, and include five example commands." [13:30–14:00]
- **Save a version gate** before going live: "Save this as V1 review. Do not deploy. Confirm build status, storage choice, access setting, and the exact version I should review." Repeat at every meaningful milestone. [15:00–16:00]
- **Prove the loop** by opening a brand-new chat (don't continue the build chat) and invoking the skill by name — e.g., "Use [App] admin to add: [thing]. Put it in [column] with a first-pass score and next step." [16:30–17:00]
- **Browse the Codex Plugins tab** and add Figma, Canva, HeyGen, Remotion, FAL AI, and Hugging Face if your product needs design, video, or images. Consider Game Studio as a top-of-funnel game if you're building a consumer app. [07:00–08:00]
- **For non-coders**: outsource the architecture questions to Codex itself — ask "what records and actions do I need?" and "what safe actions should I create?" rather than guessing. [11:30–12:00]

## Open Questions

- **Custom domains and public deploys** — when will Codex Sites support publishing to your own domain and going live publicly, not just internal team sharing? Greg says "very, very, very, very, very soon" but no date. [04:30, 18:30]
- **Pricing tier rollout** — Greg notes "not everyone has access" and predicts "coming really soon for plus plus people", but he doesn't know the exact rollout plan or whether it will be free, included, or paid. [05:30–06:00]
- **Best database choice for production** — Codex used Cloudflare D1 in this build, Greg mentions Convex as another popular option, but he doesn't compare them on cost, scaling, or DX. [10:30, 20:30]
- **How do automations and cron jobs actually work in Codex Sites?** Greg says you can "ask Codex Sites to run an automation like every week to automatically add to this board" and offers a follow-up video, but he doesn't demo it here. [19:00–19:30]
- **Plugin depth and limits** — how much of Figma, Canva, HeyGen, Remotion, FAL AI, and Hugging Face is actually exposed inside Codex Sites vs. just linked? Are there rate limits, quotas, or billing on top of Codex? Greg doesn't say. [07:00–13:00]
- **Security of safe actions** — Greg frames the safe-action boundary as "the agent can only call named mutations rather than arbitrary SQL", but he doesn't cover auth, per-user access control, or what stops a different Codex user on the same team from calling a safe action on someone else's data. [11:00–12:30]
- **What "missing analytics, missing email, missing payments" actually means in practice** — Greg lists these as gaps Codex Sites has, but doesn't show workarounds (e.g., does Stripe work via a plugin? Is Postmark/Mailgun available?). [04:00]
- **Are the prompts in the show notes already posted?** Greg promised to put all the example prompts in the video description, but doesn't link to them in this recording. [15:30]

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 24:43 transcript)</summary>

[00:00] I saw that Codex launch sites, and when I first saw the news, I was like, is this is just a worse version of Replit or Lovable that's just inside Codex? But the more I dug into it, the more I realized it's actually worth understanding how to use it and how to get the most out of it. So, uh today is a full tutorial on basically what the big announcement is around Codex sites, how does it compare to the competition? >> [music] >> Uh we're actually going to go and live

[00:30] build using Codex sites, and through that, I'm actually going to teach you >> [music] >> uh basically the best practices for using Codex sites. So, by the end of this episode, if you stick around, I'm going to teach you how to build a how to build a shell using Codex sites, how [music] to add memory using Codex sites, how to add what's called safe actions using Codex I sites, and I'll explain what that means >> [music] >> in the episode, how to create skills with Codex sites, how to save [music] gate using Codex sites, and how to prove

[01:00] the loop using Codex sites, which which makes [music] it uh work autonomously. Let's get into it. >> [music] [music] >> So, what is the difference between Codex sites and Replit and Lovable and and stuff like that? So, um I will say Replit and Lovable and and and those and those products are really

[01:30] good if you want to like one prompt something, and it has an editor, it has a database, it has server, it has hosting. A lot of them have connections to domains as well, too. Like, you can just uh cre- uh register a domain within it. Um so, that's really amazing. Um but Codex sites, if you live in Codex, and I'm starting to live in Codex. I mean, I think it was about a month ago I had Riley Brown on the podcast and I I basically said like, "Hey, convince me

[02:00] to use Codex. I'm in the Anthropic ecosystem. Convince me to use Codex." And now I will say it's a part of my daily driver. Yes, I still live in the Anthropic ecosystem, but I'm also using Codex. And um I think that if you are in Codex and you are putting just all your contacts there, what's really cool about Codex sites is uh you can actually use that to go and build your ideas, your apps, and stuff like that. And what's the coolest

[02:30] part about Codex sites is it updates your uh your app autonomously. So, what does that mean? It means that uh you can have it uh basically create a personal website, say, and uh you know and let's say, for example, go to my personal website. Um this is a static uh this is a static website. So, I actually have to go in and and basically, you know, 100 158,000 people

[03:00] enjoy reading my newsletter, but like when it becomes 160,000, I have to go and update it. But with Codex sites, you can actually have it so it automatically updates these things. It automatically creates, for example, guides based on my content. It automatically, you know, adds the different companies I work on. So, it basically is this whole idea around autonomous product building. I've talked about this before, but the idea around

[03:30] you're going to have in the future and and the future is now the present, basically agents going and updating products autonomously. But the thing is, it is missing off. It's missing databases. It's missing payments. It's missing missing email sending. It's missing analytics and it's missing a vault for secrets. So, a lot you You if you want something more simple, everything is in there. You're going to want to use something like Rapid or Lovable, but if you understand a little bit about off, if you understand a little bit about database,

[04:00] payment, stuff like that, um and you live in the Codex ecosystem, and you are really interested in this whole idea around autonomous apps, Codex sites are really, really, really cool. And I also say one thing, today you can't um publish these websites, at least not to my knowledge, you can't publish these websites on your own domain and go and deploy it publicly. These are internal apps that you can share with your team right now. But obviously that's going to

[04:30] change very, very, very, very, very soon. So, let's get right into it. So, I I was thinking that we can create um a startup ideas OS. So, basically a live board with columns, uh inbox, researching, validating, building, and killed startup ideas. And each card can have an idea, buyer, pain, proof, next step, and score. So, this is something that, you know, could be an internal internal tool that I would use. And we're going to basically try to build it in six

[05:00] prompts. And like I said, as I build it, I'm going to share uh sort of the big takeaway. So, the first uh first thing we're going to do, let's go open Codex. So, I uh created a new project here. Um I'm I opened a uh a new chat. And you know, the first thing is, you know, if you want to actually use sites, you have to invoke it at sites. So, it works basically as a plugin. So, I said,

[05:30] "Build a startup OS." Um I'm going to go ahead and send it. Um and uh yeah, it works as a plugin. You invoke it there. Um and like I said, not everyone has access to it. Um uh but I would imagine that access is probably coming really soon for for plus plus people. And by the way, I have no affiliation with OpenAI. I just think this is a really interesting product and I wouldn't be making this episode if I didn't think

[06:00] that you can get a lot of value from it, too. So, um what is the insight I have for you about this particular prompt is that, you know, um well, there's a few things. Uh yeah, invoke the way to to to get it going is you want to invoke sites. Um you want to actually ask it to use realistic sample data. Um you also want to save it for review. So, I noticed that um sometimes when I

[06:30] ask I prompt it an idea, it'll just try to deploy it. So, uh a a really good tip is to save for review, do not deploy. Um and this basically unlocks building a real product service, not a homepage. So, basically, I what I'm trying to do by building this is to build that whole idea around autonomously being able to edit it and and work on it um cuz that's sort of sort of the dream state for me. Um so, let's go ahead and go back to

[07:00] Codex. Okay, while that is being worked on, um I just wanted to say that if you if you go to the plugin section over here, so you click plugins, there's a bunch of plugins that are going to help you make your sites a lot better, right? So, um you know, a lot of people aren't using these plugins, um but think about like Figma. Think about um

[07:30] Canva. Think about HeyGen for avatar videos. Think about Remotion. These are uh a bunch of plugins that could make your ideas for your sites a lot more interactive, a lot more a lot more interesting. Uh Another really interesting one that's underrated I think is Game Studio. So, you know, one of the biggest problems that people have with vibe coding and agentic engineering is they build something and no one no one's

[08:00] uh no one's going to it. Well, you know, if you build games for example, that actually generate buzz around what you're you the bigger you know, the the product you're building, that's a way to get attention and then you bring those people into your core your core product. Now, of course that needs to make sense for whatever it is you're building. And this works better with consumer apps, right? So, you go and create a um you know, a Paper Boy competitor

[08:30] that's fun to play that you can kind of like newsjack a based on a particular news topic and then you bring those people into um you know, whatever your core experience is. Maybe it's an email newsletter or who knows, but the the point is like I think a lot of people are sleeping on this idea that you can go and create little apps that could bring them into the core experience. All right, so it's built the board. I think it looks pretty pretty clean.

[09:00] Um got the inbox over here, researching, validated, building, killed. Definitely not the most beautiful, but clean, minimalistic. Um good enough for a first version. Um so, let's go back and keep going. So, how do we add memory, right? Cuz on Codex sites it's it's not going to add memory without us basically getting it to to prompt it.

[09:30] So, let's go ahead and go back into Codex. I'm copying this prompt. So, I say add persistent storage so ideas saved between visits stay saved between visits. Before coding show me the data model in which records action the app needs. And this is by the way, these prompts are similar prompts that you can use for when you're using Codex sites. Um so it says I'll use the sites building guidance here because this is a hosted app with storage. Since you asked

[10:00] for the model first, I'm going to inspect the existing schema and then lay out the proposed records and mutations before touching code. So it says it's actually going to use Cloudflare, right? I'll use Cloudflare D1 as the durable store with one main record type ideas. This already matches the project's current direction and OpenAI has D1 DB data model. So then it goes and if you if you see here it says the record the apps need.

[10:30] So it says it needs an idea, one one card on the board. It It stores the full card content, the current column. It It needs an owner email. And then these are the actions that the app needs. List ideas, add idea, update idea, move idea, scoring the idea, archive the idea, and sure and sure seated. Um and then it says I'll wait for your go ahead before coding the persistent path path. So this is the whole idea of safe

[11:00] actions which are you know, um Well, before I get into that, why add memory? Well, because we need for this to be a productive piece of software, we need it to remember things, right? So we want to make sure that we've got that in there. But the whole idea around safe actions is is going to be it's it's an unlock because we can be in other chats and because we live in Codex, we can basically say, "Hey, I you know, maybe I'm like ping-ponging with Codex and

[11:30] then I hit me back with a an idea startup idea and I'm like oh this is really good. Let me just Let me just add So let me just at add idea and it it'll directly add it to the application which is so cool. So you're going to want to create safe actions because you know in order to get the most in order to get the most out of it. So I'm just going to go ahead and and copy that prompt create safe actions for add idea update idea and and the reason you know it's important to

[12:00] that I you know I I I I said show me the data model and which record and actions the app needs is you might not know what safe actions to create. So you you might as well act ask Codex and it'll give it to you right there. So for people non-technical people especially like that you might not know your safe actions are you just ask Codex what what they should be. So it says I'll use the sites building workflow again since this is a worker D1 service. I'm going to inspect the current action

[12:30] routing and tighten into an explicit safe action boundary so the agent can only call named mutations rather than the arbitrary SQL. So you're starting to see that Codex it does feel a little more technical than your your lovable or your replate or your bolt but if you can stay with it the output I think is super super valuable. Like the idea that you can have it self self update the idea that you're in

[13:00] Codex and you can bring in all this stuff from Codex. The idea that you can go into the plugins and and just use all this stuff from the get-go like these are some of the I mean FAL AI and image generation like so much stuff hugging face these are all open source models like just all built in from the get-go. It's pretty sweet. So that's completed so the next thing we're to want to do is create a skill.

[13:30] So, we're going to copy this here so that the chats, our future chats, are going to know how to use this app. So, create a Codex skill called Startup Ideas Admin. It should explain how to read the board, how to add ideas, how to move cards, how to score ideas, and include five example commands. This is something that I think that is you know, I I started seeing people use uh Codex sites and they're not using skills. And I'm like,

[14:00] this is one of the greatest parts of of Codex sites is the ability to create these skills. So, you might as well might as well might as well uh start adding some skills to get the most out of your application. So, it says, "I'll use the skill creator guidance for this since you're asking for a new Codex skill. I'm going to read the skill instructions and create Startup Ideas Admin in your local skill directories with the board action workflow and example commands. The skill name is already valid and the scope is clear. Operational guidance for

[14:30] this board um and it's safe actions. So, it's gone ahead and created the Codex skill. It it it's done everything we've asked for, reading the board, adding ideas, updating cards, moving cards, scoring ideas, archiving ideas, five example commands, and it says, "Validation pass. The skill is valid." It's going to be helpful for you to actually save gates. What do I mean by that? I mean, you know, the way I think about it is like a video game, right? Like, you have

[15:00] like checkpoints as you go through a video game, and sometimes it'll auto save, and you're you're happy it auto saved. But, the thing with Codex is it doesn't auto save. Um so, it's helpful to go in there and just say like, "Hey, just do a checkpoint here before a live URL." So, uh let's go ahead and go back into Codex. And I'll say, "Save this as V1 review. Do not deploy. Confirm build status, storage choice, access setting, and the exact version I should review. And I'll

[15:30] include, by the way, all these prompts I'll include in this show notes in the description for for people to download. Um so that they can go ahead and and and as they're building Codex sites, they could uh they can go and use some of this stuff. So it says, I'll use the sites hosting workflow for the save-only review session. I'm going to validate the current build, confirm the storage access config, commit the latest safe action changes, and then save a sites version without deploying. There you go. So prompt is done. It's saved for

[16:00] review. It isn't deployed. The build status is passed. Um the storage choice is still D1. The access setting is custom. Um One thing to note here is at the top right, you can see like your whole environment here. So you can see all the different changes you made. You can see if you're working on locally or you're connected to Codex web. Um here I'm connected to the main branch. Um and so I you know it's just all all up here on the top right.

[16:30] The last prompt I want to do is the whole proving the loop process. So what I'm going to do is I'm going to grab this prompt right here. And I'm going to say in a new chat, important important that's in a new chat, use Startup Ideas admin to add, here's the startup idea, AI agent SEO grader for local businesses. Put it in an inbox with a first pass score and the next step. And let's see if it actually can do that. Does it open up a new chat or do we actually have to go and open up a new chat? Let's see.

[17:00] It says, I'll treat this as two pieces. Use the new Startup Ideas admin skill instructions and create a fresh chat thread to do the actual board update. There, yes. I'm loading the skill and finding the thread creation tool now. The skill says to only use Oh. Look, it's gone and opened. It's gone and created the chat. I can open it right here. So, it says, "I'm using the skill. Um I'm going to find out how the local app is meant to run. I'm going to read the board. I'm going to add the inbox

[17:30] card and the safe action and verify by reading again." Exactly what I wanted to do. The project is clean and looks like a next style app with a worker and a verifiable script. "I'm checking the API implementation now so I can call the same local service the app expects. The app exposes exactly the safe route the skill expects." Yeah. So, this is doing exactly what I want it to be doing. And let's see if it works. All right. So, the prompt is done. It says, "Done using only the safe board

[18:00] API," which is what we wanted. "In the action layer, there's no raw SQL SQL, no generic database writes, and no deploy." It's gone and did it. It went really, really fast. So, now I'm going to say, "Can you publish Now, I'm going to say, "Can you publish website?" and see what happens. So, it's gone ahead and deployed it. You'll notice that it's this crazy URL. And that's a downside of Codex sites at

[18:30] the moment. I think this is going to change. That's my prediction. It's going to change hopefully soon where they're going to be able to have custom domains. But, I can go and open it in Codex browser on the right here. It's got off built in here. I do have to sign up. So, I'm going to go ahead and sign up. So, as you can see, this is exactly what we wanted. We've got the inbox, the researching, the validated. Um if I make it bigger here, I can see more. The building, the killed.

[19:00] Um and it's got everything I've asked for, right? Um Now, if I want a new idea, I can go and actually create a new idea. Or again, I can use a safe action to go and do it, or I can have it run an automation like every week to automatically add to this board. So, we've seen that you can actually do that. Um I can go more in-depth in a future video if people are interested in like how to do automations and cron jobs and stuff like that, but you can basically just uh

[19:30] you know, ask Codex Sites go and do that for you. And I think what's really cool is that like you know, if you listen to this channel, a lot of us are interested in creating startups that you know, we don't need big teams to to manage, right? And this whole What's so cool about this is we're getting to this with Codex Sites. We're getting to this If you can create agents that go and automatically update based on, you know, different uh

[20:00] criterias, then and then and it work and these are products that work and are valuable to people, then um that's sort of sort of the dream. So, this you know, is it the most beautiful website on the planet? No. Does it work? Yes. Does it look decent? Yes. Could I get it to a point where it looks beautiful? Um I can. And um and that's that's pretty cool. So,

[20:30] to to to like TD TLDR it, like what are the main concepts to understand in within Codex Sites is number one, you're going to want to ask it to have memory, right? You know, the app saves data, but without this it's just a demo. So, you're going to have to ask it to to save memory. You're going to have to ask it to have a database. Um a lot of people are starting to use Convex with um with Codex Sites. So, that's something

[21:00] to look into. Um I imagine that over time it's just going to be easier and easier to use Codex sites, um but now you do need a prompt it to do a lot of these things. The second thing is is this concept called safe actions. So, this whole idea that you can have approved buttons, um and and through that you can have it auto automate uh adding, removing, editing your apps, um so that, you know, you are

[21:30] as the human being aren't doing everything and you don't have to actually edit every uh every website or app you create, you know? Uh I used to run a web design agency. It was one of my first jobs and you know, one of the things I used to say was a website is a living and breathing entity. Um it isn't something that you hit publish and you can just like walk away forever. And, you know, we're now in this era 2026 where the agents are actually doing

[22:00] the the the updating, the editing, uh the removing, and that's through things like safe actions and skills. Like, use skills with Codex. We saw how how it could be valuable in this in this episode, but a skill is basically this reusable instruction manual, so Codex knows how to operate the app later. So, you're going to need to create skills so you can use the safe action safe actions and so that and obviously you're going

[22:30] to want to store that in the memory so that it, you know, it it does it safely and and is giving the right information. So, uh all this to say, the wow moment for me, um >> [snorts] >> is is building apps where I could do like, you know, in this example, I could open a new chat and say add this idea to my startup ideas OS. It shows it shows it in the live site updating, right? So, once it's published, um I could just be

[23:00] like, at do this and it's going to add it or I can have an agent do it and it's going to add it and it's going to be all on my live website, which is really cool. Um, I think that a lot of people are going to use Codex Sites to make like personal web pages, to make like little apps and stuff like that. But I actually think that the the real unlock here is to make products that Codex can keep operating for you. That is what's exciting me about Codex Sites is that

[23:30] it if we can create ideas and apps and websites that are automatically updated, automatically get better, are are autonomous, I just find that so so interesting and I think this is a trend that's only going to get bigger, better, and it was interesting to see that Codex Sites is is leading the charge. So, yeah, this has been a inside look as to how to use Codex Sites, what I think is interesting about it, some best practices. I hope it's been helpful. I'm just trying to share the most the the

[24:00] new tools that I think are are going to make uh increase I'm just trying to share the the new tools that are going to increase the probability of success for you, whatever it is you're building, um and just share the best way to use these tools, um and give you ideas along the way. If this gave you an ounce of value, please uh like, comment, and subscribe. I'll see you in the comment section. I read every single comment and uh I'm I'm rooting for you. Uh you know, whatever

[24:30] it is you're building, I'm rooting for you and I can't wait to see what you build. I'll see you on the next one and thank you for uh joining in the Startup Ideas podcast.

</details>
