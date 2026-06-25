---
title: "Run AI On Your Laptop for FREE — Private, Offline, No GPU (Full Guide)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-24"
duration_seconds: 655
video_id: "bjLPFQ4AzaE"
url: "https://www.youtube.com/watch?v=bjLPFQ4AzaE"
language: "en"
tags: [local-llm, ollama, qwen, llama, gemma, mlx, quantization, context-window, vscode, privacy, offline-ai]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-25"
---

# Run AI On Your Laptop for FREE — Private, Offline, No GPU (Full Guide)

**Channel:** Hyperautomation Labs
**Published:** 2026-06-24
**Duration:** 10m 55s
**Watch:** https://www.youtube.com/watch?v=bjLPFQ4AzaE

## TL;DR

You can run a genuinely useful coding AI on a normal laptop — no GPU, no subscription, no internet — in about 5 minutes using Ollama. The entire decision boils down to three numbers: (1) your available RAM (the operating system eats a few GB), (2) model parameter count (≈0.5–0.7 GB per billion params at Q4 quantization), and (3) context window size (which lives in the same RAM as the model). Match the model to your memory tier — 3–4B for 8 GB laptops, 7–8B for 16 GB, 14B for 24–32 GB — and pick Q4-quantized variants (which Ollama defaults to) for the best size/quality trade. On a 16 GB Apple Silicon machine, Qwen 2.5 Coder 7B ran at ~48 tokens/sec, wrote clean Python offline, and used ~4.7 GB on disk. Three small upgrades turn it from a toy into a daily driver: wire it into VS Code via Continue, prefer MLX-tagged models on Apple Silicon, and enable KV-cache quantization for longer conversations.

## Key Insights

- **Local AI is a memory problem, not a GPU problem.** The whole model must fit in RAM (or unified memory on Macs) all at once. Once you accept that, model selection becomes a simple arithmetic exercise.
- **The rule of thumb: ~0.5 GB of RAM per billion parameters at full precision, ~0.7 GB at Q4 quantization.** So a 7B model ≈ 4–5 GB at Q4; a 14B model ≈ 8–10 GB. A "16 GB laptop" really gives you 11–12 GB usable after the OS.
- **Quantization (Q4) is essentially free quality-wise.** It rounds model weights from high precision to ~4-bit — like JPEG-compressing a photo. You trade a barely-perceptible quality loss for ~70% memory savings. Ollama applies Q4 by default.
- **Context window is the silent killer.** The model's "short-term memory" (everything typed + everything it generated this conversation) lives in the same RAM as the model itself. Paste a huge file and you blow past your ceiling — the model slows to a crawl or crashes.
- **Formula:** Total RAM needed = model size + active context + OS overhead. Stay under that total and you're fine. A smaller model with breathing room beats a bigger one that's suffocating.
- **Cheat sheet by RAM tier:**
  - 8 GB → 3–4B models (great for chat, simple code)
  - 16 GB → 7–8B models (the sweet spot; genuinely useful for real coding)
  - 24–32 GB → 14B models (serious work)
  - 32 GB+ → 30B+ models unlock
- **Practical demo numbers (Apple Silicon laptop):** Qwen 2.5 Coder 7B = 4.7 GB on disk, ~48 tokens/sec generation, clean correct Python, fully offline. Faster than you can read.
- **Three upgrades that turn a toy into a daily driver:**
  1. Wire the local model into VS Code via the free **Continue** extension (or any client extension) → private autocomplete + chat right in your editor.
  2. On Apple Silicon, prefer models tagged **MLX** — they're tuned for the architecture and run noticeably faster.
  3. Enable **KV-cache quantization** → compresses the context memory so you can fit much longer chats into the same RAM.
- **Setup is genuinely 5 minutes and 3 commands** (Mac/Windows/Linux the same):
  1. Download Ollama from ollama.com
  2. `ollama run qwen2.5-coder:7b` (downloads on first run)
  3. Type your prompt. `/bye` to exit. Swap `qwen2.5-coder:7b` for any other model name.

## Notable Quotes

> "Your laptop can run an AI that writes real code. Completely free, completely private, with no internet, no subscription, and nothing ever leaving your machine."

> "There are only three numbers that decide whether running AI locally feels like magic or misery."

> "Running a model locally is not really about how fast your processor is. It comes down to a single resource — memory."

> "Quantization simply rounds those numbers down to a smaller size, exactly like saving a photo as a compressed JPEG instead of a giant raw file."

> "A smaller model with room to breathe will beat a bigger model that's suffocating. Don't just max out the model size. Always leave headroom for the conversation."

> "If you can copy and paste one line, you can run AI locally."

> "Running AI locally was never about a fancy graphics card. It's about three numbers."

## Tools and Resources Mentioned

- **Ollama** — free, tiny desktop app that runs local LLMs via a single CLI command. Cross-platform (Mac/Windows/Linux). Defaults to Q4 quantization. Site: ollama.com
- **Qwen 2.5 Coder (7B)** — standout coding model for 16 GB machines; punches "absurdly above its size"
- **Google Gemma** — "fantastic and tiny" all-rounder for writing and reasoning
- **Llama** — rock-solid for general chat
- **Smaller Qwen models** (3–4B tier) — recommended for 8 GB machines
- **MLX-tagged models** — Apple-Silicon-tuned variants that run noticeably faster on M-series Macs
- **Continue** (VS Code extension) — free extension that plugs a local Ollama model into VS Code for private autocomplete and chat
- **Client extension for VS Code** — generic name referenced for editor integration
- **KV-cache quantization** — Ollama setting that compresses context memory so longer conversations fit in the same RAM
- **Author's free one-page cheat sheet** — model picks per memory size, exact commands, speed settings. Available by commenting "offline" on the video or via the link in the description.
- **Author's four paid guides** — Claude Code, Codex, and AI workflows (for going from local setup to building real systems). Links in the video description.

## GitHub Repos and URLs Referenced

- https://ollama.com — Ollama download and model library
- https://www.youtube.com/watch?v=bjLPFQ4AzaE — source video

## Action Items

- [ ] Check your machine's actual available RAM (Task Manager on Windows, About This Mac → Memory on Mac) and subtract ~3–4 GB for OS overhead to get your usable ceiling.
- [ ] Download Ollama from ollama.com and install it.
- [ ] Run `ollama run qwen2.5-coder:7b` in a terminal and verify it works (asks it to write a Python function).
- [ ] On Apple Silicon, search for an MLX variant of the model you want for a noticeable speed boost.
- [ ] Install the Continue extension in VS Code and point it at your local Ollama model for in-editor private autocomplete.
- [ ] Enable KV-cache quantization in Ollama to fit longer conversations in the same RAM.
- [ ] Bookmark the Ollama model library page so you can swap in `llama`, `gemma`, `qwen`, etc. by just changing the name.
- [ ] Comment "offline" on the video to get the free one-page cheat sheet (or use the link in the description).

## Open Questions

- How does KV-cache quantization interact with very long code files or large PDF ingest — any quality degradation at extreme context lengths?
- Are MLX models always strictly faster than their non-MLX equivalents on Apple Silicon, or is the trade-off model-dependent?
- For an 8 GB laptop specifically, which 3–4B model gives the best balance of code quality vs. chat quality — Qwen, Gemma, or Llama?
- Does the ~48 tokens/sec figure on Apple Silicon scale predictably with unified memory tier (e.g., 8 GB vs 16 GB vs 24 GB), or does it plateau?
- How does Qwen 2.5 Coder 7B compare to a 14B general-purpose model like Llama 3.1 14B on real refactor tasks, given the same memory budget?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 10m 55s transcript)</summary>

```
0:00 Your laptop can run an AI that writes
0:02 real code.
0:03 Completely free,
0:05 completely private, with no internet, no
0:08 subscription, and nothing ever leaving
0:11 your machine. But, almost everyone who
0:13 tries it picks the wrong model, watches
0:16 it crawl, and quits,
0:18 convinced their computer just isn't good
0:20 enough.
0:21 It almost always is.
0:24 There are only three numbers that decide
0:26 whether running AI locally feels like
0:28 magic or misery.
0:31 Once you know them, you'll pick the
0:32 perfect model in about 10 seconds.
0:35 I'll walk you through all three,
0:36 tell you exactly which models to
0:38 download, and show you the real numbers
0:41 from running one on a normal laptop.
0:42 Let's go.
0:43 First, why even run AI on your own
0:46 machine when ChatGPT exists? Three
0:49 reasons.
0:50 One, privacy.
0:52 The model runs entirely on your
0:55 computer.
0:56 Your code, your documents, your
0:58 half-formed ideas, none of it ever
1:00 leaves the laptop. Two, it's free.
1:03 No $20 a month subscription, no per
1:06 message bill, no credit card at all. Run
1:09 it a million times, it costs you
1:10 nothing. Three, no limits, and no
1:14 internet needed.
1:15 On a plane, in a cafe with terrible
1:17 Wi-Fi,
1:18 at 2:00 in the morning,
1:20 it just works.
1:21 And it never tells you you've hit your
1:23 usage cap.
1:24 The only catch is that you have to pick
1:26 a model that actually fits your machine.
1:29 And that is exactly where the three
1:31 numbers come in.
1:32 Here's the one idea that makes all of
1:34 this click.
1:35 Running a model locally is not really
1:38 about how fast your processor is.
1:41 It comes down to a single resource,
1:44 memory,
1:45 the RAM,
1:47 or on a Mac, the unified memory inside
1:50 your machine.
1:52 The entire model has to fit inside that
1:54 memory, all at once.
1:57 So, everything we're about to cover
1:59 reduces to three numbers.
2:01 Number one,
2:02 how much memory the model needs.
2:05 Number two,
2:06 quantization.
2:08 A trick that shrinks that number by
2:10 about 70%
2:12 almost for free.
2:14 And number three,
2:15 the context window.
2:17 The silent killer that quietly eats your
2:20 memory and grinds everything to a halt.
2:24 Get these three right and you will never
2:26 pick a bad model again.
2:28 Number one,
2:29 the memory ceiling.
2:31 A model is really just a giant pile of
2:33 numbers called parameters.
2:35 7 billion of them,
2:37 14 billion, and so on.
2:40 To run, every single parameter has to
2:42 load into memory.
2:44 Here's the rule of thumb worth
2:45 memorizing.
2:46 At the normal setting, a model needs a
2:49 little over half a gigabyte of memory
2:51 for every billion parameters.
2:54 So, a 7 billion model needs roughly 4 to
2:56 5 gigabytes.
2:58 A 14 billion needs 8 to 10. Now, look at
3:01 your own machine.
3:02 But remember, you can't use all of it.
3:06 Your operating system needs a few
3:07 gigabytes just to run.
3:09 So, on a 16 gigabyte laptop, you've
3:11 realistically got 11 or 12 to play with.
3:14 Which makes a 7 or 8 billion model your
3:16 sweet spot.
3:17 That's the ceiling.
3:19 Stay under it and everything stays
3:21 smooth.
3:22 Number two,
3:23 quantization.
3:25 This is the one that feels like
3:27 cheating.
3:28 By default, a model stores each of its
3:30 numbers in full
3:32 high precision.
3:33 That's accurate, but enormous.
3:37 Quantization simply rounds those numbers
3:39 down to a smaller size,
3:41 exactly like saving a photo as a
3:43 compressed JPEG instead of a giant raw
3:46 file.
3:47 And the trade is incredible.
3:50 The most popular setting called Q4
3:53 cuts the model's memory footprint by
3:55 around 70%.
3:56 And in real everyday use, you can barely
3:58 tell the quality changed.
4:00 That same 7 billion model that needed 14
4:02 GB at full precision
4:04 quantized to Q4 it's under five.
4:07 That is the entire reason a normal
4:09 laptop can run these at all.
4:11 And the good news?
4:12 When you download a model with a tool
4:14 like Ollama, it's already quantized
4:16 sensibly for you. Just remember, Q4 is
4:19 your friend.
4:20 Number three.
4:21 The context window.
4:23 This is the one everyone forgets.
4:26 And the one that secretly ruins the
4:27 experience.
4:29 The context window is the model's
4:31 short-term memory.
4:33 Everything you've typed plus everything
4:35 it has written back in the current
4:37 conversation.
4:38 Here's the catch.
4:39 That memory is not free.
4:42 It also lives in your RAM
4:44 sitting right on top of the model
4:45 itself.
4:47 The longer the conversation, the more
4:49 memory it eats.
4:50 Paste a huge file into the chat and you
4:53 can blow straight past your ceiling.
4:55 The model spills out of fast memory
4:57 and either slows to a crawl or simply
4:59 crashes.
5:01 So, here's the real lesson.
5:03 A smaller model with room to breathe
5:05 will beat a bigger model that's
5:07 suffocating.
5:09 Don't just max out the model size.
5:11 Always leave headroom for the
5:12 conversation.
5:13 So, let's combine the three numbers into
5:15 one simple formula.
5:17 The memory you need equals the model's
5:20 size
5:21 plus the context
5:23 plus a little for your system.
5:25 As long as that total stays under your
5:27 machine's memory
5:28 you are golden.
5:30 Here's the cheat sheet version.
5:32 On 8 GB, run a three to four billion
5:35 model seem
5:36 great for chat and simple code.
5:38 On 16 GB, the sweet spot
5:41 run a seven or eight billion model
5:43 genuinely useful for real coding.
5:45 On 24 or 32 GB you can step up to a 14
5:49 billion model and get serious. And above
5:51 that, the big 30 billion plus models
5:54 open up.
5:55 Notice what this is all about.
5:56 Memory.
5:57 Not some thousand dollar graphics card.
6:00 If you've got an Apple silicon Mac or
6:02 any laptop with decent RAM, you're
6:04 already in the game. Ready in.
6:06 All right, actual names.
6:08 What should you download?
6:10 For coding on a 16 GB machine, the
6:13 standout right now is Qwen 2.5 coder,
6:16 the 7 billion version.
6:18 It punches absurdly above its size.
6:21 And it's the one I'll run for you in a
6:23 moment.
6:24 If you want a brilliant all-rounder for
6:25 writing and reasoning,
6:27 Google's Gemma models are fantastic and
6:29 tiny.
6:31 For general chat, Llama and the smaller
6:34 Qwen models are rock solid.
6:36 And if you're on 8 GB, just drop to
6:38 just drop to the 3 to 4 billion versions
6:40 of those same families.
6:42 The beautiful part,
6:44 every one of these is free, open, and a
6:47 single command away.
6:49 You don't have to guess.
6:50 Match the model to your memory tier and
6:53 it simply works.
6:55 Now, let me prove this isn't just
6:56 theory.
6:57 So, what does this actually look like in
6:59 practice?
7:00 I ran exactly this on an Apple silicon
7:03 laptop and these are the real numbers.
7:06 Asked to write a Python function.
7:08 Qwen
7:10 2.5 coder produced clean, correct code
7:12 in seconds. Offline, with no internet
7:14 connection at all.
7:16 The model is 4.7 GB on disk.
7:20 It generates around 48 tokens a second,
7:22 faster than you can read.
7:24 And it runs entirely in local memory.
7:27 No API key, no bill, no data leaving the
7:30 machine.
7:31 That's a genuinely capable coding
7:33 assistant running on a normal laptop for
7:36 absolutely nothing.
7:38 Now, here's exactly how you set this up
7:39 yourself, step by step.
7:41 Here's the whole setup.
7:43 Three steps,
7:44 about 5 minutes,
7:46 and it works the same on
7:47 Mac, Windows, and Linux.
7:51 Step one.
7:52 Go to ollama.com
7:54 and download Ollama.
7:56 It's a free, tiny app that runs models
7:59 for you.
8:00 Install it like any other program.
8:02 Step two.
8:04 Open your terminal and type
8:06 Ollama
8:08 run quant 2.5 coder colon 7B.
8:11 The very first time, it downloads the
8:13 model, a few gigabytes,
8:15 just once.
8:17 Step three.
8:18 That's it.
8:20 It's running.
8:21 Start typing.
8:22 Ask it to write code,
8:24 explain an error,
8:25 refactor a function.
8:27 To leave, type {slash} bye.
8:30 And to try a different model,
8:31 just swap the name.
8:33 Ollama run Gemma.
8:35 That is the entire learning curve.
8:37 If you can copy and paste one line, you
8:40 can run AI locally.
8:42 Once you're hooked, three small upgrades
8:44 take this from a toy to a daily driver.
8:47 One,
8:47 connect it to your code editor.
8:49 Free tools like Continue or the client
8:52 extension
8:53 for VS Code
8:55 plug a local model
8:57 straight into your editor,
8:58 giving you private auto complete and
9:00 chat
9:01 right where you already work.
9:02 Two,
9:03 if you're on a Mac, look for models
9:05 labeled MLX.
9:07 They're tuned specifically for Apple
9:09 silicon and run noticeably faster.
9:11 And three,
9:12 if you want longer conversations without
9:14 blowing past your memory,
9:15 turn on KV cache quantization, that is.
9:17 It compresses that context memory we
9:19 talked about,
9:20 so you can fit much longer chats into
9:22 the same RAM.
9:23 Tiny settings,
9:25 big difference.
9:26 And every single one of them is free.
9:29 So, let's lock it in.
9:30 Running AI locally was never about a
9:32 fancy graphics card. It's about three
9:34 numbers.
9:35 One, memory,
9:37 a little over half a gig per billion
9:38 parameters. So, match the model to your
9:41 RAM.
9:42 Two,
9:42 quantization.
9:44 Q4 shrinks it about 70%
9:47 almost for free.
9:48 And it's handled for you by default.
9:50 And three, context. Leave headroom.
9:53 Because a smaller model that can breathe
9:56 always beats a bigger one that's
9:57 choking.
9:59 Match the model to your memory tier.
10:01 Run one command and you've got a
10:02 private, free, offline AI assistant of
10:05 your own.
10:06 I packed every piece of this. The model
10:08 picks for each memory size,
10:10 the exact commands, and the speed
10:12 settings
10:13 into a free one-page cheat sheet.
10:15 To grab that cheat sheet,
10:17 just comment the word offline
10:20 and I'll send it straight to you. Or get
10:23 it from the link below.
10:24 And if you want to go further, my four
10:26 guides on cloud code, code X, and AI
10:29 workflows
10:30 take you from this all the way to
10:32 building real systems.
10:34 The links are in the description.
10:36 If this just saved you a setup headache,
10:38 do one thing for me.
10:40 Subscribe here on YouTube and follow
10:43 Hyper Automation Labs on Instagram and
10:45 Facebook. I do the boring research and
10:47 testing so you get the simple,
10:49 honest version.
10:50 Now, go run your first model. I'll see
10:52 you in the next one.
```

</details>
