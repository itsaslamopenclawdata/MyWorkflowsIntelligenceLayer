---
title: "The Next $100B Market: Selling to AI Agents"
channel: "Greg Isenberg"
channel_slug: "greg-isenberg"
channel_id: "UCPjNBjflYl0-HQtUvOx0Ibw"
published: "2026-06-02"
duration_seconds: 840
video_id: "MlptIfpoLlw"
url: "https://www.youtube.com/watch?v=MlptIfpoLlw"
language: "en"
tags: ["ai-agents", "agent-economy", "agent-native", "agent-first", "stripe-agent", "agentmail", "mcp", "startup-ideas", "machine-to-machine"]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-06"
---

# The Next $100B Market: Selling to AI Agents

**Channel:** Greg Isenberg  **Published:** 2026-06-02  **Duration:** 14:00  **Watch:** https://www.youtube.com/watch?v=MlptIfpoLlw

## TL;DR

A 14-minute solo episode mapping the shift from human-first to agent-first internet — where AI agents are the customers, evaluating tools, transacting, and recommending. The thesis: over the next 10 years, "billions of customers (aka agents) with millions of wallets" will want to use services. Every SaaS category gets rebuilt for agents — payments, communication, memory, identity. Maps the agent buying journey, names the new infrastructure (identity, tools, inbox, memory, wallet, receipts), and shows concrete examples (AgentMail, Stripe agent wallet) plus how to make your site agent-readable (structured docs, schemas, MCP tools, executable actions). Closes with rapid-fire startup ideas.

## Key Insights

- **The big shift**: from human-first to agent-first internet. AI agents are becoming the customer, not just a tool the customer uses. [0:00–0:30]
- **The tweet that started it**: "Build startups for agents. Over the next 10 years, you're going to have a market of billions of customers, aka agents, with millions of wallets." [0:50–1:05]
- **Every SaaS category gets rebuilt for agents** — agent-native payments, agent-native communication, agent-native memory. The categories you use today (Notion, Slack, Stripe) all have agent-native versions waiting to be built. [1:05–1:30]
- **The "machine-to-machine economy"** is the framing. Almost nobody is building for it yet. [1:27–1:35]
- **Old web vs. agent web**: humans searching/reading/comparing/clicking vs. agents discovering/evaluating/invoking tools/paying. Your website isn't the surface anymore — your API + structured docs are. [1:50–2:10]
- **The agent buying journey**: finding → evaluating → transacting → using tools → recommending to other agents. Each step has a different product opportunity. [2:24–4:38]
- **What agents need beyond what humans need**: identity, tools, an inbox, memory, a wallet, and receipts. [4:38–5:30]
- **Concrete examples**: AgentMail (email for agents), Stripe's agent wallet, support, procurement, MCP, travel agent. [5:30–8:24]
- **Building an agent-readable website** = structured docs + schemas + MCP tools + executable actions. [8:24–9:31]
- **What this changes for startups**: instead of CAC/SEO funnels for humans, optimize for agent discoverability and toolability. [9:31–11:55]
- **Rapid-fire startup ideas for agents** (11:55–13:07): per Greg's framing, any category you're in, ask "what's the agent-native version?"
- **The 10-year prediction**: build startups for agents. The window is open right now, the saturation is 12-24 months away. [13:07–14:00]

## Notable Quotes

- "Build startups for agents. Over the next 10 years, you're going to have a market of billions of customers, aka agents, with millions of wallets." [0:50–1:05] (the original tweet, repeated)
- "Every single category gets rebuilt for agents. We're entering the machine-to-machine economy and almost nobody is building for it yet." [1:25–1:35]
- "We're entering the machine-to-machine economy and almost nobody is building for it yet." [1:27–1:35]

## Tools and Resources Mentioned

- **AgentMail** — email for AI agents (referenced as the proof point). [5:30]
- **Stripe's agent wallet** — the example of agent-native payments. [5:30]
- **MCP (Model Context Protocol)** — how agents invoke external tools. [5:30, 8:24]
- **Notion, Slack, Stripe** — the human-first SaaS Greg uses as the analogy. [1:10]
- **Support, procurement, travel** — three example agent categories. [5:30–8:24]

## GitHub Repos and URLs Referenced

- No specific GitHub repos referenced in the transcript.
- **AgentMail** — likely https://agentmail.com (verify before linking).
- **Stripe's agent wallet** — likely a Stripe product page (verify before linking).

## Action Items

- [ ] **Audit every SaaS you use** for the agent-native version. If you use Notion, the question is "what's Notion-for-agents?" If you use Stripe, "what's Stripe-for-agents?" [1:10–1:25]
- [ ] **Make your own product agent-readable** — add structured docs, schemas, MCP tools, executable actions. Without these, agents can't discover or use you. [8:24–9:31]
- [ ] **Pick one category from the 6 agent needs** (identity, tools, inbox, memory, wallet, receipts) and ship a focused MVP. [4:38–5:30]
- [ ] **Test AgentMail + Stripe agent wallet** as integration patterns for your own agent products. [5:30]
- [ ] **Run an "agent discoverability" audit on your site** — can an agent find, evaluate, and invoke your product without human help? [8:24–9:31]
- [ ] **Time-box this thesis**: the saturation window is 12-24 months. Build within that, or the wave passes. [13:07–14:00]

## Open Questions

- **How big is "billions of customers" really?** Greg's framing is rhetorical. The real number depends on how many agents actually have wallets (currently small).
- **Who pays the agent?** If an agent acts on behalf of a human with the human's wallet, the customer is still the human. The "agent as customer" framing works only when agents have autonomous budgets.
- **What does "agent-native" actually mean in code?** Is it just a JSON-RPC endpoint? An MCP server? A schema? Greg's examples don't spec the protocol stack.
- **Why is this $100B and not $10B or $1T?** The number is a vibe, not a forecast. Worth modeling.
- **What about the regulatory layer?** Autonomous agents with wallets = KYC, AML, tax. The infrastructure story Greg tells skips the compliance story.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 14:00 transcript)</summary>

0:00 There's a really big shift happening
0:01 right now on the internet and I don't
0:03 think people are talking about it. You
0:05 know, for the longest time, the user of
0:07 the internet were human beings. They
0:09 were us, right? We would create
0:10 websites, we create apps, and the end
0:13 user was human beings. And that's no
0:16 longer the case. The agents, the AI
0:19 agents are becoming the customer. So, in
0:22 today's episode, I'm going to give you a
0:24 clear primer on what is changing on the
0:26 internet, and how you could actually
0:30 make money, build products, and what you
0:32 really need to know about this agentic
0:35 era of the internet. I haven't seen
0:36 anyone really post and do a de facto
0:38 episode on it. So, I figured I'd do it.
0:50 So, I tweeted this and I think this
0:52 will, you know, resonate with you. I
0:55 said, "Build startups for agents. Over
0:57 the next 10 years, you're going to have
0:59 a market of billions of customers, aka
1:02 agents, with millions of wallets that
1:05 want to use your services. Go look at
1:08 every SAS tool you use. Notion, Slack,
1:11 Stripe, etc.
1:12 Now ask what is the version of this
1:16 that's built purely for agents? Agent
1:19 native payments, agent native
1:21 communication, agent native memory.
1:24 Every single category gets rebuilt for
1:27 agents. We're entering the machine
1:30 toachine economy and almost nobody is
1:33 building for it yet. So I tweeted this a
1:36 few months ago and I started seeing more
1:38 and more stuff come out. So let's
1:41 actually go through what is happening,
1:43 what is the shift so that we really
1:46 understand it. So the old web was humans
1:50 searching, reading, comparing, clicking
1:52 and buying. And it was your website,
1:55 your beautiful website that was built to
1:57 win the attention. But in the agent web,
2:01 you know, it's it's not a it's not for
2:03 humans, right? It's agents discovering,
2:05 evaluating, invoking tools, paying,
2:08 transacting, and recommending to other
2:10 agents. And each step of that journey
2:12 is a product opportunity. So, the agent
2:14 buying journey: finding, evaluating,
2:16 transacting, using tools, and then
2:18 recommending to other agents. Right.
2:19 That's the buyer journey. And I want
2:21 to, you know, dig into each step. So
2:23 finding. how do agents find what to
2:25 use? It used to be Google. Now it's
2:27 the equivalent of a search engine, but
2:29 for agents, an agent discoverability
2:31 layer, you know, so the winners there
2:33 are going to be the ones who create
2:35 that. So a tool like an MCP server, a
2:37 tool like, you know, agent to agent
2:39 sort of marketplace, an agent specific
2:40 search. Evaluating. So the agent is
2:42 going to evaluate. How does it do
2:44 that? It's going to look at, you know,
2:45 your structured data, your schemas, it
2:48 might call other agents to verify, to
2:50 get reviews, to get sort of input
2:52 before it actually decides. So the
2:54 winners there are going to be like an
2:56 agent review system, you know, agent
2:58 native reviews. Transacting. So how
3:00 does an agent pay? Well, it needs a
3:02 wallet, right? It needs to be able
3:04 to, you know, move money, be it stable
3:06 coins, be it the existing rails, um,
3:09 and the receipts. The receipt story is
3:11 really important. Like how does an
3:12 agent get a receipt so the human can
3:14 trust what happened. Um, the receipt
3:16 is a whole new category, you know,
3:18 sending invoices back and forth. Using
3:20 tools. So the agent needs to be able
3:22 to invoke your tool. So that's MCP
3:24 servers, that's, you know, you can
3:25 build that pretty easily. And then
3:27 recommending to other agents. So the
3:29 referral layer, the agent to agent
3:31 referral, when one agent says to
3:33 another agent, hey, you know, this is
3:34 really good. This is really bad. That's
3:36 a product. Right. And so you can kind
3:38 of see, like, I haven't really seen
3:40 anyone talk about like all these
3:42 categories in a way that kind of
3:44 makes it like concrete. So I want to
3:46 give you a little bit of like a
3:47 breakdown of each. So agents, what
3:49 do agents actually need? So you know,
3:51 beyond what humans need, agents need
3:53 identity, tools, an inbox, memory,
3:54 a wallet, and receipts. That's the
3:55 list. Let's go through each one. So
3:58 identity. So how does an agent know
4:00 who it is, who it's acting on behalf
4:02 of, what its permissions are, what
4:04 its goals are? That's an identity
4:06 layer. You can build that. Tools. So
4:08 what can the agent actually do? What
4:10 actions can it take? You know, the
4:12 tool layer, the MCP, the composio.
4:14 The inbox. So agents need an inbox.
4:16 So this is something like AgentMail.
4:18 An agent needs to be able to send
4:20 and receive emails, parse them, act
4:22 on them. That's a product. Memory.
4:24 So agents need persistent memory.
4:25 They need to be able to remember
4:26 things across sessions, across tools,
4:28 across conversations. That's a product
4:30 layer. The wallet. So the agent needs
4:32 a wallet. How does it pay? How does
4:33 it hold money? You know, the Stripe
4:34 agent wallet, that's the beginning
4:35 of that. And then receipts. So how
4:37 does the agent prove what it bought
4:38 to the human? That's a receipts
4:40 layer. Right. And so these are all
4:42 products to build. Let me go through
4:43 some of the examples. So AgentMail.
4:45 AgentMail is this. It's basically
4:47 email for agents. So you can have
4:48 an agent that has an email address.
4:49 It can send and receive emails, and
4:50 it can act on them. And the use case
4:52 is, you know, a lead gen agent that
4:54 sends out cold emails, that responds
4:56 to replies, that books meetings.
4:58 That's AgentMail. The Stripe agent
4:59 wallet. So Stripe's been rolling out
4:60 an agent wallet. So you can have an
5:02 agent that holds money, that pays
5:04 for APIs, that pays for tools, and
5:05 that has like a budget that you as
5:07 the human can set. And that's a real
5:09 product. That's a real category. The
5:11 support agent. So you can have a
5:13 support agent that integrates with
5:14 your support inbox and handles tier
5:15 one support, and it can, you know,
5:17 respond, it can refund, it can do
5:18 all of that. That's a product. The
5:20 procurement agent. So a procurement
5:21 agent that helps you buy things.
5:23 It can find vendors, it can compare
5:25 prices, it can place orders. That's
5:26 a product. The MCP. So the model
5:28 context protocol. So you can build an
5:30 MCP server for your product, and
5:31 that allows agents to invoke your
5:33 product as a tool. That's a product.
5:35 The travel agent. So a travel agent
5:36 that books flights, books hotels,
5:38 books restaurants, all without a
5:39 human. That's a product. So I could
5:40 go on and on. There's like an agent
5:42 native version of every single
5:43 category. And what I want to kind
5:45 of, you know, I want to give you a
5:46 quick way to think about it. So if
5:48 you're building a startup today,
5:50 right. And I think the way to think
5:51 about it is, you know, make your
5:52 website agent readable. That's step
5:54 one. So what does that mean? It
5:55 means having structured docs, it
5:57 means having schemas, it means
5:58 having MCP tools, it means having
5:59 executable actions. So that an
6:00 agent can come to your site, read
6:02 what you do, and actually invoke
6:04 your product. Right. If you don't
6:05 do that, an agent can't use your
6:07 product. And the agents that are
6:09 going to win, the startups that
6:09 are going to win, are the ones that
6:10 are agent native, not just agent
6:12 friendly. So I want to give you
6:14 some rapid fire startup ideas. So
6:16 one, an agent native help desk. So
6:17 a help desk that's built for agents
6:19 to use, not humans. Right. Like
6:20 the front door is an API, not a
6:21 web form. Two, an agent native
6:22 calendar. So a calendar that an
6:24 agent can read and write to. Three,
6:25 an agent native task manager. So
6:27 a task manager that's built for
6:28 agents to use. Four, an agent
6:30 native file storage. So a file
6:31 storage that's built for agents
6:31 to use, with like a search layer
6:32 that's actually for agents, not
6:33 humans. Five, an agent native CRM.
6:34 So a CRM that an agent can use.
6:36 Six, an agent native email. So
6:36 an email that an agent can use.
6:37 Seven, an agent native payment
6:38 system. So a payment system that
6:38 an agent can use. So the through
6:39 line, you know, every single
6:40 category gets rebuilt for agents.
6:41 And the question is, which one
6:42 are you going to build? So that's
6:43 the shift. The old web is humans.
6:44 The new web is agents. And the
6:45 startups that are going to win
6:46 are the ones that are agent native,
6:47 not just agent friendly. So the
6:48 call to action is, you know, if
6:49 you're a founder, build agent
6:50 native. If you're an operator, you
6:51 know, audit your stack for agent
6:53 native tools. And if you're an
6:54 investor, you know, this is the
6:55 next 10 year, you know, this is
6:56 the next 10 year thesis. So let
6:57 me know what you think. Drop a
6:58 comment. Subscribe if you found
6:59 this useful. And I'll see you in
6:59 the next one.

</details>
