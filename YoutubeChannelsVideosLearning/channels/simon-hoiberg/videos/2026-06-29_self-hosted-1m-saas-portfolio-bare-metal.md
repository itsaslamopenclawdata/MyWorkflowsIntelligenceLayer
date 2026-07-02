---
title: "I Run a $1M SaaS Portfolio on This Box (Self-Hosted)"
channel: "Simon Høiberg"
channel_slug: "simon-hoiberg"
channel_id: "UCMo28ATCDU0Kn9dpilAF79Q"
published: "2026-06-29"
duration_seconds: 899
video_id: "eT4OaFE4IIQ"
url: "https://youtube.com/watch?v=eT4OaFE4IIQ"
language: "en"
tags: [self-hosting, kubernetes, k3s, postgres, redis, pgvector, minio, hetzner, bare-metal, wireguard, cloudflare, saas-infrastructure, indie-hacking]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-07-02"
---

# I Run a $1M SaaS Portfolio on This Box (Self-Hosted)

**Channel:** Simon Høiberg  **Published:** 2026-06-29  **Duration:** 14:59  **Watch:** https://youtube.com/watch?v=eT4OaFE4IIQ

## TL;DR

Simon walks through his complete self-hosted infrastructure stack for a multi-product SaaS portfolio serving 50,000+ users on bare-metal Hetzner servers (not AWS). The stack: 3 Hetzner servers running K3s (lightweight Kubernetes), CloudNative PG for Postgres, Redis for caching, PGVector for vector search, MinIO for S3-compatible object storage, and a public-facing Hetzner VPS acting as a WireGuard-tunneled edge node. The hard-won lessons: avoid DynamoDB for SaaS (use Postgres), avoid custom deployment scripts (use Helm + K8s), and use a public VPS as a disposable edge instead of exposing the cluster directly. Concrete cost: replaced unpredictable AWS bills with fixed Hetzner server rentals. Honest flag: MinIO's open-source version is in maintenance mode — yellow flag for long-term use, acceptable for non-sensitive assets like social media files.

## Key Insights

- **The "self-hosting is brutal" reputation is outdated — AI agents change the learning curve.** Old self-hosting meant reading docs, GitHub issues, and random forum threads. New approach: give a Claude Code-style agent read-only access to the K8s cluster (pods, events, ingress, helm values, metrics) and it can diagnose most issues before you open a terminal. (12:40-13:20)

- **Three-server K3s setup is the foundation, not a hyperscale architecture.** One dedicated Hetzner server + two cheaper auction servers, all running K3s (lightweight Kubernetes). Docker-ize every service (app, API, workers) so deployments become "push code → build image → Helm rolls out → health checks → switch over." Standardized across all products. (00:55-02:30)

- **Self-host Git too — moved off GitHub for code hosting.** Runs a self-hosted git service called Forgejo. Pipeline on push builds Docker image, pushes to registry, Helm deploys. Full CI/CD self-owned. (01:44-02:18)

- **DynamoDB was a mistake — Postgres would have been better from day one.** Picked DynamoDB in 2021 because it was trendy. Realized he was using it as a relational database anyway, while paying per read/write, getting locked in, and actively giving users a worse experience to avoid query costs. Moved everything to Postgres. (03:26-04:36)

- **CloudNative PG makes Postgres ops trivial — backups are 5 lines of config.** Postgres runs via CloudNative PG (Kubernetes operator from the Postgres community). It manages pods, failover, backups, restores. Backups: tell it where to store, how often, how long to keep. That's it. Stored in two locations for safety: a Hetzner storage box + a separate object store. (04:36-05:50)

- **The boring stack wins: Postgres + Redis + PGVector.** Postgres for product data, Redis for fast temporary stuff (caching, queue-style workloads), PGVector when vector search is needed. PGVector is "super fast" — third-party vector databases are unnecessary for most use cases. (06:00-06:30)

- **MinIO is a yellow flag in 2026 — repo archived, no new features.** Open-source version moved to maintenance mode, repo archived/read-only, no new pull requests, security fixes evaluated case-by-case. Company pushing the actively-maintained product towards AIStore (enterprise). For non-sensitive files (social media assets, images, videos) it's still acceptable. For sensitive data (legal, medical, financial) — use a managed provider or invest heavily in encryption/replication/access control. (06:50-08:58)

- **Public traffic architecture: VPS as disposable edge, not direct cluster exposure.** Replaced CloudFront with a small Hetzner VPS as public entry point. Two implementation tiers: (1) simple IP allowlist (cluster only accepts traffic from VPS IP), (2) better: WireGuard tunnel (public VPS connects to private infrastructure over WireGuard, real ingress only listens to private connection). Public VPS becomes disposable — can be swapped without touching the real cluster. (09:08-11:00)

- **The origin-isolation framing, not the DOS protection.** A VPS edge does NOT stop serious DOS attacks (still need Cloudflare or similar for that). The point is: real servers aren't naked on the internet, public edge is cheap/stateless/disposable. The trade-off ladder: Cloudflare (easiest serious public edge) → Tailscale (easiest private network) → WireGuard (self-managed) → VPS edge (good enough for most cases). (10:58-12:05)

- **The deeper business case: ownership, not just cost.** Self-hosting saves money, but the bigger win is options. "If every important layer of your operation runs on some kind of managed platform, your business is basically owned by those other companies. Maybe you own a brand name, but if that's really all, you're in a terribly fragile position." Can move infrastructure, rebuild pieces, replace providers without rebuilding the company around their API. (13:50-14:37)

- **Start small, not with the full stack.** If this feels overwhelming: set up one service, give your AI agent readonly access, let it help you understand errors/firewall rules/backup config. Spend a few weeks with it. Let it become another founder skill. (14:37-14:57)

## Notable Quotes

> "I was using DynamoDB in a regular relational database kind of way anyway. And now I had to consider carefully how I used it cuz with Dynamo DB you pay per read and per write to the database. It locked me in and it literally encouraged me to give my users a worse experience." — 04:08

> "MinIO used to be the obvious choice for self-hosted object storage. It's open source, S3 compatible, fast, and easy to set up. The problem is that the community version is now in a much worse place than it used to be." — 07:39

> "The public VPS becomes a disposable edge node. It can receive traffic from the internet but the actual applications and data are not sitting on that box and it doesn't have any open incoming connections at all." — 10:40

> "If every important layer of your operation runs on some kind of managed platform, your business is basically owned by those other companies. You have to stop and ask yourself, what do I actually own here? Maybe you own a brand name, but if that's really all, you're in a terribly fragile position." — 13:56

## Tools and Resources Mentioned

- **Hetzner** — bare-metal dedicated + auction servers + storage boxes. The infrastructure provider for the entire portfolio. https://www.hetzner.com
- **K3s** — lightweight Kubernetes distribution. https://k3s.io
- **CloudNative PG** — Kubernetes operator for Postgres. Manages pods, failover, backups, restores. https://cloudnative-pg.io
- **PostgreSQL** — primary database. Boring, mature, well-supported, fits relational SaaS data.
- **Redis** — caching and queue-style workloads.
- **PGVector** — Postgres extension for vector search/RAG. Considered sufficient for most use cases without a dedicated vector DB.
- **MinIO** — S3-compatible object storage. (VENDOR FLAG: open-source version is in maintenance mode as of 2026 — repo archived, no new features. Acceptable for non-sensitive assets; consider alternatives for sensitive data.)
- **Forgejo** — self-hosted Git service. Replaced GitHub for code hosting. https://forgejo.org
- **Docker** — containerization for every service.
- **Helm** — Kubernetes package manager. Standardized deployments across all products.
- **WireGuard** — VPN tunnel between public VPS edge and private cluster. The "self-managed" tier of the trade-off ladder.
- **Tailscale** — easy WireGuard alternative. (VENDOR FLAG: third-party product, not the user's stack. Adds a control plane dependency.)
- **Cloudflare** — public edge with DOS protection, WAF. The "easiest serious" tier. (VENDOR FLAG: third-party service, adds managed-platform dependency.)
- **CloudFront** — AWS CDN. Replaced with the VPS-edge pattern.
- **AIStore** — MinIO's enterprise product, the actively-maintained alternative. https://aistore.nvidia.com (Note: MinIO is pushing users here as the OSS version goes into maintenance.)

### Vendor disambiguation

- **"openclaw agent" in the transcript at 12:44** — this is almost certainly an ASR mis-rendering of "Claude Code" (or generic "Claude agent"). Context: AI agent with readonly K8s access for debugging. Normalized in the transcript. The video is NOT about a product called "openclaw."
- **"Hzner" / "Hner" / "Hester" in the transcript** — all ASR mis-renderings of **Hetzner**. Normalized in the transcript.

## GitHub Repos and URLs Referenced

None referenced in this video. (The video is a high-level stack walkthrough, not a code tutorial. He links to "all resources" at https://simonl.ink/infra in the description but the video itself does not name specific repos.)

Other URLs mentioned in description (not in body):
- https://simonl.ink/infra — "Links to all resources"
- https://simonl.ink/feedhive — FeedHive (his own product)
- https://simonl.ink/aidbase — Aidbase (his own product)
- https://simonl.ink/founderstack — SaaS bundle (LTD)

## Action Items

- [ ] **Audit your own cloud bill for what could move to Hetzner bare-metal.** For a solopreneur running <100K users on managed services, the fixed-cost server rental model can save 5-10x. Run the numbers for your specific stack.
- [ ] **Replace DynamoDB / Firestore / managed NoSQL with Postgres if you're using it relationally anyway.** If your access pattern is "give me row by primary key" + the occasional scan, you're paying managed-DB prices for an ORM.
- [ ] **Set up a public VPS edge in front of your cluster, not direct cluster exposure.** Even the IP-allowlist tier is a massive security improvement. WireGuard is the better tier.
- [ ] **Evaluate MinIO carefully for your use case.** Acceptable for non-sensitive assets (user uploads that aren't irreplaceable). Reconsider for legal/medical/financial files.
- [ ] **Give an AI agent readonly access to your infrastructure (K8s pods, logs, monitoring).** Let it triage the "what is this error" questions before you spend 30 min on docs.
- [ ] **Pick one service to self-host first.** Don't try to migrate the full stack in a weekend. Start with the lowest-risk service (e.g., a worker queue) and build confidence.

## Open Questions

- What does "AIStore" (MinIO's enterprise replacement) actually cost at SaaS scale, and is the migration path clean for existing MinIO users?
- How does CloudNative PG's backup/restore time scale to databases > 1TB? For a single-server Hetzner setup, restore time is the SLA ceiling.
- Simon's stack is 3 servers today — at what point does he need to split Postgres off the K3s cluster onto a dedicated DB server? What's the trigger metric?
- WireGuard is "self-managed" but at what scale does it become operationally painful vs. paying for Tailscale's control plane?
- How does the public VPS + WireGuard pattern hold up against sophisticated attackers? IP allowlist is fine, but a determined attacker who compromises the VPS can pivot through the tunnel.
- The 50K users number — is that across all products in the portfolio or per-product? Affects whether the architecture is generalizable.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full HH:MM:SS transcript)</summary>


[00:02] Last year, I moved my SaaS portfolio off
[00:04] the cloud, which means I moved it off
[00:07] AWS and said goodbye to unpredictable
[00:10] billing, being locked into an ecosystem
[00:12] of tools, and to paying tens of
[00:14] thousands of dollars yearly for services
[00:17] that were utterly unnecessary to run my
[00:19] business. Instead, I'm now self-hosting
[00:21] everything on bare metal servers I rent
[00:23] with Hetzner, and I'm still serving more
[00:26] than 50,000 users who use my SaaS tools.
[00:28] And I've got a ton of questions from you
[00:30] guys. What about maintenance? How do you
[00:32] handle backups? How do you handle
[00:35] security? What tools are you actually
[00:37] using to self-host your products? So, in
[00:39] this video, I'm going to answer all of
[00:42] that. I'll show you my exact self-hosted
[00:44] setup, how I handle backups and
[00:46] security, how I handle critical issues,
[00:49] and how you absolutely do not need to be
[00:52] an expert SISAT and or DevOps engineer
[00:55] to self-host your SaaS in 2026. So, let's
[00:58] start with the foundation. My entire
[01:00] setup runs on three servers from Hner.
[01:02] The main server is a dedicated server
[01:04] and then I have two cheaper auction
[01:06] servers next to it that help run the
[01:08] workloads. And on top of these three
[01:11] servers, I run K3S which is a
[01:13] lightweight version of Kubernetes. The
[01:15] way this works is that basically
[01:17] everything I run is dockerized. The app
[01:19] is a Docker container. The API is a
[01:21] Docker container. The workers that run
[01:23] in the background are Docker containers.
[01:26] So instead of installing node, postgress
[01:28] clients, random packages, and custom
[01:30] scripts directly on the server, each
[01:32] service gets packaged into its own image
[01:34] with everything it needs to run. When I
[01:35] need to deploy a new version of any of
[01:38] my SaaS, I don't have to touch the
[01:40] server. All of this happens through
[01:41] automated deployments. And I actually
[01:44] moved away from GitHub for this as well.
[01:47] I now run my own self-hosted git service
[01:49] called for which is basically a
[01:51] self-hosted GitHub alternative. So when
[01:54] I push code to a repository, a pipeline
[01:56] runs and it builds a new Docker image,
[01:58] pushes that image to the registry, and
[02:01] then Helm tells Kubernetes to roll out
[02:03] the new version. Kubernetes then starts
[02:05] the new containers, waits until they're
[02:08] healthy, and only then removes the old
[02:10] ones. That means I get the nice
[02:12] deployment flow you normally expect from
[02:14] a managed platform. Push code, build
[02:17] image, roll out, health checks, switch
[02:18] over. But instead of paying for a
[02:20] managed platform to run all of this for
[02:22] me, it runs on my own fixed cost
[02:24] servers. And I know a lot of people love
[02:26] to talk about Kubernetes because every
[02:28] time I mention Kubernetes, someone will
[02:30] say you absolutely do not need
[02:33] Kubernetes for a SaaS business this size.
[02:36] And sure, technically you don't. You can
[02:38] run a SaaS product on a single VPS with
[02:41] Docker Compose and a few scripts. And I
[02:43] guess that can be totally fine. But I'm
[02:45] not using Kubernetes because my products
[02:48] need some insane hypers scale setup. I'm
[02:50] using it because it's practical because
[02:52] I run multiple products and I want them
[02:55] deployed in the same standardized way. A
[02:57] SaaS is rarely just one app sitting on a
[03:00] server. You have the stuff users touch
[03:01] and then you have all the background
[03:04] pieces around it. Jobs that need to run,
[03:06] internal services, monitoring, small
[03:08] processes that only exist to do one
[03:11] thing. And all of that has to run
[03:13] somewhere. And I don't want every
[03:15] product to have its own weird little
[03:17] deployment setup with custom scripts and
[03:19] duct tape. With Kubernetes and Helm,
[03:21] that just becomes super clean. It's very
[03:23] similar to the experience you get from a
[03:26] managed platform, just self-hosted. Next
[03:28] is the database. So, when I first
[03:30] started building SaaS products, I picked
[03:33] Dynamo DB because, yeah, I don't even
[03:35] know why, to be honest. I thought it was
[03:38] cool. Managed schemalist databases. It
[03:40] was what everyone was talking about back
[03:43] in 2021 and I just kind of went with it.
[03:45] I was reading about single table design
[03:47] and all those fancy Dynamo DB patterns
[03:50] and I guess I convinced myself that this
[03:52] is what serious SaaS products should be
[03:54] using and it was the stupidest decision
[03:57] cuz in reality I was just making my own
[03:58] life harder. every time I wanted to
[04:01] change something in the product, I had
[04:03] to think about table design again. And I
[04:05] just ended up using it in a regular
[04:08] relational database kind of way anyway.
[04:11] And now I had to consider carefully how
[04:13] I used it cuz with Dynamo DB you pay per
[04:17] read and per write to the database. It
[04:19] locked me in and it literally encouraged
[04:21] me to give my users a worse experience
[04:23] because I would constantly consider
[04:25] whether a read or scan here and there
[04:27] would end up costing too much for my
[04:29] products. That was a lot of complexity
[04:32] with very little upside. So I moved
[04:36] basically everything to PostgresQL which
[04:37] honestly I should have just went with
[04:39] that from the beginning. Postgress is
[04:42] boring in the best possible way. It is
[04:44] mature, well supported and every
[04:46] developer tool understands it. It also
[04:48] fits how most SaaS products actually
[04:51] work. Users belong to workspaces.
[04:53] Workspaces have subscriptions. Products
[04:55] have posts, tickets, conversations,
[04:57] settings, whatever the product is built
[05:00] around. A relational database is just
[05:01] very good at that. In my cluster,
[05:04] Postgress runs through cloudnative PG.
[05:07] So cloudnative PG is a Kubernetes
[05:09] operator from Postgress. So instead of
[05:11] manually installing Postgress on a
[05:13] server, I defined the database setup in
[05:15] Kubernetes and the operator handles the
[05:18] annoying operational parts. It manages
[05:21] the Postgress pods, failover, backups
[05:24] and restores. And backups are a good
[05:26] example of something people over
[05:28] complicate. With CloudNative PG, the
[05:31] backup setup is basically configuration.
[05:33] You tell it where to store the backups,
[05:34] how often to run them, and how long to
[05:37] keep them. That's it. So when people
[05:38] ask, "Oh, but how do you handle
[05:43] backups?" Well, this is how like five
[05:45] lines of code, that's how in my setup,
[05:47] database backups go to object storage
[05:49] and from there they can also be copied
[05:51] offsite. I store mine in two places just
[05:53] to be safe in a storage drive I rent
[05:56] with Hner and on a separate object store
[05:58] held by another company. Besides
[06:00] Postgress, I also use Reddis where it
[06:02] makes sense, mostly for caching and Q
[06:05] style workloads. And for 8base, we use
[06:07] PG vector for the rag and vector search
[06:09] parts which is an extension you install
[06:12] on your Postgress database. And yeah,
[06:15] what can I say? It's super fast. People
[06:16] who say you need a designated third
[06:19] party vector database tool, I'm not sure
[06:21] they've actually tried PG vector. It's
[06:24] very fast. For all practical purposes,
[06:26] it just does the job perfectly well.
[06:28] Postgress for the main product data,
[06:30] Reddis for the fast temporary stuff, and
[06:32] PG vector when I need vector search. And
[06:34] because it's all based on boring open-
[06:37] source tools, I can run this anywhere.
[06:39] Another hexner server, another
[06:41] Kubernetes cluster, or even a managed
[06:43] Postgress provider if that ever makes
[06:47] sense. Next is file storage. For this, I
[06:50] use Min.io. Minio is an S3 compatible
[06:52] object store that I can run inside my
[06:53] own infrastructure. So, the products can
[06:55] talk to it more or less the same way
[06:58] they would with AWSS3,
[07:00] except the files are stored on my own
[07:02] setup. And most SaaS products need
[07:04] something like this. You don't put
[07:06] everything in Postgress. Product data
[07:08] belongs in the database. Files usually
[07:10] don't. So if a user uploads a video or
[07:13] an image that goes into object storage.
[07:15] Same with exports, attachments,
[07:16] generated media, and files like that.
[07:18] For my portfolio, that works pretty
[07:20] well. A lot of the files we store are
[07:22] social media assets. Feedhive, for
[07:24] example, deals with images and videos
[07:26] people are going to post online. So
[07:28] Minio makes sense for that kind of
[07:31] workload. It is fast and it uses the S3
[07:34] API and it is easy to run next to the
[07:36] rest of the stack, but I don't want to
[07:39] oversell minio. Minio used to be the
[07:40] obvious choice for self-hosted object
[07:42] storage. It's open source, S3
[07:45] compatible, fast, and easy to set up.
[07:46] The problem is that the community
[07:48] version is now in a much worse place
[07:50] than it used to be. The open- source
[07:52] repository was officially moved into
[07:55] maintenance mode and the official note
[07:57] says that there are no new features. No
[07:59] new pull requests and critical security
[08:01] fixes are only evaluated by case by
[08:04] case. The repository was also archived
[08:06] and made read only. On top of that,
[08:08] Minio has been pushing the actively
[08:11] maintained product towards AI store
[08:13] which is their enterprise product. So I
[08:15] don't think minio suddenly became bad
[08:17] software. The concern is the product
[08:19] direction for storage. I would want
[08:21] something that is maintained long-term.
[08:23] Ideally, you don't want to be dealing
[08:25] with broken files or security issues.
[08:28] So, I'd consider minio a bit of a yellow
[08:31] flag right now. For my portfolio, I'm
[08:32] okay with this for now because of the
[08:35] type of files we store. A lot of it is
[08:37] social media assets like images, videos,
[08:40] generated assets, and so on. Important,
[08:43] yes, but usually not sensitive,
[08:45] irreplaceable customer data. But if you
[08:47] store legal documents, medical records,
[08:49] financial documents, or files that are
[08:52] genuinely critical to your customers, I
[08:53] would be much more careful. For that
[08:55] kind of product, I would probably look
[08:57] at a managed provider or at least spend
[08:58] a lot of time on encryption,
[09:01] replication, access control, and
[09:03] possibly look into other lesserk known
[09:05] solutions. Now, let's talk about public
[09:08] traffic and security. Because if you
[09:10] self-host a SaaS product, something has
[09:12] to be reachable from the internet. Users
[09:14] need to open the app. Web hooks need to
[09:17] hit your APIs and the browser needs to
[09:19] load the website. But the real servers
[09:22] do not have to sit fully exposed. I used
[09:23] to have CloudFront in front of
[09:25] everything. So traffic would hit
[09:27] CloudFront first and then CloudFront
[09:28] would forward the request to my
[09:30] infrastructure. That setup makes a lot
[09:32] of sense. You get a public edge with
[09:34] firewall rules and DOS protection. And
[09:36] you also get TLS caching and a lot of
[09:38] security features without building all
[09:40] of it yourself. But CloudFront is still
[09:42] a managed cloud dependency sitting in
[09:45] front of the whole stack and I wanted to
[09:47] get rid of that and move to a much more
[09:49] simple approach. So instead the public
[09:51] entry point is now a small VPS I rent
[09:54] with Hester. That VPS receives the
[09:56] public web traffic and then forwards it
[09:58] to the real infrastructure behind it.
[10:00] Similar to what CloudFront used to do,
[10:02] but a much simpler cloudless version of
[10:04] it. And there are a few ways you can
[10:07] achieve this. The simple version is IP
[10:09] allow listing. The cluster only accepts
[10:11] web traffic from the VPS. Everything
[10:13] else is blocked. So even if someone
[10:16] finds the real server IP, they should
[10:17] not be able to hit the cluster directly.
[10:20] This is easy to set up. You can disable
[10:22] traffic from all IPs except the one from
[10:25] your VPS directly in Hner's robot
[10:26] interface. The better version is
[10:29] WireGuard. And this is what I'm using.
[10:31] You connect the public VPS to a private
[10:33] infrastructure over a WireGuard tunnel
[10:35] and the real ingress only listens to
[10:38] that private connection. So the public
[10:41] VPS becomes a disposable edge node. It
[10:42] can receive traffic from the internet
[10:45] but the actual applications and data are
[10:47] not sitting on that box and it doesn't
[10:49] have any open incoming connections at
[10:52] all. That means I can swap out the
[10:54] public VPS without touching the real
[10:56] infrastructure behind it. So this does
[10:59] not magically stop a serious DOS attack.
[11:01] If someone really wants to flood your
[11:03] public endpoint, you still need a proper
[11:05] DOS protection in front of it. The point
[11:07] here is origin isolation. The real
[11:09] servers are not sitting naked on the
[11:12] internet and the public edge is cheap,
[11:13] stateless and disposable. If you want
[11:16] the easiest serious version of this,
[11:17] Cloudflare is probably the obvious
[11:20] choice. Put Cloudflare in front, use
[11:22] their waffenos protection and lock down
[11:24] your origin so traffic only comes
[11:27] through Cloudflare tunnels. That is in
[11:29] all honesty a great tradeoff for a lot
[11:31] of founders. You just have to be honest
[11:32] that you are now depending on
[11:35] Cloudflare. It's not truly cloudless
[11:38] this way. Same with tail scale. So tail
[11:40] scale is basically the easy version of
[11:42] wire guard. It is extremely convenient
[11:44] especially for internal access. But
[11:46] again it adds a control plane
[11:48] dependency. So I think about this as a
[11:51] trade-off. Cloudflare is the easiest
[11:53] serious public edge. Tail scale is the
[11:56] easiest private network. Wireguard is
[11:58] the more self-managed version. And a VPS
[12:00] as the public edge is good enough to
[12:01] protect your infrastructure in most
[12:04] cases. Now, at this point, I know some
[12:06] of you are probably thinking, "Okay, but
[12:08] this sounds like a lot. I'd much rather
[12:11] just pave or sell or superbase to not
[12:13] have to think about any of this." And I
[12:14] get that. We just covered a whole bunch
[12:16] of stuff here. And a few years ago, I
[12:18] would have agreed. But I think the fear
[12:21] around this is becoming a bit outdated.
[12:22] The old version of self-hosting was
[12:25] brutal. If something broke, you would
[12:27] end up reading documentation and digging
[12:29] through GitHub issues. Then you'd find
[12:31] some random forum thread and run a
[12:33] command you only halfway understood.
[12:35] That's not really how it works anymore.
[12:38] AI is extremely good at infrastructure
[12:40] work, especially when you give it real
[12:42] access to inspect the system. I would
[12:44] recommend giving your Claude Code agent (likely — ASR misrendered "openclaw")
[12:47] readonly access to a Kubernetes cluster
[12:49] blogs and monitoring because it can
[12:52] gather the full picture in seconds. It
[12:54] can check the pods, the events. It can
[12:56] inspect the ingress, the helm values,
[12:59] and the metrics. And very often, it can
[13:01] tell you what is probably wrong before
[13:04] you even open that terminal window. If a
[13:06] pod is crashing, it can explain the
[13:08] logs. If traffic is not reaching the
[13:09] app, it can trace the path from the
[13:12] public BPS into the cluster. And if
[13:14] backups are failing, it can look at the
[13:16] conflict and point you to the line that
[13:18] looks wrong. That changes the learning
[13:20] process completely. You're no longer
[13:23] sitting alone with a wall of DevOps
[13:25] documentation. You can learn while you
[13:28] build. And trust me, after a few weeks,
[13:30] a lot of this becomes much less
[13:31] intimidating. Yes, infrastructure is
[13:34] hard, but founders learn hard things all
[13:38] the time. Ads, sales, SEO, marketing,
[13:40] development, and the list goes on. It's
[13:43] part of the job. So, I don't buy that
[13:45] infrastructure is that one thing
[13:47] founders are somehow incapable of
[13:49] learning. And I think it is becoming a
[13:51] really important skill because the
[13:54] alternative is not neutral. If every
[13:56] important layer of your operation runs
[13:58] on some kind of managed platform, your
[14:01] business is basically owned by those
[14:03] other companies. You have to stop and
[14:05] ask yourself, what do I actually own
[14:07] here? Maybe you own a brand name, but if
[14:10] that's really all, you're in a terribly
[14:12] fragile position. Look at where the
[14:14] world is going. Do you really want your
[14:16] business and livelihood to depend on big
[14:18] US tech companies right now? If you're a
[14:20] tech founder, you should take
[14:22] self-hosting seriously. It can save a
[14:25] lot of money, but the bigger win is that
[14:28] it gives you options. You understand how
[14:30] your product runs. You can move it. You
[14:32] can rebuild pieces of it. You can
[14:34] replace a provider without rebuilding
[14:37] the entire company around their API. So,
[14:40] if this feels overwhelming, start small.
[14:42] Set up one service. Give your AI agent
[14:45] readonly access. Let it help you
[14:47] understand the errors, the firewall
[14:49] rules, and the backup config. Spend a
[14:51] few weeks with it. Let it become another
[14:54] founder skill you've gathered. In 2026,
[14:57] I think this is one of the best skills you can learn.


</details>
