---
title: "10 GitHub Repos So Good They Shouldn't Be Free — Part 5 (Kill $189K/yr of SaaS)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-26"
duration_seconds: 947
video_id: "0NpOcIa3qsk"
url: "https://youtube.com/watch?v=0NpOcIa3qsk"
language: "en"
tags: [self-hosted, foss, saas-killers, supabase, gitea, nextcloud, medusa, posthog, keycloak, erpnext, open-source, kill-saas]
transcript_status: "fetched"
generated_by: "channels-youtube-content"
generated_on: "2026-06-27"
---

# 10 GitHub Repos So Good They Shouldn't Be Free — Part 5 (Kill $189K/yr of SaaS)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-26  **Duration:** 00:15:47  **Watch:** https://youtube.com/watch?v=0NpOcIa3qsk

## TL;DR
Part 5 in the "kill SaaS bills" series goes after the big enterprise line items: Supabase (Firebase+Auth0 stack), cal.com (Calendly), RustDesk (TeamViewer), Strapi (Contentful), Gitea (GitHub Enterprise), Nextcloud (Dropbox), Medusa (Shopify Plus), PostHog (Mixpanel/Amplitude), Keycloak (Okta), and ERPNext (NetSuite/SAP). Together they replace **nearly $189,870/yr of software** at the team sizes shown. The honest catch on every one: **self-hosting saves you the license fee, not the work — you run the server**.

## Key Insights
- **The "honest catch" rule applies to every one:** "Self-hosting saves you the license fee, not the work. You run the server." (timestamp 0:56)
- **#1 Supabase (105k stars, Apache 2.0) — the open-source Firebase.** Real Postgres, auth, real-time subscriptions, file storage, edge functions, auto-generated REST/GraphQL APIs. Replaces Firebase + Auth0 (Auth0 alone is $240/mo after 1,000 users = $2,880/yr just for login). Setup: `git clone` → Docker folder → `docker compose up`. (timestamp 1:09)
- **#2 cal.com (~46k stars, MIT) — the open-source scheduling platform.** Booking links, team round-robin routing, availability rules, calendar/video integrations. Calendly Teams is $16/seat/mo — a 25-person sales team pays $4,800/yr just to send a calendar link. cal.com is $0. **The MIT code is free; SAML SSO is in the paid tier.** (timestamp 2:32)
- **#3 RustDesk (117k stars, AGPL) — the open-source remote desktop.** Screen control, file transfer, unattended access. You self-host the relay so sessions route through your own machine. TeamViewer Corporate is $245.90/mo (~$3K/yr) and caps concurrent sessions. RustDesk has no concurrency tax, unlimited techs and sessions. (timestamp 3:46)
- **#4 Strapi (~73k stars, MIT) — the open-source headless CMS.** Model your content, Strapi auto-generates REST + GraphQL API + a clean admin panel. BYO database (Postgres/MySQL/SQLite). Contentful entry plan is $300/mo ($3,600/yr); enterprise is far more. **MIT core is free; SSO/RBAC/audit logs are paid enterprise.** (timestamp 5:10)
- **#5 Gitea (~57k stars, MIT, single tiny binary) — self-hosted Git platform.** Repo hosting, PRs, code review, issues, package registry, built-in CI/CD with Gitea Actions. GitHub Enterprise is $21/user/mo. A 50-dev engineering team = **$12,600/yr**. Gitea is free, no per-seat cost. (timestamp 6:26)
- **#6 Nextcloud (~36k stars, AGPL) — your own Dropbox/Google Drive.** File sync, desktop + mobile clients, calendar, contacts, document editing. Capacity is limited by your disk, not a per-seat tier. Dropbox Business Advanced is $24/user/mo. For 50 people = **$14,400/yr**. (timestamp 7:38)
- **#7 Medusa (~35k stars, MIT, TypeScript) — open-source headless commerce.** Cart, orders, products, inventory, regions, all through a flexible API you build any storefront on. Shopify Plus platform fee alone is $2,300/mo = **$27,600/yr before a single transaction**. Medusa is MIT, no fee. **Real catch: Medusa is back-end only — you take on hosting, PCI-compliant payments, and the storefront build.** (timestamp 8:51)
- **#8 PostHog (~35k stars, MIT) — the open-source product analytics platform.** Not one tool, the whole stack: product analytics, web analytics, session replay, feature flags, A/B experiments, surveys. Mixpanel Growth at ~10M events/mo is ~$2,500/mo = **$30,240/yr**, scales with volume. PostHog is MIT self-hosted, your event data stays yours. **Real catch: runs a heavy ClickHouse data stack; a few enterprise features live in a separate directory.** (timestamp 10:06)
- **#9 Keycloak (Apache 2.0) — open-source identity and access management.** Every feature, zero per-seat fee. Okta's like-for-like essential suite is $17/user/mo. A 200-person company pays **$40,800/yr just to log in**. Keycloak is free. **Catch: you run the high-availability clustering and upgrades; no vendor support line unless you pay Red Hat.** (timestamp 11:30)
- **#10 ERPNext (~36k stars, GPL) — the open-source ERP.** Accounting, stock, orders, manufacturing, HR + payroll, projects, CRM, end-to-end. NetSuite for a realistic 25-user mid-market company is **~$50,000/yr, all in** (and they won't publish a number). ERPNext replaces it for free. **Honest catch: license is $0, but budget for hosting and realistically an implementation partner — an ERP is a project, not a download.** (timestamp 12:48)
- **The "counter" framing:** the video runs a live on-screen counter of the total annual savings as each repo is added, ending past $189,000. The series total across all 5 parts is 50 repos replacing "hundreds of thousands of dollars a year." (timestamp 14:08)

## Notable Quotes
> "Self-hosting saves you the license fee, not the work. You run the server. Deal? Let's go kill some invoices." — 1:00
> "That's Octa's per seat empire toppled." — 12:45
> "A $50,000 ERP offer free. That's part five." — 14:17

## Tools and Resources Mentioned
- **Supabase** (github.com/supabase) — Apache 2.0, Firebase+Auth0 replacement
- **cal.com** (github.com/calcom) — MIT, Calendly replacement (now fully MIT; SAML SSO is the paid add-on)
- **RustDesk** (github.com/rustdesk) — AGPL, TeamViewer/AnyDesk replacement
- **Strapi** (github.com/strapi) — MIT core, Contentful replacement
- **Gitea** (github.com/go-gitea) — MIT, GitHub Enterprise replacement
- **Nextcloud** (github.com/nextcloud) — AGPL, Dropbox/Google Drive replacement
- **Medusa** (github.com/medusajs) — MIT, Shopify Plus replacement
- **PostHog** (github.com/posthog) — MIT, Mixpanel/Amplitude replacement
- **Keycloak** (github.com/keycloak) — Apache 2.0, Okta replacement
- **ERPNext** (github.com/frappe) — GPL, NetSuite/SAP replacement
- **Docker / Docker Compose** — the install surface for nearly all 10
- **Postgres / MySQL / SQLite** — backing databases for several of the stack
- **Frappe Docker Compose** — ERPNext's official setup path
- **The "self-hosted stack" PDF** (free; comment "self-host" on the video or grab at hyperautomationlabs.co/free/selfhost) — collects all 50 repos from parts 1-5 with the exact deploy command for each

## Action Items
- [ ] Pick the ONE line item on your SaaS bill that costs the most per year and stand up its open-source replacement this weekend. The video proves each repo is a one-Docker-run setup.
- [ ] Before adopting any of these, allocate a real maintenance budget (uptime, backups, SSO wiring, HA clustering). The "license is $0" story is real, the "ops is $0" story is not.
- [ ] If you're a 200-person company paying Okta, Keycloak alone saves you $40K/yr — that's a hire.
- [ ] If you're a 50-dev team paying GitHub Enterprise, Gitea saves you $12.6K/yr with no per-seat cap. Audit who actually needs GitHub-collaborator status and who can read-only.
- [ ] For Medusa specifically: budget the storefront build before committing. The $2,300/mo Shopify Plus saving is real but "Medusa is back-end only" means you take on the customer-facing surface.
- [ ] Download the free "self-hosted stack" PDF — it has all 50 repos from parts 1-5 with deploy commands.

## Open Questions
- The video cites NetSuite at ~$50K/yr for 25 users but acknowledges "they won't even publish a number." Is the real mid-market cost 2-3x that? ERPNext's value proposition shifts dramatically if the actual NetSuite bill is $100-150K.
- PostHog's "ClickHouse data stack" — what's the minimum infra (RAM, disk, k8s) to run a non-toy PostHog instance? The "hobby Docker Compose" mention undersells the production story.
- For Keycloak, what's the realistic engineering hours to wire it to an existing user directory (LDAP/AD) plus enable WebAuthn? The "one Docker run" framing is true for the demo, not for the SSO rollout.
- Medusa's "storefront" gap: is there a canonical open-source storefront (e.g. a Next.js starter) that's known to work? The video leaves this as "wire a storefront to the API" which is the actual hard part.

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 00:15:47 transcript)</summary>

[Full transcript stored at channels/hyperautomation-labs/transcripts/2026-06-26_10-github-repos-part-5-189k-saas-killers.txt]

</details>
