---
title: "I Rebuilt All 7 Claude Fable 5 Demos Anthropic Showed 4.2M People — Here's the Scoreboard"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-15"
duration_seconds: 979
video_id: "JQEPHFbLPEY"
url: "https://www.youtube.com/watch?v=JQEPHFbLPEY"
language: "en"
tags: [AI, AI coding, AI demos, AI export controls, AI news, Anthropic, Boeing 747 benchmark, Claude, Claude Code, Claude Fable 5]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-15"
---

# I Rebuilt All 7 Claude Fable 5 Demos Anthropic Showed 4.2M People — Here's the Scoreboard

**Channel:** Hyperautomation Labs  **Published:** 2026-06-15  **Duration:** 16:19  **Watch:** https://www.youtube.com/watch?v=JQEPHFbLPEY

## TL;DR
Reproductions of all 7 official Claude Fable 5 launch demos, each graded ONE-SHOT / FIXED / PARTIAL. Scoreboard: 3 ran clean on first try (goldfish pond, drowned gothic shader, 747 before its self-critique loop), 2 needed tuning (Suminagashi ink fluid, Minecraft wooden house spec), 1 was honest about its broken physics (poseable ragdoll with "paper legs"), and 1 was never a one-shot at all (soccer overlay is a real CV pipeline, not a magic trick). Mid-test, the US government hit Anthropic with an export-control directive that pulled Fable 5 from foreign nationals — every one of these builds is now an artifact of a very short window.

## Key Insights
- **Three-call test framework for grading AI demos**: ONE-SHOT (worked first try), FIXED (needed cleanup passes), PARTIAL (headline over-promised vs. build). Same prompt, same constraints, browser-screenshot verification — no exception. (01:14)
- **Self-verifying loop is the actual product, not the 747**: the most important demo on the list is the airplane only because the model screenshotted its own renders from 6 angles, critiqued its silhouette, and re-ran geometry — 6 iterations to a 747-400 with double-bubble fuselage, swept-wing kink, and underslung engines. That loop is what to port into your own builds. (05:06)
- **Fluid simulation is the trap, not the visual**: suminagashi ink demo looked like a fluid but was actually a flat gray wash settling too slowly. Two tuning passes on drag and ink density got real marbled filaments. If you ask a model for "fluid," audit the physics, not the look. (03:34)
- **Spec-following test beats aesthetic test**: the Minecraft wooden house benchmark stripped creativity and forced the model to obey rules (no hollow rooms, door faces path, roof has no gaps, every room furnished + lit). 875 blocks, passes walkthrough. This is the test format that maps to real shipping work. (08:14)
- **Honest demo is rare in launch week**: the poseable ragdoll dev admitted the "paper legs" and backwards knees in the same tweet as the launch clip. The reproduction is grade REAL with paper legs — the model pinned feet to floor, arm floats, no weight. (09:37)
- **Soccer overlay is a CV pipeline in costume**: a glowing ball trail with km/h readout looks like a one-prompt build, but the underlying rig is object detection + body-pose tracking + months of engineering. Fable 5 improved it, didn't conjure it. Reproducing the overlay without the rig gives you a physics sim wearing a CV mask, with decorative confidence %. (11:02)
- **The official showcase chose 7 visual toys, zero business apps**: no agent doing real work, no bug-fix demo, no migration test. Visual demos go viral because they're judgeable in one second. The model can probably do the 50M-line migrations — they just don't fit in a 4.2M-view thread. (12:33)
- **Government export-control directive on June 13 pulled Fable 5 from all foreign nationals**, including Anthropic's own staff, over an alleged jailbreak. Anthropic pushed back, said the demo only surfaced known-minor issues, but complied. The free launch window went from "deadline June 23" to "deadline June 13 + political." (14:06)
- **Reproducible test recipe**: 7 prompts, word-for-word, browser-verified, one-file self-contained, no libraries. You can paste them into any strong model and run the same scoreboard yourself. (01:14)

## Notable Quotes
> "The showcase is the appetizer." — 13:55
> "Every single demo the official account chose is a visual toy. Not one business app. Not one agent doing real work." — 13:25
> "It was a real project that a very good model joined. The thread implies one prompt. The truth is more impressive and less viral." — 12:25
> "A model powerful enough to grade its own airplane and contained before most people even got to try it." — 15:21

## Tools and Resources Mentioned
- **Claude Fable 5** (Anthropic) — vendor: third-party Anthropic model, NOT the user's MiniMax Hermes Agent. Public version of the Mythos-class model; was free inside Claude subscriptions at launch, now restricted by US export controls.
- **Claude Code** (Anthropic) — vendor: third-party Anthropic CLI, NOT the user's Hermes stack.
- **3JS (Three.js)** — referenced by the 747 demo's creator as the library the result "never shipped" from.
- **HuggingFace** — Clem Delangue (head of product) posted the 747 self-critique prompt that became the scoreboard's most important demo.
- **Voxil / browser voxel world** — the Minecraft-equivalent sandbox used to re-run the wooden house spec.

## GitHub Repos and URLs Referenced
- https://www.youtube.com/watch?v=JQEPHFbLPEY — video
- @midori_tatsuta (the goldfish pond original builder) — credited in description
- @wharton (Ethan Mollick, drowned gothic shader) — credited in description
- Free 7-Demo Scorecard: comment "SEVEN" on the YouTube video to receive prompts + grades + the self-checking loop trick

## Action Items
- [ ] Port the self-critique loop (screenshot → critique → fix → re-render) into your own AI build workflow — it's the highest-leverage pattern in the scoreboard.
- [ ] When evaluating any "one-prompt AI demo," ask: is this a real one-shot, or is there a CV/data pipeline underneath in costume? The soccer overlay is the test case.
- [ ] If you build AI products for non-US users, audit your dependence on US-hosted frontier models. June 13 set a precedent — export controls can rip a model out in days.
- [ ] Run the spec-following test (rules-of-engagement prompt) on your own model picks before locking in for a project — it's a better predictor of shipping success than aesthetic demos.

## Open Questions
- Which "minor, already known issues" did the Fable 5 demo surface that triggered the export-control letter? The video says "alleged jailbreak" but doesn't name the actual finding.
- Did Anthropic restore Fable 5 for foreign nationals after the directive, or is the ban still active? The video's date is mid-test, before resolution.
- Are the 7 demo prompts available outside the YouTube comment funnel? The guide is gated on "comment SEVEN" — not machine-readable.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 16:19 transcript)</summary>

```
0:00 2 days ago, the official Claude account
0:03 posted seven demos to 4.2
0:08 million people with one line. Here are
0:11 some projects people already built with
0:13 Fable 5, a goldfish pond, a Boeing 747,
0:18 an infinite Gothic city drowning in the
0:21 ocean. Most people scrolled, said,
0:24 "Wow," and kept moving. I did something
0:27 else. I took all seven prompts, opened a
0:31 blank editor, and tried to rebuild every
0:35 single one myself from scratch blind.
0:38 Then I graded each one on a simple
0:40 scale. Did it work on the first try? Did
0:44 it need fixes or did it quietly not work
0:48 at all? Seven demos, seven receipts. By
0:53 the end, you will know which of these
0:54 are real oneshot magic, which take more
0:57 hands than the threads admit and which
1:01 one on that list is not what it looks
1:02 like. There is also a twist I did not
1:06 see coming when I started this. While I
1:08 was testing, the government stepped in.
1:11 Let me show you the scoreboard. First,
1:15 the rules because a fair test needs
1:18 them. Fable 5 launched on June 9th.
1:22 It is the public version of Anthropics
1:24 Mythos class model, the strongest thing
1:27 they have ever handed to ordinary users
1:30 and right now it is free inside Claude
1:34 subscriptions. The official accounts
1:36 seven demos were the highlight reel. So
1:40 here is exactly what I did with each
1:42 one. I used the same prompt the original
1:46 builder used word for word where I could
1:48 find it. Everything had to be
1:51 self-contained.
1:53 The same bar they set, usually a single
1:56 file with no outside libraries, and
1:58 nothing counted as done until I loaded
2:00 it in a real browser, took screenshots,
2:03 and looked at them with my own eyes.
2:06 Three possible grades, one shot if it
2:09 ran correctly on the very first try,
2:11 fixed if it worked but needed cleanup
2:14 passes, and partial if the headline
2:17 turned out bigger than the build. Demo
2:19 one, the one everybody shared. A
2:22 Japanese developer posted it with one
2:24 line. With just Fable 5, an app that
2:26 lets you feed goldfish. You click a
2:29 pond, food drops, and the fish swim over
2:32 and eat it. It looks like nothing.
2:36 It is exactly the kind of thing that is
2:38 deceptively hard because beautiful water
2:42 plus fish that wander then notice food
2:45 then chase it then bump around each
2:48 other instead of overlapping is a dozen
2:51 little systems pretending to be one. So
2:54 I handed my editor the same brief. One
2:57 self-contained file. No libraries. Here
3:00 is what came back. a pond with sun rays,
3:04 lily pads, and 11 distinct goldfish,
3:07 each with a flowing procedural tail.
3:09 Then I clicked the water. Food scattered
3:12 across the surface, and the whole school
3:14 turned and converged on it. One fish
3:17 caught midbite with a little splash. It
3:20 ran on the first try. 21 kilobytes of
3:24 code. No errors. Grade one shot. One
3:28 down.
3:30 This is the easy end of the scale. It
3:32 gets harder fast. Demo 2 was a dare.
3:36 Another developer posted it saying, "I
3:39 deliberately threw a tough challenge at
3:40 it, expecting it to fail." The
3:43 challenge, an effect where ink melts
3:46 together like a fluid.
3:48 Real Japanese ink marbling, where you
3:51 drop sumi black and indigo onto water
3:54 and they swirl and blend like smoke.
3:57 That word fluid is the trap. Anyone can
4:01 fade two colors together. Actually
4:04 simulating fluid means solving the same
4:07 equations that model real water on the
4:10 graphics card 60 times a second. So that
4:14 is what I asked for. The first build ran
4:18 with no errors. But watch what happened.
4:22 The colors spread and then over a few
4:26 seconds they all blurred into one flat
4:29 gray wash. Technically a fluid.
4:33 Aesthetically mud. The fix was not a bug
4:38 fix. It was a physics fix. The motion
4:41 was settling too slowly and the black
4:43 ink was drowning every other color. Two
4:46 tuning passes later, the drag pulls the
4:49 ink into real marbled filaments. green
4:51 and salmon and blue threading through
4:54 each other in a spiral. That is genuine
4:57 fluid simulation, not a gradient. Grade
5:00 fixed. It got there. It just needed a
5:03 steadier hand than one prompt. Demo 3 is
5:07 the one that made even the skeptics go
5:09 quiet. The head of product at
5:11 HuggingFace gave Fable a prompt that is
5:15 really an instruction to grade its own
5:17 work. Build the most realistic Boeing
5:20 747 in 3D in code. Then, and this is the
5:23 important part, build a camera system.
5:26 Look at your own renders and loop until
5:29 you are satisfied. No reference images,
5:32 just shapes, math, and selfcorrection.
5:36 So, I ran the same loop. Round one
5:39 looked like this. A plane sure, but the
5:41 hump was too short, the wings too wide.
5:44 It read more like an Airbus than a 747.
5:48 And then the model did the thing that
5:50 makes this demo special. It took
5:53 screenshots from six different angles,
5:56 critiqued its own silhouette, and fixed
5:58 the geometry round after round. The hump
6:02 grew into that iconic upper deck. The
6:06 wings got their swept kink and their
6:08 winglets. A weird little nub on the nose
6:10 got sanded down over three separate
6:12 passes. Six iterations later, that is a
6:16 747400
6:18 double bubble fuselage, four underslung
6:21 engines, full landing gear, all built
6:24 from geometry that critiques itself in a
6:26 loop. The creator of 3JS himself looked
6:30 at the community results and said,
6:33 "These models are now inventing their
6:35 own geometry tricks. The library never
6:38 shipped."
6:39 This is the most important demo on the
6:41 whole list. And it is not because of the
6:44 airplane. It is because the model could
6:47 see its own mistakes and fix them
6:50 without me in the loop. Great. It
6:53 compiled first try, then improved itself
6:56 six times. Call that earned. Demo 4 came
6:59 from Warton Professor Ethan Mollik, and
7:02 it is pure showing off. One prompt.
7:05 Create a shader, just math, no images,
7:09 of an infinite city of neo gothic towers
7:12 half drowned in a stormy ocean with huge
7:15 waves. A shader is about the hardest way
7:19 there is to make a picture. You do not
7:22 place anything. You write one math
7:24 formula that every pixel on the screen
7:27 runs at the same time. And out of that
7:30 single formula, a whole world is
7:32 supposed to appear. So I asked for the
7:34 drowned Gothic city. Rows of dark towers
7:37 with spires fading into storm fog. Waves
7:41 crashing between them. Rain, lightning
7:44 washing the whole scene. Cold for a
7:46 frame. It compiled on the first try. No
7:49 errors. And then a make it better pass.
7:52 Added the lightning bolts, the lit
7:54 windows, and sharper waves. The entire
7:58 flooded Cathedral City is one page of
8:00 math. grade one shot. That is three of
8:06 seven that ran clean on the first
8:08 attempt. But the next one is a
8:11 completely different kind of test. Demo
8:14 5 looks the simplest and is secretly the
8:17 strictest. A tester who benchmarks AI
8:21 models by making them build in Minecraft
8:23 posted a wooden house by Fable 5 Max
8:27 Reasoning.
8:29 The catch is in his setup. He uses what
8:32 he calls a safe system prompt, a list of
8:35 rules that strips out creativity and
8:39 forces the model to be functional
8:41 instead. No empty shells. The door has
8:45 to face the path. The roof cannot have
8:48 gaps. Every room has to be furnished and
8:51 lit. So I reproduced both the house and
8:54 the rule book in a browser voxil world.
8:57 lock corners, plank walls, a proper
8:59 pitched roof, a porch, and a path
9:01 leading to the door. And then the rule
9:04 that actually matters. Inside is not a
9:07 hollow box. There is a bed, a table, a
9:11 chair, bookshelves, a carpet, and three
9:15 torches genuinely casting light across
9:18 the room. 875 blocks, and it passes the
9:23 walkth through, grade, fixed, and
9:26 functional. It earns its pass because
9:29 the test was never can you make a cube.
9:32 It was can you follow a spec you are not
9:35 allowed to argue with. Demo 6 is my
9:38 favorite because the person who posted
9:40 it was honest and honesty is rare in a
9:43 launch week. A developer built a
9:46 poseable vauil character. You grab a
9:49 hand or a hip, drag it, and the whole
9:51 soft body follows along. But he added a
9:54 line that most people skipped right
9:56 past. Still work to do on weight,
9:58 gravity is so wooi and the paper legs.
10:03 So I rebuilt it and I learned exactly
10:05 what he meant. A blocky figure with
10:08 control points on the hands, the feet,
10:10 the hips, and the head. I drag the right
10:14 hand up. The arm raises and the shoulder
10:17 and torso lean into the pull. It looks
10:20 alive. And then you push on it and the
10:24 cracks show. The character only stands
10:28 at all because I pinned its feet to the
10:31 floor like a puppet on a stand. There is
10:34 no real weight to it. The knees bend
10:37 backwards. The arms float.
10:40 This is the honest edge of the whole
10:42 launch. The kind of physics that makes a
10:45 body actually fall and catch itself
10:48 needs more than the trick everyone is
10:50 using right now. And he said so out loud
10:53 while everyone else posted only their
10:55 best angle. Grade real with paper legs.
10:59 Exactly as advertised. Demo 7 is the one
11:03 I have to be careful about because it is
11:06 both the most impressive and the most
11:09 misunderstood. A computer vision
11:11 developer posted a clip of Fable 5 with
11:14 the line, "Help me shoot this soccer
11:16 ball faster and a gorgeous overlay
11:19 tracking a ball with a glowing speed
11:22 colored trail." Here is the part the
11:24 screenshot does not tell you. That is
11:27 not a one-prompt build.
11:30 He films himself shooting real soccer
11:32 balls and behind that clip is a real
11:35 engineering pipeline, object detection,
11:39 body post tracking, months of work.
11:42 Fable 5 did not conjure that out of
11:44 nothing. It helped him improve it. So I
11:47 was honest with myself. I could not
11:50 reproduce his computer vision rig in an
11:52 afternoon and neither could a single
11:54 prompt. What I could rebuild was the
11:56 overlay itself.
11:59 the speed colored trail, the tracking
12:00 box, the live kilometers per hour,
12:03 automatic goal detection.
12:06 But underneath my version is a physics
12:08 simulation wearing a computer vision
12:10 costume. The confidence percentage is
12:13 pure decoration. And that is the whole
12:15 point. Grade partial, not because Fable
12:19 failed, because this one was never a
12:22 magic trick. It was a real project that
12:25 a very good model joined. The thread
12:27 implies one prompt. The truth is more
12:30 impressive and less viral. So here is
12:33 the scoreboard. Seven demos.
12:36 Three of them ran perfectly on the first
12:38 try. The goldfish, the shader, and if
12:42 you count the compile, the airplane
12:44 before its loop even started.
12:47 Two worked, but needed a steadier hand.
12:50 The ink and the house. One was
12:54 refreshingly honest about its own broken
12:55 physics. the character and one was never
12:59 a oneshot at all. The soccer overlay
13:02 that is all by itself a genuinely strong
13:05 model.
13:07 But now step back and look at the whole
13:08 list with me. A goldfish, a shader, an
13:12 airplane, a gothic city, a vauxil house,
13:17 a ragd doll, a ball with a trail, notice
13:21 anything.
13:23 Every single demo the official account
13:25 chose is a visual toy. Not one business
13:28 app. Not one agent doing real work. Not
13:31 one of the boring, valuable, unglamorous
13:33 things that people actually pay money
13:36 for. That is not an accident. Visual
13:39 demos go viral because you can judge
13:41 them in one second flat. The real tests
13:44 of this model, the 50 million line code
13:47 migrations, the bugs that stumped every
13:50 other model on Earth, those do not fit
13:52 inside a 4.2 million view thread. The
13:55 showcase is the appetizer.
13:58 And there is a reason Antropic wanted
14:00 the whole internet hungry and fast
14:04 because of what happened next. Here is
14:06 the twist I promised you. While people
14:09 were busy building goldfish ponds, on
14:11 June 13th, the US government sent
14:14 Anthropic a letter, an export control
14:17 directive effective immediately. Fable 5
14:21 and its bigger sibling, Mythos, had to
14:23 be cut off from every foreign national
14:26 anywhere in the world, including
14:28 Anthropic's own staff. The government's
14:31 stated worry was that someone had found
14:33 a way to jailbreak the model. Antropic
14:36 looked at the demonstration, said it
14:39 only surfaced minor, already known
14:41 issues, and pushed back hard. But to
14:44 comply, they had to abruptly disabled
14:46 the model for enormous numbers of
14:48 customers. So the free window everyone
14:51 was racing inside did not just have a
14:54 price deadline on June 23rd. It suddenly
14:56 had a political one, too.
14:58 The most capable model handed to the
15:01 public in years became for a lot of
15:04 people simply unavailable within days of
15:08 these demos going up, which makes every
15:12 one of these seven little builds an
15:14 artifact of a very strange week. A model
15:17 powerful enough to grade its own
15:19 airplane and contained before most
15:21 people even got to try it. I put the
15:24 whole test into a free guide, all seven
15:27 prompts, word for word, so you can paste
15:30 them straight into Fable or honestly
15:33 into any strong model and run the exact
15:37 same scoreboard yourself plus my grade
15:40 on each one. What broke and the single
15:43 trick that self-checking loop from the
15:45 airplane that made the biggest
15:47 difference across all seven. Comment the
15:50 word seven and I will send it straight
15:53 to you free. If watching me turn seven
15:57 magic tricks over to see the wires
15:58 underneath was worth your time,
16:01 subscribe because I do the building so
16:04 you know what is real before you spend a
16:06 credit on it. I drop bite-size AI
16:09 breakdowns every day on Instagram and
16:12 the full deep dives like this one right
16:14 here on YouTube. I will see you in the
16:17 next one.
```

</details>
