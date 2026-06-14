---
title: "Claude Fable 5 Edited Its Own Launch Video — No Human Opened an Editor (Copy the Pipeline)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-11"
duration_seconds: 923
video_id: "HcUok_nxoTA"
url: "https://youtube.com/watch?v=HcUok_nxoTA"
language: "en"
tags: [claude-fable-5, ai-video-editing, ffmpeg, whisper, remotion, figma, thariq-shihipar, anthropic, agentic-pipelines]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# Claude Fable 5 Edited Its Own Launch Video — No Human Opened an Editor (Copy the Pipeline)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-11  **Duration:** 15:23  **Watch:** https://youtube.com/watch?v=HcUok_nxoTA

> **Source note:** This is a decode of Thariq Shihipar's (@trq212, Claude Code team) public interactive deck about how Anthropic's Fable 5 launch video was edited entirely by Fable 5. The original deck (https://thariqs.github.io/cc-video-editing-deck/) is the source of truth. Vendor: Anthropic. The "~10 re-renders through the night" cost breakdown is the channel's reading of Thariq's public numbers.

## TL;DR

A 5-station blueprint for editing video with Claude Fable 5, reverse-engineered from the public deck by Thariq Shihipar (the Claude Code engineer who presented and edited the Fable 5 launch video). 17 takes + 25GB of raw 4K footage in, verified rough cut out in 7 minutes. The one idea: the edit is text. The 5 stations: (1) Whisper for word-level timestamps, (2) Claude writing a cut list as JSON, (3) FFmpeg executing it, (4) color grade as a LUT text file, (5) Remotion React components for motion graphics. Plus the Figma round trip (code↔Figma, twice) and the meter: total ≈ $100, but the cutting/grading/transcription stations cost only ~$10; the other 90% burned on iterating motion graphics. The one rule that holds it together: verify everything. The honest catches: Whisper is too polite (it deletes ums), FFmpeg cuts on keyframes (can land mid-sentence), and most stations don't need Fable 5 at all — only the long-horizon parts do.

## Key Insights

- **The receipts**: On 2026-06-09 Anthropic posted the Fable 5 launch video. 2026-06-10, Thariq Shihipar (Claude Code team engineer, on-camera presenter of the video) revealed no human ever opened a video editor. 17 takes, 25GB raw 4K footage, 7 minutes later a verified rough cut came out. The kickoff prompt was shockingly casual: pointed Claude Code at the footage folder, said the script is in a markdown file, gave human-editor notes ("best takes usually at the end with fewest hums, cut the warm-up phrase at the start of each take, write a JSON file showing every clip and time range you chose"), then **one final line: `/goal Don't stop until you have a final video.`** 4 days later it shipped as the official launch video. (01:13)
- **The one idea that makes it work**: in a normal edit, decisions live inside a binary timeline (Premiere project file) only Premiere can open. **In this pipeline, the edit is text.** Transcript is text. Cut list is JSON. Color grade is a text file. Graphics are React code. A model that can read/write text can now read/write the edit — diff it, explain it, re-render at 3am without you. (02:25)
- **Station 1 — The Ears (Whisper)**: OpenAI's Whisper ran locally on a laptop, free, no cloud upload. Output: not just words, but every word with start/end times in JSON. That timestamp layer is what turns audio into something a coding agent can cut. In the demo one warm-up phrase ended at 66.40s, the agent placed the cut 500s of a second later inside the silent gap. **Honest catch**: vanilla Whisper is too polite — it quietly deletes most "ums" and "uhs" from the transcript. If your plan is to hunt filler words by searching the text, stock Whisper hides exactly what you're hunting. For true "um" detection, use a verbatim-tuned variant (Whisper-timestamped or Crisper Whisper, both open source). (03:41)
- **Station 2 — The Brain (cut list as JSON)**: Claude read all 17 transcripts and faced a human question: which take is best? Demo's answer — one sub-agent per scene, reading every candidate take, plus verifier agents double-checking picks. Selections landed in one file, `final_edit.json`: for every scene, the candidates, the chosen clip, exact in/out times, **and a written rationale**. Sample rationale: "The final take inside clip C012 is flawless. Zero ums. The warm-up ends at 66.40. The cut-in sits in the silent gap." **The step that separates this from sloppy AI demos**: Claude transcribed its own finished cut and checked it again for leftover filler. Fresh ears grading the work. (05:04)
- **Station 3 — The Hands (FFmpeg, and where cuts break)**: FFmpeg is the 25-year-old free CLI tool that powers half the internet's video. Two moves: (1) slice — for each chosen take, FFmpeg cuts from in to out and writes a clean segment, (2) stitch — list segments in a text file, FFmpeg's concat mode joins them with no re-encode. Seconds, not hours. **Where AI editing demos quietly fall apart**: when FFmpeg copies without re-encoding, it can only cut on key frames, which can sit half a second from where you asked, and transcript timestamps drift by a tenth of a second. The CEO of a competing AI editing tool (grain of salt) ran his own test and reported cuts landing mid-sentence 11 of 11 times. **Why the launch video worked — 3 copyable defenses**: (1) cut in silence gaps, not at word boundaries, (2) re-encode when you need frame accuracy, (3) verify by re-transcribing the output. The blade is free. The discipline is the skill. (06:27)
- **Station 4 — The Look (color as plain text LUTs)**: footage was S-Log 3 off a Sony camera, raw log footage washed in gray. In Premiere that's a color panel and a lot of sliders. **In the edit bay, a grade is a LUT — a `.cube` file, which is plain text.** A grid of numbers mapping every input color to an output color. Thariq prompted "the grading feels a bit too muted. Make some examples and let me choose one." Claude wrote LUT files from scratch — seven of them, named like film stocks: Neutral 709, Warm Filmic, Punchy, Teal and Orange, etc. Built a side-by-side preview page so a human could pick the winner. The final video shipped on a custom grade called "neutral cool desat," applied with one FFmpeg flag at encode time. The entire visual mood of a launch video is now a text file you can version, diff, and regenerate by describing a feeling. (07:55)
- **Station 5 — The Motion (Remotion)**: 11 static PNG images from the design team. Old workflow = After Effects, keyframe by keyframe. Claude rebuilt every static design as a React component in Remotion — free, open-source framework where video is code. Every frame renders from components. Every animation is a number you can edit. All timing in one file, 6 numbers driving every animation. "Make it snappier" = one-line change. Even cues got automated: to land a graphic exactly when a word is spoken, Claude searched the Whisper timestamps for that word and set the cue to that frame. **The unlock**: Remotion's official docs now have a page for prompting videos with coding agents, plus an installable skill pack for Claude Code. The barrier to motion graphics just became a prompt. (09:13)
- **The Figma round trip that made designers' jaws drop**: design teams live in Figma, not code. Thariq typed one more prompt: "Great. Now, can you also export it to a Figma file?" Through Figma's official integration with Claude Code, Claude built a real Figma file from the video's code. Components, the color station, even live-rendered motion previews. The design team opened it in their own tool and made their pass. Then the reverse prompt: "The design has been updated in this Figma. Can you update the video to match?" And the code rebuilt itself to mirror the new design. Code to Figma, Figma to code, twice. Nobody copying anything by hand. That integration is public — one command installs it. (10:35)
- **Render night**: 4K render, 4,334 frames. While it rendered, Claude screenshotted its own frames and reviewed them before each pass. ~10 re-renders through the night. Finished at 6:24am. Nobody was awake. **That is what a long-horizon model actually looks like at work.** (11:25)
- **The meter — 3 honest catches**:
  1. **The cost**: Thariq said the whole edit ≈ **$100 of usage**. But the breakdown matters more: transcription + cutting (the part that replaces an editor's weekend) was only **~$10**. The other 90% burned on iterating the motion graphics. **Polish is expensive. Cutting is almost free.**
  2. **The model**: Fable 5 is the most expensive Claude ever — $10/M in, $50/M out, double Opus, counts double against subscription limits. Free window on paid plans ends 2026-06-22. One respected reviewer racked up a $110 bill in one afternoon. **What saves you: most stations don't need Fable 5 at all.** Whisper is free. FFmpeg is free. LUTs are text. A cheaper model writes those commands just fine. What Fable 5 brings is the long-horizon part. Anthropic's exact claim: "it can work autonomously for longer than any previous Claude model." That's the "don't stop until the video is done" part. **Rent the marathon runner for marathons.**
  3. **The taste**: a human wrote the script, shot the takes, set the preferences, picked the grade. The agent replaced the labor. It did not replace the judgment. **Whoever holds the taste still holds the job.** (11:54)
- **The one rule that holds it together**: verify everything. Cut in silence. Re-transcribe the output. Screenshot the frames. **The edit is text now. And text is the one thing these models are born to work with.** (14:15)

## Notable Quotes

> "Footage by a camera. Taste by Tarik. Everything in between by the agent the video is about." — Thariq Shihipar, end credits (02:17)

> "The edit is text. The transcript is text. The cut list is JSON. The color grade is a text file. The graphics are React code. And that changes everything. Because a model that can read and write text can now read and write your edit." (02:54)

> "The blade is free. The discipline is the skill." (07:53)

> "Polish is expensive. Cutting is almost free." (12:27)

> "Whoever holds the taste still holds the job." (13:42)

> "The edit is text now. And text is the one thing these models are born to work with." (14:24)

## Tools and Resources Mentioned

- **Thariq Shihipar's (@trq212) original interactive deck** (source of truth): https://thariqs.github.io/cc-video-editing-deck/
- **The finished launch video** (vendor: Anthropic / @ClaudeDevs): https://x.com/ClaudeDevs/status/2064399512664526853
- **Anthropic Fable 5 announcement**: https://www.anthropic.com/news/claude-fable-5-mythos-5
- **Remotion — AI/Claude Code agent docs** (vendor: Remotion): https://www.remotion.dev/docs/ai/claude-code
- **Figma × Claude Code MCP setup** (vendor: Figma): https://help.figma.com/hc/en-us/articles/39888612464151
- **OpenAI Whisper** — local word-level timestamps (vendor: OpenAI, MIT)
- **Whisper-timestamped / Crisper Whisper** — verbatim filler-word variants
- **FFmpeg** — 25-year-old free CLI tool, 2.5-line cut + concat

> **Vendor disambiguation:** Thariq Shihipar = Claude Code team engineer (Anthropic employee). Remotion = open-source React video framework. Figma = design tool vendor. Whisper = OpenAI's open-source speech recognition. None of these are the user's stack.

**Free AI Edit Bay Blueprint** (5 stations, copy-paste starter prompts, FFmpeg commands, Whisper filler workaround, Remotion+Figma setup, every catch): comment "CUTLIST" on the video
**Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

## Action Items

- [ ] Read Thariq's full interactive deck before building the pipeline yourself (link above)
- [ ] Station 1: if you need to hunt filler words, use Whisper-timestamped or Crisper Whisper instead of stock Whisper
- [ ] Station 3: always cut in silence gaps, not at word boundaries, or re-encode for frame accuracy
- [ ] Station 3: verify every AI cut by re-transcribing the output (the "fresh ears grading the work" pattern)
- [ ] Station 4: prompt Claude to write LUT files from a grade mood description, then build a side-by-side preview page for human pick
- [ ] Station 5: install the Remotion × Claude Code skill pack (one command per Remotion docs)
- [ ] Figma round trip: install the Figma × Claude Code MCP integration (one command) to do code↔Figma, code↔Figma
- [ ] **Cost control**: route transcription, cutting, grading, and LUT writes through a cheaper model — reserve Fable 5 for the long-horizon motion-graphics iteration loop
- [ ] Set a per-render budget cap before kicking off a render night (~10 re-renders is normal at 4K)
- [ ] Treat the "taste" step as human-required: script, takes, preferences, grade pick

## Open Questions

- Thariq's "$100 total / $10 cutting / $90 motion graphics" breakdown — is the $90 number from one render night, or summed across multiple nights?
- Which exact Fable 5 model variants were used for which stations in the demo? (Haiku 4.5 for grading? Sonnet 4.6 for the cut list? Fable 5 only for the motion-graphics loop?)
- The "competing AI editing tool CEO" who reported 11/11 mid-sentence cuts — who is this, and what was their test setup?
- The 6 numbers in the Remotion timing file — what units? Per-animation or shared?
- The "verify by re-transcribing the output" pattern — is this an explicit prompt the agent does, or an external hook the channel added?
- For a non-launch video use case, what's the actual savings vs Premiere + After Effects in $/hour terms?
- Does the Figma MCP export render real previews inside Figma, or is it just static frames?
- For a 10-minute video (4× the launch length), does the loop-engineering pattern from the prior video (memory ladder, self-correction) hold up?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 15:23 transcript)</summary>

0:00 On June 9th, Anthropic posted the launch
0:02 video for Claude Fable 5.
0:04 3 minutes, 4K clean cuts, a cinematic
0:08 grade, animated graphics.
0:10 Then, a day later, the engineer in that
0:13 video revealed something strange.
0:16 No human ever opened a video editor.
0:19 The model being launched did the entire
0:21 edit itself.
0:23 17 takes, 25 GB of raw footage went into
0:27 a folder.
0:28 7 minutes later, a verified rough cut
0:31 came out. No timeline, no Premiere, just
0:35 code.
0:36 And here is the part almost everyone who
0:38 shared this story missed.
0:40 Every tool in that pipeline is free,
0:42 public, and documented.
0:45 This is not a flex about a new model. It
0:48 is a blueprint.
0:50 So, in this video, the full AI edit bay,
0:52 station by station.
0:54 The transcription trick, the cut list,
0:56 the assembly,
0:58 the color grade, the motion graphics.
1:01 Plus, the parts the demo did not put in
1:04 bold.
1:05 Where the cuts break.
1:08 And the one station
1:10 that quietly burned
1:11 90% of the money.
1:13 First, the receipts.
1:16 The person behind the demo is Tarik
1:18 Shihab, an engineer on the Claude Coder
1:21 team at Anthropic,
1:23 and the on-camera presenter of the
1:26 launch video itself.
1:28 He did not just tweet a highlight clip.
1:31 He published a full interactive deck,
1:34 showing the actual prompts,
1:36 files, and commands.
1:39 Link is the first line of the
1:40 description.
1:42 And his kickoff prompt is shockingly
1:44 casual.
1:45 He points Claude Coder at the footage
1:47 folder, says the script is in a markdown
1:49 file, and adds notes you would give a
1:51 human editor.
1:53 The best takes are usually the ones at
1:55 the end with the fewest hums.
1:57 Cut the warm-up phrase at the start of
1:59 each take.
2:00 Write a JSON file showing every clip and
2:02 time range you chose.
2:04 Then one final line. /goal
2:07 Don't stop until you have a final video.
2:10 4 days later, the finished cut was the
2:12 official launch video.
2:14 His closing credit says it all.
2:17 Footage by a camera.
2:19 Taste by Tarik.
2:21 Everything in between
2:22 by the agent the video is about.
2:25 Before the stations
2:27 the one idea that makes this work.
2:30 In a normal edit, your decisions live
2:32 inside a timeline.
2:34 A Premiere project file.
2:36 A binary blob only Premiere can open.
2:39 In this pipeline, the edit is text.
2:43 The transcript is text. The cut list is
2:45 JSON.
2:46 The color grade is a text file.
2:49 The graphics are React code.
2:52 And that changes everything.
2:54 Because a model that can read and write
2:56 text can now read and write your edit.
2:58 Diff it. Explain it.
3:01 Re-render it at 3:00 in the morning
3:03 without you. So here is the edit bay.
3:05 Five stations.
3:07 One the ears.
3:09 Whisper turns every take into word-level
3:12 timestamps.
3:13 Two
3:14 the brain.
3:15 Claude picks takes and writes the cut
3:17 list as JSON.
3:19 Three
3:20 the hands.
3:22 FFmpeg executes that JSON into a real
3:24 video.
3:26 Four the look.
3:27 Color as plain text Lottie files. Five
3:31 the motion.
3:32 Remotion turns static designs into
3:34 animated code.
3:36 Five stations.
3:38 Zero video editors.
3:39 Let's build it.
3:41 Station one the ears.
3:43 The demo ran OpenAI's Whisper model
3:46 locally on a laptop.
3:48 Free
3:49 open source
3:51 no cloud upload.
3:53 And the output is the magic part.
3:55 Not just words.
3:57 Every word with a start time and an end
4:00 time written into JSON.
4:03 That timestamp layer is what turns audio
4:05 into into something a coding agent can
4:08 cut.
4:09 In the demo,
4:10 one warm-up phrase ended at 66.40
4:14 seconds.
4:15 So, the agent placed the cut 500s of a
4:17 second later inside the silent gap.
4:21 Try doing that by scrubbing a timeline.
4:24 Now, the honest catch nobody mentions.
4:27 Vanilla Whisper is too polite.
4:30 It quietly deletes most of the ums and
4:33 uhs from the transcript.
4:35 So, if your plan is to hunt filler words
4:38 by searching the text, stock Whisper
4:41 hides exactly what you are hunting.
4:44 Words like like and you know
4:46 come through fine.
4:48 For true um detection,
4:52 use a verbatim tuned variant.
4:54 Whisper timestamped or Crisper Whisper,
4:58 both open source, are built for this.
5:01 Same pipeline, smarter ear.
5:04 Station two, the brain.
5:06 This is where editing taste becomes a
5:08 file.
5:10 Claude read all 17 transcripts and faced
5:12 a human question.
5:14 Which take is best? The demo's answer.
5:18 One sub-agent per scene, reading every
5:20 candidate take, plus verifier agents
5:23 double-checking the pics.
5:25 The selections landed in one file, final
5:27 edit.json.
5:30 For every scene, it lists the
5:31 candidates, the chosen clip, the exact
5:35 in and out times,
5:36 and best of all, a written rationale.
5:40 Listen to this one.
5:42 The final take inside clip C012 is
5:45 flawless.
5:46 Zero ums.
5:48 The warm-up ends at 66.40.
5:51 The cut-in sits in the silent gap.
5:54 One take got disqualified for a 5.8
5:57 second dead pause.
5:59 This is the file a human editor keeps in
6:01 their head.
6:02 Written down where you can read it
6:05 and change it.
6:07 And then, the step that separates this
6:09 from every sloppy AI demo.
6:12 Claude transcribed its own finished cut
6:16 and checked it again
6:17 for leftover filler.
6:19 Fresh ears
6:20 grading the work.
6:22 That is the difference between a cut you
6:23 trust and a cut you baby sit.
6:26 Station three,
6:28 the hands.
6:29 The cut list is a plan.
6:32 FFmpeg
6:33 swings the blade.
6:35 FFmpeg is the 25-year-old free command
6:36 line tool that quietly powers half the
6:41 internet's video.
6:43 The agent uses it in two moves. Slice.
6:46 For each chosen take, FFmpeg cuts from
6:49 the in point to the out point and writes
6:52 a clean segment.
6:53 Stitch.
6:55 List the segments in a text file
6:57 and FFmpeg's concat mode joins them,
7:00 copying data straight over with no
7:02 re-encode.
7:03 Seconds, not hours. But slow down
7:06 because this is where AI editing demos
7:09 quietly fall apart.
7:12 When FFmpeg copies without re-encoding,
7:15 it can only cut on key frames,
7:17 which can sit half a second from where
7:19 you asked, and transcript timestamps
7:22 drift by a tenth of a second.
7:24 The CEO of a competing AI editing tool
7:27 said,
7:28 grain of salt,
7:30 ran his own test and reported cuts
7:32 landing mid-sentence 11 out of 11 times.
7:36 So, why did the launch video work?
7:39 Three copyable defenses.
7:41 Cut in silence gaps, not at word
7:43 boundaries.
7:45 Re-encode when you need frame accuracy.
7:48 And verify by re-transcribing the
7:50 output.
7:51 The blade is free.
7:52 The discipline
7:53 is the skill.
7:55 Station four, the look.
7:57 This footage came off a Sony camera in
8:00 S-Log 3.
8:02 Raw log footage
8:04 looks like someone washed the world in
8:05 gray.
8:07 Every pixel needs remapping before it
8:10 looks like film.
8:11 In Premiere, that is a color panel
8:14 and a lot of sliders.
8:16 In the edit bay, a grade is a LUT, a
8:18 lookup table.
8:20 A dot cube file,
8:21 which is, wait for it, plain text.
8:25 A grid of numbers
8:26 mapping every input color to an output
8:29 color. So, when Tarik prompted,
8:32 "The grading feels a bit too muted.
8:34 Make some examples and let me choose
8:36 one."
8:37 Claude wrote LUT files from scratch.
8:40 Seven of them, named like film stocks.
8:43 Neutral 709,
8:45 warm filmic,
8:46 punchy,
8:48 teal and orange.
8:49 It even built a side-by-side preview
8:51 page
8:52 so a human could pick the winner.
8:55 The final video
8:56 shipped on a custom grade called neutral
8:59 cool desat,
9:01 applied with one FFmpeg flag at encode
9:04 time.
9:05 The entire visual mood of a launch video
9:07 is now a text file you can version,
9:10 diff, and regenerate by describing a
9:11 feeling.
9:12 Station five, the motion.
9:15 The launch video needed animated
9:17 graphics.
9:19 And the design team delivered them as 11
9:21 static PNG images.
9:24 Beautiful, but frozen.
9:26 The old workflow is After Effects,
9:29 keyframe by keyframe.
9:32 Instead, Claude rebuilt every static
9:35 design
9:36 as a React component in Remotion.
9:38 Remotion is the free open source
9:40 framework
9:41 where video is code.
9:44 Every frame renders from components.
9:47 Every animation is a number you can
9:49 edit. And once a design is code, every
9:52 word, every color,
9:54 every beat of timing becomes a parameter
9:56 you can prompt.
9:58 The demo kept all timing in one file.
10:00 Six numbers driving every animation.
10:03 Make it snappier becomes a one-line
10:05 change.
10:06 Even cues got automated.
10:09 To land a graphic exactly when a word is
10:10 spoken,
10:12 Claude searched the Whisper timestamps
10:13 for that word and set the cue to that
10:16 frame.
10:17 And here is your unlock.
10:19 Remotion's official docs now have a page
10:22 for prompting videos with coding agents.
10:24 Plus an installable skill pack for
10:26 Claude code.
10:28 One command and your agent knows how to
10:30 animate.
10:32 The barrier to motion graphics just
10:33 became a prompt.
10:35 Now, the round trip that made designers'
10:37 jaws drop.
10:38 Design teams live in Figma,
10:41 not code.
10:43 So, Tariq typed one more prompt.
10:45 Great.
10:46 Now, can you also export it to a Figma
10:48 file?
10:50 Through Figma's official integration
10:51 with Claude code,
10:54 Claude built a real Figma file from the
10:55 video's code.
10:58 Components, the color station,
11:00 even live-rendered motion previews.
11:03 The design team opened it in their own
11:04 tool and made their pass.
11:06 Then the reverse prompt.
11:08 The design has been updated in this
11:10 Figma.
11:11 Can you update the video to match?
11:14 And the code rebuilt itself to mirror
11:16 the new design.
11:17 Code to Figma,
11:18 Figma to code, twice.
11:21 Nobody copying anything by hand.
11:23 That integration is public. One command
11:26 installs it.
11:27 Then came render night, a 4K render,
11:31 4,334
11:33 frames.
11:35 While it rendered, Claude screenshotted
11:37 its own frames and reviewed them before
11:39 each pass.
11:40 Roughly 10 re-renders through the night.
11:44 The finished file was done at 6:24 in
11:46 the morning.
11:47 Nobody was awake.
11:49 That is what a long horizon model
11:51 actually looks like at work.
11:53 Time for the meter and the fine print.
11:56 Because this is a launch demo by the
11:58 company
11:59 launching the model. Catch one, the
12:01 cost.
12:03 When people asked, Tharic said the whole
12:05 edit came to roughly $100 of usage.
12:09 But the breakdown matters more.
12:12 The transcription and cutting,
12:14 the part that replaces an editor's
12:15 weekend, was only about $10.
12:19 The other 90% burned on iterating the
12:21 motion graphics.
12:23 Polish is expensive.
12:25 Cutting is almost free.
12:27 Catch two, the model.
12:30 Fable 5 is the most expensive Claude
12:32 ever.
12:33 $10 per million input tokens, 50 per
12:36 million output.
12:37 Double Opus,
12:39 and it counts double against
12:40 subscription limits.
12:42 The free window on paid plans ends June
12:44 22nd.
12:46 One respected reviewer racked up a $110
12:47 bill in one afternoon of testing.
12:52 But here is what saves you. Most
12:54 stations do not need Fable 5 at all.
12:56 Whisper is free.
12:58 FFmpeg is free.
13:00 Hello T's are text. A cheaper model
13:03 writes those commands just fine.
13:05 What Fable 5 brings is the long horizon
13:08 part.
13:09 Anthropic's exact claim, it can work
13:12 autonomously
13:13 for longer than any previous Claude
13:15 model.
13:16 That is
13:18 the don't stop until the video is done
13:21 part.
13:22 Rent the marathon runner for marathons.
13:25 Catch three,
13:27 the taste.
13:28 A human
13:29 wrote the script, shot the takes, set
13:32 the preferences,
13:33 picked the grade.
13:35 The agent replaced the labor.
13:37 It did not replace the judgment.
13:40 Whoever holds the taste still holds the
13:42 job.
13:43 So, here is the edit bay one more time.
13:45 The ears. Whisper.
13:48 Turning footage into word level
13:50 timestamps.
13:52 The brain.
13:53 Claude writing the cut as Jason
13:56 with reasons attached. The hands.
13:58 FFmpeg executing that file into a real
14:02 video. The look.
14:04 Color as plain text lots. The motion.
14:07 Remotion.
14:09 Turning static designs into animated
14:11 code.
14:12 And the rule that holds it together.
14:15 Verify everything.
14:16 Cut in silence.
14:18 Retranscribe the output.
14:21 Screenshot the frames.
14:23 The edit is text now.
14:24 And text is the one thing these models
14:27 are born to work with.
14:29 If you want to try this without
14:30 assembling it from scratch, I packed it
14:33 all into a free PDF.
14:35 The AI edit bay blueprint.
14:37 All five stations. The startup prompts.
14:41 The FFmpeg commands.
14:43 The whisper filler word workaround.
14:45 The remotion and Figma setup.
14:48 And every catch from this video.
14:51 With links to Tharik's original deck.
14:54 Comment the word cut list and I will
14:56 send it straight to you.
14:58 Full credit to Tharik Shiipara
15:01 and the Claude code team.
15:02 His deck is the first link in the
15:15 description.
15:06 I drop bite-size AI breakdowns every day
15:09 on Instagram.
15:10 And the full deep dives right here on
15:13 YouTube.
15:14 Subscribe.
15:15 Because the next launch video will not
15:17 be edited by a human either.
15:19 The question is whether yours will be.

</details>
