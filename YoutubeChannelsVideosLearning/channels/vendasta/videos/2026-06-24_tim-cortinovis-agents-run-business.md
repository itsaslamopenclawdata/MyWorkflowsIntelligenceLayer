---
title: "AI Agents Run 98% of His Business (No-code Setup)"
channel: "Vendasta"
channel_slug: "vendasta"
channel_id: "UCooW1kDrMUb1EORhDbmciOw"
published: "2026-06-24"
duration_seconds: 981
video_id: "12yzXz_oYmY"
url: "https://www.youtube.com/watch?v=12yzXz_oYmY"
language: "en"
tags: [ai-agents, no-code, sales-automation, proposal-agent, keynote-business, vendasta, solopreneurship]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-26"
---

# AI Agents Run 98% of His Business (No-code Setup)

**Channel:** Vendasta  **Published:** 2026-06-24  **Duration:** 16:21  **Watch:** https://www.youtube.com/watch?v=12yzXz_oYmY

## TL;DR

Tim Cortinovis (Forbes "tech visionary," Thinkers360 top-10 agentic-AI thought leader, author of an Amazon #1 book on agent-run companies) walks through his entire no-code agent stack: a proposal-writing agent that closes keynote inquiries in minutes, a prospecting agent that runs all-funnel outreach, "Rick" (a personal voice agent trained on 8 books + recordings), "Sam" (a calendar/CRM personal assistant), and "Sophia" (a research agent that reads his newsletters + notes nightly and pushes back on his keynote assumptions). Predicts the email-based SDR is dead inside 12 months and the closing layer moves up to C-suite.

## Key Insights

- **The stack is small and named.** Four agents cover ~98% of inbound + outbound: (1) Proposal writer — pulls inquiry email + inquirer background, matches against Tim's keynote topics, assembles agenda + benefit bullets + fee + calendar link. (2) Prospecting agent — searches for ICP matches (conference speaker-selection contacts), writes + sends personalized outreach. (3) Rick — customer-facing voice agent on WhatsApp/email, trained on all 8 of his books + podcast transcripts, replaces him in workshops. (4) Sam — personal assistant; takes "find me a meeting with Michael next week" via chat, parses calendar availability, finds Michael's email in CRM, drafts and sends. (5) Sophia — nightly research agent that reads the day's AI newsletters + Tim's Evernote notebook, summarizes, and emails pushback if a source contradicts his keynote claims. (3:20–8:25)

- **The high-leverage agent is the proposal writer, not the assistant.** Tim says explicitly: "The agent with the most commercial impact is the one that actually writes my proposals." It collapses the inquiry-to-quote cycle to "a couple of minutes," and his clients value that speed over the personal touch. (4:00–5:20)

- **The 10-minute meeting prep workflow.** Step 1 — Perplexity with "deep research" switched on: `give me the backgrounds to company Enterprise X and tell me where are their challenges right now in relationship to applying agentic AI`. Step 2 — paste the report into Claude with: "You know who I am, my value proposition. Tell me where exactly can I deliver value to this company. And please prepare me — I have a meeting with a VP sales in 10 minutes." Step 3 — connect Google Calendar to Perplexity via TidyCal so when someone books, the agent auto-researches the domain and fills the calendar event description. Total: 8–10 minutes. (8:25–11:25)

- **The personal-relationship assumption is wrong — speed + accuracy beats presence.** Tim's year-long A/B against his own prior behavior: clients value speed and accuracy more than personal contact, especially when the AI agent has a consistent tonality, voice, and reliable history. "Trust is not especially your presence, your face, your voice, whatsoever." One or two personal contacts per year is enough to keep deals warm if systems are in place. (11:35–13:40)

- **The SDR-as-email-role is dead in 12 months.** Tim's prediction: top-of-funnel becomes fully agentic in every business, including complex B2B — agents can handle complex inquiries. Closing moves up the seniority ladder (SDRs → CEOs) because the execution layer is automated. Salespeople need to learn to "sell to buying agents" — your prospect's AI will shortlist vendors before the prospect even knows they're in the market. (13:40–16:00)

- **The winner is whoever puts their knowledge into agents, not whoever has the most agents.** "The companies that will win will be the companies that are able to put all their knowledge, all their thinking, all they know about markets and clients and prospects into systems and into agents." (15:40–16:00)

## Notable Quotes

> "I haven't touched my own inbox in almost a year. 98% of the time my clients say the answers are remarkable." — 00:00

> "Some people might say this sounds impersonal. But it delivers real value to my clients. And they value the speed with which I deliver more than everything else." — 03:48

> "Trust is not especially your presence, your face, your voice, whatsoever." — 13:39

> "The email-based SDR has no reason to exist within the next 12 months." — 15:26

> "Salespeople need to learn not to sell to humans, but to buying agents. Your prospect's AI will shortlist vendors before your prospects even know they're in the market." — 15:32

> "The companies that will win will be the companies that are able to put all their knowledge, all their thinking, all they know about markets and clients and prospects into systems and into agents." — 15:45

## Tools and Resources Mentioned

- **Perplexity (with Deep Research toggle)** — Tim's first-stop research tool. The deep-research switch produces a 3–5 minute detailed report per company.
- **Claude (Anthropic)** — Tim's preferred writing/prep model at time of recording. *vendor: Anthropic's Claude — third-party consumer product, distinct from any in-stack Claude tooling the user might run.*
- **TidyCal** — booking tool whose integration with Perplexity triggers automatic background research on the booker's domain and writes the result into the calendar event description.
- **Evernote** — Tim's notebook where he bookmarks every AI newsletter article; Sophia reads it nightly.
- **Google Calendar + CRM integration** — used as the calendar/CRM substrate Sam queries to find contacts and availability.

## GitHub Repos and URLs Referenced

- (No GitHub repos in this video.)

## Action Items

- [ ] If you handle inbound sales: identify the ONE agent that would most compress your inquiry-to-quote cycle and build it first. Proposal-writing > scheduling > prospecting for most service businesses.
- [ ] Build a "Rick-equivalent" customer-facing agent trained on your own content (book, podcast transcripts, talks) and route it to WhatsApp + email.
- [ ] Adopt the 10-minute prep workflow: Perplexity deep-research → paste into Claude with your value-prop in context → drop into calendar event description.
- [ ] If you're in B2B sales: assume the buyer is an AI agent shortlisting you in the next 12 months. Start writing your product data and value prop so an agent can parse it.

## Open Questions

- How much does Sophia's nightly pushback actually change Tim's keynote content? He mentions one McKinsey contradiction example but doesn't quantify how often this loop has actually shifted a keynote vs. how often it's a non-event.
- What's the failure mode when an agent mis-handles an inquiry and a client notices? Tim says clients "value speed more than presence" but doesn't address escalation: how does a human in the loop get pulled in when an agent hits a category of question it shouldn't answer?
- Tim is a keynote speaker; his business model is unusually suited to agent automation (no fulfillment risk after the talk). How transferable is his 98% claim to a business where the deliverable is ongoing services?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 16:21 transcript)</summary>

0:00 I haven't answered my own emails in 11
0:03 months and 98% of the time my clients
0:06 say the answers are remarkable.
[...]
16:00 systems and into agents. And the better
16:03 they learn this and they handle these
16:06 systems, the better they will be in the
16:08 market.

(Full 15,134-character transcript saved to channels/vendasta/transcripts/2026-06-24_tim-cortinovis-agents-run-business.txt)

</details>