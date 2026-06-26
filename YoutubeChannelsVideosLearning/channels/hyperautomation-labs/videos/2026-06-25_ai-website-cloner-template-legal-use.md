---
title: "This Free Tool Rebuilds ANY Website With One Command (20,000 Stars) — The Legal Way to Use It"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-25"
duration_seconds: 514
video_id: "ZGMzocFOyYo"
url: "https://youtube.com/watch?v=ZGMzocFOyYo"
language: "en"
tags: [ai-agents, claude-code, website-cloning, nextjs, design, legal, automation]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-26"
---

# This Free Tool Rebuilds ANY Website With One Command (20,000 Stars) — The Legal Way to Use It

**Channel:** Hyperautomation Labs  **Published:** 2026-06-25  **Duration:** 00:08:34  **Watch:** https://youtube.com/watch?v=ZGMzocFOyYo

## TL;DR
The "AI Website Cloner" GitHub template (20k+ stars) turns Claude Code into a `/clone-website` command that reverse-engineers any site into a clean Next.js 16 + React 19 + TypeScript + shadcn/ui + Tailwind v4 codebase. 5-phase pipeline: reconnaissance → foundation → section specs → parallel build (one agent per section in its own git worktree) → visual-diff QA. The legal line: the tool isn't the risk; what you point it at is.

## Key Insights
- **It's a template, not a scraper.** A scraper copies files; this one studies the page and writes brand-new code you own. "Think of it less like photocopying a painting and more like a student sitting in a gallery, studying the brush work, and learning to paint it themselves." (timestamp 0:35)
- **The legal line is sharp.** Two doors: (1) trouble — cloning a competitor's site, copying logos/brand assets, scraping sites whose ToS says no, impersonating a brand; (2) where this earns its stars — rebuilding your own site stuck on an old platform, recovering lost source, learning by taking apart a great site. The project's own README explicitly forbids deceptive use. (timestamp 1:54)
- **Phase 1 — Reconnaissance:** the agent opens the site in a real browser, takes screenshots, extracts design tokens (fonts, colors, spacing), runs an interaction sweep (scroll, click, hover), checks mobile vs. desktop. (timestamp 3:15)
- **Phase 2 — Foundation:** writes in real fonts, real color palette, global styles, downloads every asset (images, videos, icons). The project skeleton already feels like the original. (timestamp 3:48)
- **Phase 3 — Specs (where most tools fail):** for every section, the agent writes a detailed spec file with exact computed CSS values, button states, behaviors, real content. "No guessing" — the builder agents get everything handed to them. (timestamp 4:12)
- **Phase 4 — Parallel build:** dispatches a team of builder agents, each in its own isolated git worktree — header, hero, footer, all rebuilt in parallel at the same time. (timestamp 4:46)
- **Phase 5 — Merge + visual diff:** merges worktrees, wires sections into one page, runs a visual diff comparing rebuild against original side-by-side. (timestamp 5:08)
- **The output stack is 2026-modern:** Next.js 16, React 19, TypeScript in strict mode, shadcn/ui on Tailwind v4. "Not a dead end. A real codebase you can read, change, ship." (timestamp 5:35)
- **Setup is 4 steps:** click "use this template" (NOT clone the original directly), `npm install`, start Claude Code with Chrome flag so the agent can see the browser, type `/clone-website` with the link (can pass several links at once). (timestamp 6:14)
- **Not magic.** Phase 5 does a visual comparison instead of trusting itself because AI still gets details wrong; you'll need to clean up and customize. "The legal part is on you, not on the tool. If a site's terms say no, that is a no." (timestamp 6:57)

## Notable Quotes
> "Think of it less like photocopying a painting and more like a student sitting in a gallery, studying the brush work, and learning to paint it themselves." — 1:33
> "The tool isn't the risk. What you pointed at is. Stay behind that second door and this becomes one of the most useful things you can run." — 2:58
> "Used honestly on your own projects, this collapses days of tedious rebuilding into a single command." — 7:29

## Tools and Resources Mentioned
- **AI Website Cloner template** — the 20k+ star GitHub repo (search: "AI Website Cloner" + Claude Code). Vendor: open-source community project, NOT the user's MiniMax Hermes Agent.
- **Claude Code (Anthropic)** — vendor: Anthropic's CLI coding agent (the recommended setup, also works with Cursor, Copilot, Gemini, ~12 other agents)
- **Next.js 16 + React 19 + TypeScript (strict) + shadcn/ui + Tailwind v4** — vendor: Vercel, Meta, Microsoft, shadcn, Tailwind Labs respectively — the modern stack the rebuild produces
- **Chrome flag for Claude Code** — lets the agent see the live browser

## Action Items
- [ ] Use the "use this template" button on the repo (don't clone the original).
- [ ] Before pointing it at any site: read that site's ToS. If the ToS says no scraping / no replication, don't use it.
- [ ] Allowed use cases: rebuild your own stuck site, recover lost source from a live site you own, learn by studying a great site's structure.
- [ ] After the rebuild, run your own visual review — the tool does it once, but you'll catch things it missed.
- [ ] Customize to make it yours before shipping — logos, copy, brand assets must be yours.

## Open Questions
- What's the exact repo URL? Search "AI Website Cloner" on GitHub; the video doesn't show the link on-screen.
- How does this interact with copyright on page layout vs. copyright on specific assets (images, fonts, copy)?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full HH:MM:SS transcript)</summary>

0:00 Someone built a free tool that rebuilds
0:02 almost any website with a single
0:04 command. It has over 20,000 stars on
0:08 GitHub.
0:09 You point it at a URL you type/clone
0:12 website and an AI agent goes to work. It
0:16 takes screenshots. It pulls the fonts
0:18 and the colors and it writes you a
0:21 clean, modern codebase from scratch. It
0:25 honestly looks like magic. But there is
0:27 a part almost nobody talks about the
0:31 line between using this brilliantly and
0:33 using it in a way that gets you sued. So
0:36 let's break down exactly how it works
0:39 and the right way to actually use it.
0:42 First what this actually is because the
0:44 name sounds a little scary. It's called
0:47 the AI website cloner template and the
0:50 key word there is template. It is not a
0:54 shady scraper that rips a site and hands
0:56 you a copy of its files. It is a
0:59 starting point on GitHub that turns your
1:02 AI coding agent into a reverse
1:05 engineering machine.
1:07 The recommended setup is claude code,
1:10 but it also works with cursor, copilot,
1:13 Gemini, and about a dozen other agents.
1:17 Now, here is the difference that
1:18 matters. A scraper copies files. This
1:22 one rebuilds. It studies how a page is
1:25 put together. And then it writes brand
1:28 new code that recreates it in a clean,
1:31 modern stack that you own.
1:33 Think of it less like photocopying a
1:35 painting and more like a student sitting
1:38 in a gallery, studying the brush work,
1:41 and learning to paint it themselves. And
1:43 that brings us to the part you need to
1:46 hear before you ever touch this. Because
1:50 a tool this powerful has two doors.
1:54 Behind the first door is trouble.
1:57 Cloning a competitor's website and
1:59 passing their design off as your own.
2:02 Copying logos, brand assets, or original
2:06 writing that belongs to someone else.
2:10 Scraping a site whose terms of service
2:12 say do not. Or worst of all,
2:15 impersonating a brand to trick people.
2:18 The project's own readme says it
2:20 plainly.
2:22 It must not be used for deceptive
2:24 purposes, impersonation, or any activity
2:27 that breaks the law.
2:29 Behind the second door is where this
2:31 tool earns its stars.
2:34 You own a website that is stuck on some
2:36 old platform and you want it rebuilt on
2:38 a modern one. Or your site is still
2:41 live, but the source code is gone. The
2:44 developer left and you need it back. or
2:47 you simply want to learn by taking apart
2:51 how a great site actually works. Same
2:54 exact tool. So here is the line to
2:56 remember. The tool isn't the risk. What
3:00 you pointed at is stay behind that
3:03 second door and this becomes one of the
3:05 most useful things you can run. So how
3:08 does it actually pull this off? When you
3:10 run the command, it kicks off a
3:12 fivephase pipeline. And this is the part
3:15 that is genuinely clever. Phase one is
3:18 reconnaissance. The agent opens the site
3:21 in a real browser and looks at it the
3:24 way a person would. It takes
3:26 screenshots. It extracts the design
3:28 tokens, the exact fonts, the colors, the
3:32 spacing, and it runs an interaction
3:35 sweep, scrolling, clicking, hovering,
3:39 and checking how the layout changes on
3:41 mobile versus desktop.
3:44 Phase two is the foundation. Before it
3:48 builds a single section, it lays the
3:50 groundwork. It writes in the real fonts,
3:54 the real color palette, and the global
3:56 styles, and it downloads every asset the
4:00 site uses, the images, the videos, the
4:03 icons. Now, the project already has a
4:08 skeleton that feels like the original.
4:10 Phase three is where most tools would
4:12 fall apart and where this one gets
4:14 serious. For every section of the page,
4:18 the agent writes a detailed spec file,
4:21 not a vague description,
4:24 the exact computed CSS values, the
4:27 different states a button can be in, the
4:30 behaviors, and the real content.
4:33 As the readme puts it, the builders get
4:36 all of this handed to them in line with
4:39 quote no guessing.
4:42 Phase 4 is the one that makes engineers
4:44 smile.
4:46 Instead of building the whole page one
4:48 slow piece at a time, it dispatches a
4:51 team of builder agents, each working in
4:54 its own isolated git work tree, one
4:57 agent per section.
4:59 the header, the hero, the footer, all
5:03 being rebuilt in parallel at the very
5:05 same time. And phase 5 brings it all
5:08 home.
5:10 It merges every work tree back together,
5:13 wires the sections into one finished
5:15 page, and then it runs a visual diff
5:19 comparing its rebuild against the
5:20 original side by side to see how close
5:24 it got. reconnaissance, foundation,
5:27 specs, parallel build, and a final
5:30 quality check. That is the whole
5:33 machine. And what you are left with
5:35 matters just as much as how you got
5:37 there. This does not hand you a pile of
5:40 tangled spaghetti code that nobody can
5:42 maintain. It builds on a clean modern
5:45 stack. Next dot js16
5:49 running React 19. Typescript in strict
5:54 mode, Shad, C, and UI components sitting
5:58 on top of Tailwind version 4. This is
6:01 the same kind of stack a senior team
6:04 would actually choose in 2026, which
6:06 means the result isn't a dead end. It is
6:09 a real code base that you can read,
6:11 change, and ship. Now, here is how
6:14 little it takes to start. Step one, on
6:18 the GitHub page, you click use this
6:20 template and make your own copy. You do
6:24 not clone the original repo directly.
6:27 Step two, you open your new copy and run
6:31 npm install. Step three, you start
6:34 clawed code with the Chrome flag so the
6:37 agent can actually see the browser. And
6:40 step four, you type /clone website and
6:43 paste in your link. You can even pass
6:46 several links at once in a single
6:48 command. That is it. From there, the
6:51 pipeline takes over and you customize
6:54 whatever you want once it is done. Now,
6:57 let me be straight with you because that
6:59 is the whole point of this channel. This
7:02 is not a magic button. AI still gets
7:06 details wrong, which is exactly why
7:08 phase 5 does a visual comparison instead
7:11 of just trusting itself. You will still
7:14 need to clean things up and make the
7:16 site genuinely yours. And the legal part
7:19 is on you, not on the tool. If a site's
7:22 terms say no, that is a no. But used
7:26 honestly on your own projects.
7:29 This collapses days of tedious
7:32 rebuilding into a single command. And
7:36 that is genuinely worth understanding.
7:39 So, if this was useful, here is how to
7:42 go deeper. Subscribe on YouTube and
7:45 follow along on Instagram and Facebook,
7:48 too, because that is where these
7:50 breakdowns drop first. And if you want
7:52 to support the channel and get even more
7:54 out of it, the channel membership on
7:57 YouTube is the best way to do that.
8:00 If you want my hands-on guides for
8:02 getting the most out of clo code and
8:04 building real things with AI, the links
8:06 are waiting for you down in the
8:08 description. One last thing, comment the
8:14 word reverse on this video and I will
8:17 send you a free website cloner playbook.
8:20 It has got the safe use checklist, the
8:22 full pipeline cheat sheet and the exact
8:25 setup commands all in one PDF.
8:30 Now go build something the right way.

</details>