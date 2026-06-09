---
title: "From MCP to Scale: Pipelines That Build Themselves — Rafael Levi, Bright Data"
channel: "AI Engineer"
channel_slug: "ai-dot-engineer"
channel_id: "UCLKPca3kwwd-B59HNr-_lvA"
published: "2026-06-07"
duration_seconds: 1525
video_id: "zTZ0qunQXnM"
url: "https://www.youtube.com/watch?v=zTZ0qunQXnM"
language: "en"
tags: [ai, ai engineer, ai engineering, software development, tech, startups]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-09"
---
# From MCP to Scale: Pipelines That Build Themselves — Rafael Levi, Bright Data

**Channel:** AI Engineer  **Published:** 2026-06-07  **Duration:** 25:25  **Watch:** https://www.youtube.com/watch?v=zTZ0qunQXnM

## TL;DR

Rafael Levi from Bright Data reframes scraping: the hard part isn't writing the scraper, it's maintaining it. The agent pattern — explore via MCP, understand data shape, write a scraper, monitor it, fix it when it breaks — turns the maintenance loop into the agent's job. Demo: a Walmart scraper that works through Bright Data's anti-bot, built in ~3 minutes. The 30-minute self-healing cron (LLM checks, fixes in 5 min, shuts down) eliminates the 2am page. Key insight: stop using LLMs to parse pages repeatedly. Use them to *write* the scraper, then only re-engage when it breaks. Massive token savings.

## Key Insights

- **The real problem is maintenance** (00:01:20) — writing a scraper is easy. Maintaining it when the site changes its selectors, or it's a React app, or the anti-bot gets aggressive — that's where the time goes. Often you spend more time *maintaining* than *writing*.
- **The agent pattern** (00:01:50) — agent uses MCP to explore the site → understands the data shape → writes the scraper → runs it → *monitors* it and fixes it when it breaks. The maintenance loop is the agent's job, not yours.
- **Bright Data skills** (00:02:50) — a GitHub repo of skills teaches your LLM how to build scrapers. The agent reads the skills + uses Bright Data's MCP to extract HTML + identify selectors + write a production scraper. Demo: a Walmart scraper that *works* through Bright Data's anti-bot circumvention. Build time: **~3 minutes**.
- **The 30-minute self-healing cron** (00:02:05) — Rafael runs an LLM class every 30 minutes. It checks what the data looks like. If everything is fine, it shuts down. If a data point is missing, the agent fixes it. **5 minutes to repair. No 2am pages.**
- **Save tokens by switching from page parsing to reusable scripts** (00:00:50) — a common Reddit question: 'scanning 10,000 products is so many tokens.' Answer: don't parse the page every time. Write a scraper once, run it many times, only re-engage the LLM when something breaks.
- **Live demo on Walmart** (00:03:00) — Walmart has aggressive anti-bot. Direct scraping doesn't work. Through Bright Data's MCP, the agent extracts HTML, finds selectors, writes a scraper that works in the live demo.

## Notable Quotes

> "Scraping is not the hard part anymore. Maintaining scrapers is." — 00:01:20
> "An agent solves all that headache. It can explore with our MCP, it understands what the data is needed. It writes the scraper and it actually runs it and executes it and maintains it." — 00:01:50
> "I have every 30 minutes I have an LLM class that spools up. It checks what the data is collected, makes sure that everything is fine. Everything is fine, it shuts down. If for this example, there's a missing data point, your agent fixes it. 5 minutes. You don't have to wake up in the middle of the night." — 00:02:05

## Tools and Resources Mentioned

- **Bright Data MCP** (brightdata.com) — vendor: Bright Data — managed scraping + MCP, anti-bot circumvention
- **Bright Data Skills** (github.com) — vendor: Bright Data — GitHub repo of skills that teach LLMs to build scrapers
- **Claude Code** — vendor: Anthropic — used as the agent harness in the live demo (not MiniMax Hermes Agent — Anthropic's product)

## GitHub Repos and URLs Referenced

- [brightdata/skills](https://github.com/brightdata/skills) — vendor: Bright Data — scraper-building knowledge base the agent reads

## Action Items

- [ ] Audit any current data pipeline: are you calling an LLM to parse pages repeatedly, or did you write a script and only call the LLM on failure?
- [ ] For sites with anti-bot: prototype with Bright Data MCP / similar managed scraping, not homegrown stealth browser automation.
- [ ] Set up a 30-min self-healing cron over any data pipeline that has 2am-page risk. LLM cost is a rounding error vs. on-call pain.

## Open Questions

- What's Bright Data's pricing model for the MCP + skills combo? (Talk is a demo, not a sales pitch.)
- How does the 5-minute repair scale when the *whole site's structure* changes, not just a selector? (Boundary case not covered.)

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 25:25 transcript)</summary>

0:15 All righty, let's dive into it.
0:17 So, uh in the previous session, I I
0:19 don't know how many of you were here,
0:20 but I talked about how MCP gives access
0:23 to LLMs to websites that are behind uh
0:26 CAPTCHA, bot detection systems, and so
0:28 on.
0:30 And in this session, I want to talk
0:32 about um how do you actually collect
0:34 data on scales with LLM? Because a lot
0:37 of times I'm seeing on Reddit and other
0:38 social media is like, "Oh, I need to
0:40 scan 10,000 products, but that's so many
0:41 tokens if I need to parse everything
0:43 with LLM." So, obviously, you don't do
0:45 that.
0:46 Right? So,
0:48 the whole session is how do you build
0:51 pipelines, right? With LLM. Instead of
0:53 telling, "Hey, LLM, can you go and uh
0:55 parse this for me?" build a scraper
0:57 that's going to parse it for me, and I
0:58 will demonstrate how easy it is
1:01 uh with our skills, right? So, Bright
1:03 Data has skill sets that actually
1:05 teaches your LLM on how to build a
1:07 pipeline. With our MCP, it can actually
1:10 extract HTML so that it knows what are
1:12 the selectors that it needs to parse,
1:14 and so on.
1:16 So, um
1:17 the scrape tags, right? Write the
1:19 scraper.
1:20 Uh I don't know how many of you actually
1:22 wrote scrapers before.
1:25 Okay, so you know the headache when all
1:26 of a sudden things are missing, data is
1:28 missing, you got to wake up. I don't
1:30 know if you guys did it for clients, and
1:31 clients are like, "Oh my god, there's no
1:33 So, basically, that's what used to be.
1:35 You write a scraper, and you maintain
1:37 it. As a matter of fact, sometimes you
1:38 maintain it more than it it it takes you
1:40 to write it, right? So, everything,
1:41 especially if the website is constantly
1:43 changing
1:44 uh its selectors, or if it's a React
1:45 website, it gets really complicated,
1:47 right?
1:49 So,
1:50 an agent it it it solves all that
1:53 headache, right? It can explore with our
1:55 MCP, it understands what the data is
1:57 needed. It writes the scraper and it
1:59 actually runs it and executes it and
2:01 maintains it. As a matter of fact, I do
2:03 collections on the daily basis and I
2:05 have every 30 minutes I have an LLM
2:07 class pool spools up. It checks what the
2:10 data is collected, make sure that
2:11 everything is fine. Everything is fine,
2:13 it shuts down. If for this example,
2:15 there's a
2:16 always set a validation for data, right?
2:18 Let's say the data point is uh missing
2:20 some something.
2:22 Your agent fix it. 5 minutes. You don't
2:24 have to wake up in the middle of the
2:25 night.
2:27 Uh
2:29 So, let me demonstrate. So, for this
2:31 demo, I want to use Cloud Code. I don't
2:33 know how many of you use Cloud. If
2:35 you're using Codex or whatever it is, I
2:36 prefer Cloud Code. I like how it
2:40 I like it. It does a great job.
2:42 So, the way that you build scrapers now
2:45 and it's ridiculous because, you know,
2:47 back in the day it took weeks to set it
2:48 up. We created a Bright Data like GitHub
2:51 page, right? Bright Data skills. Here
2:53 basically, your agent has everything
2:55 that it might need, okay? Um scrape
2:59 builders back practices, how to
3:01 everything. Everything that it needs in
3:03 order to build a scraper.
3:05 And what I want to show is
3:07 uh first of all,
3:09 let's
3:11 I'm going to start simple. Go to
3:15 build me a scraper and I wanted to
3:17 record it because I thought it's going
3:18 to take a long time, but now it takes a
3:20 little like 3 minutes. Build me a
3:21 scraper
3:23 uh two inputs
3:25 keyword search
3:27 max pages for walmart.com.
3:32 Everybody's familiar with Walmart.
3:33 Walmart has a very aggressive anti-bot
3:35 systems. If anybody tried to scrape it,
3:37 um it just doesn't work. But, through
3:40 Bright Data,
3:48 it will figure it out, but you're you're
3:51 all right. Let's just correct that.
3:54 walmart.com
3:56 Um
3:59 run a search for headphones, collect
4:03 three pages.
4:08 Uh so, what it's going to do right now
4:10 is going to go to our GitHub, it's going
4:11 to get all the skill set that it needs,
4:13 how to build scrapers, then it's going
4:14 to go uh with the MCP that's already
4:16 connected to the cloud, it's going to
4:18 extract the HTML from the page.
4:21 Uh it's going to find all the selectors
4:23 that it needs, and it's going to build
4:24 you a scraper, and uh
4:29 So, right now you can see a scraper as a
4:30 markdown, it's basically extracting the
4:32 the the the text, right? So, for the
4:35 skills, we don't need the HTML, we just
4:36 need the text.
4:38 Uh scraper as a markdown is a part of
4:40 the MCP of Bright Data MCP.
4:42 Uh the MCP has 5,000 requests for free,
4:45 so if anybody wants to try it, you guys
4:47 can try it for free. Um
4:50 You will need to just open an account
4:51 with Bright Data, which doesn't cost you
4:53 anything.
4:54 And
4:57 let it do its thing. So,
5:01 why is this better than having an LLM
5:04 parse every single page, every HTML?
5:07 It's I'm I'm literally afterwards I'm
5:09 going to ask it to tell you how many how
5:11 much tokens it saves.
5:12 So, for the three pages, I've done this
5:14 before, it saves about a million tokens
5:16 just to from building the scraper
5:19 uh and using a script to parse the HTML.
5:23 And um
5:25 even if you are not doing any scraping
5:28 for production, but let's say that you
5:29 want to find the best best headphones
5:32 for the money, right? It used to be you
5:34 go to Google, you go to some CNET where
5:36 they uh compare everything, but here you
5:38 can use the the marketplace reviews.
5:42 So, I can tell it here like hey hey, um
5:45 scan the five pages, find me the best uh
5:47 review to headphones. So, it could be
5:49 even useful for you as a personal in in
5:51 a personal way, right? So, instead of it
5:54 getting blocked, it can actually find
5:56 you things that you need on websites
5:57 that are behind Cloudflare.
6:00 Oh, I forgot to delete the old one.
6:04 No. No, stop. Stop. Stop. Hold on a
6:07 second.
6:09 Delete the old scraper.
6:12 Scraper.
6:14 I totally I was testing it and I totally
6:16 forgot to clean up.
6:19 Uh, let's do a different website. Pick a
6:21 website. What's a popular marketplace in
6:23 uh that's aggressive in blocking in UK?
6:28 >> Very.
6:28 >> Amazon? It's not that aggressive. You'll
6:31 be surprised. I can scrape it with data
6:32 center IPs.
6:34 What's a popular website that everybody
6:36 uses here?
6:36 >> Very.
6:38 Very.
6:39 >> V-
6:39 >> v e r y.com.
6:43 >> V-
6:46 Very?
6:47 >> Very.
6:47 >> Like that?
6:49 >> y
6:49 >> y.com?
6:50 >> Yeah.
6:53 >> Oh, that's the UK?
6:55 Okay, perfect.
6:58 So, this way I don't I don't want to
7:00 Stop it.
7:01 New session.
7:03 Uh
7:06 Let's do that.
7:09 Let's do that.
7:11 Where's the new session? Oh, there it
7:12 is.
7:19 Really?
7:28 What is wrong with my paste?
7:31 Okay.
7:33 Uh, it's clothing store?
7:36 >> Uh, it's category.
7:38 >> Okay, so let's do headphones again, the
7:40 same thing, right? So, I don't know.
7:42 I've never used this website. I've
7:46 Look.
7:47 Clean test. No cheating.
7:54 Um
7:57 So So, what else does this give you? So,
7:59 again, market research.
8:01 Um
8:02 For example, I was looking for a new
8:04 apartment, right? I would want to move a
8:06 house. So,
8:08 with a CloudCrawl, with BrightData, I
8:10 set up a listener. Literally just
8:11 telling Hey, listen. Build me a scraper
8:13 that will run every half an hour when in
8:16 this area there's a a house, private
8:18 house, under this price, notify me.
8:20 That's all I did. In a few days, I got a
8:22 notification and now I live there.
8:24 So, these things are not only useful on
8:26 a scale where, you know, oh, I need to
8:28 scrape millions of records, but even for
8:30 your personal use.
8:32 It's so easy these days.
8:35 CloudCrawl does an amazing job, right?
8:39 I know Crawlera does a great job as
8:40 well, but I prefer CloudCrawl because I
8:42 don't know. It just
8:43 gives me less headache.
8:45 Crawlera sometimes takes me on a wild
8:47 goose chase.
8:49 Um how many of you use VibeCode?
8:54 It's It's amazing. Why not, right?
8:56 Anybody can build anything now.
8:58 Um
9:00 So, did you build it? I've got the
9:01 structure, the search patterns. I don't
9:02 know what third party I'm going to
9:03 build. Oh, okay. It's building a
9:04 scraper.
9:05 Um
9:07 This used to take,
9:09 I don't know. If you If you're having a
9:10 good day, maybe a full day, maybe a day
9:12 and a half, right? You need to go check
9:14 out the selectors, figure it out. It
9:16 used to be interesting and fun,
9:18 but you don't need to do that anymore.
9:20 So, what I'm trying to show you guys is
9:22 that
9:24 with our
9:25 MCP, with our
9:28 infrastructure, we have over 150 million
9:30 IPs.
9:31 Uh with our unlocking technology where
9:33 we even though if it needs to run a
9:35 remote browser, so if you want to It can
9:37 actually write you a browser automation.
9:39 Uh Uh the browsers are running on our
9:41 system. So, I can literally right now
9:42 open a thousand browsers on this laptop
9:44 that are running on our servers.
9:46 And they can go do things whatever you
9:48 needed to.
9:50 So, it already got 90 products.
9:55 Okay, it just needs to fix the Unicode
9:58 because it's in pounds.
10:06 Almost done.
10:08 >> Can you also
10:10 go into details about the MCP or is that
10:12 it?
10:12 >> Sure, I did it in the previous session,
10:14 but while it's loading, let me tell you.
10:15 So, basically, the MCP gives you a
10:17 agent 66 tools.
10:20 Uh some of them is basically uh we have
10:22 a system where it can send a curl to any
10:24 URL and our system will literally get
10:26 the HTML back. It will solve a capture
10:28 if needed and send it with a token. It
10:31 will It knows exactly what headers and
10:33 cookies the website needs. So,
10:34 basically, it will make sure that the
10:36 server thinks it's a browser and serve
10:38 the HTML back. So, your agent can
10:39 literally send curls, pull data without
10:42 any questions.
10:43 It can pull a full HTML. It can pull
10:45 just a scrape as a markdown. Markdown is
10:47 It's to save tokens, right? You just
10:49 want the text of the page. You don't
10:50 care about the HTML tags.
10:53 It doesn't like the pound.
10:57 Come on, you can do it.
11:00 Um so, that's number one. Second, we
11:03 have about 500 different APIs pre-built
11:06 for different domains.
11:07 So, instead of actually getting
11:08 markdown, you can actually get a JSON of
11:10 the product. For example, for Amazon, we
11:12 have pre-built API. You can listen when
11:14 you add your agent, it can be like,
11:16 "Okay, go and check on Amazon
11:17 something." It doesn't even need to
11:19 build a scraper. It can literally just
11:20 send the the request and get the data
11:22 back.
11:23 Um on top of that, remote browser
11:25 infrastructure and the anything that
11:28 needs
11:29 anything that your agent needs to access
11:31 the web.
11:32 It has, right? So, you don't get
11:34 blocked.
11:35 While this is running, I want to show
11:36 you for example
11:38 uh tell
11:40 one
11:41 to Walmart
11:43 do a search for headphones without
11:48 MCP one
11:51 So, I'm telling it go to Walmart, do a
11:53 search for headphones, and tell me what
11:54 is the first result.
11:56 Without the Bright Data MCP.
11:59 Uh
12:01 It's going to do a fetch, which is going
12:02 to get blocked.
12:07 Product security verification screen,
12:08 robot or human, obviously, right? That's
12:10 That's the first thing.
12:13 Now, do the same with Bright
12:17 Um
12:18 Oh my god.
12:27 So, now it's using Scrape as a markdown.
12:29 It's doing a search. It's only pulling
12:31 the text. It's not pulling the HTML,
12:32 just the text itself.
12:45 Always when you do a live, it's slows
12:47 down.
12:49 The time is like
12:55 Oh, actually, it could be. It could be
12:56 opening a browser and actually holding
12:58 the button. You know, the Walmart has
12:59 like one of those click and hold, and it
13:01 needs to hold it for like 30 seconds.
13:02 So, it could be doing that right now.
13:05 So, is it
13:07 We have built to capture solving
13:09 solutions. Like, we literally have
13:11 in-house We have a AI solving capture.
13:14 And
13:15 moving, clicking things, and like what?
13:17 It's perfect.
13:18 So, it already got
13:22 first result, blue headphones. Oh,
13:24 basically, there you go. It already has
13:26 the results of the headphones without
13:29 robot or human with full product listing
13:31 name.
13:33 Uh
13:33 so, we here already have the output.
13:36 Tell me
13:38 if you were to do this manually,
13:42 how many how much more tokens have you
13:46 used?
13:47 How many did you save? Let's just give
13:50 it a breakdown, and this is probably the
13:51 biggest issue, right? Tokens is
13:53 expensive.
13:55 I'm going through millions and millions
13:56 of tokens a day.
13:58 I used to go more, but I I optimized it.
14:01 So, um
14:02 all of you are looking how do we save
14:03 money on LM? How do we waste less tokens
14:05 of web access and um
14:08 Bright Data has the solution. Instead of
14:10 parsing the full HTML, create a scraper.
14:13 Uh instead of using
14:15 um you know, okay, it pulls the HTML and
14:17 then it extracts the data, it builds the
14:19 the parser.
14:22 But, it's working very slow right now.
14:25 I feel like everybody's white coding.
14:26 So, basically, here's the breakdown,
14:27 right?
14:28 What do we have here?
14:31 The big swings output
14:33 parsing 90 products with
14:37 input tokens,
14:39 output tokens,
14:41 total save.
14:43 So, it's about a 62% save of tokens.
14:46 This is not a high number. This website,
14:47 I guess, uh has um maybe a structured um
14:51 HTML. I'm not sure.
14:54 But,
14:55 this is what I wanted to show you. And
14:57 the best thing about it is that it will
14:59 maintain it. If it breaks it, it will
15:01 fix it. I can set up a loop, right? So,
15:03 for example, in Cloud, I can set a
15:04 schedule every 30 minutes you do and run
15:06 and check something.
15:08 And this is
15:09 we are giving you guys, okay? With our
15:11 MCP, your agent has access to all the
15:13 web
15:14 uh without getting blocked. No capture
15:17 will stop it. No robots antibot systems
15:19 will stop it. And uh you have no
15:22 headaches of that. I don't know how many
15:24 of you have
15:25 You guys probably dealt with blocking,
15:27 right? When you build a scraper, it gets
15:29 really complicated. So, this kind of
15:30 removes all the headache for it.
15:32 Um any questions?
15:37 >> Where is the code?
15:38 >> Excuse me?
15:39 >> The code the code you generate a
15:40 scraper, right?
15:42 >> I can I If you you want to see the code?
15:45 I mean, it's here. We have the scraper.
15:47 Let's check it out.
16:03 So, it's using API web unlocker. This is
16:07 the same thing as a scraper as a
16:08 markdown with an MCP.
16:10 It sends a simple request and gets the
16:12 data back. This is the parser that it
16:13 built.
16:17 I mean,
16:21 it looks pretty good. This is the the
16:23 schema that it built for the output.
16:28 It's doing a keyword search. It has the
16:30 max page, right? So, I asked for two
16:31 inputs, the keyword search and how many
16:33 pages to scrape.
16:38 And hold on. Let's see Let's see We can
16:40 run it
16:41 through here as well. Where is the
16:43 variables? API key is on key.
16:52 Let's run it.
16:54 Do another run
16:56 on
16:57 laptops.
16:59 What are the two pages results?
17:04 And now you kind of control it. Like you
17:06 don't even need to run it, right? It
17:08 will trigger it for you. It will
17:09 maintain it for you. Um you can create a
17:12 script that will automatically do all of
17:14 this. I prefer the visual interface for
17:15 the demonstration. Sometimes they you
17:17 like looking at our code it's a little
17:19 more complicated. But right now
17:21 basically I can ask it any questions. It
17:23 will actually run the script. So it's
17:24 not wasting tokens to execute the script
17:26 maybe like 60 tokens, right right now.
17:28 So it's going to literally get all this
17:30 data for 100 tokens.
17:32 And then you can do whatever you can ask
17:34 it questions about it. But now we're
17:35 working with a JSON and JSON is much
17:37 more token efficient than any markdown
17:39 or any other file, right?
17:44 Still the usual.
17:51 >> Can I ask can you can you do this on all
17:53 the authorization sites as well?
17:55 >> Uh no, we only talk we only deal with
17:57 public data. So behind login it's um
18:00 it's private data. And and uh just you
18:02 know just a heads-up.
18:04 If you create an account, you accept
18:06 terms and conditions of the website.
18:08 Always check terms and conditions of the
18:09 website. If they say don't scrape, don't
18:11 use robots, and you do, then that
18:14 company can actually sue you. And this
18:15 is happening
18:16 you probably heard it in the news all
18:18 the time. LinkedIn is suing them.
18:20 Everybody's suing each other because
18:22 they the data right now is like the new
18:24 gold the oil, right? Everybody's trying
18:26 to like oh this is my data. Elon Musk
18:28 took over Twitter, locked it down.
18:30 That's it. Literally like uh the it used
18:32 to be so open and now it's all locked in
18:34 a few accounts that you can actually
18:35 scrape. So the we're seeing this on
18:38 every single level.
18:40 Very slow today.
18:42 Um so yes, also same thing if you accept
18:45 uh there's like terms and like if you do
18:47 a search and there's a checkpoint, I
18:49 accept terms and conditions, always be
18:50 careful with that. So we only deal with
18:53 public data. So nothing behind login. We
18:55 don't accept terms and conditions.
18:57 And we actually won a few lawsuits. We
19:00 were sued by Meta. We were so sued by
19:02 Elon Musk a month after he took over.
19:05 And uh the judge said it's very simple.
19:07 Public data is public data.
19:09 It doesn't matter how you collect it.
19:10 Doesn't matter what you do with it. It's
19:12 public. You know, it's like walking on
19:14 the street, you write down the prices on
19:15 the counter and then you sell it to
19:17 somebody.
19:18 It's public data. It's available. You
19:20 can do whatever you want with it. Okay?
19:21 So,
19:24 as usual, it gets stuck on a live demo,
19:26 but
19:28 we can
19:31 we can run this manually.
19:48 Oh my god.
20:00 What the
20:02 I'm setting a variable. It's doing this.
20:04 No, it's not going to work.
20:17 What am I missing?
20:21 Still stuck? Oh, okay. It's done.
20:24 Okay, so here we got we got
20:28 Let's see. How many tokens?
20:31 How many tokens did you spend on getting
20:36 the these?
20:42 So, even if you're not be able to
20:44 building pipelines for any
20:46 you know, big companies and you don't
20:47 need to get for personal use, I always
20:49 have the MCP connected. I don't ask the
20:51 you know, LLM to go do I always ask
20:54 build a script that can later on be used
20:57 by it. It's using its own script to save
20:59 the tokens.
21:10 >> Literally like we're talking about 1,000
21:11 tokens where if you know if if it needs
21:14 to go through the JSON, it's like 10,000
21:16 tokens. We're talking about like
21:17 literally pennies compared to what it
21:19 would be to actually scrape it.
21:21 Any more questions?
21:24 How about this? Anybody has problems
21:25 with actually getting data?
21:30 No, no question. Everybody is like
21:32 I'm not sharing my problems. I have no
21:34 problems. And they go home and like oh I
21:35 do have a problem. But in any case,
21:37 listen, we have a booth. If you don't if
21:39 you want to talk in private and you have
21:40 questions about data or access of LLM,
21:44 feel free. I'm always willing to help.
21:46 Um
21:48 we can connect
21:50 on LinkedIn by the way, guys, if you
21:51 want. Let me just summarize a few things
21:53 what we did here.
21:54 So um self-healing pipeline. When you
21:56 have when your agent actually has access
21:59 to a blocked website and you're working
22:01 I mean, the MCP is mostly useful in
22:04 about 20% of the of the domains, right?
22:06 The ones that have Akamai, Data Dome,
22:07 Cloudflare, those heavy protected
22:09 domains. They're the usually the most
22:11 juiciest one, right? Like real estate or
22:14 uh big e-commerce places.
22:16 Uh with our MCP, it has access to it. If
22:19 it has access to it, it can build a
22:20 scraper. If it can build a scraper, it
22:21 can maintain the scraper. This is
22:23 basically the whole thing that I wanted
22:24 to show you. That in Bright Data, we
22:26 have all the tools that your agent might
22:28 need to explore, to build and maintain
22:32 uh a pipeline, right? So, if you want to
22:35 set up a listener for an apartment and
22:37 you're looking to move into a cheaper
22:38 place or maybe you want to book a table
22:41 in a restaurant where it's always
22:43 packed. And literally I I I have a
22:45 listener right now. I'm waiting for 2
22:46 months already. Everybody is like
22:47 booking right away. So, as soon as the
22:49 spot opens, it will automatically book a
22:51 spot for me. It can be very useful in
22:53 just kind of like even even the small
22:55 things, personal things, right? I'm not
22:57 talking about just enterprise scale
22:58 where I need to download a million
23:00 records. Okay? But having access to all
23:02 the websites
23:04 is this is important.
23:06 >> So, apart from scraping
23:08 can you also do actions on the website?
23:10 >> Yes, of course.
23:13 Fill up a form, submit it as well. Yes.
23:15 The only thing you can't do is log in.
23:19 Right? So, if you have let's say you
23:21 need to perform a search, right? You
23:23 cannot generate the URL, you need to
23:25 click buttons. Let's say flights. You
23:27 want to check flights availability,
23:28 Skyscanner or something like that,
23:29 right? The URL is usually a hash and you
23:32 can't do anything with it. So, yes, LLM
23:35 can spool a browser, remote browser,
23:37 even if it's a geo-restricted site. It
23:39 can be like, "Okay, I want IP from the
23:40 United States." So, it's open a browser
23:42 with the United States IP and then it
23:43 goes and clicks things, fills it up, and
23:45 so on. The beauty of it is that our
23:47 browser will mimic real human behavior.
23:50 So, when your agent clicks, it's not a
23:52 teleportation. There's a mouse
23:53 pre-recorded like a real human being
23:55 moving it. When it types, it will type a
23:58 little slower, speed up, like maybe even
23:59 mistake, and so on. So, we have
24:01 pre-recorded typing, we have
24:02 pre-recorded mouse movements. So, if the
24:04 website has a tracker that's constantly
24:06 sending to the server what the user is
24:07 doing, it will look like a real human
24:09 being.
24:10 Doesn't matter what your agent, even if
24:11 it's a low like for browsing agents, I'm
24:14 never used the top models, right? For
24:16 example, if with Claude Haiku model is
24:18 more than enough for browsing. If it's
24:21 being masked that it's a real human, it
24:24 works just fine.
24:27 And
24:28 so, that's pretty much it. If you guys
24:29 want to connect on LinkedIn, feel free.
24:31 I'm always willing to help. If you have
24:32 any questions regarding how to get data,
24:34 if you have problems with accessing
24:35 anything, feel free to message me.
24:40 I feel like there's been so much more
24:41 than 15 minutes. I love it. It's the
24:43 second time I'm doing a speech and I got
24:44 like half an hour instead of 15 minutes.
24:46 It's amazing.
24:47 Um
24:50 Now's the time if you have any
24:50 questions,
24:52 discussions.
24:55 No, nothing? Great. Okay, guys, I guess
24:57 I will conclude this session in this
24:58 Feel free to come to the booth on the
25:00 third floor if you have more questions
25:01 and um
25:03 let's keep the public data public.
25:07 Thank you.


</details>
