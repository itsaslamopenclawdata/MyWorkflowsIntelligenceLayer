---
title: "Building Interactive UIs in VS Code with MCP Apps — Marlene Mhangami & Liam Hampton, GitHub"
channel: "AI Dot Engineer"
channel_slug: "ai-dot-engineer"
channel_id: "UCLKPca3kwwd-B59HNr-_lvA"
published: "2026-06-06"
duration_seconds: 966
video_id: "_xIwFcnHqp4"
url: "https://www.youtube.com/watch?v=_xIwFcnHqp4"
language: "en"
tags: ["mcp", "mcp-apps", "vscode", "interactive-ui", "shopify", "excalidraw", "agent-ui", "github", "sandbox-iframe", "tool-calling"]
transcript_status: "partial"
generated_by: "channels-youtube-content"
generated_on: "2026-06-07"
---

# Building Interactive UIs in VS Code with MCP Apps — Marlene Mhangami & Liam Hampton, GitHub

**Channel:** AI Dot Engineer  **Published:** 2026-06-06  **Duration:** 16:06  **Watch:** https://www.youtube.com/watch?v=_xIwFcnHqp4

## TL;DR

A 16-minute deep-dive on MCP Apps — the pattern that lets MCP tools return interactive HTML UIs that render inside VS Code's chat as sandboxed iframes. Demo: a Go app running bubble sort + Fibonacci, the result renders as a live, scrollable, queryable flame graph directly inside the chat (not a link, not a text summary). Real production examples: Shopify uses this for checkout flows inside chat; Excalidraw uses it for interactive drag-and-edit architecture diagrams. The security model: sandboxed iframe so the UI can't escape and call external APIs or chew up your VS Code settings.

## Key Insights

- **MCP Apps = MCP tool returns data + resource reference pointing to bundled HTML UI.** VS Code fetches the HTML and renders it sandboxed in chat. [description]
- **The live demo**: a Go app running bubble sort + Fibonacci, results rendered as an interactive flame graph in the VS Code chat window. Scrollable, queryable, live. [description]
- **The architecture is event-driven**: app calls back to the server, server returns fresh data, UI updates. [description]
- **Two production examples**: [description]
  - **Shopify** — checkout flows inside chat.
  - **Excalidraw** — interactive architecture diagrams you can drag and edit.
- **The security model**: sandboxed iframe, "for the same reason you put a hamster in a cage — so it cannot chew up your VS Code settings or call external APIs." [description]
- **The speakers walk through building one from scratch** using a skill from the MCP repository. [description]
- **The implication**: every agent UI today is a text reply. MCP Apps make the reply a real app. [implied]
- **No transcript available** — note generated from description.

## Notable Quotes

- "The demo profiles a Go app running bubble sort and Fibonacci and the result renders as an interactive flame graph directly inside the VS Code chat window. Not a link. Not a text summary. A live iframe you can scroll and query." [description]
- "Sandboxed for the same reason you put a hamster in a cage: so it cannot chew up your VS Code settings or call external APIs." [description]

## Tools and Resources Mentioned

- **MCP (Model Context Protocol)** — the protocol. [description]
- **MCP Apps** — the pattern for interactive UI returns. [description]
- **VS Code** — the chat host. [description]
- **Go** — the demo language. [description]
- **Shopify** — production example (checkout flows). [description]
- **Excalidraw** — production example (interactive diagrams). [description]
- **MCP repository** — contains the building-block skill. [description]

## GitHub Repos and URLs Referenced

- **The MCP repository** (https://github.com/modelcontextprotocol — verify URL) — has the building-block skill. [description]
- **https://x.com/marlene_zw** — Marlene's X. [description]
- **https://www.linkedin.com/in/marlenemhangami/** — Marlene's LinkedIn. [description]
- **https://github.com/marlenemhangami** — Marlene's GitHub. [description]
- **https://x.com/liamchampton** — Liam's X. [description]
- **https://www.linkedin.com/in/liam-conroy-hampton/** — Liam's LinkedIn. [description]
- **https://github.com/liamchampton** — Liam's GitHub. [description]

## Action Items

- [ ] **Watch the full 16:06 video** for the actual build walkthrough and the MCP repository skill name. [transcript_status: partial]
- [ ] **Try the demo Go app** — bubble sort + Fibonacci flame graph is the canonical "this is what MCP Apps can do" example. [implied]
- [ ] **Audit your own MCP tool returns** — are they text-only, or could they be interactive UIs? [implied]
- [ ] **Consider the security implications** before shipping MCP Apps to users — sandboxed iframe is the right model, but what's the threat surface? [description]
- [ ] **Think about what UI you'd build** for your own agent — checkout flow? Diagram editor? Dashboard? Form? [implied]

## Open Questions

- **The MCP repository skill** — what's it called? Where in the repo? The description doesn't say.
- **Sandbox granularity** — what CAN the iframe do? Local network calls? LocalStorage? Cross-origin to other MCP servers? Or strict no-network no-storage?
- **Production examples** — what % of Shopify's checkout flow is actually inside chat? Same for Excalidraw? Or are these "lab demos"?
- **VS Code-only?** Or do other MCP hosts (Claude Desktop, Cursor, Windsurf) support MCP Apps too?
- **Bidirectional events** — when the user clicks a button in the iframe, how does that call back to the server? HTTP? WebSocket? MCP protocol itself?

---

*Note: transcript was unavailable. Note generated from description, which provides a clear technical pattern + 2 production examples.*
