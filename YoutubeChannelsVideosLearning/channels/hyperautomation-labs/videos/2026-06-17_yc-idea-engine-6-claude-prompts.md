---
title: "YC Just Said Stop Hunting the Perfect Startup Idea — I Turned Their Framework Into 6 Claude Prompts"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-17"
duration_seconds: 765
video_id: "-ya1zrj608c"
url: "https://www.youtube.com/watch?v=-ya1zrj608c"
language: "en"
tags: [AI startup ideas, AI tools for founders, AI workflow, Boom Supersonic, Claude, Claude Code, Corgi Insurance, GovDash, Paul Graham, Y Combinator, YC startup school, build a startup, entrepreneurship, founder market fit, how to choose a startup idea, how to pick a startup idea, startup advice, startup idea framework, startup ideas, verticalize]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-18"
---

# YC Just Said Stop Hunting the Perfect Startup Idea — I Turned Their Framework Into 6 Claude Prompts

**Channel:** Hyperautomation Labs  **Published:** 2026-06-17  **Duration:** 12:45  **Watch:** https://www.youtube.com/watch?v=-ya1zrj608c

## TL;DR
A YC partner's framework for picking a startup idea is encoded as 6 Claude prompts that force a single pick, "burn the boats" on the alternatives, drill deep enough to run the customer's business, and stress-test the idea against three AI-era filters. The 6 prompts run sequentially — pick → commit → deep-customer-simulation → AI-capability edge → verticalize to own the outcome → most ambitious rewrite → failure-postmortem. The output of step 6 is usually a *different*, better idea than the one you walked in with.

## Key Insights
- **Two founder traps YC names explicitly:** (1) waiting for the perfect idea before committing, and (2) weaponizing founder-market-fit to delay starting. Both freeze you. (0:15–2:25)
- **The "burn the boats" test is concrete:** new company name, new website, new emails, new internal story. GovDash pivoted 5 times and changed identities each time before their 5th idea worked — they're now post-Series B. (3:40–4:50)
- **The "could you run your customer's business" test is the brutal depth check:** if you want to build voice agents for cleaning companies, you need to know what the phone-miss problem actually costs a cleaning business per day. The 2nd prompt simulates the customer's brutal day hour-by-hour and generates 20 expert-level interview questions. (4:50–6:15)
- **The 3 AI-era filters to score a committed idea:** (a) sits at the edge of what models can do — your product might barely work today but the unblocking bottleneck is a company in itself, (b) verticalizes to own the outcome (Corgi didn't build insurance software, it became an insurer), (c) most ambitious version of itself — the cost of chasing a wildly ambitious idea ≈ the cost of a modest one. (6:30–9:45)
- **Paul Graham's "live in the future, then build what's missing" reframed:** the 3rd prompt asks the model to map your idea against current frontier capabilities and name the single biggest thing it can't reliably do. If the gap closes on its own, ride the wave; if it doesn't, that unsolved bottleneck may be the actual business. (7:00–8:00)
- **The deepest insight in the framework:** going deep rarely validates your first idea — it surfaces the better idea hiding underneath. The 6th prompt is a postmortem that names the deeper structural problem your customers kept circling. (10:45–12:00)

## Notable Quotes
> "Startups are brutally hard. So surely you should find the best possible idea before you commit. But YC's point is that the perfect idea does not exist on paper." — 1:15
> "If several ideas look equally attractive, you don't keep them all alive. You choose one." — 3:14
> "In the early fog, where you can only see 10 ft ahead, the instinct is to take tiny steps in every direction. That teaches you almost nothing. Pick one direction and walk fast." — 11:54
> "Don't build software for insurance companies. Be the insurer. Don't sell back office tools to banks. Be the bank." — 8:13

## Tools and Resources Mentioned
- **Claude (Anthropic)** — the free AI model used to run the 6-prompt engine. Not OpenAI Codex or Google's Antigravity.
- **YC partner John's original video** — the source framework (not linked in the transcript, referenced as the genesis).
- **Hyper Automation Labs' "AI era Idea Engine" free guide** — comment "boats" or use the description link. Comment-driven lead magnet, not a vendored product.

## GitHub Repos and URLs Referenced
- No GitHub repos referenced in this video.
- **GovDash** (referenced as case study): https://www.govdash.com — government contract SaaS, post-Series B after 5 pivots.
- **Corgi Insurance** (referenced as case study): https://www.corgiinsurance.com — AI-era verticalized insurer that acquired a carrier during YC batch.
- **Boom Supersonic** (referenced as founder-market-fit counterexample): https://boomsupersonic.com — Blake Scholl's ad-tech-to-supersonic pivot.

## Action Items
- [ ] Pick one idea from your short list and run the 1st prompt — score each on curiosity + unfair advantage, force a single pick.
- [ ] Burn the boats: rename the project, change the email, write a new internal story about why you're building it.
- [ ] Run the 2nd prompt against your committed idea to simulate a brutal day in the customer's business and generate 20 expert-level interview questions.
- [ ] Ask the model to name the single biggest thing current frontier models can't reliably do for your use case — that's your radar for a future-proof company.
- [ ] Push the idea down the value chain (4th prompt) — "what's the full outcome my customer wants, and what would it take to own it?"
- [ ] Run the postmortem prompt (6th) on any failed idea to surface the deeper structural problem hiding underneath.

## Open Questions
- Which of the 6 prompts is the right starting point for a founder who hasn't yet committed to any domain?
- How often does the "deeper idea underneath" surface from the 6th prompt become a different industry than the original?
- Is the 3-filter scoring system (edge of models, verticalize, ambitious) stable across non-AI sectors, or does it depend on AI's specific cost dynamics?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 12:45 transcript)</summary>

0:00 Right now, you've probably got three or four startup ideas sitting in open browser tabs, and you keep telling yourself that once you figure out which one is the winner, that's when you'll really commit.
0:15 Yesterday, a partner at Y Cominator named John posted a short video that says this exact instinct is the reason most founders never actually start. I watched it and then I did something with it. I took YC's framework, the one they're teaching founders right now, and I turned it into a workflow you can run today with a free AI model. It picks your one idea, it forces you deep enough to find the real opportunity, and it surfaces the better idea, hiding underneath the one you walked in with. Every prompt is on screen, and the full pack is free at the end.
0:58 Let's build it. Here's the trap in John's words. Founders overthink in two ways. The first is waiting for the perfect idea. It feels responsible. Startups are brutally hard. So surely you should find the best possible idea before you commit. But YC's point is that the perfect idea does not exist on paper. You can only discover what's actually worth building by making contact with reality and getting feedback from real customers.
1:33 The second trap is asking, am I even the right founder for this? Founder market fit is real. A non-technical founder probably won't dream up the killer developer tools company. But John says founders, especially second time founders, weaponize this against themselves. They convince themselves they need a decade of domain experience before they're allowed to start. They don't. Blake Scholes spent his early career on ad tech at Amazon and Groupon, then decided to go commercialize supersonic flight. People thought he was insane. Boom is now a billion dollar company.
2:17 So the first job isn't to find the perfect idea. It's to stop letting these two questions freeze you. So let's get unstuck. Instead of agonizing in your head, make the AI do the cold structured comparison you keep avoiding. Here's the first prompt in the engine. You paste in your short list of ideas and you tell the model to score each one on two axes only. how genuinely curious you are about the problem and how much unfair insight or access you already have. Not market size, not how big the exit could be, just curiosity and unfair advantage. Because those are the two things that keep you going deep when it gets hard. The model ranks them, explains the trade-offs, and forces a single pick. The rule from YC is simple. If several ideas look equally attractive, you don't keep them all alive. You choose one. The point of this prompt isn't that the AI is smarter than you. It's that it ends the stalling. You walk away with one idea and permission to commit to it.
3:36 Now comes the part most people skip. YC calls it burning the boats. Once you've picked, you explicitly close the other doors. You stop working on the other ideas. You tell any customers you've pivoted. You go all in on the one. John describes going deep as putting on a new skin, becoming an almost unrecognizable version of yourself. New company name, new website, new emails, even a new internal story about why you're building this. He worked with a startup called Gvash that helps companies win government contracts. They pivoted at least five times before landing on it and every single time they changed their name and how they talked about their mission. At one point, John literally lost contact with them because they kept changing their email addresses. By actually becoming experts in government procurement, their fifth idea worked so well they could barely keep up with demand. They just raised a series B.
4:52 So, you've committed. How do you know if you're actually going deep or just telling yourself you are? John gives one brutal test. Could you run your customers business? Say you want to build voice agents for cleaning companies. The question isn't whether you talk to 20 owners. It's this. If I dropped you into a cleaning business tomorrow, would you know how to run it? Do you know their daily fires? Do you know if answering the phone is even a top five problem? Do you know how much money they lose when a call goes unanswered and what they'd pay to never lose another one? This is where AI becomes a genuine unfair advantage. And here's the second prompt. You tell the model to act as a skeptical owner of that exact business and to walk you through a brutal day in their life, hour by hour, naming every fire and what it costs them. Then you flip it. You ask it to generate the 20 questions a true expert could answer that a tourist couldn't. Those become your interview script for real customers. The AI doesn't replace talking to humans. It makes sure that when you do, you ask like an insider instead of a tourist. The goal, in John's words, is a tight loop. Understand the customer. Ship something. Understand them deeper. Ship something better.
6:25 Once you're deep, YC gives three filters to know if the idea is worth continuing in the AI era. The first, a great idea today sits right at the edge of what models can do. That means your product might barely work on the best models that exist right now, but it clearly gets better as they improve. Here's why that's gold. If you understand exactly which bottleneck is holding your product back, then solving that bottleneck can become the entire company. This is Paul Graham's old line. Live in the future, then build what's missing. So the third prompt asks the model to map your idea against current frontier capabilities and name the single biggest thing it can't reliably do yet for your use case. That gap is your radar. If models get better and the gap closes on its own, you ride the wave. If it doesn't close, that unsolved bottleneck might be the actual business hiding inside your idea.
7:41 The second filter, the best ideas verticalize, meaning they eventually sell an outcome, not just software. Think about it. In the AI era, the cost of producing software is racing towards zero. So software for X stops being the valuable part. What becomes valuable is customer trust, licenses, regulatory permission, and owning the outcome. YC's blunt version. If you want into insurance, don't build software for insurance companies. Be the insurer. Don't sell back office tools to banks. Be the bank. AYC company called Corgi did exactly this. They refused to just be a tech enabled broker because that's owning a sliver. Instead, they went after the whole commercial insurance stack from underwriting to customer service and even acquired an insurance carrier during their batch to pull it off. So, the fourth prompt pushes your idea down the value chain and asks, "What's the full outcome my customer actually wants and what would it take to own that outcome instead of just selling them a tool?"
8:53 The third filter is the one that separates the toys from the companies. Your idea should be the most ambitious version of itself. Here's the counterintuitive part. The cost of chasing a wildly ambitious idea and the cost of chasing a modest one are roughly the same. Both are brutally hard. Both eat your time and your life. So, you might as well aim at the version that if it works, rewrites a whole sector of the economy because that's also the version that scares off competitors, attracts the best people, and earns a moat worth building. The fifth prompt takes your committed idea and asks the model to rewrite it three times, each more ambitious than the last, until the final version is taking on a regulated industry or a 10 billion incumbent or genuinely hard technology. You're not required to build the most extreme one, but you should know what it looks like because that's the direction worth walking.
10:16 Now, the question everyone's actually scared of. What if you do all this and the idea fails? Here's the part that flips the whole thing. You end up dramatically better off than when you started. You have real unambiguous customer data. You know whether there was ever a hair on fire problem here or whether you just talked yourself into one. And most importantly, you almost always walk away with a new idea that actually works. Because when founders start, they're solving surface level pain. The real opportunities are the deeper structural problems underneath. Going deep was never really about validating your first idea. It's how you find the better one hiding under it. So the last prompt in the engine is a postmortem. You feed in everything you learned and you ask the model to name the deeper structural problem your customers kept circling, the one nobody has built for yet. That answer is often the real company.
11:29 So here's the whole engine. Stop hunting for the perfect idea and just pick one. Burn the boats. Get deep enough that you could run your customers business. Run it through the three AI era filters. Edge of the models, own the outcome, most ambitious version. And when something breaks, mine it for the idea underneath. In the early fog, where you can only see 10 ft ahead, the instinct is to take tiny steps in every direction. that teaches you almost nothing. Pick one direction and walk fast. I packaged all six prompts into a free guide called the AI era Idea Engine. Comment the word boats and I'll send it straight to you or grab it at the link in the description. If you want to go deeper, my paid build guides are linked there, too. And if this gave you a real edge, follow Hyper Automation Labs on YouTube, Instagram, and Facebook because this is what I do here every single day. Now go pick one and go deep.

</details>
