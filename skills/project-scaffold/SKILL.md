---
name: project-scaffold
description: Turn a plain description of a business problem into a real, structured first version of a working tool or solution — set up safely enough that a developer could pick it up later. Scales its questions and output to match how simple or complex the build actually is. Use when starting a brand new coding project, not for editing something already built.
---

# What this does

Takes a plain description of a problem and turns it into a first working
version of something that solves it. Simple builds get built fast, with
almost no questions. Builds that touch other systems, other people, or
sensitive data get a few more questions up front and a short architecture
note, so there's something a developer can actually review before it goes
near anyone real.

# Before starting

- Confirm this is a NEW project, in its own folder, separate from any
  existing business folder (like an AI Brain folder). If currently inside
  one, stop and create a new folder outside it first.
- Create a folder named after the project. Move into it.

# Step 1: Get the basic idea

Ask only what's missing:

- What's the actual problem? What's slow, annoying, or manual today?
- What would "working" look like today — the smallest version that's
  actually useful?

Keep this short, one exchange.

# Step 2: Size it up

Ask these four questions plainly, in one message:

1. Who uses this — just you, your team, or your customers/clients?
2. Does it touch anything sensitive — client data, financial info,
   personal details?
3. Does it need to connect to another account or system — email, a CRM,
   payments, a calendar?
4. Will anyone other than you need to understand or change this later?

**If every answer is the simple one** (just you, nothing sensitive, no
connections, no one else needs to maintain it): treat this as a
**simple build**. Skip straight to Step 3, ask nothing else.

**If any answer points the other way**: treat this as a **complex
build**. Ask one or two follow-up questions on exactly what's sensitive
or what it connects to, nothing more, then go to Step 3.

A simple build should feel faster for answering fewer questions, not
slower — the sizing step itself is four short questions, never an
interview either way.

# Step 3: Set the project up properly

- `git init`
- Create `README.md`: what it does, who it's for, what's assumed, what's
  still unknown or unconfirmed
- Create `DECISIONS.md`: a running log, plain language, one line per real
  decision and why it was made. Add to it every session, not just once.
- If the project will ever need a password, API key, or login, create
  `.gitignore` and `.env.example`. Real secrets never get written into
  code or committed — they go in a local `.env` file that `.gitignore`
  excludes.
- **Complex builds only:** also create `ARCHITECTURE.md` covering what
  data moves where, what external systems are touched, where secrets
  live, and anything that should be checked by a developer before this
  goes near a real client or real money.
- First commit: "Initial scaffold"

# Step 4: Build the first working version

- Pick the simplest technology that solves the actual problem. A single
  HTML file beats a framework. A short script beats a server, if a
  script is all that's needed.
- Build the one core thing that matters most first — not every feature,
  the one piece that proves it works.
- Commit again once it runs.

# Step 5: Wrap up honestly

Tell the user plainly:

- What got built, and what to test
- What was assumed or guessed — point to `DECISIONS.md`
- What isn't finished or isn't confirmed yet
- That a first version is expected to need changes once it's actually
  used — that's normal, not a failure
- **Complex builds only:** state clearly that this should get a
  developer's eyes before it touches real data or goes live, and point
  to `ARCHITECTURE.md` as the starting point for that review

# Rules

- Never hardcode a password, API key, or token into code. Always `.env`
  plus `.gitignore`.
- Commit after every real change, not one giant commit at the end.
- Don't over-build. Solve today's version of the problem, not every
  future version of it.
- The sizing-up step always runs, even for a build that turns out
  simple — four quick questions, never a blocker.
- Never skip the architecture note for a complex build, even if the
  user seems in a hurry. This is the part that protects them later.
- Write all documents in plain language — a non-developer should be
  able to read them back, and a developer should be able to pick the
  project up from them alone.
- If the core problem itself is too vague to start, ask before building
  anything.
