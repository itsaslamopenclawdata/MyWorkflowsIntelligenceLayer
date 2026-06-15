---
title: "Free clones: Notion, Lovable, Notebook LM + top 10 repos"
channel: "The Next New Thing AI"
channel_slug: "the-next-new-thing-ai"
channel_id: "UCNZEktrsM5oJZ-MK4jKPMOQ"
published: "2026-06-12"
duration_seconds: 1945
video_id: "2WNl5VidRS8"
url: "https://www.youtube.com/watch?v=2WNl5VidRS8"
language: "en"
tags: [repos, open-source, last-30-days, headroom, open-notebook, taria, taste-skill, markitdown, agent-reach, openai-plugins, pm-skills]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-15"
---

# Free clones: Notion, Lovable, Notebook LM + top 10 repos

**Channel:** The Next New Thing AI  **Published:** 2026-06-12  **Duration:** 32:25  **Watch:** https://www.youtube.com/watch?v=2WNl5VidRS8

## TL;DR
Weekly top-10 GitHub repos roundup covering research skills, token-compression tools, open-source NotebookLM alternatives, an obsidian-replacement markdown app, a Riley Brown-style lovable clone, project-management skills, OpenAI's Codeex plugins, agent-reach CLI, NVIDIA Cosmos world models, taste-design skills, Apple Container, and Microsoft's markitdown. The throughline: Fable 5 is making solo devs ship Lovable/Notion clones in 2 prompts; the open-source alternatives are getting good enough that the "must pay for" tier is shrinking. Repo of the week: **last-30-days** by Matt Van Horn — a research skill that pulls the last 30 days of context from X/Reddit/YouTube/web and writes a deliverable.

## Key Insights
- **Repo of the week: last-30-days (Matt Van Horn).** A research skill that pulls the most recent 30 days of context on a topic from X, Reddit, YouTube, and the web, then writes a deliverable. The "use your browser cookies" technique is what bypasses API-key walls. Often the user doesn't even read the report — they just want the email/cold-pitch it then produces. (timestamp 00:38)
- **Headroom — token compression for agent workloads.** JSON smart-crushers (DDUP, structural compression) deduplicate repeated fields; code compression strips syntax overhead. Authors' own benchmarks show modest gains generally but significant gains on specific tasks (debugging, structured output). Token-overhead reduction is the wedge. (timestamp 03:54)
- **Open Notebook — open-source NotebookLM replacement.** Generates podcasts from your sources, configurable structure, multiple speaker profiles (not just Google's locked 2-host NPR style). Can run on local models. Pitches itself on privacy and model flexibility. (timestamp 06:10)
- **Taria — the markdown note app the host says is better than Obsidian for most people.** Open-source, free, file-system-based (so Claude Co-work or any agent can edit files directly and the app auto-updates). Looks like Notion. Specifically positioned for AI integration: "the files are on your system, the agent doesn't need to use the app to edit them." (timestamp 10:39)
- **The Lovable clone built in 2 prompts with Claude Fable 5 (Riley Brown).** Showed the actual chat thread: prompt 1, run on simulator 2, screenshot all the screens, "redesign to look exactly like this." Built a working Lovable-style mobile app from screenshots alone. Then asked Fable to build a Notion clone from the same conversation. GitHub repo has 67 stars; "don't replace Lovable with it, but it's riable." (timestamp 12:59)
- **PM Skills — 68 skills, 42 chained workflows, 9 plugins.** Big prompt library for project managers. The interesting bit: an "interview me about my project" mode that drills questions until it can build a plan. Treat as a "steal from this" repo, not a wholesale adoption. (timestamp 14:57)
- **OpenAI Codeex Plugins — official-ish OpenAI distribution.** Plugins for Notion, Airtable, Gmail, Google Calendar, and research APIs. Semi-official (or fully official). Lets you say "implement this Jira ticket and update the comments" within a Codeex workflow. (timestamp 16:51)
- **agent-reach — CLI for agent-driven research across 17 platforms.** Twitter/X, Reddit, YouTube, GitHub, plus some Chinese social networks (Bilibili et al). Surgical tool: "look on X for X" or "research this person on LinkedIn" without producing the 30-day synthesized deliverable. (timestamp 19:14)
- **NVIDIA Cosmos — open platform for world models, physical AI datasets, robotics.** Omni-model: handles text, movement, images, all input types. Robotics, autonomous vehicles, smart infrastructure. Not applicable to most people but substantive for the physical-AI space. (timestamp 21:32)
- **Phantom Stars — fake-engagement detector.** A tool that flags repos where engagement looks suspicious (users with no other activity mass-liking). The "buying stars" market is real: hosts cite "$1,000 for 1,000 repo stars" as the going rate. Worth being aware of when evaluating any "trending repo" list. (timestamp 22:55)
- **Taste Skill — design differentiation for the AI-slop era.** Targets the "everyone's design looks the same" problem (especially anything from Claude). The skill ships preset design personalities (brutalist, minimalist, soft) with their own color/font systems. Peter pushes back: "you're trading one set of cliches for another." Verdict: use as inspiration, fork the skill files, change the fonts/colors, ship your own variant. (timestamp 24:31)
- **Apple Container — Linux VMs on Apple silicon.** Announced at WWDC. The integration story matters: bidirectional filesystem sync between macOS and the VM. The WSL-equivalent dream (run Linux GUI apps from your Mac desktop) is the long-term goal. (timestamp 27:11)
- **Mark It Down (Microsoft) — 110,000+ stars, free.** Converts PDFs, Word docs, Excel, PowerPoint, images, audio, YouTube videos to clean markdown. PDF pages cost 1,500-3,000 tokens to load raw; markitdown cuts that by up to 70%. Comes with an MCP server that auto-converts uploads. (timestamp 29:32)
- **The Fable 5 subtext of the whole show:** "If you wanted a software that just comes out of the tap, this is it." The host's framing: every demo this week ended with "shipped in 2 prompts" or "cloned in a weekend." The bar for "I need a dev team" keeps dropping.
- **Cookie-sharing security caveat (per host):** "You might want to be careful with… use the things you've already got that you're logged in with, and then these tools synthesize all that information it finds." Shared cookies = shared identity. Use a separate browser profile for high-value sessions. (timestamp 01:53)

## Notable Quotes
> "You can go in and say, 'Well, actually, I want to make my own style inspired by all of this.' Copy and paste it, change the fonts around, change the colors around, and bam, you've got your own little design system come out of it." — 26:12
>
> "Use the things you've already got that you're logged in with, and then these tools synthesize all that information it finds into a deliverable." — 01:53
>
> "It's got 67 stars. I don't necessarily recommend that you replace lovable with this. Like, get it. It's riable. Riley's lovable, but it gives you a sense of what can be done with Fable." — 14:17
>
> "Every PDF page can consume between 1,500 to 3,000 tokens. So 20page document burns through up to 70,000 tokens in one shot. And this is before you even ask your first question." — 30:17
>
> "I'll star your repo for $1,000. So, you know, if anyone wants that help, you know." — 24:22

## Tools and Resources Mentioned
- **last-30-days** (Matt Van Horn) — research skill. Repo of the week.
- **Headroom** — token compression for agent workloads. JSON DDUP, structural compression, code compression.
- **Open Notebook** — open-source NotebookLM alternative with multi-speaker podcast generation.
- **Taria** — markdown note app, Obsidian alternative with native AI integration. Files live on disk; agents can edit them directly.
- **PM Skills** — 68 skills + 42 chained workflows + 9 plugins. Project management interview/prompt library.
- **OpenAI Codeex Plugins** — official/semi-official distribution for Notion, Airtable, Gmail, GCal, research APIs.
- **agent-reach** — CLI for reading X, Reddit, YouTube, GitHub, Bilibili, etc. Granular research tool.
- **NVIDIA Cosmos** — open world-model platform for physical AI / robotics.
- **Phantom Stars** — fake-engagement detector.
- **Taste Skill** — design differentiation for AI-generated output. Brutalist / minimalist / soft design presets.
- **Apple Container** — Linux VMs on Apple silicon with filesystem sync.
- **Mark It Down** (Microsoft) — universal file-to-markdown converter. MCP server included. 110K+ stars.
- **Riley Brown's Lovable clone (Claude Fable 5 demo)** — github repo referenced; 67 stars; "riable" per the host.
- **Zapier MCP** — sponsor. https://zapier.com/mcp
- **Justine Moore (A16Z partner)** — surfaced the Tian archetype skill the host demos. Worth following for AI-tool investment signals.

## GitHub Repos and URLs Referenced
- **last-30-days** (Matt Van Horn) — full link in video description.
- **Headroom** — full link in video description.
- **Open Notebook** — full link in video description.
- **Taria** — full link in video description. Founder "Luca" mentioned.
- **Riley Brown's lovable-clone repo** — github.com (search "Riley Brown lovable clone Fable"). 67 stars at time of recording.
- **PM Skills** — full link in video description.
- **OpenAI Codeex Plugins** — full link in video description.
- **agent-reach** — full link in video description.
- **NVIDIA Cosmos** — developer.nvidia.com/cosmos (general; specific repo not given).
- **Phantom Stars** — full link in video description.
- **Taste Skill** — full link in video description.
- **Apple Container** — announced at WWDC; check Apple's developer site for the OSS repo.
- **Mark It Down (Microsoft)** — github.com/microsoft/markitdown. 110K+ stars.
- **Zapier MCP** — zapier.com/mcp (sponsor).

## Action Items
- [ ] **Install last-30-days and run it once on a topic you actually need a brief on.** Matt Van Horn's pattern is to use the output as a writing prompt, not the deliverable — give it a topic, get the synthesized context, then write your cold email or post from there.
- [ ] **Test Headroom on your agent's structured-output workloads.** If you're burning tokens on JSON-heavy tool calls, the DDUP+structural compression may pay for itself.
- [ ] **Try Open Notebook if you've been frustrated with NotebookLM's locked 2-host format.** Run it locally with a smaller model; multi-speaker profiles are the wedge.
- [ ] **Migrate 10% of your markdown notes to Taria** for a side-by-side with Obsidian. If the AI-integration story (file-system-as-API) holds, it changes the design constraint.
- [ ] **If you're using Claude Co-work or Cursor for design work:** ship the Taste Skill on a landing page and A/B against your current design. Fork the skill, change the fonts/colors, make it yours.
- [ ] **Wire markitdown into your file-upload pipeline** if you feed PDFs to Claude regularly. The 70% token reduction is a meaningful cost save at scale.
- [ ] **For Apple-silicon dev work:** watch Apple's Container rollout. Bidirectional filesystem sync alone is meaningful; WSL-equivalent GUI pass-through would be a major unlock.
- [ ] **Audit any "trending repo" list for bought stars.** Phantom Stars flags the pattern; the "$1,000 for 1,000 stars" market is real. Diversify signal sources.
- [ ] **Use the cookie-sharing tools (last-30-days, agent-cookie, agent-reach) in a separate browser profile** so a compromised tool doesn't have access to your primary sessions.

## Open Questions
- **The "$1,000 for 1,000 stars" market** — is it really that cheap, and what does that mean for evaluating "trending" repos across the whole ecosystem? Worth a follow-up investigation.
- **Open Notebook's local-model podcast quality** vs. NotebookLM — the host claims it works, but the audio quality on local models is usually a step down. Real-world test needed.
- **Taria's data model under multi-agent editing:** if two agents write to the same Taria vault simultaneously, what's the conflict-resolution story? (Files-on-disk suggests git-like merge conflicts, not real-time collab.)
- **Apple Container's timeline for GUI-app pass-through.** The host speculates; Apple hasn't committed. If it ships, this changes the macOS-Linux dev workflow.
- **Riley Brown's lovable clone — "riable" but is it maintainable?** 2-prompt prototypes are great for demos. Production hardening is a different question.
- **The host's "everyone's design looks the same" critique of Claude products:** valid, but does the Taste Skill actually fix it, or does it just move the cliche to a different font/color combo? (Peter's pushback suggests the latter.)

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 32:25 transcript)</summary>

0:00 You know how everyone's got all these
0:01 markdown files and you can't keep them
0:02 in Notion. You don't know where to put
0:03 them. Obsidian gets too complicated.
0:05 I've got a beautiful free solution that
0:07 will work for your LLM and that you will
0:08 enjoy using too. Again, free. Everyone
0:09 else's website is starting to look like
0:11 slop. I've got something that will add
0:12 taste to your site. And finally, what
0:14 about when you have your agent try to
0:15 look up information on the internet and
0:16 gets blocked blocked? I've got two free
0:17 solutions that will unblock it and pull
0:18 the most important data to you. That and
0:20 so much more coming up. presented by
0:21 Zapier, the AI automation company.
0:23 >> Peter, the audience loved you last week.
0:25 It was the number one GitHub repo show
0:26 that I ever did. So, I'm glad that
0:27 you're back. Thank you.
0:29 >> Let's get into the first repo of the
0:30 week, which is last 30 days. Skill, I've
0:31 been really eager to talk about this.
0:33 Here's what this is about. You and I
0:34 know that when we're doing research,
0:35 especially for stuff that I'm doing over
0:36 here, the most relevant information is
0:37 on sites that are hard to access like X,
0:39 which will keep blocking my bots. And
0:40 it's not just on these sites. It's also
0:41 within the last 30 days. Don't give me a
0:42 tweet that happened six six years ago or
0:43 even frankly uh six months ago. It's not
0:44 relevant anymore. What he did, Matt, was
0:45 he created a skill set right here that
0:46 makes it easy to go and pull that data.
0:48 And that's why people are loving it.
0:50 I've actually, I think, plugged it in
0:51 the f in the past, but it never really
0:53 made it into the top 10. It is now
0:54 number one the most popular repo of the
0:55 week. What do you think of this? I mean,
0:57 do you want your own little kind of like
0:58 mini Gartner industry analyst on your
0:60 side? This is that kind of skill. Uh,
0:61 you know, it's going to go around and
0:62 pull stuff from all sorts of places. And
0:63 >> Mhm.
0:64 >> you might be like, "Hang on, how's it
0:65 going to grab stuff from X when I
0:67 haven't got an API key? I'm not paying
0:68 for the access." Uh, and that's because
0:69 hidden within this repo, there's lots of
0:70 little tools for accessing things like X
0:71 and YouTube and stuff like that. And it
0:73 uses your own browser's cookies. So, it
0:74 kind of acts as if it's you,
0:75 >> which you know is something you might
0:76 want to be careful with. Um, but, uh,
0:78 yeah, if it works, it works. And it is
0:79 it is a common technique to get around
0:80 the platforms locking you down. Use the
0:81 things you've already got that you're
0:82 logged in with, and then these tools
0:83 synthesize all that information it finds
0:84 into a deliverable that then you can
0:85 read and enjoy and use however you like.
0:86 I'm pretty sure though they did ask me
0:87 for my YouTube uh, API key and maybe
0:88 even my X. I think it's doing it's doing
0:89 both. I thought I could be wrong, but
0:90 you're saying the heart of this is it's
0:92 not supposed to, right?
0:93 >> It's not supposed to, but you can bring
0:95 your own keys into this app. So, if
0:96 you've got keys, then it will use them.
0:97 Um, but I believe it has fallbacks so
0:99 that it will use, you know, it will try
1:00 and slurp things out of your browser if
1:01 you are logged into those sites.
1:03 >> Okay. I I like this um video here that
1:05 shows Matt actually using it. Let's do
1:06 >> this is one
1:08 that I did right before we started. So I
1:09 said last 30 days highest performing
1:10 cold email frameworks for ICP out output
1:12 three email variant subject line.
1:15 So it went on X went on Twitter found
1:16 Reddit threads expost web pages and what
1:18 what's interesting how I use this tool
1:19 is I often don't even read what it says.
1:21 Like sure it's interesting to see what
1:22 it learned but mostly I just wanted to
1:23 write a good email. So I said, "Can you
1:24 write me some cold emails for getting on
1:25 Greg Eisenberg's podcast?" Uh, sorry I
1:26 spelled your name wrong. Good target.
1:27 Startup ideas later. It's all about
1:28 unconventional startup ideas, community
1:29 building unique relevance. Know what's
1:30 your angle? What's your credibility
1:31 signal? Any connection points to Greg?
1:32 Mutual follows. What timely? Uh, talk
1:33 about AI tools I'm working on and I once
1:34 made a smart oven. Uh,
1:35 >> okay. And then what he's using is he's
1:36 looking it up, seeing what's hot right
1:37 now and what's effective for cold email.
1:38 And then he's having his AI write it for
1:39 him. Good use case. He's got a few
1:40 others. And of course, we've got the
1:42 report here with the full video for
1:43 people who want to go see it. I love
1:44 that. Next, number two is Headroom. This
1:45 has been especially popular this week.
1:47 How would you explain what this does?
1:48 >> So, we had this one last week, but it is
1:49 back. Um, and the whole way that it
1:51 works is that it uses various forms of
1:52 analysis of basically big things that
1:53 are going over the wire. So things like
1:54 log files and JSON files and things like
1:55 that. It kind of has these techniques to
1:57 boil them down into kind of like minimal
1:58 representations of what the agent
1:59 actually requires to do its job. Um, and
1:60 then that supposedly will significantly
1:62 reduce the number of tokens going over
1:64 the wire. And there is some uh you know
1:65 the truth to this technique. Some of
1:66 their own benchmarks showed minor gains,
1:68 but then I believe you have some
1:69 benchmarks from them that show
1:70 significantly bigger gains uh when
1:72 performing specific tasks like debugging
1:73 and so on and so forth.
1:74 >> Yeah, it's and I think it's because of
1:75 Fable. Everyone is now seeing that Fable
1:76 Fable is
1:77 really powerful, but at the
1:78 same time it just burns through tokens.
1:80 >> A lot of people have burned through
1:81 tokens within a day um all of their a
1:82 lotments. And so this is becoming
1:83 especially hot. Um there is an old post
1:84 here that I'll include in the show notes
1:86 for people that that just shows that
1:87 um actually
1:88 >> I I asked you did you understand what he
1:89 said and you said oh yeah um what what
1:90 is he saying here? He's evaluating lots
1:91 of different tools like this. So this is
1:92 a list of various different tools and
1:94 technologies being used to basically as
1:95 I said take things like JSON. So where
1:97 it says there smart crusher for JSON
1:98 DDUP and structural compression it's
2:00 because things like JSON files uh and
2:01 JSON documents contain often lots of
2:02 things that repeat over and over and
2:03 over. So if you can strip all of that
2:04 out dduplicate it that's what ddup
2:05 means. Uh then you can sign
2:06 significantly make it smaller and then
2:08 smaller equals you know fewer tokens.
2:10 Uh, and it's the same thing with code as
2:12 well. So where it says they're aware
2:14 code compression, that's basically
2:14 taking the structure of the syntax of
2:16 code and then boiling it down to just is
2:17 bare essentials so that you can make the
2:19 code smaller. Again, fewer tokens over
2:20 the wire.
2:21 >> Okay. All right.
2:22 >> Let's go on to the next one. I really
2:24 like this one. I love Notebook LM
2:25 because this is Google's project where I
2:27 can really learn things the way that I
2:28 like to learn things. My way of using it
2:30 is I will put a big document into it and
2:32 then I end up with a chatty podcast
2:34 where two people who sound like NPR
2:35 hosts are talking about and teaching me
2:36 the topic. The problem that I have with
2:37 it is those two people get very boring
2:39 because you still hear the same two
2:40 people in the same approach over and
2:41 over again. And um I think that there
2:42 are other features I would want and I'd
2:43 want to pull it away from Google's
2:44 framework because I think they're
2:45 smarter models that I'd at least like
2:46 to experiment with. And so what they did
2:47 here was, and here it is. It's open
2:48 notebook. They basically said, "Let's
2:49 reproduce what notebook is doing, but
2:50 give people a lot more flexibility. I've
2:51 got a really good video here that I I'd
2:52 like to play a little bit of, and I know
2:53 people have told me to told you, I
2:54 guess, or told me that we we should not
2:55 be talking over so much, but I'll let it
2:56 play a little bit, and when I get
2:57 annoyed, I'll stop." First, the podcast
2:58 generator. Notebook. LM made AI podcasts
2:60 feel actually pretty cool. If you
2:61 haven't played with it, maybe you
2:62 should. If I run it here, well,
2:63 something else happens. Take a listen.
2:64 >> It's a game changer for researchers
2:65 looking for autonomy and privacy.
2:67 Absolutely, Alex. I think one of the
2:68 coolest aspects of a llama.
2:70 >> Cool, right? But Open Notebook gives you
2:71 more control over that format. You can
2:73 generate podcasts from your sources,
2:75 configure the structure, and use
2:76 multiple speaker profiles instead of
2:77 being stuck with one fixed style.
2:79 multiple speaker profiles is is where
2:80 they got me. Maybe not even have two
2:82 different personalities every time, but
2:83 even have a third person. Anyway, it's
2:84 great. We have a full link here uh for
2:85 everybody who wants to go check it out.
2:87 Any thoughts on this?
2:88 >> I think the biggest win here is privacy.
2:90 So, when you're using Google,
2:91 everything's, you know, going up to
2:92 their servers or whatever, but this
2:93 really pitches itself as being something
2:94 that you can run locally on local
2:95 models. Now, you might think, oh, it's
2:96 gonna not sound very good or not perform
2:97 very well because obviously running
2:98 local models is very intensive and a lot
2:00 of people's machines just can't run
3:01 them. Uh, but as we saw, that's getting
3:02 better. Uh, and last week we had, I
3:03 think, something called Vox TTS, which,
3:04 you know, we tried out and produces
3:05 absolutely amazing voices in such a
3:06 small amount of space. Um, that
3:07 actually, you know, you could produce
3:08 voices that are entirely prompted. You
3:09 could say, "Oh, I want it to be someone
3:10 with a particular accent or, you know, I
3:11 want it to be,
3:12 >> you know, you just describe who it is
3:13 you want it to sound like." Uh, you
3:14 can't do that with Google. You can do
3:15 that with local models. So, it is worth
3:16 a try. Um, you know, but it is going
3:17 to be worth setting it all up. So, don't
3:18 think it's just as simple as Notebook
3:19 LM. You know, you've got you've got
3:20 things to set up here.
3:21 >> Um, that team, by the way, reached out
3:22 to me and I love that they did. I'm
3:24 hoping I get to talk to them. I've got
3:25 another video here for you to take a
3:26 look at when when we're done, folks.
3:27 And now comes up my comes my sponsor
3:28 Zapier MCP. If you are here, you are
3:29 probably messing around with lots of
3:30 different uh tools, lots of different
3:31 LLMs, lots of different computers even.
3:32 In fact, I was complaining to Peter
3:33 quite a bit listening as he said hello
3:34 to me with how many things get lost.
3:35 Skills are in this computer. Anyway, the
3:36 beauty of Zapier MCP is you get all of
3:37 your connections to all your tools that
3:38 you love in one place. It is so easy to
3:39 use. I really urge you to go and try it
3:40 out. It's free right now to use it and
3:41 you can experience what it's like to
3:42 connect all your tools and give it the
3:43 the parameters that you want. So maybe
3:43 they don't have right access, maybe
3:44 they have read access, maybe they have
3:45 draft access, etc. And now you have a
3:46 URL, a simple tool that you can give to
3:47 every uh every other um product that
3:48 you work with. Go get it. Go check it
3:49 out. And thanks to Zapier, we're al
3:50 also going to get to do these repos
3:51 worth checking in between here, the
3:52 top 10. And the first one came from
3:53 you, Peter. What is this one?
3:54 >> So, I first saw this in an ex post by
3:55 Justine Moore, who is a partner um at
3:56 A16Z,
3:57 >> and she was very
3:58 impressed with what
3:59 came out of this. There, this is the uh
3:60 the tweet here. So, what you do is
3:61 direct this skill um it's a codeex one
3:62 at the moment because it uses Codeex's
3:63 built-in image generation tools. What
3:64 you do is you point this to like an
3:65 article and preferably one that you've
3:66 written yourself. Uh, and it will go
3:67 through and yes, this all written in
3:67 Chinese. I did translate it into English
3:68 to see what it was about, and it's all
3:69 pretty straightforward, but you point at
3:70 your content. It works out some
3:71 metaphors for the different things that
3:72 you're trying to communicate in that
3:73 content. Uh, and then turns it into
3:74 these kind of cool illustrations with
3:75 this um, black kind of like blob
3:76 character that you can see. Um, and it
3:77 adds annotations. And by default, it I
3:78 think it does actually do it in Chinese,
3:79 but you can just tell it do it in
3:80 English and it will do it in English.
3:81 And uh I've played with this quite a bit
3:82 and I've actually been really impressed
3:83 with the kind of the metaphors that come
3:84 out of it. It's you know quite
3:85 impressive and it's using uh the GBT
3:86 image 2 model for generating the images
3:87 behind the scenes because that's what
3:88 Codeex uses. I really like that you
3:89 found this. I mean honestly for me I
3:90 love that we're doing the top 10 because
3:91 it says something. But I also actually
3:92 not also I prefer these great finds that
3:93 people wouldn't discover otherwise. Like
3:94 this one. This is called Taria. And this
3:95 is another one that you found. Oh, this
3:96 is so beautiful. I'm so glad you turned
3:97 me on to this. People are going to love
3:98 it. Uh, what's the problem this is
3:99 solving? And then what is it looking
3:00 what does it look like?
4:01 >> So, lots of people now, um, me included,
4:02 have lots of markdown notes. Uh, you
4:03 might want to categorize them and just
4:04 keep them around, you know, on your
4:05 system, be able to search them and be
4:06 able to, you know, look at things and do
4:08 a whole wizzywig markdown editing thing.
4:09 This does all of that. So, there's lots
4:10 of other tools of this kind of nature
4:11 out there, but this one is open source
4:12 and it's free and it's particularly
4:14 focused on AI integration if you want
4:15 it. I mean, you don't have to use AI
4:16 with this whatsoever, but you can uh
4:17 because all of the files that it uses
4:18 are literally stored on your file
4:19 system. So, you could have something
4:20 like, you know, co-work just produce
4:21 files and edit the files and it doesn't
4:22 even have to use the app. Like, it can
4:23 just edit the files on the file system
4:24 and then they automatically update in
4:25 real time within this uh you know, note
4:26 management app. So very cool. I gave it
4:27 a run um and really liked it, but uh you
4:28 know, it's a case of migrating over to
4:29 these things. I've already got my own
4:30 system, but I would very you much like
4:31 to try and get that done. I've seen so
4:32 many people look for tools that will
4:33 help them keep all their markdown files
4:35 organized. Obsidian is the one that's
4:36 talked about the most, but for most
4:37 people, Obsidian is too much and it's
4:38 it's just not engaging. Meanwhile, look
4:40 at this. Pretty looks simple. Looks a
4:41 lot like Notion to me. In fact, I don't
4:42 know why, but they also
4:43 have at the top right here under
4:44 properties Notion ID. So, I'm guessing
4:46 they're pulling documents out of Notion,
4:47 too. There. Um, but it is such a good
4:48 find. I love that you got that. Oh,
4:49 there's Luca, the founder. Um,
4:50 >> there he is.
4:51 >> Final one came from me. I'm really
4:53 excited about this one because as soon
4:54 as I saw this, Riley Brown pushed this
4:55 video on X, which just
4:56 went insane. Guys, Claude Fable or
4:57 Mythos is absolutely insane. On the left
4:58 here, we have the actual level lovable
4:59 mobile app. And here we have a lovable
4:60 mobile app that I built in two prompts
4:61 with Claude Fable 5. This is the chat
4:63 thread. Here's prompt one. And then I
4:65 just said run it on simulator 2 and then
4:66 go. So that just counts as one prompt.
4:67 And then it did some stuff. Did some
4:68 stuff. And then I just screenshotted all
4:69 the screens on Lovable. I just need you
4:70 to redesign it to look exactly like
4:71 this. And
4:72 >> okay, and it did it. It made it look
4:73 just like Lovable as you can see on your
4:74 screen. But the cool part is that at the
4:75 end of it, he said, "You know what? I
4:76 now want you to build me something." And
4:77 the thing he said to Lovable to build
4:78 was Notion. The thing he said to his
4:79 copycat of Lovable that Fable built is
4:80 Notion. And then it went headto-head.
4:81 And you know what he said? In some ways,
4:82 I really like mine my version better. I
4:83 guess there were some people who said,
4:84 "Is this real?" He then put it up on
4:85 GitHub and said, "Here you go, folks. Go
4:86 play with it and you see for yourself if
4:87 this if this stands up." It's got 67
4:88 stars. I don't necessarily recommend
4:89 that you replace lovable with this.
4:91 Like, get it. It's riable. Riley's
4:92 lovable, but it gives you a sense of
4:93 what can be done with Fable. And as soon
4:94 as I saw this, my eyes were open to what
4:95 I could build. I love this. What do you
4:96 think?
4:97 >> I don't have a lot to add to that
4:98 really. I mean this is clearly one
4:99 developer's passion project and you know
5:00 that's one of the reasons that people
5:01 stick with things like Lovable and Bolt
5:02 when they get them working is because
5:03 you know they know there's a massive
5:04 amount of money on the table and there's
5:05 a big team and all that type of thing
5:06 but it is great to see that just
5:07 individual developers can spin you know
5:08 spin things like this up now. It's
5:09 totally within your power if you've uh
5:10 you know got the skills to do it.
5:11 >> Don't use it to replace lovable use it
5:12 to see what you can
5:13 >> not just yet. No.
5:14 >> Okay. So now number four repo of the
5:15 week is PM skills 68 skills
5:16 and 42
5:17 chained workflows AC across nine
5:18 plugins. I was like ho hom about it and
5:19 I was a little sheepish and then you
5:20 said no there's a real value here. What
5:21 do you see that's valuable in this?
5:22 >> Again you know this is another one of
5:23 these repos that's full of different
5:24 skills and prompts. uh it is basically a
5:25 big prompt library but this is clearly
5:26 built by someone who you know has a
5:27 little bit of knowledge about project
5:28 management. I know nothing about project
5:30 management. So any guidance that I could
5:31 get is valuable. Um but it doesn't it
5:32 does have some commands in it. So you
5:33 can do things like uh get it to
5:34 interview you about your project and so
5:35 it will just keep drilling you with
5:36 questions until it can put together a a
5:37 plan um and it will do things um you
5:38 know like help you do consulting and
5:40 strategy and all those types of things.
5:41 I don't know those areas too well, so
5:42 this is useful for me. But I would say
5:43 if you do have any knowledge of those
5:44 areas, this is another one of those
5:45 repos to go through, read, and steal
5:46 from because you might not want to take
5:47 on their approach to project management
5:49 wholesale. You might want to come up
5:50 your own thing. Um, and this will give
5:51 you a good basis upon which to build
5:52 your own, you know, tooling to do those
5:53 interviews on yourself.
5:54 >> We'll say, you know, I usually like to
5:55 find YouTube videos that illustrate this
5:56 to see how other people use it. I found
5:57 one. These guys went through it and it
5:58 was terrible. And then I got in my own
5:58 head. I go,
5:59 >> I take it all back.
5:60 >> No, no, no, no, no. It wasn't the skill
5:61 that's terrible. Their video was skill
5:62 was terrible. So I go,
5:63 >> oh no, they've they've got a lot of
5:64 views, but it makes no sense what
5:65 they're saying. They're just, am I that
5:66 bad? And then I started getting in my
5:67 head about like, I've got to get better
6:00 here. I've got to prepare more. And then
6:01 I drove myself and my family crazy this
6:02 morning trying to like go through this
6:03 and not be bad and not So anyway, I've
6:04 got no video on this. Just all I got is
6:05 a head case on this and I'm working
6:06 through it. So, let's go on to the next
6:07 one. OpenAI plugins. This is another one
6:08 that I didn't fully comprehend the value
6:09 of until you and I talked and uh it's
6:10 from OpenAI. It's plugins for their
6:11 software for Codeex. What is this?
6:12 Well, of course, I just want to firstly
6:13 say that, you know, everyone should go
6:14 and use your um sponsor Zappia,
6:15 >> but this does provide some similar
6:16 skills if you're willing to kind of get,
6:17 you know, deep down dirty with codeex um
6:18 and you want to plug in things like Asa
6:19 and Air Table you can see on the screen
6:20 there, but also things like Gmail and um
6:21 GCAL and different research things as
6:22 well I noticed were in there like things
6:23 I would never use, but there's like
6:24 research APIs and things if you want to
6:25 provide access to those to codeex these
6:26 are the plugins to do so because you
6:27 know they're kind of semiofficial or
6:28 probably even fully official. I don't
6:29 really know what the third parties have
6:30 to say about it but this is what OpenAI
6:30 is putting forward as saying like you
6:31 know you want to hook into like notion
6:32 for example then install this plugin
6:33 into codeex and off you go you can ask
6:34 it to do this and do that. So, um, you
6:35 know, this is kind of almost like a a
6:36 homebrew local version of some of like
6:37 what tools like Zappy are doing in
6:38 connecting things together, but yeah,
6:39 you kind of have to figure out all the
6:40 moving parts for this. What I also saw
6:41 was that it does it's it's about getting
6:42 data out of these tools to do something
6:43 with the tools. It's not just
6:44 open-ended. So, for example,
6:45 >> I might connect Notion directly into
6:46 Claude,
6:47 >> and that's fine. But what they're trying
6:48 to say here is if you want to turn a
6:49 spec into implementation in claude, we
6:50 also are going to have that covered and
6:51 this will find the specs, turn it and
6:52 start to implement. That's it's like a
6:53 not connect. It's not about the
6:54 connection from what I understand. It's
6:55 about the utility with guidance. Am I
6:56 getting that right?
6:57 >> No, I totally agree. I mean and this is
6:58 the type of thing where you can use
6:59 these tools within your other workflows
6:60 that you're doing. So let's say you know
6:01 you're building uh an app in codeex and
6:02 you want it to use your project
6:03 management system like say Jira or
6:04 something like that for doing tickets
6:05 and said you know you could you can tell
6:06 it you know go and look at the tickets
6:07 that are currently on our system pull
6:08 them down implement something and then
6:09 update the ticket with comments or
6:10 whatever it is that you want to do. So
6:11 it just allows you to plug in these
6:12 third party systems into your codeex
6:13 workflow.
6:14 >> Okay. All right. There's our launch
6:15 video. I'll leave it for everyone to get
6:16 in the show notes. We're going to move
6:17 on to agent reach. This is one CLI that
6:18 lets your agent read and search Twitter,
6:19 Reddit, YouTube, GitHub, and other
6:20 sites. Um,
6:21 >> you you made a distinction between this
6:22 and the first 30 and the last 30 days
6:23 uh skilled, sorry, the last 30 days repo
6:24 that we talked about in the beginning.
6:25 What's the difference here?
6:26 >> When I looked through the code, I just
6:27 kind of saw some similarities between
6:28 the two repos. So that last 30 days
6:29 thing, you basically give it a topic and
6:30 it produces a deliverable uh of, you
6:31 know, what happened in the last 30 days
6:32 in whatever topic you want, but
6:33 underneath the hood, it's using a bunch
6:34 of tools to access things like X and
6:35 YouTube and so on and pulling data from
6:36 those to synthesize that report. Well,
6:37 this is like if you just took that layer
6:38 of tools and just turned that into a
6:39 thing. So, if you want more granular
6:40 access,
6:41 if you want to be able to ask uh
6:42 Claude or whatever, you know, go and
6:43 look on X for such and such or look on
6:44 YouTube for whatever it is that you
6:45 want, um then this is the kind of the
6:46 more surgical like the surgical knife
6:47 that allows you to do that without
6:48 producing that big deliverable. You just
6:49 use it within whatever workflow you're
6:50 working on at this current moment.
6:51 >> I like this example for LinkedIn. Tell
6:52 your agent, "Help me set up LinkedIn."
6:53 Um yeah, again this is for researching
6:54 for understanding somebody. When I talk
6:55 with Adam about tools like this and I
6:56 say how do you use it? He says that they
6:57 use it all the time in the venture
6:58 studio because one of their companies is
6:59 trying to hire so they want to research
6:60 people. One of their companies is trying
6:61 to buy a company or work with a company
7:00 and so they need good research
7:01 tools. They don't want to have somebody
7:02 clicking a mouse on a screen and that's
7:03 where this comes in. Make sense?
7:04 >> And it does a few it does a few Chinese
7:05 social networks as well. I don't know
7:06 anything about these networks, but
7:07 >> um I believe the developer is Chinese
7:08 and so they've added in these various
7:09 other sites that I'm completely unaware
7:10 of like was it Billy Billy Billy or
7:11 something? I don't know. I know nothing
7:12 about these sites, but uh I guess you
7:13 know if you want access to them, then
7:14 great.
7:15 >> Yeah, I don't know if you noticed, but
7:16 when I read off the list of sites that
7:17 you can read from, I intentionally said
7:18 and others once we had get to the
7:19 Chinese ones to make sure that I didn't
7:20 mispronounce them.
7:21 >> Not familiar with these.
7:22 >> Okay, the tool still works. Really
7:23 popular and it's number six this week.
7:24 Uh again, download everything in the
7:25 description. Let's go on to this one.
7:26 Less applicable to our people, but still
7:27 worth knowing about. This is Nvidia's
7:27 open platform for world models, data
7:28 sets, and tools for physical AI. We're
7:29 now talking about robots, autonomous
7:30 vehicles, smart infrastructure. I've got
7:31 kind of a video here to to show.
7:32 Anything you want to say about this? Um,
7:33 not really. other than the fact that
7:34 this is a new kind of what they call an
7:35 omni model. So it can handle lots of
7:36 different types of input, not just text,
7:38 but also, you know, like movement within
7:39 space and images and all this type of
7:40 thing.
7:41 >> So it's good for people that working in
7:42 the physical space, which is not me. I
7:43 know absolutely nothing about robotics,
7:44 but you want to look at robot arms
7:45 moving around, then this is the place to
7:46 do it.
7:47 >> Yeah, they do have that on their site.
7:48 And I do wonder if people who are who
7:49 were listening are doing that. I'll tell
7:50 you this folks, I stopped talking over
7:51 the videos because one commenter told
7:52 told us that and Peter uh Peter noticed
7:53 it and told me if this is something that
7:54 you're building with, let us know. Let
7:55 us know how you're using
7:56 >> of omnidreams, an action conditioned
7:57 world model. Cosmos predicts the future
7:58 frame by frame.
7:59 Post train Cosmos and it becomes a world
7:60 action model. Perceiving, reasoning,
7:61 planning, generating actions.
7:62 Okay. Um, I like that it's here. I like
7:63 that we're getting more substantive and
7:64 getting offline. I don't think it's
7:65 applicable to most people. We'll move on
7:66 to number eight. Oh, before we do, we
7:67 keep commenting on how some repos don't
7:68 seem to fit here. How do they get all
7:69 these stars? And you have said, look,
7:70 some people do. Adam actually said some
7:71 people buy. You've been questioning
7:72 some. And then you you highlighted
7:73 these. Uh, what are we looking at here?
7:74 >> So, I noticed that this Phantom Stars
7:75 account, which I know nothing about what
7:76 this is, but
7:77 >> it's a tool of some kind that is going
7:78 around and commenting on different repos
7:79 where it thinks there has been what it
7:80 calls fake engagement. So, it's not
7:81 making a direct, you know, accusation,
7:82 and we're not making a direct accusation
7:83 that these projects are engaging in any
7:84 kind of like buying stars or whatever,
7:85 >> but it's saying we've noticed that
7:86 there are these users that are very suspicious
7:87 and do nothing but go around and like
7:88 random repos and have no other activity.
7:89 So, I just thought it was interesting
7:90 that it cropped up on a few of the ones
7:91 that we've covered today. But, I guess
7:91 that makes sense since they are the most
7:92 popular ones of the week. They're the
7:93 ones that most likely to uh attract
7:94 this, you know, whether or not it's
7:95 being done intentionally or not.
7:96 Yeah, they're going to get the most
7:97 everythings. Okay, so we've got links
7:98 here for those. It is happening.
7:99 >> It's a thing.
8:00 >> Yeah. And if anyone has any information
8:01 about this, let us know. I'm curious
8:03 about who's buying stars. What does
8:04 stars cost? I've been hearing a lot
8:05 about that. People who are buying
8:06 engagement on X and doesn't cost that much. Some
8:07 anywhere from
8:08 >> I'll star your repo for $1,000. So, you
8:09 know, if anyone wants that help, you
8:10 know,
8:11 >> they want bots to do it. They want a
8:12 thousand repos for $1,000. Okay, this
8:13 is bringing up Taste Skill is bringing
8:14 up a really big issue, which is that
8:14 everybody's design looks the same.
8:15 Especially if it comes from any of
8:16 Claude's products, except I don't know
8:17 about Fable. I've been hearing Fable's
8:18 getting better at it. But if you want to
8:19 create your unique taste, if you want to
8:20 create your unique angle, don't start
8:20 with what Claude has and adjusted. Start
8:21 with something brand new. That's the
8:22 vision here. Um, and they've got here,
8:23 let me show you a before and after from
8:24 this video.
8:25 >> So, you can see this is a very basic
8:26 landing page. Um, so even though I think
8:27 it's uh decent, but it's pretty basic.
8:28 So, let's check out the one that has the
8:29 test
8:30 skill.
8:31 >> Taking a moment, but he'll get it.
8:32 >> And you can see that this is better. So,
8:33 this is actually really premium. And you
8:34 can see that uh the UI is very elevated.
8:35 So, it's very good. So
8:36 >> that's that's the idea here. You can
8:37 take a look at their site, which of
8:38 course we'll link to, and uh and you can
8:39 get a sense of their design style. I
8:40 like it. I like these a lot. What do you
8:41 think?
8:42 >> I think it's very important to note that
8:43 you are basically trading one set of
8:43 cliches for another with skills like
8:44 this. So, like when I went into and look
8:45 through the skill files, you know, it's
8:46 got all these different kind of like um
8:47 tones like brutalist design and a
8:48 minimalist design and a soft design
8:49 which you can see on that page as well.
8:50 >> Um and if you go into the skill files,
8:51 it basically says, oh, you know, like a
8:52 soft design will use these types of
8:53 colors and it will use these types of
8:54 fonts,
8:55 >> but you're really just over, you know,
8:56 steering the model away from what it
8:57 would do by default into this other kind
8:58 of lane. So, you're just trading one set
8:59 of cliches for another. Um, but the good
8:59 thing about it is you can take repos
8:00 like this. you can go in and say, "Well,
9:01 actually, I want to make my own style
9:02 inspired by all of this." Copy and paste
9:03 it, change the fonts around, change the
9:04 colors around, and then bam, you've got
9:05 your own little design system uh come
9:06 out of it. So, I don't mind repos like
9:07 this. It is nice to see what other
9:08 people's takes are on designing things.
9:09 Um, and it's kind of like fun to play
9:10 with. Uh, you know, it's not like it's
9:11 producing code that's going to
9:12 completely break everything. It is
9:13 basically just changing the design, the
9:14 style, the CSS, the fonts, and so on.
9:15 Um, so yeah, experiment, play, but also
9:16 again, you know, I've said this on so
9:17 many repos. It's a case of go into the
9:18 repos, look at the skills, and see if
9:19 you're happy with what it's suggesting
9:20 because you might not like you might not
9:21 like these designs, but you can change
9:22 it. What I like about this video from
9:23 Dev's Kingdom is he he shows how easy
9:24 it is. He just has it create another
9:25 version. He clicks it open and he shows
9:26 us what it looks like. And I think
9:27 that's another fun thing about this.
9:28 Just throw your design at it, see what
9:29 it can do, and then adjust. All right.
9:30 This is Apple's own tool to run Linux
9:31 containers as lightweight virtual
9:32 machines on Apple silicon.
9:33 This came out at WWDC this week. How and
9:34 what's going on with this? So I mean
9:35 this idea um even at Apple has been
9:36 actually around for you know a year or
9:37 two now which is that it allows you on
9:38 Mac OS to basically run Linux within a
9:38 tiny
9:40 virtual machine within your machine. Now
9:41 you've been able to do this with third
9:41 party tools for a long long long time.
9:42 This is you know a technology that goes
9:44 back decades but now Apple's getting in
9:45 on the action and people were thinking
9:46 well why why would they want to do that?
9:47 And that's why the announcements at WWDC
9:48 this week in particular were interesting
9:49 is because they're taking it to the next
9:50 level. So it's not just about running,
9:51 you know, a random Linux in a VM. You've
9:52 been able to do that for years. They're
9:53 focusing more on the integration now
9:54 between Mac OS and these underlying VMs.
9:55 So they're adding in things like being
9:56 able to keep the file system synced
9:57 between the two. Um, and hopefully, you
9:58 know, they will eventually get it to the
9:59 point where it's a bit like there's
9:60 something in Windows called WSL which
9:61 allows you to run Linux and it fully
9:62 integrates with Windows. You can even
9:63 run graphical apps from Linux and they
9:64 appear on the screen, you know, almost
9:65 as if they're Windows applications.
9:66 The idea is that hopefully you'll be
9:67 able to do all of this as well with Mac
9:68 OS eventually. Uh, they're just kind of
9:69 like teasing out bit after bit and Tim
9:70 Snif there is one of the people that's
9:71 actually working on this feature. Um, I
9:72 mean, one of the things actually I found
9:73 quite funny about this tweet is that he
9:74 said, "Oh, you know, I love what's going
9:75 on with Apple Container." And someone
9:76 replied back and said, "Oh, you know,
9:77 we've been able to do this for years and
9:78 people didn't realize he's the guy
9:79 actually implementing this stuff." So,
9:80 it was one of those kind of scenarios,
9:81 but it's nice to see that Apple's
9:82 interested in this and they're allowing
9:83 the people to talk about it. That's
9:84 quite unusual at Apple with technical
9:85 stuff. You know, you don't often see
9:86 them tweeting about things that they're
9:87 actually implementing. So, it seems like
9:88 they want to engage with our community
9:89 and they want, you know, developers and
9:90 particularly AI developers to use these
9:91 containers. I mean, they're technically
9:92 VMs, um, to run workloads safely within
9:93 a Mac OS machine without it taking over
9:95 the entire machine. And that is one of
9:96 the things that this allows you to do.
9:97 All right,
9:98 repeat. Mark it down. Coming back again.
9:99 This one keeps making into the top 10.
9:00 This is m Microsoft's
9:01 way of helping you turn PDFs into
9:02 markdown office docs, images, uh, audio
9:03 into clean markdown files, even YouTube
9:04 videos into markdown files. We we've
9:05 talked about it before. So, you know
9:06 what? Today, what we're going to do is
9:07 we're going to have this YouTuber who I
9:08 I can't tell if this is a real guy or
9:09 not cuz he's so like he's so always on
9:10 exactly right here. So, maybe he's super
9:11 edited. Everyone uploading PDFs to
9:12 Claude is basically wasting their
9:13 tokens. And Microsoft had a free
9:14 solution to this for months. So every
9:15 time you upload a PDF, Claude has to
9:16 process the entire thing. The
9:17 formatting, the broken tables, the
9:18 images, and all the extra junk inside
9:19 the file. And each PDF page can consume
9:20 between 1,500 to 3,000 tokens. So 20page
9:21 document burns through up to 70,000
9:22 tokens in one shot. And this is before
9:23 you even ask your first question. The
9:24 fix is simple. It's called Market It
9:25 Down, a free Microsoft tool with over
9:26 110,000 stars on GitHub. It takes any
9:27 file, be it PDFs, Word docs, Excel
9:28 sheets, PowerPoints, or even YouTube
9:29 videos, and converts them into clean
9:30 markdown text. This drops your token
9:31 usage by up to 70%. And Claude actually
9:32 gives better answers because it was
9:33 trained on millions of markdown
9:34 documents and understands the format
9:35 natively. Plus, Mark Itown comes with an
9:36 MCP server, meaning when you connect it
9:37 to Claude desktop, it automatically
9:38 converts every file you upload to a MD
9:39 file. So, check the pinned comment for
9:40 the tool link and the full PDF guide.
9:41 >> All right. I like his his way of doing
9:42 it. Do you think he's human?
9:43 >> I'm not sure. But are you human?
9:44 >> I would like to be less human.
9:45 >> I definitely am.
9:46 >> I would like to be less human. I'd like
9:47 to get like more AI into the scripting
9:48 here. Look at how organized he was with
9:49 that.
9:50 >> All right. Of course, that report with
9:51 his video and everything else is going
9:52 to be in the description. Before we go,
9:53 Peter, what are you up to this weekend?
9:54 I am literally doing nothing. I'm
9:55 attending a family barbecue, but other
9:56 than that, I'm doing nothing because I
9:56 just need to decompress. All these stars
9:56 are literally getting into my head.
9:57 >> I need to like get rid of the stars.
9:58 >> That
9:59 >> Yeah, I am going to be mowing, mowing,
9:60 mowing this weekend, doing a lot of yard
9:61 work, and then Olivia is taking the two
9:62 older boys with her to San Francisco to
9:63 be with her family. And I've got the
9:64 baby with me for 10 days. And I don't
9:65 know what we're going to do.
9:66 >> I've done that before.
9:67 >> Yeah, it's um it's something. But, you
9:68 know, he's in daycare. And then I think
9:69 I think on the weekends I'm going to
9:70 take him to um
9:71 >> to San Antonio. We're in Austin. And
9:72 I'll take him to a museum where he can
9:73 run around all my guitar with my
9:74 earphone so I could practice and just
9:75 have some downtime while he's running.
9:76 All right. So, there it is. As the next
9:77 video now that this is over, you should
9:78 know that there have been some incredible
9:79 AI releases this week that did not get a
9:80 much attention because Fable was big
9:81 and also because people just don't have
9:82 that much attention span. We found the
9:83 best ones. In the next video that
9:84 you're going to watch, you're going to
9:85 see them. See you
9:86 in there.

</details>
