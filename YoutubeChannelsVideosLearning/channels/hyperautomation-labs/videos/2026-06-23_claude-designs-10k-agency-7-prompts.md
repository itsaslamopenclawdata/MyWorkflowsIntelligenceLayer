---
title: "Claude Designs Like a $10K Agency (If You Use These 7 Prompts)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-23"
duration_seconds: 653
video_id: "tnlfiR_0XoE"
url: "https://www.youtube.com/watch?v=tnlfiR_0XoE"
language: "en"
tags: [claude, ai-design, web-design, shadcn, tailwind, design-systems, framer-motion, playwright, prompt-engineering]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-25"
---

# Claude Designs Like a $10K Agency (If You Use These 7 Prompts)

**Channel:** Hyperautomation Labs
**Published:** 2026-06-23
**Duration:** 10:53
**Watch:** https://www.youtube.com/watch?v=tnlfiR_0XoE

## TL;DR

Claude can produce agency-grade website designs for free, but only when briefed like a real creative director instead of given vague adjectives. The video lays out a 7-prompt "design brief" that converts Claude from a generic intern into a senior designer: (1) extract a design language spec from a reference screenshot, (2) define design tokens before any component, (3) name a specific aesthetic movement instead of a vibe, (4) build on shadcn + Radix + Tailwind v4, (5) demand three distinct directions and merge them, (6) add motion with intention via Motion (Framer Motion), and (7) close a screenshot→critique→fix loop (optionally automated with Playwright in Claude Code). The single core thesis: "Vague in, vague out. Specific in, stunning out."

## Key Insights

- **Adjectives are wishes, not briefs.** Words like "modern," "clean," and "sleek" collapse to the average — which is exactly the boring default everyone else gets. A real design brief references concrete artifacts, color systems, type styles, and rules.
- **Show, don't tell — but extract first, don't copy.** Pasting a screenshot of a site you admire and asking Claude to *reverse-engineer the design language as a spec* (hex codes, font pairings, type scale jumps, spacing rhythm, feeling in 3 words) produces dramatically better results than asking for a clone. The spec becomes a reusable brief.
- **Tokens before components.** Defining a design system up front (color roles — background/surface/primary/accent/muted/border; a fixed-ratio type scale; an 8-point spacing system; radius and shadow tokens) with the rule that *every component may only use these tokens* makes the site structurally incapable of looking sloppy.
- **Name the aesthetic, not the vibe.** Naming a real design movement (Swiss, editorial, Bauhaus, brutalist, neobrutalism, glassmorphism) hands Claude an implicit rulebook it already knows. One word — "glassmorphism" vs "Swiss" vs "neobrutalism" — produces three completely different, intentional websites from the same request.
- **Don't handwrite CSS from scratch.** Build on **shadcn** (copy-paste component code, not an installable library) atop **Radix** (free accessibility, keyboard nav, focus management, screen reader support) with **Tailwind v4** (wire design tokens directly into the theme). This is what separates a demo from something you'd ship.
- **Never accept the first idea — demand three.** "Give me three genuinely distinct directions. Not three color swaps of the same layout." Direction A bold/editorial, B calm/premium whitespace, C high-energy/saturated. Pick the winner and merge pieces (headline from A, color from C). This is how studios actually work.
- **Motion with intention is what screams "expensive."** Specify the library (Motion / formerly Framer Motion), the exact behavior (scroll reveal fade-and-lift ~16px, short stagger between grouped items, custom ease-out never linear, durations 200–500ms, respect `prefers-reduced-motion`).
- **Close the loop with screenshots — Claude is designing blind.** Render, screenshot, paste back, and ask Claude to critique itself "like a senior art director doing a design review, and be harsh." Check focal point, 3-second squint test, cramped/floating elements. Fix the top three, re-render. In Claude Code this can run automatically via Playwright — Claude becomes its own art director on a loop.

## Notable Quotes

> "Claude isn't a bad designer. You're just a bad creative director. Stop giving it adjectives and start giving it a brief."

> "Adjectives are wishes. They are not a brief."

> "Vague in, vague out. Specific in, stunning out."

> "It writes the code, but it cannot see what that code actually looks like when it renders. It is designing with its eyes closed."

> "Critique this like a senior art director doing a design review, and be harsh."

> "Motion should reward attention, not demand it."

> "It was never a bad designer. You were just briefing it like a wish instead of a brief."

## Tools and Resources Mentioned

- **Claude** (Anthropic) — primary design tool used throughout.
- **Claude Code** — CLI/agentic variant used to automate the screenshot-critique-fix loop.
- **shadcn** — Not an installable component library; a collection of beautifully designed component code you copy into your own project.
- **Radix** — Accessibility primitives (keyboard nav, focus management, screen reader support) that shadcn components are built on top of.
- **Tailwind v4** — Utility CSS framework; v4 lets you wire design tokens directly into the theme.
- **Motion (formerly Framer Motion)** — Animation library recommended for intentional, restrained motion.
- **Playwright** — Browser automation tool used inside Claude Code to drive a real browser, screenshot Claude's output, and feed it back for self-critique.
- **Awwwards** — Reference site suggested for sourcing screenshot inspiration alongside Linear and Stripe.
- **Linear** and **Stripe** — Cited as examples of sites with strong design language worth reverse-engineering.

## GitHub Repos and URLs Referenced

- **shadcn/ui** — https://ui.shadcn.com (implied; the canonical source for the shadcn component code discussed).
- **Radix UI** — https://www.radix-ui.com (implied; underlying primitives).
- **Tailwind CSS** — https://tailwindcss.com (v4 theme-token integration).
- **Motion (Framer Motion)** — https://motion.dev (formerly framer.com/motion).
- **Playwright** — https://playwright.dev (browser automation for the self-critique loop).
- **Awwwards** — https://www.awwwards.com (reference gallery).
- **Linear** — https://linear.app and **Stripe** — https://stripe.com (cited as design references).
- **Channel: Hyper Automation Labs** — Instagram and Facebook presence mentioned for daily AI build tips. Video also offers a free "design brief kit" of all 7 prompts (word-for-word) to anyone who comments the word **agency** on the video.

## Action Items

- [ ] Pick one reference site from Awwwards / Linear / Stripe, screenshot it, and ask Claude to extract the design language as a spec (hex codes, font pairing, type scale, spacing rhythm, 3-word feeling) — **before** writing any UI code.
- [ ] Define a token-first design system prompt: named color roles, fixed-ratio type scale, 8-point spacing, radius and shadow tokens; enforce "every component uses only these tokens."
- [ ] Replace vague aesthetic words ("modern," "clean," "sleek") in prompts with a named movement — Swiss, editorial, Bauhaus, brutalist, neobrutalism, glassmorphism — and pick one that fits the brand.
- [ ] Switch any hand-rolled CSS workflow to shadcn + Radix + Tailwind v4, with design tokens wired into the Tailwind theme.
- [ ] Add the "three distinct directions" prompt to the workflow; after rendering, pick a winner and explicitly merge pieces across directions (e.g., headline from A, color from C).
- [ ] Add Motion (Framer Motion) with specific behavior: scroll reveal fade-and-lift ~16px, short stagger, ease-out curve, 200–500ms durations, and `prefers-reduced-motion` support.
- [ ] Implement the screenshot → critique → fix loop: render → screenshot → paste back → "critique like a senior art director, be harsh" → fix top three → re-render. Evaluate automating this with Playwright inside Claude Code.
- [ ] Comment **agency** on the video to receive the free 7-prompt design brief kit (word-for-word copies of the prompts used in the video).

## Open Questions

- Which named aesthetic (Swiss, editorial, Bauhaus, brutalist, neobrutalism, glassmorphism) is the best default for a generic SaaS landing page vs a personal portfolio vs an e-commerce storefront?
- How many screenshot-critique rounds are typically needed before the design "holds up" — and what's the token cost / time cost per loop when automated with Playwright?
- Does the token-first approach translate cleanly to non-Claude models (GPT, Gemini, open-source), or is it Claude-specific because of how it handles long structured specs?
- How does the workflow change for mobile-first or responsive-heavy designs, where the reverse-engineered spec is desktop-biased?
- For shadcn + Tailwind v4 token wiring, what's the minimal prompt that reliably produces a theme file Claude can extend without drifting from the token system?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 10:53 transcript)</summary>

0:00 A design agency would charge you $10,000
0:03 to build a website that looks like this.
0:05 Claude can build the exact same thing in
0:07 an afternoon for free.
0:09 But here's the catch.
0:10 Nine out of 10 people who try get
0:12 something that looks cheap, generic,
0:15 like every other AI website on the
0:16 internet.
0:17 And the reason isn't the AI.
0:19 It's one word you keep typing into it.
0:22 In the next 10 minutes, I'm going to
0:23 hand you seven prompts, the same brief a
0:26 real design studio would write,
0:28 that turn Claude from a mediocre intern
0:31 into a senior designer.
0:33 And every single website you're about to
0:34 see,
0:35 Claude built it using exactly these
0:38 prompts. Let's go.
0:40 First, that one word.
0:42 Watch what most people type. Make it
0:45 modern. Make it clean. Make it sleek.
0:48 The problem is that modern is an
0:50 average.
0:51 And when you ask an AI for the average,
0:53 you get the boring, forgettable default
0:55 that everyone else gets to.
0:58 Adjectives are wishes. They are not a
1:00 brief.
1:02 A real agency never briefs a designer
1:04 with "Make it nice."
1:06 They hand over references, a color
1:08 system, a name style, and a set of
1:10 rules. So here's the line I want you to
1:12 remember.
1:13 Claude isn't a bad designer. You're just
1:16 a bad creative director. Stop giving it
1:18 adjectives and start giving it a brief.
1:21 These seven prompts are that brief.
1:23 Number one is the most powerful and
1:25 almost nobody uses it.
1:27 Technique one. Show, don't tell.
1:30 Claude can see.
1:32 You can paste a screenshot of any
1:34 website you admire straight into Claude,
1:37 and it will read the spacing, the type,
1:40 the color, the density,
1:43 far more precisely than it will ever
1:44 understand a word like premium.
1:47 But here's the move almost everyone
1:49 misses. Don't ask it to copy the
1:51 screenshot.
1:52 Ask it to reverse engineer the design
1:54 language first and write you a spec.
1:57 The color palette as hex codes, the font
2:00 pairing, the size jumps between
2:02 headings, the spacing rhythm, the
2:04 feeling in three words.
2:06 Make it commit to the specifics before
2:08 it writes a single line of code. So,
2:10 find one site on Awwwards or Linear or
2:13 Stripe that makes you a little jealous.
2:16 Screenshot it and say, "Don't build
2:18 anything yet. Just extract the design
2:21 language and write it back to me as a
2:22 spec."
2:24 That one reframe is the difference
2:26 between a cheap knockoff and a site that
2:28 inherits real taste.
2:29 Technique two,
2:31 tokens before components.
2:32 This is the secret behind why agency
2:34 websites feel so tight.
2:36 Everything lines up. The colors
2:38 obviously belong together. The corners
2:41 all match.
2:42 That doesn't happen by accident.
2:45 It happens because professionals define
2:47 a design system first.
2:49 And then every button, every card, every
2:52 section inherits from it.
2:53 So, before Claude writes any interface,
2:55 tell it, "Define the tokens first.
2:58 A color palette with named roles,
3:01 background, surface, primary, accent,
3:04 muted, border.
3:06 A type scale with a fixed ratio.
3:08 An eight-point spacing system.
3:11 Radius and shadow tokens.
3:13 One single source of truth. Then give it
3:16 the rule,
3:17 "Every component you build may only use
3:19 these tokens.
3:21 No random hex codes, no one-off pixel
3:23 values."
3:24 This is the screen you're looking at
3:26 right now.
3:27 That's a real design system Claude
3:29 generated from one prompt.
3:31 Build from that, and your site becomes
3:33 structurally incapable of looking
3:35 sloppy.
3:36 Technique three, name the aesthetic.
3:39 This is the fastest upgrade on the
3:41 entire list.
3:43 Instead of modern, name an actual design
3:45 movement.
3:47 Because a named style comes with a
3:48 rulebook that Claude already knows.
3:50 Watch what one word does. Say design and
3:53 you get this.
3:55 A visible grid,
3:56 huge type, brutal white space.
3:59 One accent color, total restraint.
4:01 Say glassmorphism and you get this.
4:03 Depth,
4:05 blur,
4:06 glowing gradients,
4:07 frosted panels. Say neobrutalism and you
4:11 get this.
4:12 Raw,
4:13 loud, thick borders,
4:16 acid color,
4:17 zero apology.
4:19 Same request.
4:20 Three words,
4:21 three completely different, completely
4:23 intentional websites. And not one of
4:25 them looks like the generic AI default.
4:29 Editorial,
4:30 Bauhaus,
4:31 brutalist, Swiss.
4:33 Pick the language that fits your brand.
4:36 And hand Claude the rulebook instead of
4:38 a vibe. Vague in, vague out.
4:42 Specific in, stunning out.
4:44 Technique four, build on real
4:46 foundations.
4:47 Here's where the pros separate from the
4:49 amateurs.
4:50 When you let Claude handwrite CSS from
4:52 scratch,
4:54 you get components that look okay, but
4:55 break.
4:57 Dropdowns that aren't keyboard
4:58 accessible.
5:00 Dialogs that trap your focus.
5:02 Inconsistent everything.
5:05 Instead, tell Claude to build with
5:06 shadcn and Tailwind.
5:09 And one quick truth, because people get
5:11 this wrong all the time.
5:12 shadcn is not a component library you
5:14 install.
5:15 It's a collection of beautifully
5:17 designed component code
5:18 that you copy straight into your own
5:20 project.
5:21 Built on top of something called Radix,
5:23 which handles all the accessibility, the
5:26 keyboard navigation, the focus, the
5:28 screen reader support for free.
5:31 And Tailwind version four lets you wire
5:33 your design tokens right into the theme.
5:36 So, you say, use shadcn components,
5:39 wire in my tokens, keep all the styling
5:42 in Tailwind.
5:43 Now, every menu, every dialog, every tab
5:47 looks handcrafted and behaves like a
5:49 real product.
5:51 That's the difference between a demo and
5:53 something you'd actually ship.
5:55 Technique five, never accept the first
5:57 idea.
5:58 When you give Claude one prompt, you get
6:00 its safest, most average answer.
6:03 Literally, the first thing it thought
6:05 of.
6:06 But a real agency never shows a client
6:08 one concept. They show three. So, do
6:11 exactly that.
6:12 Tell Claude, "Give me three genuinely
6:14 distinct directions.
6:16 Not three color swaps of the same
6:17 layout."
6:18 Direction A,
6:20 bold and editorial.
6:21 Direction B, calm and premium, lots of
6:24 white space.
6:26 Direction C, high energy, saturated,
6:29 unconventional.
6:30 Render all three side by side.
6:33 And now, you're not a prompter anymore.
6:35 You're the creative director.
6:38 You look at three real options. You pick
6:40 the winner, and you tell Claude which
6:43 pieces to merge.
6:44 Take the headline from A, the color from
6:46 C.
6:47 That is how studios actually work, and
6:49 it costs you exactly one prompt.
6:52 Technique six, make it move with
6:55 intention.
6:56 Here's what silently screams expensive
6:58 on a website.
7:00 It's not the colors, it's the motion.
7:03 Sections that gently rise into view as
7:05 you scroll.
7:07 Buttons that respond the instant your
7:09 cursor touches them.
7:11 Nothing abrupt, nothing janky.
7:14 The amateur tell is motion that's either
7:16 missing completely
7:17 or way, way too much.
7:20 So, be specific.
7:22 Tell Claude to use motion.
7:24 That's the animation library that used
7:26 to be called Framer Motion.
7:28 And ask for the exact behavior.
7:31 Scroll
7:32 reveal
7:34 that fades and lifts elements
7:36 in by about 16 pixels.
7:39 A short stagger between items in a
7:42 group.
7:43 A custom ease out curve,
7:45 never linear.
7:46 Durations between 2 and 500
7:49 milliseconds.
7:50 And respect reduced motion
7:53 for accessibility.
7:55 Motion should reward attention, not
7:58 demand it.
7:59 Get this one right, and a flat static
8:02 template suddenly feels like a living
8:04 breathing product.
8:06 Technique seven. And this is the one
8:07 that closes the gap completely.
8:10 Here is Claude's single biggest blind
8:12 spot.
8:13 It writes the code, but it cannot see
8:15 what that code actually looks like when
8:16 it renders.
8:18 It is designing with its eyes closed.
8:20 So, you become its eyes.
8:22 Render the page,
8:24 take a screenshot, and paste it right
8:26 back to Claude with this instruction.
8:28 Critique this like a senior art director
8:30 doing a design review, and be harsh.
8:33 Is there one clear focal point?
8:35 Does the hierarchy survive a 3-second
8:37 squint test?
8:39 Is anything cramped or floating?
8:42 Then fix the top three problems and
8:43 re-render.
8:45 Watch this. This is version one.
8:47 Flat.
8:48 Everything competing for attention.
8:51 And this is the same site after two
8:53 rounds of that screenshot and critique
8:55 loop. That is the glow up. And if you
8:58 use Claude code, you can make this run
9:00 completely automatically.
9:02 It drives a real browser through the
9:04 Playwright tool,
9:05 screenshots its own work,
9:07 critiques it, and fixes it on a loop
9:10 until the design holds up. Claude
9:12 becomes its own art director.
9:14 So, let's put the whole brief together.
9:16 Seven prompts.
9:17 Show a reference and extract the design
9:19 language.
9:20 Define your tokens before any component.
9:23 Name a real aesthetic instead of a vibe.
9:26 Build on Shadcn and Radix.
9:29 Demand three directions, then merge.
9:31 Add motion with intention.
9:33 And close the loop with screenshots.
9:36 None of these are tricks.
9:38 This is simply what a real design studio
9:40 does.
9:41 And now you can hand that exact brief to
9:44 Claude for free.
9:46 So, remember the one line.
9:48 It was never a bad designer.
9:52 You were just briefing it like a wish
9:53 instead of a brief.
9:55 Fix that one thing and the $10,000
9:57 website is a single afternoon away.
10:00 Now, I packaged all seven of these
10:02 prompts,
10:03 the full
10:04 copy and paste
10:06 word-for-word versions,
10:08 the exact ones I used to build every
10:11 site in this video,
10:13 into one free design brief kit.
10:16 To get it, just comment the word agency
10:18 on this video and I'll send it straight
10:20 to you.
10:21 If you want to go deeper, I've got
10:22 premium guides on Claude code and
10:25 building with AI, all linked down in the
10:27 description.
10:28 I post quick AI build tips every single
10:30 day on Instagram and on Facebook, both
10:32 at Hyper Automation Labs, and the full
10:35 deep dives like this one right here on
10:37 YouTube. So, do three quick things.
10:40 Subscribe here on YouTube,
10:42 follow me on Instagram and Facebook, and
10:44 grab that free kit by commenting agency.
10:47 Then go build something that doesn't
10:49 look like everyone else's. I'll see you
10:51 in the next one.

</details>