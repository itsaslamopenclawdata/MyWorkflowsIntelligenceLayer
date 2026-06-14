---
title: "I Made Opus 4.8 and Fable 5 Build the Same App — Both Worked, Until I Opened the Data"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-11"
duration_seconds: 598
video_id: "yKF68OZUGRU"
url: "https://youtube.com/watch?v=yKF68OZUGRU"
language: "en"
tags: [claude-fable-5, claude-opus-4-8, head-to-head, model-comparison, expense-tracker, code-audit, test-kit, float-drift, integer-cents]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-14"
---

# I Made Opus 4.8 and Fable 5 Build the Same App — Both Worked, Until I Opened the Data

**Channel:** Hyperautomation Labs  **Published:** 2026-06-11  **Duration:** 09:58  **Watch:** https://youtube.com/watch?v=yKF68OZUGRU

> **Source note:** The channel's own instrumented head-to-head run. Every number (build times, tokens, tool calls, test results, stored data) is from the channel's run, not a vendor demo. API pricing: Opus 4.8 $5/M input, $25/M output; Fable 5 $10/M input, $50/M output (exactly 2x).

## TL;DR

A scripted, rerunnable head-to-head: identical one-shot prompt, no follow-ups, no second chances — build a complete expense tracker as a single self-contained HTML file. Opus 4.8: 6m 02s, 44K tokens, 9 tool calls, 1001 lines / 41KB. Fable 5: 8m 50s, 71K tokens, 18 tool calls. Both pass 10/11 automated tests (add/edit/delete/undo, XSS injection, month-boundary trap, July-from-June jump, persistence). **The 11th test — opening the stored data — is where Fable wins decisively.** Opus stored dollars as floating point, total reads 226.39000000000001. Fable stored integer cents, total reads 22,639. Fable also reflows cleanly on a 390px phone (Opus stays 435px and clips dollar amounts). The eerie part: both models independently named the app "Ledger" and picked the same storage key `Ledger.expenses.v1`. Fable's extra 3 minutes went to attacking its own code in an automated browser and fixing 2 real bugs before declaring done. The verdict: if a human reviews every line, Opus at half price is rational. If the code ships the moment the model says done, Fable's paranoia is the cheapest insurance.

## Key Insights

- **The test design — what makes it honest**:
  - One prompt, identical to the letter: "Build me a complete expense tracker as one single HTML file" with add/edit/delete, monthly view + chart (drawn itself, no libraries), no CDN, no network requests, data saved locally, has to look like something you'd use every day
  - Each model in its own isolated session, same machine, same tools, started at the same second
  - Every check is an automated script, not the channel's opinion — kit can be re-run on any two models in 20 minutes (00:58)
- **The race telemetry**:
  - **Opus 4.8**: 6 min 02 sec, 44,000 tokens, 9 tool calls, finished app, 1,001 lines of code, 41 KB file
  - **Fable 5**: 8 min 50 sec, **~3 min longer**, 71,000 tokens (**60% more**), 18 tool calls (**exactly 2×**)
  - If this were a race, Opus just won it: cheaper, faster, done (01:51)
- **But those extra tool calls — what Fable did differently**: those 18 calls were not writing more code. Fable did something the channel has never seen a model do unprompted. (See Reveal 3 below.) (02:36)
- **First look**:
  - **Opus**: tight two-column dashboard, donut chart drawn by hand on canvas, transactions grouped by day, clever touch — seeds 5 sample expenses on first open so the app never greets you with an empty screen
  - **Fable**: more product. Summary cards, budget slot, a second chart for daily spending, a floating add button, designed empty states. Breakdown panel literally says "Nothing spent this month." Nice or suspicious? A model wrote that joke. (02:40)
- **The eerie convergence**: both models named their app `Ledger` independently. Both picked the exact same storage key: `Ledger.expenses.v1`. Load them in the same browser and they would literally fight over your data. **Same instincts, same lineage.** (03:23)
- **The 11-test automated gauntlet** (same 7 expenses to the cent):
  - add / edit / delete / undo — both passed
  - XSS script injection in the note field — both rendered it harmless
  - June 1st expense planted, leak into May check — neither leaked
  - July expense added while standing in June — both jumped straight to July like they'd rehearsed it
  - reload persistence check
  - **10 tests in, scoreboard: 10 to 10.** The only blemish anywhere: Opus stacking up 7 little toast notifications like unwashed dishes. Cosmetic. (03:47)
- **Reveal 1 — the number that should not exist** (Test 11 — check the stored data down to the last decimal):
  - **Fable's storage reads 22,639.** Weird until you realize it's counting cents. Whole, exact, integer cents.
  - **Opus's storage reads 226.39 followed by 11 zeros and then a 1.** That trailing 1 is float drift. The display rounds it away so the user never sees it. The demo looks perfect. **The data is quietly wrong.**
  - Every senior engineer watching just nodded. **Rule 1 of handling money: you never store it as floats.** Fable followed the rule without being told. Opus shipped the thing that looks identical in every screenshot and fails the audit. **You cannot see this difference in a demo. That is exactly the point.** (04:39)
- **Reveal 2 — the phone** (390px wide):
  - Fable reflowed into a clean single column. Cards stacked, charts resized, add button floats right where the thumb lives.
  - Opus did NOT reflow. Its layout stayed 435px wide on a 390px screen. Dollar amounts, the actual numbers an expense tracker exists to show you, get clipped off the right edge of the display. It wrote a responsive breakpoint — it just never tested it.
  - **The pattern again**: looks finished on the developer's monitor, breaks in the one place the developer wasn't looking. **An expense tracker that hides your money on a phone is failing at its only job.** (05:44)
- **Reveal 3 — the self-test** (where Fable's extra 3 minutes went):
  - After writing the app, Fable **opened its own code in an automated browser and attacked it like a hostile tester**. Add, edit, delete, undo, reload, the whole drill.
  - It found 2 real bugs in its own work: a CSS class collision that wrecked the bar chart, a toast notification painting just off-screen. Fixed both, tested again, only then declared the job done.
  - Opus verified 2 to be fair — 8 assertions in a headless browser, all green. More than most humans do.
  - **Fable behaved like the engineer who refuses to trust their own code until it survives an attack. That paranoia is what you are paying double for.** (06:35)
- **Where Opus 4.8 genuinely wins**:
  - Finished almost 3 minutes sooner
  - Used 38% fewer tokens
  - Runs at half the price ($5 in / $25 out vs $10 in / $50 out for Fable)
  - Shipped 2 ideas Fable never had: **demo data on first launch** (so the app never looks dead) and **custom categories** (type anything, it invents a color on the spot; Fable's categories are a fixed list of 10)
  - **If you are a developer who reviews every line anyway, Opus at half price is not a compromise. It is the rational choice.** (07:26)
- **The verdict**:
  - Final score: **Fable 11/11, Opus 10/11, plus a phone layout**
  - The channel's tests only caught what they went looking for
  - Both apps demo perfectly. Both screenshots look shippable.
  - **The price gap is invisible until month three** when the float drift meets a tax export, or a user opens the app in a checkout line
  - **What you are buying for double the money is not smarter code. It is instincts.** Integer sense without being asked. Testing its own work like an enemy would. The boring discipline that never shows up in a screenshot. (08:15)
- **The decision rule**: if a human reviews everything Claude writes, save your money and run Opus. If the code ships the moment the model says done — and increasingly that is how all of us work — then **Fable's paranoia is the cheapest insurance you can buy.** (09:00)

## Notable Quotes

> "Both models named their app Ledger independently. And both picked the exact same storage key. Ledger.expenses.v1. Load them in the same browser, and they would literally fight over your data. Same instincts, same lineage." (03:31)

> "The display rounds it away so the user never sees it. The demo looks perfect. The data is quietly wrong." (05:14)

> "An expense tracker that hides your money on a phone is failing at its only job." (06:33)

> "Fable behaved like the engineer who refuses to trust their own code until it survives an attack. That paranoia is what you are paying double for." (07:21)

> "What you are buying for double the money is not smarter code. It is instincts. Integer sense without being asked. Testing its own work like an enemy would. The boring discipline that never shows up in a screenshot." (08:46)

> "If the code ships the moment the model says done and increasingly that is how all of us work, then Fable's paranoia is the cheapest insurance you can buy." (09:11)

## Tools and Resources Mentioned

- **Claude Opus 4.8** (vendor: Anthropic) — $5/M input, $25/M output
- **Claude Fable 5** (vendor: Anthropic) — $10/M input, $50/M output (2× Opus)
- **Free "Same-App Test Kit"** — exact prompt, all 11 automated checks, full scorecard, rerun guide: https://hyperautomationlabs.co/free/same-app-test or comment "LEDGER" on the video
- **Channel's Claude Code guide on Gumroad**: https://hyperautomationlabs.gumroad.com/l/claude-code-guide

> **Vendor disambiguation:** Opus 4.8 and Fable 5 are both Anthropic models. The "Ledger" name and `Ledger.expenses.v1` storage key are coincidental (and eerie) collisions from the two models' training data. Not a product called Ledger in the user's stack.

## Action Items

- [ ] Download the Same-App Test Kit and run the 11-check gauntlet on your current model pair — takes 20 minutes
- [ ] If you review every line of AI-generated code: stay on Opus 4.8 at half price, no Fable 5 needed
- [ ] If code ships the moment the model says done: pay 2× for Fable 5's "self-attack-its-own-code" paranoia
- [ ] For money-handling code: always ask the model "did you store dollars as float or cents as integer?" — the answer reveals the model's instinct level
- [ ] For UI code: always test at 390px (iPhone width) and 320px (small Android) before accepting — Opus's 435px-on-390px bug is the kind that ships to production
- [ ] Track "money-correctness" and "phone-layout" as part of your model-acceptance criteria, not just feature completeness
- [ ] At month 3 of a model rollout, audit for float drift in any monetary storage — bugs hide, demos don't show
- [ ] Pair Fable 5 with a second-pass Opus check: have Opus do the first build for speed, Fable 5 audit for money/layout bugs

## Open Questions

- Is the "integer cents" instinct a property of Fable 5's training, or did the prompt somehow telegraph it (e.g., one model's name being "Ledger" suggesting accounting)?
- The 18 vs 9 tool call ratio — was Fable's "self-attack" loop a tool-call pattern or a sub-agent pattern? Could Opus be coaxed into the same loop with explicit prompting?
- For Opus's missed phone reflow — would adding "test on a 390px screen" to the prompt have caught it, or is the breakpoint skill itself missing?
- The 38% fewer tokens for Opus — is that because Fable 5's extra 9 calls were verification, or because Fable's code was longer/more elaborate?
- Custom categories (Opus's win) — at what data size does Fable's fixed-10-category list become a real limitation?
- The "demo data on first launch" pattern from Opus — is that a default Claude Code convention, or did Opus invent it independently?
- The 226.39000000000001 value — how many add/edit operations before Opus's float drift becomes visible in the displayed total?
- For model-comparison methodology: does the 11-test gauntlet cover what most production apps actually do, or is it too expense-tracker-specific?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 9:58 transcript)</summary>

0:00 These two apps look almost identical.
0:03 Same dark theme. Same donut chart.
0:06 And the same name. Ledger.
0:09 But nobody designed them to match.
0:12 The one on the left was built by Claude
0:14 Opus 4.8.
0:15 The one on the right was built by Fable
0:18 5.
0:19 The brand new flagship that costs
0:22 exactly double.
0:24 I gave both models the exact same
0:26 prompt.
0:27 Word for word.
0:28 One shot.
0:30 No follow-ups.
0:31 No second chances.
0:34 Build me a complete expense tracker as
0:35 one single file.
0:37 Both of them shipped.
0:39 Both of them passed almost every test I
0:41 threw at them.
0:43 I was about to call it a tie.
0:45 Then I opened the stored data.
0:48 And I found a number. That should not
0:50 exist.
0:51 That number is the real difference
0:54 between these two models.
0:56 And nobody is showing it in the demos.
0:58 Here is the test design. Because a
1:00 comparison is only as honest as its
1:03 rules.
1:04 One prompt identical to the letter.
1:07 A personal expense tracker in one
1:09 self-contained HTML file.
1:12 Add, edit, and delete expenses.
1:16 A monthly view with a chart the model
1:18 has to draw itself.
1:20 No libraries. No CDN.
1:23 No network requests at all.
1:25 Data saved locally. And it has to look
1:27 like something you would actually use
1:29 every day.
1:30 Each model ran in its own isolated
1:33 session. On the same machine with the
1:35 same tools. Started at the same second.
1:38 One more thing.
1:40 Every check you are about to see is an
1:42 automated script. Not my opinion.
1:45 You can download the whole test kit and
1:47 run it on any two models you like.
1:49 The link is below.
1:51 Opus came back first.
1:53 6 minutes and 2 seconds.
1:55 44,000 tokens.
1:58 Nine tool calls and a finished app.
2:01 1,001 lines of code in a 41 kilobyte
2:05 file.
2:06 Fable took 8 minutes and 50 seconds,
2:09 almost 3 minutes longer.
2:11 71,000 tokens, 60% more than Opus.
2:15 And 18 tool calls, exactly twice as
2:18 many.
2:19 If this were a race, Opus just won it.
2:22 Cheaper,
2:23 faster, done.
2:25 But those extra tool calls Fable made,
2:28 it was not writing more code with them.
2:30 It was doing something else entirely.
2:33 Something I have never seen a model do
2:35 unprompted.
2:36 Hold that thought, because it decides
2:38 the whole comparison.
2:40 First look, and honestly both of these
2:43 are good.
2:44 Opus built a tight two-column dashboard.
2:47 Donut chart, drawn by hand on a canvas.
2:51 Transactions grouped by day.
2:53 And a clever touch, it seeds five sample
2:56 expenses on first open. So, the app
2:59 never greets you with an empty screen.
3:02 Fable went more product. Summary cards,
3:05 a budget slot, a second chart for daily
3:07 spending, a floating add button, and
3:10 designed empty states.
3:12 Its breakdown panel literally says,
3:15 "Nothing spent this month." Nice or
3:18 suspicious? A model wrote that joke.
3:21 But here is where it gets eerie.
3:23 Both models named their app Ledger
3:26 independently.
3:28 And both picked the exact same storage
3:30 key.
3:31 Ledger.expenses.v1.
3:36 Load them in the same browser, and they
3:38 would literally fight over your data.
3:41 Same instincts, same lineage.
3:44 The difference is discipline, and it is
3:46 about to show.
3:47 So, I drove the same 11 tests through
3:50 both apps with a robot browser.
3:52 The same seven expenses to the cent.
3:55 Add, edit, delete, undo.
3:58 Both passed.
3:59 I attacked the note field with a script
4:01 injection.
4:02 Both apps rendered it harmless.
4:05 I planted an expense on June 1st to see
4:08 if it would leak into May.
4:09 Neither leaked.
4:11 I added a July expense while standing in
4:13 June.
4:14 And both apps jumped straight to July
4:16 like they had rehearsed it.
4:18 Reload and everything persists. 10 tests
4:21 in, the scoreboard was 10 to 10.
4:24 The only blemish anywhere was Opus
4:26 stacking up seven little toast
4:28 notifications like unwashed dishes.
4:31 Cosmetic.
4:32 Then came test 11.
4:35 The one where I stopped looking at the
4:36 screen
4:37 and looked at the data instead.
4:39 Test 11 checks the stored data
4:42 down to the last decimal.
4:45 Fable's storage read 22,639.
4:48 That looks weird until you realize it is
4:50 counting cents. Whole, exact, integer
4:53 cents.
4:55 Opus stored dollars instead as floating
4:58 point numbers. And after just eight
5:00 entries and one edit, its stored total
5:03 read 226.39
5:06 followed by 11 zeros and then a one.
5:09 That trailing one is float drift.
5:12 The display rounds it away so the user
5:14 never sees it.
5:16 The demo looks perfect. The data is
5:18 quietly wrong.
5:20 Every senior engineer watching this just
5:22 nodded.
5:23 Because rule one of handling money
5:26 is that you never store it as floats.
5:29 Fable followed the rule without being
5:31 told.
5:32 Opus
5:33 shipped the thing that looks identical
5:35 in every screenshot and fails the audit.
5:39 You cannot see this difference in a
5:41 demo.
5:42 That is exactly the point.
5:44 Then I shrank both apps to a phone
5:46 screen.
5:47 390 pixels wide.
5:50 Fable reflowed into a clean single
5:52 column.
5:53 Cards stacked, charts resized, and the
5:56 add button floats right where your thumb
5:58 lives.
6:00 Opus did not reflow.
6:02 Its layout stayed 435 pixels wide on a
6:06 390 pixel screen.
6:08 The dollar amounts, the actual numbers,
6:10 and expense tracker exists to show you
6:13 get clipped off the right edge of the
6:14 display.
6:16 It wrote a responsive breakpoint.
6:18 It just never tested it.
6:21 And that is the pattern again.
6:23 It looks finished on the developer's
6:24 monitor
6:25 and breaks in the one place the
6:28 developer was not looking.
6:30 An expense tracker that hides your money
6:32 on a phone is failing at its only job.
6:35 Which brings us back to those mystery
6:37 tool calls.
6:38 Here is what Fable spent its extra 3
6:40 minutes on.
6:42 After writing the app, it opened its own
6:44 code in an automated browser and
6:47 attacked it like a hostile tester.
6:49 Add, edit, delete, undo,
6:52 reload, the whole drill.
6:55 And it found two real bugs in its own
6:57 work.
6:58 A CSS class collision that wrecked the
7:00 bar chart and a toast notification
7:02 painting just off screen.
7:04 It fixed both, tested again,
7:06 and only then declared the job done.
7:09 Opus verified two to be fair.
7:11 Eight assertions in a headless browser,
7:13 all green.
7:15 That is more than most humans do.
7:17 But Fable behaved like the engineer who
7:19 refuses to trust their own code until it
7:21 survives an attack.
7:23 That paranoia is what you are paying
7:25 double for.
7:26 Now, the honest part
7:28 because this was not a knockout.
7:31 Opus finished almost 3 minutes sooner.
7:35 It used 38% fewer tokens.
7:38 And it runs at half the price.
7:41 $5 in and $25 out per million tokens
7:45 against 10 and 50 for Fable.
7:47 Opus also shipped two ideas Fable never
7:49 had.
7:51 That demo data on first launch, so the
7:53 app never looks dead.
7:55 And custom categories, type anything and
7:57 it invents a color for it on the spot.
8:00 Fable's categories are a fixed list of
8:02 10.
8:03 If you are a developer who reviews every
8:05 line anyway,
8:06 Opus at half price is not a compromise.
8:10 It is the rational choice.
8:12 The real question is what happens when
8:14 nobody reviews the code.
8:15 So, here is the verdict.
8:17 Final score, Fable 11 out of 11.
8:21 Opus 10 out of 11.
8:23 Plus a phone layout.
8:25 My tests only caught because I went
8:27 looking.
8:28 Both apps demo perfectly.
8:31 Both screenshots look shippable.
8:32 The price gap is invisible until month
8:36 three
8:37 when the float drift meets a tax export
8:40 or a user opens the app in a checkout
8:42 line.
8:43 What you are buying for double the money
8:45 is not smarter code.
8:47 It is instincts.
8:50 Integer sense without being asked.
8:53 Testing its own work like an enemy
8:54 would.
8:55 The boring discipline that never shows
8:57 up in a screenshot.
8:59 If a human reviews everything Claude
9:01 writes, save your money and run Opus.
9:04 If the code ships the moment the model
9:06 says done and increasingly that is how
9:09 all of us work,
9:11 then Fable's paranoia is the cheapest
9:13 insurance you can buy.
9:15 I packaged this entire experiment into a
9:18 free test kit.
9:19 The exact prompt I gave both models,
9:23 all 11 automated checks, the full
9:24 scorecard, and a guide to rerun this
9:29 test on any two models in 20 minutes.
9:32 Comment the word ledger,
9:34 the name both models chose on their own,
9:37 and I will send it to you.
9:39 It is also linked below.
9:41 If you want real tests instead of demo
9:43 hype, subscribe.
9:45 This channel runs the experiments the
9:49 launch post skip.
9:50 Bite-size AI drops on Instagram.
9:53 Deep dives here on YouTube. See you in
9:56 the next one.

</details>
