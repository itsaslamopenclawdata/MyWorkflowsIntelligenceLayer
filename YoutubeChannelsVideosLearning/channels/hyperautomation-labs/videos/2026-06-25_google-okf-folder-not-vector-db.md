---
title: "Google Just Made Vector Databases Optional — And It's Just a Folder (OKF)"
channel: "Hyperautomation Labs"
channel_slug: "hyperautomation-labs"
channel_id: "UCiax-xbEI0P6Y8C8VwZGMgQ"
published: "2026-06-25"
duration_seconds: 448
video_id: "m-D99wDLj7Y"
url: "https://www.youtube.com/watch?v=m-D99wDLj7Y"
language: "en"
tags: [okf, open-knowledge-format, google-cloud, knowledge-graph, rag, vector-database, markdown, ai-agents, context-engineering, retrieval]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-26"
---

# Google Just Made Vector Databases Optional — And It's Just a Folder (OKF)

**Channel:** Hyperautomation Labs  **Published:** 2026-06-25  **Duration:** 7:28  **Watch:** https://www.youtube.com/watch?v=m-D99wDLj7Y

## TL;DR

Google Cloud published the **Open Knowledge Format (OKF)** on June 12, 2026 — a one-page spec that replaces RAG-style vector databases for most structured knowledge with a directory of markdown files. Each file is one concept (table, metric, runbook, API), they link to each other with ordinary markdown links, and the agent *traverses* the graph deliberately instead of guessing via similarity search. The format: one required YAML field (`type`), two reserved filenames (`index.md`, `log.md`), everything else optional. "Retrieval guesses. Traversal navigates."

## Key Insights

- **The RAG-vs-folder mismatch.** Most company knowledge isn't a giant messy pile that needs fuzzy search — it's structured: tables, metrics, runbooks, APIs. Forcing it through similarity search is "alphabetizing your whole kitchen and then finding the salt by smell." Embedding models, vector DBs, chunk-size tuning, re-indexing on every doc change, debugging why the retriever pulled the wrong paragraph — none of it is free. (0:30–1:50)

- **OKF's whole idea.** Instead of dumping knowledge into a database and hoping retrieval rediscovers it, you write it down once as a folder of markdown files and let the agent read it directly the same way it reads your code. Each file is one concept. Concepts link to each other with ordinary markdown links. (2:00–2:25)

- **The spec is almost suspiciously simple.** An OKF bundle is just a directory of markdown files. Each file has a small YAML header at the top. In v0.1 there is exactly one required field: `type` (a short string: table / metric / runbook). Everything else optional but recommended: `title`, one-sentence description, link to the real resource, tags, timestamp. Two reserved filenames: `index.md` (the front door — table of contents that lets the agent see the map before it reads the details) and `log.md` (optional change history). That's the entire format. (2:25–3:25)

- **Why linking matters — the whole point.** With a vector DB the agent asks a question and gets back a handful of fragments ranked by similarity; it can't follow a thread. With OKF the agent starts at one file (say the "weekly active users" metric), that file links to the table it's calculated from, which links to the dataset it lives in, which links to the runbook for when the number looks wrong. The agent walks the graph deliberately, the way a human would. (3:25–4:05)

- **Concrete build.** Make a folder. Drop in an `index.md` listing your concepts. Then a file `metrics/weekly-active-users.md` with `type: metric`, a title, a one-line description, a link to where it lives, and the definition in the body. Then link from the metric to the table to the dataset to the runbook. (4:05–4:45)

- **When OKF beats a vector DB, and when it doesn't.** OKF wins when your knowledge is structured and your questions are about relationships — "where does this metric come from? what depends on it? what's the runbook if it looks wrong?" Vector DBs still win when the corpus is unstructured (long docs, transcripts, support tickets) and the query is genuinely fuzzy. (4:45–5:30)

- **The bigger framing.** "Retrieval guesses. Traversal navigates." If your agent is rediscovering your company from a pile of shredded paper on every question, you don't have a knowledge problem — you have a representation problem. OKF is a representation-first approach; RAG is a similarity-first approach. Pick the one that matches your knowledge. (5:30–7:28)

## Notable Quotes

> "Your agent is rediscovering your entire company from a pile of shredded paper on every single question. It never learns the shape of what you know." — 1:05

> "Forcing that through similarity search is like alphabetizing your whole kitchen, and then finding the salt by smell." — 1:48

> "One required field. Two reserved file names. That's the entire format." — 3:22

> "The agent walks the graph deliberately, the way you would. It's the difference between being handed a stack of photocopied pages and being handed a wiki you can click through." — 3:55

> "Retrieval guesses. Traversal navigates." — 4:05

## Tools and Resources Mentioned

- **Open Knowledge Format (OKF)** — Google Cloud's open spec published 2026-06-12; the one-page markdown-folder format that replaces RAG for structured knowledge. *vendor: Google Cloud product — third-party spec, not part of the user's stack.*
- **Vector databases (generic)** — what OKF is positioned against; the speaker argues most teams pay for these without needing them.
- **Embedding models (generic)** — also argued to be unnecessary for structured knowledge.
- **RAG (Retrieval Augmented Generation)** — the pattern OKF is replacing for structured corpora.

## GitHub Repos and URLs Referenced

- (OKF spec referenced; the speaker says he read the "actual spec" which "fits on a single page" — no direct link in transcript.)
- (No specific GitHub repos in this video.)

## Action Items

- [ ] Audit your knowledge corpus: how much of it is structured (tables, metrics, runbooks, APIs) vs. unstructured (long docs, transcripts, tickets)? If structured > unstructured, OKF probably beats your current RAG.
- [ ] Pick one concept you answer questions about repeatedly (e.g., a key metric) and turn it into an OKF file with `type`, `title`, description, link, and the body definition.
- [ ] Write the `index.md` first — list every concept in your knowledge base as a clickable map for the agent.
- [ ] Connect concepts with markdown links so the agent can traverse from metric → table → dataset → runbook.
- [ ] If you keep a RAG layer for the unstructured portion, use OKF for the structured portion and let the agent choose which to query.

## Open Questions

- The spec is v0.1 — what's the migration story when Google ships v0.2 or v1.0 and reserves new filenames or required fields?
- The video doesn't show the "agent reads the OKF folder" side. What tools natively support OKF traversal today? Is there an OKF-aware Claude/Cursor prompt, or do you write your own loader?
- For mixed corpora (50% structured, 50% unstructured), is the recommendation to run both in parallel and let the agent choose, or to convert the unstructured portion to OKF-style concept files too?

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 7:28 transcript)</summary>

0:00 Last week, Google quietly published a
0:02 new standard. Not a model.
[...]
7:20 (closing)

(Full 7,608-character transcript saved to channels/hyperautomation-labs/transcripts/2026-06-25_google-okf-folder-not-vector-db.txt)

</details>