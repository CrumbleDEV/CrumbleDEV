### Hi, I'm Pablo 👋

I build **LLM agent systems that ship real software**, and the products they ship.
My agents plan work, write code in isolated git worktrees, review each other, run the
tests and open draft PRs. A human approves at fixed gates; nothing auto-merges.

546 merged PRs on my main product repo and 123 on my iOS app. Most of it was built with the agent tooling below.

🌐 [gohexa.ai](https://gohexa.ai) · 📁 [Projects](https://gohexa.ai/projects) · 🇩🇪 🇬🇧

---

## Agentic engineering

| Tool | What it does |
|---|---|
| **`/workme`** | Takes one free-form goal and cuts it into at most 8 slices. Each slice gets a path-ownership table and a conflict graph, and a critic agent checks the cut. After one human approval, 2–3 slices build in parallel, each in its own git worktree. Everything merges into one integration branch and ends as one draft PR. |
| **`/loopthis`** | Picks the next unblocked slice of a project area and runs it through a gated pipeline: research → plan → gate → TDD → graph-aware code review → gate → green tests → draft PR. Wrap it in `/loop` and it works through the whole area. My most-used tool (100+ runs). |
| **`/nightly`** | An overnight loop started by launchd at 01:00. It takes the top roadmap items, builds each in a worktree, checks build and tests, runs two independent reviewers and leaves draft PRs by 09:00. |
| **Agent Virtual Office** | A pixel-art office that shows my AI coding agents working in real time. A Node daemon streams agent state into a Next.js dashboard. |
| **Harness** | A registry-driven router over ~350 skills, ~80 sub-agents and 20+ MCP servers. It has hard guardrails (pre-tool hooks block destructive commands), cost caps and a code knowledge graph that runs before every review. |

<p align="center">
  <img src="assets/workme.svg" width="49%" alt="/workme architecture: goal, slicer and critic agents, one human gate, parallel builder worktrees, integration branch, draft PR" />
  <img src="assets/loopthis.svg" width="49%" alt="/loopthis pipeline: next slice, research and plan, gate 1, TDD build, review, gate 2, tests, draft PR, repeat" />
</p>

**Principles:** gates over autonomy · one slice = one PR · tests must run green before a PR opens · agents never touch `main`.

---

## Products

**[gohexa.ai](https://gohexa.ai)**: my studio site and internal platform. Next.js 16, React 19, Supabase, Anthropic SDK.
It includes a streaming Claude chat playground, a visual workflow editor (React Flow) and the agent dashboard.

**RaveBase (iOS)**: a social app for rave crews in Swift and SwiftUI with a Supabase backend.
Event hub, festival finder, crew chat, live photo drops, a drink-cost splitter and meeting points.

**Client sites** (shipped and live): [WZ-Atelier](https://wz-atelier-site.vercel.app) (tattoo studio with booking CRM and Three.js),
PSA-System, Heartbeats Agency and more.

---

## Stack

- **LLM / agents:** Claude API (Anthropic SDK) · MCP servers · multi-agent workflows · prompt & context engineering
- **Web:** TypeScript · Next.js · React · Tailwind · Framer Motion · Three.js
- **Backend:** Supabase / Postgres (RLS, RPC) · Node · Python · Vercel
- **Mobile:** Swift · SwiftUI
- **Quality:** TDD (Vitest) · code-review knowledge graph · CI gates

---

Most repos are private (client code). Happy to walk you through any of them live. Reach me via [gohexa.ai](https://gohexa.ai).
