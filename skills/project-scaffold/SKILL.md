---
name: project-scaffold
description: Turn a plain description of a business problem into a real, structured first version of a working tool or solution — set up safely enough that a developer could pick it up later. Use when starting a brand new coding project, not for editing something already built.
---

# What this does

Takes a plain description of a problem and turns it into a first working
version of something that solves it. Sets the project up properly from the
first commit, so what gets built today can be tested, revisited, and handed
to a developer later without anyone having to reverse-engineer it.

# Before starting

- Confirm this is a NEW project, in its own folder, separate from any
  existing business folder (like an AI Brain folder). If currently inside
  one, stop and create a new folder outside it first.
- Create a folder named after the project. Move into it.

# Step 1: Understand the problem

Ask before building, if any of this is missing:

- What's the actual problem? What's slow, annoying, or manual today?
- Who uses this — just the user, their team, or their customers?
- What would "working" look like today — the smallest version that's
  actually useful?
- Any must-haves (a specific number, format, or piece of data) versus
  nice-to-haves?

Keep this short. One or two rounds of questions, not an interview.

# Step 2: Set the project up properly

- `git init`
- Create `README.md`: what it does, who it's for, what's assumed, what's
  still unknown or unconfirmed
- Create `DECISIONS.md`: a running log, plain language, one line per real
  decision and why it was made. Add to it every session, not just once.
- If the project will ever need a password, API key, or login, create
  `.gitignore` and `.env.example`. Real secrets never get written into code
  or committed — they go in a local `.env` file that `.gitignore` excludes.
- First commit: "Initial scaffold"

# Step 3: Build the first working version

- Pick the simplest technology that solves the actual problem. A single
  HTML file beats a framework. A short script beats a server, if a script
  is all that's needed.
- Build the one core thing that matters most first — not every feature,
  the one piece that proves it works.
- Commit again once it runs.

# Step 4: Wrap up honestly

Tell the user plainly:

- What got built, and what to test
- What was assumed or guessed — point to `DECISIONS.md`
- What isn't finished or isn't confirmed yet
- That a first version is expected to need changes once it's actually
  used — that's normal, not a failure

# Rules

- Never hardcode a password, API key, or token into code. Always `.env`
  plus `.gitignore`.
- Commit after every real change, not one giant commit at the end.
- Don't over-build. Solve today's version of the problem, not every
  future version of it.
- Write `README.md` and `DECISIONS.md` in plain language — a
  non-developer should be able to read them back, and a developer should
  be able to pick the project up from them alone.
- If the problem described is too vague to start, ask before building
  anything.
