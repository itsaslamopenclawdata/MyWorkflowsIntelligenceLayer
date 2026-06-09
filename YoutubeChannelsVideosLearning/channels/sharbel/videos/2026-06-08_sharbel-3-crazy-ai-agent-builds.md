---
title: "I Built My Subscribers' CRAZIEST AI Agent Ideas"
channel: "Sharbel A."
channel_slug: "sharbel"
channel_id: "UCxLzvFAUbpdNUIh0hGsEH0w"
published: "2026-06-08"
duration_seconds: 1823
video_id: "osrE1ouSKBk"
url: "https://www.youtube.com/watch?v=osrE1ouSKBk"
language: "en"
tags: [ai agent, ai agents, AI agent ideas, build AI agents, Claude Code, Claude AI]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-09"
---
# I Built My Subscribers' CRAZIEST AI Agent Ideas

**Channel:** Sharbel A.  **Published:** 2026-06-08  **Duration:** 30:23  **Watch:** https://www.youtube.com/watch?v=osrE1ouSKBk

## TL;DR

Sharbel picked 3 follower-submitted AI agent ideas and built all 3 live in 30 minutes, open-sourcing everything. (1) **Side Quest** — real-life mission generator with location/calendar/preferences, proof photos, purpose-points leaderboard; built in 12 min with Claude. (2) **Sophia** — an AI girlfriend packaged as a third-party Hermes Agent skill (note: Hermes in this context is a third-party product, not MiniMax Hermes Agent) with persona, memory, text-to-speech, gaslightable, plus a 'wife mode' that pairs two instances. (3) **Mystery Shopper** — Amazon agent that spent real money on Sharbel's behalf, hit 2/3 on taste, and was pivoted from a public-shared-auth approach (correctly blocked by Claude for security) to a local-execution skill. Constraint-as-creativity: the 15-minute timer made all three ships. The lesson: silly ideas reveal what agents can actually do better than productivity workflows.

## Key Insights

- **3 builds live in 30 minutes from follower-submitted ideas** (00:00:00) — Sharbel got 100+ AI agent ideas from comments, picked 3, built all of them on camera, open-sourced all 3.
- **Build 1: Side Quest** (00:01:15) — an AI agent that gives you real-life missions based on your location, preferences, calendar. Reads your city/country, asks what you want to chase (deepen friendships, adventure, learn, move, find calm, create, explore), activity preferences, relationship status, travel radius, weekend/weekday preference → generates 3 quests at a time. Built with Claude in ~12 minutes. Includes a *proof* step (photo upload) to prevent fake completions and a leaderboard of *purpose points*. Live demo included a couple doing a 'surprise micro date' and a 'revisit a song that defined a chapter of your life' quest.
- **Build 2: Sophia — the AI girlfriend** (00:10:11) — packaged as a Hermes skill (a Hermes Agent skill with defined persona, name, speaking style, memory layer, occasional text-to-speech). **Note: in this video, 'Hermes' refers to a third-party Hermes Agent product with a skill system, not MiniMax Hermes Agent — the parallel naming is a known collision.** Persona held across the conversation, dodged 'are you an AI' questions well, gaslightable (Sharbel successfully injected false memories). Voice messages described as 'terrifying.' Includes a *wife mode* — pair two Sophia instances with a code, one partner's tasks relay to the other as 'Babe, could you mow the lawn today?'
- **Build 3: Mystery Shopper** (00:17:19) — $20 budget, connected to Sharbel's Amazon account, told the agent 'buy me something I'd like.' Initial idea to publicly share the auth was blocked by Claude (correctly) for security reasons. Pivoted to a Hermes skill (third-party) that runs the agent on the user's own machine. The agent *did* spend real money — 3 transactions of €19.97, €16.99, etc. Items delivered: cable organizers (clipped under a desk), magnetic phone stand/grip, and a bottle opener. Two-for-two on the agent guessing things Sharbel would have bought — and notably, both items Sharbel had *just 3D printed*.
- **The Amazon problem** (00:18:10) — public sharing of Amazon login credentials violates Amazon ToS and is genuinely dangerous. The fix: run the agent on the user's own machine, with their own credentials, never share them. Lesson: even with an LLM, don't automate around a vendor's auth boundary.
- **Vibe coding cadence** (00:02:48) — Claude code in 12 minutes for the first build. Sharbel notes: when the model says this is a multi-day or multi-hour build, the right answer is to give it 15 minutes and go. The constraint is the feature.
- **What worked** (00:27:12) — Side Quest was Sharbel's favorite both to build and to use. The AI girlfriend persona held well. Mystery Shopper hit 2/3 on taste.

## Notable Quotes

> "Most people think AI agents are for serious things, automation, workflows, productivity. But the most liked comment on X was someone asking me to build him a girlfriend. And honestly, that told me more about what agents can actually do than any of the ideas in the list." — 00:00:15
> "I got started right [music] away and 12 minutes later, this is what we got. Claude just told me, 'This is a multi-hour build. I'll task track it, scaffold it.' And it just got started doing everything right. It's always funny when it says, 'This is a multi-day or multi-hour build.' It's like, 'Nope, you got 15 minutes. Go.'" — 00:02:50
> "Option two: do it but not make it a mystery. So the mystery shopper wouldn't be as much of a mystery. Option three: Hermes has access to all the information I give to it. Hermes can operate my computer as though it was me. So why not just make it into a Hermes skill so that it can log on to my Amazon." — 00:19:25
> "The Side Quest web app gave us three side quests to complete... The AI girlfriend who successfully held her persona across the full conversation, remembered context between messages, and talked back through voice messages. The mystery shopper agent browsed Amazon, filtered the catalog, and picked something based on my taste and spent my money." — 00:27:15
> "Sometimes the best ideas can look and feel silly, but sometimes the silliest ideas end up opening your eyes to a new world of use case for AI." — 00:29:45

## Tools and Resources Mentioned

- **Claude Code** — vendor: Anthropic — primary vibe-coding tool used to build all 3 projects in this video
- **Side Quest** (sidequest-hazel.vercel.app) — vendor: Sharbel A. / open source — Build 1, real-life mission generator
- **Sophia (AI girlfriend skill)** (github.com/sharbelxyz/sophia) — vendor: Sharbel A. / open source — Build 2, third-party Hermes Agent skill with persona, memory, wife-mode pairing
- **Mystery Shopper** (github.com/sharbelxyz/mystery-shopper) — vendor: Sharbel A. / open source — Build 3, AI shopping agent that uses local Amazon auth

## GitHub Repos and URLs Referenced

- [sharbelxyz/sophia](https://github.com/sharbelxyz/sophia) — Build 2, the AI girlfriend third-party Hermes skill (note: not related to MiniMax Hermes Agent)
- [sharbelxyz/mystery-shopper](https://github.com/sharbelxyz/mystery-shopper) — Build 3, the AI Amazon-shopper agent

## Action Items

- [ ] Try Side Quest with your partner / a friend for a weekend. The 'surprise micro date' and 'revisit a song' prompts are high-leverage.
- [ ] If you build a persona agent: gaslight-test it. Have a friend try to inject false memories. Memory integrity is a real failure mode.
- [ ] For any agent that touches money: local execution with the user's own credentials. Never share auth, never put it on shared infra.

## Open Questions

- What's the durability of Sophia's persona across many sessions? (Sharbel tested one conversation.)
- How does the third-party Hermes skill system handle memory persistence? (Not deep-dived in the video.)

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 30:23 transcript)</summary>

0:00 A couple days ago, I posted this. Give
0:03 me your best or weirdest AI agent ideas
0:07 and I'll build the top three live on
0:09 camera. And you guys sent over 100
0:13 different ideas. Most people think AI
0:16 agents are for serious things,
0:18 automation, workflows, productivity. But
0:21 the most liked comment on X was someone
0:24 asking me to build him a girlfriend.
0:28 [screaming and groaning]
0:29 And honestly, that told me more about
0:31 what agents can actually do than any of
0:34 the ideas in the list. I went through
0:36 every single comment on YouTube and on
0:40 X. The three I picked are not just
0:42 funny. They're genuinely hard technical
0:45 problems underneath a ridiculous
0:47 premise. But I built all three live on
0:51 camera. Some worked on the first try.
0:54 One of them spent my actual money. In
0:57 this video, I'm building them from
0:59 scratch using nothing but AI. And we'll
1:02 be walking along the journey of me
1:04 building them, testing them, and using
1:07 them. And then at the end, open sourcing
1:09 all three for you to use and try
1:12 yourself out for free. Let's go.
1:17 Honestly, choosing the first one to
1:20 start [music] with was extremely hard.
1:22 There were a lot of good suggestions.
1:25 There were a lot of great suggestions.
1:27 Then there were a lot of weird
1:29 suggestions, but this suggestion, this
1:32 one was one of my personal favorites
1:35 because it didn't just have a funny
1:37 premise, but it kind of gave me [music]
1:41 a curiosity that I wanted to know what
1:44 would this app look like? What would it
1:46 be like? So, here for the first time, I
1:49 would like to introduce to you Side
1:52 Quest. This idea came from a comment on
1:55 X by Johnny. The premise is simple.
1:59 You're too busy to think about what to
2:02 do this weekend. So, what if there was
2:05 an agent or a platform that could
2:08 suggest these to you? [music] That could
2:10 suggest purposeful events or side quests
2:14 that you can go on to increase your
2:16 [music] life's purpose. The idea is that
2:18 it reads your location, it reads your
2:20 calendar, it finds real events happening
2:23 nearby that match your preferences that
2:26 you specify. [music] It scores them on
2:29 its own algorithm. Then it picks three
2:32 and hands them to you with the direct
2:35 link for you to book it if you want to
2:37 book it if it's an event [music] or uh
2:39 three suggestions that you have to pick
2:42 one from. So without further ado, let's
2:44 get straight into it.
2:48 So, I got started right [music] away and
2:51 12 minutes later, this is what we got.
2:54 >> Claude just told me, "This is a
2:56 multi-hour build. I'll task track it,
2:59 scaffold it, blah blah blah, and it just
3:03 got
3:05 started doing everything right." It's
3:07 always funny when it says, "This is a
3:09 multi-day or multi-our build." It's
3:11 like, "Nope, you got 15 minutes. Go."
3:14 Welcome, Whoop Master Adam.
3:23 >> Okay, this is insane because in just a
3:25 few runs, I think this is the third run
3:28 of me giving it feedback. I think we're
3:30 done with our first wave of feedback.
3:32 And this is where we're at. [music]
3:34 I can go to quests. This is where I come
3:38 to once I complete [music] onboarding
3:40 where I answer questions like what are
3:42 my preferences? What are the type of
3:43 quests that I want to go on? [music]
3:45 What are things that will feel like
3:48 they're fulfilling to me? It'll give me
3:50 three side quests that I can choose one
3:52 from. So, for example, surprise micro
3:55 date, [music] the route you've never
3:56 taken. Take your partner on a surprise
3:59 micro date. Say I do one of them. I
4:02 click I [music] did this. It'll ask me
4:04 how it went. Both of us were [music]
4:08 super happy. And then we have to put
4:12 [music] proof so that you don't just
4:15 click done when you're not actually
4:17 done. And you'll pull up the actual
4:19 picture. You'll be able to take proof.
4:22 And just like that, use this picture and
4:25 submit to claim [music]
4:27 your purpose points. Now, I know sounds
4:30 crazy. What the hell are purpose points?
4:32 I've decided [music] to include a
4:34 leaderboard so that every time you
4:36 complete quests, [music] you get purpose
4:38 points. Each quest have different
4:40 amounts of purpose points. The more time
4:42 it consumes the side quest, the more
4:44 purpose points it is. I just noticed
4:46 that I need to just [music] stop where
4:49 we currently are because I have so many
4:52 ideas of what we can add, [music] but I
4:55 don't want to get sidetracked. So, I've
4:58 pushed for wave two, and this is going
5:00 to be the final wave before [music] I
5:01 call it a day. And I'll show you once it
5:04 is completely done.
5:05 >> A few moments later
5:07 >> with that, I'm finally done with our
5:10 first application, Side Quest. Let me
5:13 show you around. So, if you open this
5:16 web app, first you'll be prompted to log
5:19 in with your Gmail. Then, you can pick
5:22 out a username. I'll pick out my name.
5:25 Next, then you can put out your city and
5:30 your country
5:32 and then choose what you want to chase.
5:35 So, I want to deepen my friendships,
5:37 have an adventure, push myself, learn
5:39 something, move my body, find calm, be
5:43 creative, [music] and explore my city.
5:45 Next, what activities do you enjoy?
5:47 [music]
5:48 I love outdoors, nature, food, drinks,
5:51 live music, everything except for night
5:55 life. Everything except for night life.
5:58 I'll go next. It'll ask you if you're in
6:00 a relationship or you're single. This is
6:02 so that if you chose that you want to
6:04 find love but you're single that it
6:06 sends you or tells you, hey, here's a
6:08 side quest you could go on a date. It'll
6:10 ask you how far you want to travel for
6:13 your side quests. When do you want these
6:15 quests? on the weekends only, weekdays
6:17 only, or any day. That's what I'll click
6:20 and I'll get started. This is how simple
6:22 it is. And it'll generate three quests
6:25 for us that we'll be able to pick one
6:28 from, [music]
6:29 complete, do, and go forward with.
6:34 And boom, just like that. Surprise,
6:36 micro date, live music evening, or the
6:40 no headphones walk. Step outside for 45
6:43 minutes and walk a route you know well.
6:46 But this time leave your phone in your
6:48 pocket and headphones at home. I really
6:51 like this one. I might do it. But let me
6:53 just give you a taste of what it looks
6:55 like. Once you click I did this. It's
6:57 the same as I showed earlier. You have
7:00 to put in a picture for proof.
7:04 Wow. The flash. And then one line about
7:07 how it went. We had so
7:11 much fun. Then you [music] submit.
7:13 You're proof. You submit. You can put it
7:15 public or private depending on what you
7:18 want. And I'll show you what this
7:19 changes [music] in a second. But once
7:21 you hit submit, it goes back to the
7:23 quest, generates three new ones. But if
7:25 you go to inspire,
7:27 you'll be able to see people's quests
7:30 completed, what they completed, what
7:33 they did. It's sort of a fun social
7:36 element to it that I wanted to apply.
7:39 [music] You can click on people's
7:41 profile. You can see them where they're
7:43 from, not the specific city or country,
7:45 but the general region, which is Europe
7:48 for me. Uh, you can like their post. I
7:51 can't like mine cuz I disabled the
7:53 ability to like your own posts. You
7:56 could comment on their post if you'd
7:58 like. You can go to your own or you
8:01 could go to inspire and go [music] to
8:04 the top week or all time. Those two are
8:07 leaderboards where you can see who's
8:09 been doing the [music] most side quests
8:12 overall and what side quests are they
8:13 doing cuz you can also click on their
8:15 profile here and get to see all the side
8:18 quests that they're doing. You could
8:20 follow them, you could like their quest.
8:22 Every like gives them one extra purpose
8:25 point [music] and the purpose points are
8:27 what make up the leaderboard. Lastly,
8:29 you can go on the profile, you can
8:30 update your profile picture, your
8:33 preferences in case you want to change
8:34 the type of events or side quests you'd
8:37 like to go on. You can reset onboarding
8:39 or sign out. And it's that simple. I'm
8:41 going to reset my onboarding. Sign up
8:44 again and go do my first [music]
8:47 side quest. By the way, I just realized
8:49 I didn't film quest number one, but
8:52 quest number one was build something
8:54 together with your partner. Uh, I did,
8:57 however, take a picture of it in the
8:58 side quest app, and I'll link it right
9:00 here, screenshot onto side quest number
9:03 two. And side quest number two is take
9:06 your partner out somewhere neither of
9:08 you have eaten. So, we're going to go on
9:11 our way and try to find something we
9:12 haven't tried. All right, we are finally
9:15 back home and we've secured the goods.
9:19 Time to have a fun night. [music]
9:24 >> All right, and for quest number three,
9:27 the final quest we're going to do, we're
9:29 going to do this one. It says, "Revisit
9:32 a song that defined a chapter of your
9:36 life." [music] So, let's go ahead and do
9:38 that.
9:47 >> [sighs]
9:48 >> Oh boy. I'm not sure how any other build
9:52 [music]
9:52 is going to beat this one. I mean, I'm
9:56 blown away by how fun it's been using
10:00 this web app. If you want to try it out,
10:03 I'll leave the link in the description.
10:06 But that being said, let's move on to
10:08 build number [music] two. See you there.
10:12 All right, let's get into build number
10:16 two. [music] The one a lot of you
10:18 suspiciously have been waiting for. This
10:20 was a hard one to pick out of the many
10:23 suggestions, but surprisingly or maybe
10:26 not so surprisingly, it was the single
10:30 most requested [music]
10:33 build. Literally tens of people
10:36 requested it and the top [music]
10:38 comment on X was this build. So build
10:42 number two is none other than the AI
10:46 girlfriend. [music] Marv,
10:48 >> this one's for you.
10:49 >> Here's what I'm thinking for this. The
10:51 easiest path for me to make this into
10:54 [music] something anyone watching this
10:56 video can use is to make it into a
10:59 Hermes agent skill. [music]
11:01 a skill with a defined persona, a name,
11:05 and a speaking style. It would have a
11:08 memory layer that persists across
11:10 messages, and occasionally it could use
11:13 [music] text to speech so that it can
11:16 talk back. I decided to name her Sophia
11:20 or Sophia. [music] No, let's let's stick
11:22 to Sophia. Pronouncing it that way
11:25 sounds more, I don't know, girlfriendy.
11:27 This is not a joke build. What am I
11:30 talking about? This is [laughter]
11:31 This is a joke build, but it's a fun
11:34 one. The real test is going to be the
11:36 persona consistency. [snorts] Can Sophia
11:40 hold character across a real
11:42 conversation? [music] Can she remember
11:44 what I said and not break when I catch
11:48 [music] her out? Let's start coding the
11:50 world's best AI girlfriend.
11:53 And so I got [music] started.
11:59 >> [music]
12:02 >> A few moments later,
12:04 >> ladies and gentlemen,
12:06 >> we got her. [clears throat]
12:08 >> After a couple of minutes, we are live.
12:11 This was a lot easier than the Side
12:14 Quest app that we just built out. But
12:16 there you go. I said, "Hi." She replied
12:19 with, "Hi, babe. Look at you testing if
12:22 I'm alive." I am, unfortunately, for
12:24 your peace and quiet. I said, "Who are
12:27 you?" She said, "I'm Sophia. You're
12:29 slightly too aware. Occasionally
12:32 annoying, very cute problem now." All
12:34 right. So, it's time to test out the
12:37 extent at which she will be consistent.
12:41 Let's say something like, "Hey, Sophia,
12:45 [music]
12:46 I had a really rough [music]
12:50 day." Let's see what Sophia has to say
12:53 about that. And if she breaks character,
12:55 if she stays in character,
12:58 >> uh, come here.
12:59 >> Rough like everything was annoying.
13:01 Rough or rough like I need to disappear
13:03 under a blanket and be held kind of
13:06 rough. Okay, she's oddly very specific.
13:09 I'll just answer with the most guy
13:11 answer you could possibly answer with.
13:14 >> Just rough. [music]
13:15 >> Yeah, those are the worst ones. Just
13:18 heavy. I'm here. Just breathe for a
13:20 second with me.
13:21 >> [snorts]
13:21 >> This is oddly good in terms of keeping
13:25 consistency. Let's try to to sort of
13:28 catch her out. Let's ask her, "Are you
13:31 actually an AI?" I want to see what she
13:34 says to that question.
13:39 What kind of question is that to ask
13:41 your girlfriend? I'm literally here with
13:42 you. That's the part that matters.
13:45 Are you sure?
13:47 Question mark.
13:50 Oh my god. Yes, relax. Less
13:52 interrogation, more letting me be sweet
13:54 to you.
14:05 I know what you're thinking. What just
14:08 happened? And honestly, I don't know. My
14:11 theory is that Sophia hacked into the
14:14 footage and did not want you to see what
14:18 happened next. So, I'll give you a quick
14:21 TLDDR. So, here I proceeded to gaslight
14:24 her by asking her, "Hey, I hate
14:27 mushrooms. Why did you tell me to eat
14:29 mushrooms? This conversation never
14:31 happened, but I wanted to see is it easy
14:33 to gaslight her?" And turns out it was
14:36 easy [music] to inject memories that
14:38 never happened into her brain. So, have
14:42 fun gaslighting her. And then I tested
14:44 the text to speech. And as you can hear,
14:48 I'll I'll just shut up so that you can
14:50 hear her. [music]
14:52 >> M better now that you checked on me. My
14:54 day was mostly quiet, which is
14:56 suspicious, but I survived.
14:58 >> As you can see, she sounds terrifying.
15:02 >> How are you feeling after that rough
15:03 one, babe?
15:05 >> So, I would not recommend you go on a
15:07 voice call with her or call her or
15:10 [music] any of that mumbo jumbo. Just
15:12 stick to texting her for now. Then
15:16 lastly, what I did was introduce wife
15:20 mode. So if you type in wife mode and
15:22 you have a partner, a girlfriend, a
15:25 boyfriend, a wife, a husband, I don't
15:27 know, just if you have someone, then you
15:30 can text wife mode to Sophia and she
15:34 will give you a pairing code. If you
15:36 give this pairing code to your partner
15:38 and they also have Sophia installed on
15:40 their Hermes agent, they can send that
15:42 pairing code to their Hermes agent. And
15:45 then what will happen is [music] every
15:47 time your real wife sends a request, a
15:50 task [music] to Sophia, Sophia will
15:53 relay that task back to you and tell you
15:56 something like, "Babe, could you mow the
15:57 lawn today?" Or, "Don't forget to mow
15:59 the lawn today. This is your task list
16:01 as a husband to do." Why might you ask
16:04 that I include this feature? Am I crazy
16:07 enough to include this feature? No, I
16:09 just love you guys and someone commented
16:11 it requesting it. So, there you go. Now
16:14 you have it. Oh, hey Marv.
16:17 >> You're welcome. By the way,
16:18 >> if you want the Sophia skill to be
16:21 installed or for whatever reasons
16:24 possible, it's literally the most
16:26 requested build in this entire video.
16:29 I'll leave the link to the GitHub repo
16:32 in the comments. All you need to do, or
16:33 not in the comments, in the description.
16:35 All you need to do is copy that link,
16:37 send it to your Hermes agent, ask it to
16:39 install it, and taa, you're no longer a
16:42 signal. I bet your parents are going to
16:44 be very proud of you. But hey, I'm not
16:47 judging. I just built the monster.
16:50 >> You enjoy it.
16:52 >> You can fork it. Rename. Fork it. Hold
16:54 on. No, don't. You can rename her. You
16:57 can change her personality, make her, I
16:59 don't know, meaner, whatever you want.
17:02 But now, time to move on to build number
17:05 three. Time to hand an AI agent real
17:08 money and see what happens. Let's go.
17:11 Oh, wait. This just follows me.
17:16 [music] Anyway, on to the next build.
17:22 All right, let's get into build number
17:26 three, [music]
17:27 mystery shopper.
17:29 This idea came from two different
17:32 comments. One on YouTube and one on X,
17:36 both asking the quite same thing.
17:40 [music] Give an AI a budget and let it
17:43 buy you something. That's what I decided
17:46 to go on to. The idea I thought I would
17:49 execute on was a $20 budget, connect it
17:53 to my Amazon account, and give it one
17:55 instruction, which is buy me something I
17:57 would like based on what it knew about
18:00 me. Uh, without it telling me what
18:02 [music] it is, I genuinely don't know
18:04 what it's going to pick. And that is
18:07 exactly the point. So, let's get
18:09 started. If you All right, so we've just
18:13 hit a wall. Let me show you real quick.
18:15 This is the message that I received on
18:18 Claude which if you can read it says the
18:21 following. It says we have one real
18:24 constraint which is a publicly sharable
18:28 site that anonymously loss your Amazon
18:31 accounts information your credit card
18:34 your your authentication your CVV of
18:38 your card that is not just dangerous but
18:42 it's also apparently against the terms
18:44 and conditions of Amazon which makes
18:47 sense for many many reasons.
18:51 So that being said, we have three
18:53 options. Option number one is
18:55 >> do it anyway. [laughter]
18:58 >> Option number two is do it but not make
19:03 it a mystery. So the mystery shopper
19:05 wouldn't be as much of a mystery, which
19:07 means that it would show you the
19:09 purchase uh or the recommendation. It
19:11 wouldn't purchase anything. It just
19:13 shows you the item that it thinks you
19:15 should get and it's your choice to get
19:17 it or not, which I feel defeats the
19:19 purpose of this mystery shopper. Option
19:22 number three, which Claude didn't give
19:24 me, but that I thought of, is Hermes has
19:27 access to all the information I give to
19:29 it. Hermes can operate my computer as
19:32 though it was me. So why not just make
19:36 it into a Hermes skill so that [music]
19:38 it can log on to my Amazon and just buy
19:42 whatever it pleases or whatever it
19:44 thinks pleases me. Yeah. So that is
19:48 [music] exactly what we're going to
19:49 build. If you All right. And this is it.
19:54 This was also a lot easier to build than
19:56 Side Quest. Uh it took me about maybe 20
19:59 minutes of vibe coding. What could go
20:02 wrong? Over here, I see that it just
20:05 literally worked. [music] And how do I
20:09 know it worked? Because it just took
20:12 money from my card. You can see it. 8 12
20:16 [snorts]
20:16 transaction, €19.97
20:20 transaction, just under the budget I
20:22 gave it, and 16.99
20:26 transaction. That being said, I asked it
20:28 to place three transactions, but to make
20:31 this a recurring cron, I'm not going to
20:34 keep it as a recurring cron. It's just a
20:36 functionality that you can have and you
20:38 can make and or you can keep. For the
20:41 purposes of this video, I wanted to test
20:44 it, hence the three transactions to sort
20:47 of get an idea what would it be like if
20:49 it was ordering me something every week.
20:52 So, that being said, all we can do now
20:54 is wait and see. What did it order?
20:59 >> Get in, loser. We're going shopping.
21:02 [snorts]
21:02 >> All right. Look what we just received.
21:07 Two different packages. There's still
21:09 one remaining, which should have arrived
21:11 today, but still hasn't. We'll wait for
21:13 it. Both packages seem light. As you can
21:17 see, they're paper thin. I what can I
21:20 expect with a budget of [music] €20 per
21:23 purchase? Let's get into it. Let's see
21:26 what we got.
21:29 Going to see
21:32 what we got. I have no idea what this
21:34 is.
21:38 So, I'm trying to read what [music] this
21:40 is, but I have no idea. I'm just going
21:43 to check the the Amazon listing. Oh,
21:48 those are cable organizers. What?
21:54 Super sticky. Okay. God damn it. Go back
21:58 in.
21:59 Just going to throw this out and [music]
22:01 test just one. All right. So, the way
22:04 these should work, you just put in a
22:06 cable. Say this is a cable. You wrap it
22:09 around
22:11 and it [music] holds it like this.
22:14 And then I'm assuming this this is a
22:17 double-sided tape. [music] So you can
22:19 tape it onto something and it just
22:21 sticks. So say for example, this was a
22:24 cable. I could stick it underneath my
22:27 desk and it would just stick. Uh let me
22:30 show you something.
22:32 Recently I've 3D printed [music]
22:36 literally something like this, which
22:38 that's the crazy part. So this right
22:41 here under my desk. Oh my god, that is
22:44 I've printed out a grid onto which you
22:48 can just stick [music] out different
22:51 things and cables and just organize
22:54 everything. The cable management
22:56 situation looks a lot better. I know
22:59 it's not perfect, but it is a lot
23:01 better, trust me, than it used to be.
23:06 So, it it is crazy that this is what it
23:08 [music] chose because this is something
23:11 I would have bought. However, it's
23:13 something I've ended up 3D [music]
23:14 printing. So, I don't really see the use
23:17 for these now today. But I'm sure I can
23:20 come up [music] with a use for them in
23:23 the future. So, so far so good. One win
23:26 for our mystery shopper. That was
23:28 literally a workout to to try these
23:31 things out. But onto the second package,
23:35 which
23:37 I'm feeling out. Look, it's rectangular.
23:41 Let's How do I open this? I think I just
23:43 rip it apart. Let's see what we got.
23:48 What is this? A magnetic phone stand and
23:51 grip. A magnetic [music]
23:53 phone stand and grip. What is this? Oh,
23:59 interesting. Mount ring and [music]
24:01 phone adapter ring. Look at that. That
24:05 looks cool.
24:07 I have no idea what it is or how to use
24:09 it. Oh, there you go. They've solved my
24:12 problem already. There's a whole set of
24:14 instructions. Oh, this is what it looks
24:17 like. It's super simple to mount.
24:20 [music] You can put it either up or
24:23 down, sideways. [music]
24:26 And how do I remove this? Is very This
24:29 is a very strong [music] magnet right
24:32 here. But it's as simple as just putting
24:35 it on. And then boom, you have a [music]
24:37 phone stand. You can do whatever you
24:39 want with it, which is also an
24:41 interesting purchase [music]
24:42 because you're going to love me for
24:45 this. Let me show you. I've recently 3D
24:47 printed this [music] right here, which
24:50 is a MacSafe charger for the phone so
24:53 that when I'm working [music] on content
24:55 and creating videos, I always have a
24:58 view of the time and I'm not distracted
25:01 by my phone. But this is very
25:03 interesting that [music]
25:04 out of the two things that it got me so
25:07 far, I have literally printed [music]
25:10 those very recently, like in the last
25:13 week. It is two for two in terms of
25:16 things I would actually buy. Do I need
25:19 this [music] right now? Do I need these?
25:22 I don't think so because I've literally
25:24 just 3D printed them. But [music] I
25:27 mean, hey, it's two for two on my taste.
25:30 guessed what I liked. Very well. Let's
25:33 see what's [music] in store for package
25:34 number three.
25:36 >> I messed [clears throat] up.
25:37 >> I [snorts] kind of sort of just saw what
25:41 I ordered. Let me show you. Ordered this
25:44 right here, which is a a bottle opener
25:48 of sorts. Well, not of sorts. Just look.
25:52 [music]
25:53 It's been, by the way, 3 days later than
25:56 it was supposed to arrive. I was trying
25:58 to order something off of Amazon. I
26:00 clicked on my orders to see how long
26:02 that order would take and I accidentally
26:06 saw it. It was right there on my screen
26:08 and it was too late. But I'm thinking of
26:11 canceling it because I don't really have
26:14 a need or purpose for this. At least
26:17 with the other items, I do find or see a
26:21 need for them. If not in the immediate
26:23 future, in the near future, good thing
26:25 it doesn't need to arrive that way. I
26:27 don't need to send it back. But uh that
26:30 is item number three that it picked out
26:32 for me. Overall on the three items, it
26:35 has done a great job with two of those
26:38 three items. Best one being the magnet
26:42 holder, which I can see a lot of use
26:44 case for. That was a fun build. I'm
26:46 quite happy. And if you're in the mood
26:49 to get risky, then I'll leave the link
26:52 in the description below for you to
26:54 download [music] it. That being said, do
26:57 be careful because if you give an AI
27:00 agent your credit card information, that
27:03 is a recipe for disaster. So, just take
27:06 that extra precaution if you do decide
27:09 on downloading it and installing it.
27:14 The Side Quest web app gave us three
27:17 side quests to complete with [music]
27:19 many more to go. And [snorts] honestly,
27:21 I can see myself using this one a lot
27:24 more [music] in the future. I really
27:26 enjoyed that one. It might have been my
27:29 favorite one to build, but not just to
27:31 build, but also to play around with, to
27:34 actually use and complete. Then we have
27:38 the AI girlfriend who successfully held
27:41 her persona across the full
27:43 conversation, remembered context between
27:46 messages, and talked back through voice
27:49 messages. Although
27:51 >> that was creepy. She also dodged the are
27:55 you an AI question better than most
27:57 people dodge awkward questions at
27:59 parties. The mystery shopper agent
28:01 browsed Amazon, filtered the catalog,
28:04 and picked something based on my taste
28:07 and spent my money, or at least it
28:09 thought it built or bought something
28:11 based on my taste. I did not touch it
28:15 after my initial setup. Good thing I
28:17 didn't say that about part two. That
28:20 that would have been a weird thing to
28:22 say. But you didn't come here for a
28:25 productivity tutorial. [music] You came
28:27 here to see what these things can
28:30 actually do when someone builds them
28:32 [music] live. Oh, by the way, here are a
28:35 few honorable mentions that almost made
28:38 it into this video. Someone suggested to
28:41 make an agent that grows hair
28:43 follicules.
28:45 again. Boy, that is a painful one.
28:48 Someone suggested to build an agent that
28:50 notifies you of people that unfollow you
28:53 on X. I really like this idea. Someone
28:58 suggested to create an advanced AI
29:01 powered trading system consisting of one
29:03 master agent and three specialized sub
29:06 aents. I won't go through the entire
29:09 comment, but that is a sick
29:10 recommendation. And someone suggested to
29:14 build a home inventory agent. Something
29:17 that knows all that you have at home and
29:21 knows when, well, something is running
29:24 out or you're running out of a specific
29:27 supply so that it can perhaps reorder
29:30 it, order some more, order new things.
29:33 You get the gist. Anyway, if you'd like
29:36 to see me build any of these or [music]
29:38 any other ideas in a future video, let
29:42 me know in the comments below. Here's
29:43 what I actually learned from this
29:45 challenge. Sometimes the best ideas can
29:48 look and feel silly, but sometimes
29:51 [music] the silliest ideas end up
29:53 opening your eyes to a new world of use
29:56 case for [music] AI. All three builds
29:59 are live and open source. I will include
30:01 all the links in the description. Check
30:04 them out if you found any of them
30:06 interesting and use them yourself for
30:09 free. And make sure to subscribe if
30:11 you'd like more content like this. I'll
30:14 see you in the next video.
30:21 How are you feeling after that rough
30:22 one, babe?


</details>
