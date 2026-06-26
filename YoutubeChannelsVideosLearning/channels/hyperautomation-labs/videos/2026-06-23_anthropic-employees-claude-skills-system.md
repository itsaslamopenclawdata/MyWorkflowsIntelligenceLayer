---
title: "Anthropic Employees Use Claude Skills Like THIS (Copy Their System)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-23"
duration_seconds: 660
video_id: "zTdjMfusSY8"
url: "https://www.youtube.com/watch?v=zTdjMfusSY8"
language: "en"
tags: [claude, claude-skills, anthropic, mcp, finance, legal, agentic-workflows, prompt-engineering, skill-creator, progressive-disclosure, claude-code]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-25"
---

# Anthropic Employees Use Claude Skills Like THIS (Copy Their System)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-23  **Duration:** 11:00  **Watch:** https://www.youtube.com/watch?v=zTdjMfusSY8

## TL;DR
Anthropic's own teams — finance, legal, engineering — quietly use Claude "Skills" (organized folders of instructions, scripts, and resources Claude auto-loads when a task matches) as onboarding guides for a new hire, not as one-off prompts. Finance has 70+ skills; one ("MFR") produces their monthly financial review 90–95% done before a human touches it, and the corporate finance lead credits Skills with giving her back 10–20 hours/week. Legal built per-practice-area Skills plus a Slack-pinned self-service review tool that returns risk levels + fixes (turnaround dropped from 2–3 days to ~24h). Skills load in three layers (name+description ~100 tokens → instructions ≤5K tokens → bundled scripts/files) so 100 Skills cost almost nothing at idle. Anthropic ships an official "skill creator" plugin that A/B-tests Skills vs. tokens, and Skills pair with MCP (wiring) for tool access. Warning: a Skill can run code — treat installing one like installing software.

## Key Insights
- A Claude Skill is NOT a prompt or a setting — it's an organized folder of instructions, scripts, and resources that Claude discovers and loads on its own when a task matches. Anthropic's favorite analogy: "writing an onboarding guide for a new hire." A prompt is retyped every time; a Skill is written once and Claude keeps it forever. (0:54)
- Progressive disclosure (3-level loading) is why you can install 100 Skills without overload. L1 startup: name + 1-line description, ~100 tokens each. L2 match: full instruction file, typically <5,000 tokens. L3 only if needed: bundled scripts/files — code never enters the conversation, only the result does. (2:05)
- Finance team runs 70+ Skills from one shared repo. The MFR (Monthly Financial Review) Skill produces the MFR 90–95% finished before a human reviews it; a weekly revenue/compute report that used to take hours now takes 30 minutes. CFO Krishna Rao on the Invest Like the Best podcast. (2:58)
- Alice Fong (corporance finance lead, Anthropic) publicly credits Skills with giving her back 10–20 hours every week: "Claude holds the integrity layer underneath the work. So my time goes to the narrative on top." That quote IS the playbook. (3:40)
- Legal team's pattern: one Skill per practice area — employment law, commercial agreements, privacy. Each Skill teaches Claude the voice (Mark Pike had Claude study 10 of his past memos until it matched his style) AND the format a product/employment lawyer would use. (4:20)
- The legal team's "self-service review" Skill is the killer app: pinned as a Slack command, anyone in the company runs marketing copy or a contract through it and gets a low/medium/high risk grade plus the fix (rights to this logo? is this data accurate? missing ™ symbol?). Turnaround dropped from 2–3 days to ~24 hours. (4:50)
- The meta-pattern across every Anthropic team: nobody is winning by typing cleverer prompts. They take the procedures locked in their heads — how a report is built, how a memo is written, which rules they enforce — and encode each one ONCE as a Skill. (5:40)
- You are already using Skills even if you don't know it: when you ask Claude on the web to make a PowerPoint, Excel model, Word doc, or fill a PDF, it's silently running Anthropic's pre-built document Skills behind the scenes. Skills are not a niche power-user feature — they're the layer that turns a general assistant into a specialist who already knows your job. (6:00)
- Building your first Skill takes ~5 minutes. It's a folder with one file: `skill.md`. Path: `~/.claude/skills/<skill-name>/skill.md` for personal Skills, or in the repo for project Skills shared by the team. On Claude.ai you upload as a zip. The whole file = a tiny header with description (the line Claude reads to decide when to fire) + body in plain English. (6:25)
- You can inject live data into a Skill body — e.g. a `git diff` line that drops the diff straight into Claude's context — then "summarize these changes in 3 bullets and flag anything risky." Save it, ask "what did I change?" and Claude loads the Skill automatically, or invoke with `/skill-name` on demand. (7:00)
- Anthropic ships an official "skill creator" plugin that helps you WRITE Skills and even A/B-tests them — measuring whether the Skill actually improves Claude's answers vs. the extra tokens it costs. (8:02)
- Skills pair with MCP (Model Context Protocol): MCP is the wiring that connects Claude to your tools and data; Skills are the know-how for using them. The legal team combines both. Everything you need is on the public `Anthropic/skills` repo on GitHub, including the real document Skills you can read and copy. (8:19, 8:33)
- Honest warning, straight from Anthropic: only install Skills from sources you trust. A Skill can run code and call tools, so installing one is exactly like installing software — don't paste a random Skill you found online into a work machine. (8:43)

## Notable Quotes
> "Their own finance team, the people who report the numbers to the board, quietly built over 70 custom Claude skills. And their CFO went on the record saying one of them now produces the company's entire monthly financial review. 90 to 95% finished before a human even looks at it." — 0:04
> "A skill is not a prompt, and it's not a setting. … building a skill is like writing an onboarding guide for a new hire." — 0:52
> "The people getting huge results from Claude aren't writing better prompts. They've stopped writing prompts for repeated work entirely and started writing onboarding guides their AI keeps forever." — 1:44
> "Claude holds the integrity layer underneath the work. So, her time goes to the narrative on top." — Alice Fong, Anthropic corporate finance lead (3:52)
> "A skill can teach Claude to write like an employment lawyer or format a memo the way a product lawyer would." — Mark Pike, Anthropic lawyer (4:33)
> "Turnaround dropped from two or three days to about 24 hours." — 5:20
> "Nobody at Anthropic is winning by typing cleverer prompts. They are taking the procedures locked in their heads … and encoding each one once as a skill." — 5:42
> "Skills are not a niche power user feature. They are the layer that turns a general assistant into a specialist who already knows your job." — 6:14
> "A skill can run code and call tools, so treat installing one exactly like installing software." — 8:49
> "The teams running circles around everyone else are not more talented with AI. They just stopped re-explaining themselves and wrote [it] down once." — 9:29

## Tools and Resources Mentioned
- **Claude Skill** — folder of instructions/scripts/resources Claude auto-loads when a task matches. Anthropic's preferred unit of repeated work.
- **Progressive disclosure** — 3-level loading (name+desc ~100 tok → instructions ≤5K tok → scripts/files only if needed). The reason 100 Skills cost ~nothing at idle.
- **Claude Code** — Anthropic's CLI/dev-product; Skills live in `~/.claude/skills/` (personal) or in-repo (project, shared by the team).
- **Claude.ai** — Skill upload as a plain zip file. Same mechanism the finance/legal teams use, just smaller.
- **MFR (Monthly Financial Review) Skill** — Anthropic finance's flagship Skill: produces the MFR 90–95% ready before human review.
- **Skill Creator (Anthropic plugin)** — official tool that helps you write Skills AND A/B-tests them (Skill quality vs. added tokens).
- **MCP (Model Context Protocol)** — wiring that connects Claude to your tools/data; Skills are the know-how for using those connections. Legal team uses both together.
- **Document Skills (Anthropic, pre-built)** — PowerPoint, Excel, Word, PDF Skills Claude runs silently on the web today.
- **Anthropic/skills** (GitHub) — public repo containing real document Skills and templates to copy.
- **Claude for sales playbook** + **certification prep kit** — referenced as additional Hyperautomation Labs guides.
- **Claude Code guide** + **OpenAI Codex guide** — other Hyperautomation Labs deep-dives referenced in the outro.

## GitHub Repos and URLs Referenced
- https://github.com/anthropics/skills — official Anthropic Skills repo (document Skills + templates, copyable)
- https://www.anthropic.com — Anthropic (Skill Creator plugin, Claude Code, MCP)
- https://www.youtube.com/watch?v=zTdjMfusSY8 — this video
- Reference podcast: Invest Like the Best — Krishna Rao (Anthropic CFO) on the 70+ finance Skills
- Hyperautomation Labs guides linked in description: Claude Code guide, OpenAI Codex guide, Claude for Sales playbook, Certification prep kit
- Free "skill starter kit" (skill.md templates + finance/legal patterns): comment "onboard" on the video or use the link in the description

## Action Items
- [ ] Pick the ONE report you rebuild every week or every month and turn it into a Skill — spell out exact sections, data sources, and format. Then you REVIEW instead of REBUILD. (the "finance move")
- [ ] Take the rules and style you repeat to people constantly (brand guidelines, code standards, hiring bar) and build a review Skill that returns low/medium/high risk levels + fixes. Hand your own judgment to the whole team. (the "legal move")
- [ ] Start absurdly small: one folder, one Skill, one `skill.md` file, one task you're sick of re-explaining. Five-minute first build.
- [ ] When writing a Skill body, inject live data directly into the instructions (e.g. `git diff` line) instead of asking the user to paste it.
- [ ] Run any new Skill through Anthropic's Skill Creator A/B tester before promoting it to the team repo — verify the answer quality is worth the token cost.
- [ ] Combine Skills with MCP: Skills = know-how, MCP = wiring. Use them together for tool-using Skills (legal team's pattern).
- [ ] Treat Skill installation like software installation — only install from sources you trust; never paste a random Skill into a work machine.

## Open Questions
- The video shows the legal team's Slack-pinned review tool — is the Skill itself public on `Anthropic/skills`, or only the document Skills? (worth checking the repo before claiming it's copyable.)
- For the "MFR produces 90–95% of the monthly review" claim, what's the residual 5–10% that still needs a human? (narrative framing? edge cases? regulatory footnotes?) — would change how aggressively a smaller team could rely on this pattern.
- Skills load scripts "where the code never enters the conversation, only the result does" — what's the exact sandbox boundary? Can a Skill exfiltrate data via its scripts? (Anthropic's warning implies yes — but how is that enforced technically?)
- "Skill Creator" A/B tests Skill vs. token cost — is that a public Anthropic tool, an internal one, or a Skill-Creator-as-a-Skill meta-pattern? Worth confirming before recommending.
- If finance uses a shared repo of 70+ Skills, how do they handle Skill versioning when one team's instructions change and another team's downstream Skill depends on the old version?
- For solo operators / non-Anthropic teams: at what minimum task-volume does a Skill beat a saved prompt? (the "absurdly small start" advice is right, but where's the break-even?)

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 11:00 transcript)</summary>

0:00 Anthropic just accidentally showed
0:02 everyone the future of work.
0:04 Their own finance team, the people who
0:06 report the numbers to the board,
0:08 quietly built over 70 custom Claude
0:10 skills.
0:11 And their CFO went on the record saying
0:13 one of them now produces the company's
0:15 entire monthly financial review.
0:17 90 to 95% finished before a human even
0:20 looks at it.
0:21 Their legal team did the same thing. So
0:23 did engineering.
0:24 Here's the strange part.
0:26 Almost nobody outside Anthropic uses
0:29 skills this way. And most people don't
0:31 even know what they are.
0:32 So I read every blog post, every doc,
0:35 and the CFO's full interview, and pulled
0:37 out exactly how Anthropic's own
0:40 employees use Claude skills, and the
0:42 simple way you can copy each one.
0:45 Stick around because the last pattern is
0:48 the one quietly saving people 10 to 20
0:50 hours a week.
0:52 First, forget what the name makes you
0:54 assume.
0:55 A Claude skill is not a prompt, and it's
0:58 not a setting.
1:00 Anthropic's own definition is this.
1:03 A skill is an organized folder of
1:05 instructions, scripts, and resources
1:08 that Claude discovers and loads on its
1:11 own
1:12 exactly when a task needs it.
1:15 Their favorite analogy, and it's the one
1:17 that makes it click, is that building a
1:20 skill is like writing an onboarding
1:22 guide for a new hire. Think about that.
1:25 A prompt is something you retype every
1:28 single time for one conversation.
1:30 A skill is written once.
1:33 From then on, Claude already knows your
1:35 format, your rules, your process, the
1:37 way a trained employee would.
1:39 You stop re-explaining yourself.
1:42 That's the whole shift.
1:44 The people getting huge results from
1:45 Claude aren't writing better prompts.
1:48 They've stopped writing prompts for
1:49 repeated work entirely
1:51 and started writing onboarding guides
1:53 their AI keeps forever.
1:55 Obvious question.
1:57 If Anthropic's finance team has 70 of
2:00 these,
2:01 doesn't that overload Claude?
2:03 This is the clever part.
2:05 And it's worth 30 seconds.
2:07 Skills load in three levels. Level one,
2:09 at startup, Claude only sees each
2:11 skill's name and one-line description,
2:13 about 100 tokens each. That's it it. 70
2:17 skills cost almost nothing. Level two,
2:19 the moment your request matches a skill,
2:22 Claude opens its instruction file,
2:24 usually under 5,000 tokens,
2:26 and reads the full procedure.
2:27 Level three,
2:29 only if it actually needs them, it pulls
2:31 in extra files or runs bundled scripts,
2:34 where the code never even enters the
2:36 conversation,
2:37 only the result does.
2:39 Anthropic calls this progressive
2:40 disclosure.
2:41 In plain English, you can install 100
2:43 skills and each one stays invisible and
2:45 free until the exact second it's useful.
2:49 That is why a single person can quietly
2:51 carry an entire department's worth of
2:53 expertise inside one Claude.
2:56 Let's start with the team that shocked
2:57 me most.
2:58 Finance.
3:00 On the Invest.
3:01 Like the best podcast, Anthropic's CFO
3:04 Krishna Rao said,
3:05 they now have a library of over 70
3:07 finance skills that everyone on the team
3:09 can access
3:10 through one shared repository.
3:13 One of them
3:14 is called the MFR skill.
3:16 Monthly financial review.
3:19 In his words, it can produce their
3:20 monthly financial review
3:22 90 to 95% ready. Let that land.
3:27 The most scrutinized document a finance
3:29 team produces,
3:30 nearly done automatically.
3:33 A weekly revenue and compute report that
3:35 used to take hours,
3:37 now takes 30 minutes.
3:39 And in a separate post, Anthropic's own
3:41 corporate finance lead, Alice Fong,
3:44 said Claude gave her back 10 to 20 hours
3:47 every week.
3:48 Her line is the thesis of this whole
3:50 video.
3:52 Claude holds the integrity layer
3:53 underneath the work.
3:55 So, her time goes to the narrative on
3:57 top.
3:58 Here is how you copy it.
4:00 Pick the one report you rebuild every
4:02 week or every month.
4:04 Write a skill that spells out the exact
4:06 sections,
4:07 the data sources, and the format.
4:10 Now, you review and add judgment instead
4:13 of rebuilding it from scratch every
4:14 time.
4:15 Next, the legal team.
4:17 And this one is even more clever.
4:20 Anthropic lawyer Mark Pike described
4:24 writing a separate skill for each
4:26 practice area.
4:27 One for employment law, one for
4:29 commercial agreements, one for privacy.
4:32 His quote,
4:33 a skill can teach Claude to write like
4:37 an employment lawyer
4:38 or format a memo the way a product
4:41 lawyer would.
4:42 To get the voice right, they had Claude
4:44 study 10 of his own past memos until it
4:47 matched his style.
4:49 But, the best example is this.
4:51 They built a self-service review tool
4:54 and pinned it as a hit in Slack.
4:57 Anyone in the company can run their
4:59 marketing copy or a contract through a
5:01 skill loaded with the legal team's real
5:04 guidance. And it flags each issue as
5:07 low, medium, or high risk with the fix.
5:11 Do you have rights to this logo?
5:13 Is this data accurate?
5:15 This trademark needs a symbol.
5:18 Turnaround dropped from two or three
5:20 days to about 24 hours.
5:22 Here is how you copy it.
5:24 Take the rules you repeat to people
5:25 constantly.
5:27 Your brand guidelines, your code
5:28 standards, your hiring bar.
5:31 Put them in a skill that reviews any
5:33 input and returns risk levels with
5:35 fixes.
5:37 You have just cloned your own judgment
5:38 and handed it to your whole team.
5:40 Step back and you see the pattern across
5:42 every team.
5:43 Nobody at Anthropic is winning by typing
5:45 cleverer prompts.
5:47 They are taking the procedures locked in
5:49 their heads, the way a report is built,
5:51 the way a memo is written, the rules
5:53 they enforce,
5:54 and encoding each one once as a skill.
5:58 And you are actually already using this.
6:01 When you ask Claude on the web to make a
6:03 PowerPoint, an Excel model, a Word doc,
6:07 or fill out a PDF, it is silently
6:10 running Anthropic's pre-built document
6:13 skills behind the scenes.
6:14 Skills are not a niche power user
6:16 feature.
6:18 They are the layer that turns a general
6:20 assistant into a specialist who already
6:22 knows your job. So, let me show you how
6:24 to build your first one.
6:25 It is genuinely about 5 minutes.
6:28 Here's the entire thing, start to
6:30 finish.
6:31 A skill is just a folder
6:33 with one file inside it called skill.md.
6:37 In Claude code, you make a folder in
6:39 your home directory {dot} Claude/skills/
6:42 then your skills name.
6:44 Inside skill.md,
6:46 you write a tiny header,
6:48 a description of what the skill does and
6:50 when to use it.
6:52 That one line is what Claude reads to
6:53 decide when to fire it.
6:55 And then below it, your actual
6:57 instructions in plain English.
6:59 That's it. Let me make it real.
7:02 Say you want Claude to summarize your
7:04 code changes.
7:06 Your description says, "Use this when
7:09 the user asks what changed or wants a
7:12 commit message."
7:14 Then in the body,
7:16 you can even inject live data.
7:18 A line that runs git diff
7:21 and drops the result straight in.
7:23 Followed by
7:25 "Summarize these changes in three
7:26 bullets
7:27 and flag anything risky."
7:29 Save it.
7:30 Now, you either just ask
7:32 "What did I change?" and Claude loads it
7:34 automatically, or you type {slash} the
7:37 skills name to run it on demand.
7:41 Personal skills
7:42 live in dot Claude / skills.
7:45 Project skills go in the repo.
7:47 So your whole team shares them.
7:50 On Claude.ai,
7:51 you can upload a skill as a simple zip
7:53 file.
7:54 That is the same mechanism
7:56 Anthropic's finance and legal teams are
7:58 using, just smaller.
8:00 Once you have made one, a few things
8:02 make this serious.
8:03 Anthropic ships an official tool called
8:06 skill creator,
8:07 a plugin
8:09 that helps you write skills,
8:10 and even AB tests them,
8:13 measuring whether the skill actually
8:14 improves Claude's answers
8:16 versus the tokens it costs.
8:19 Skills also pair with MCP.
8:22 Think of MCP as the wiring that connects
8:24 Claude to your tools and data,
8:26 and skills as the know-how for using
8:29 them.
8:30 Anthropic's legal team combines both.
8:33 There is everything you need
8:34 on the public Anthropic/skills repo on
8:37 GitHub,
8:38 including the real document skills you
8:40 can read and copy.
8:42 One honest warning, because Anthropic
8:43 has said it themselves,
8:44 only install skills from sources you
8:46 trust.
8:47 A skill
8:49 can run code and call tools, so treat
8:51 installing one
8:52 exactly like installing software.
8:54 Don't paste a random skill you found
8:56 online into a work machine.
8:58 So here is your copy this checklist.
9:00 One, the finance move.
9:03 Take a report you rebuild on a schedule
9:04 and turn it into a skill,
9:06 so you review instead of rebuild.
9:08 Two,
9:09 the legal move.
9:11 Take the rules and the style you repeat
9:13 to everyone and turn them into a review
9:14 skill that returns risk levels and
9:16 fixes.
9:17 Three,
9:18 start absurdly small.
9:21 One folder,
9:22 one skill,
9:23 dot MD file,
9:25 one task you're sick of re-explaining.
9:28 The teams running circles around
9:29 everyone else are not more talented with
9:31 AI.
9:32 They just stopped re-explaining
9:34 themselves and wrote put down once.
9:36 Do that this week even for one task
9:39 and you will feel the same 10 to 20
9:41 hours a week shift
9:42 Anthropic's own people are talking
9:44 about.
9:45 If this changed how you think about
9:47 working with Claude,
9:48 do me one favor.
9:50 Subscribe
9:51 whether you're watching on YouTube,
9:53 following on Facebook, or over on
9:54 Instagram.
9:56 I go deep on exactly this Claude, Claude
9:58 code, and the AI workflows that actually
10:01 save time
10:02 every single week
10:04 and I do the costly digging so you don't
10:06 have to.
10:07 Hit subscribe and the bell
10:09 so the next one finds you.
10:11 And if you want to go further, I have
10:13 put everything together for you.
10:15 Comment the word onboard and I'll send
10:17 you a free skill starter kit.
10:20 The exact skill.md
10:22 templates from this video.
10:24 Plus
10:25 the finance and legal patterns
10:27 ready to copy.
10:29 The link is in the description, too.
10:32 If you want the deep stuff, I have four
10:34 guides linked below.
10:35 My Claude code guide, my OpenAI Codex
10:38 guide,
10:39 the Claude for sales playbook,
10:41 and my certification prep kit
10:43 built for people who want to get
10:45 genuinely dangerous with this.
10:47 Comment your favorite Anthropic skill.
10:49 Subscribe on YouTube, Facebook, and
10:51 Instagram
10:52 and I'll see you in the next one.
10:54 And the description has a tip if you
10:56 want to watch a little faster.

</details>
