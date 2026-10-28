# Project Build — User Level Skill Framework

A single Claude Code skill. It turns a plain description of a business
problem into a real, structured first version of a working tool, built
the way a developer would set one up.

Built by GRAFTD Media.

## What it does

Given a short description of a real problem, Claude will:

- Ask four quick questions to size up the build (who uses it, does it
  touch sensitive data, does it connect to another system, will anyone
  else need to maintain it)
- Set up a new project folder with its own git repo
- Write a plain-language `README.md` (what it does, who it's for, what's
  assumed)
- Keep a `DECISIONS.md` log of real choices made, and why
- Keep any passwords or API keys out of the code, in a local `.env` file
- For anything more than a simple, single-user build: also write an
  `ARCHITECTURE.md` covering what data moves where and what a developer
  should check before it goes live
- Build the simplest working first version of the one thing that matters
  most
- Tell you plainly what's finished, what's guessed, and what to test next

A simple build (just you, nothing sensitive, no other systems) skips
straight past the extra questions and the architecture note — it only
shows up when the build actually needs it.

Full detail: [`skills/project-scaffold/SKILL.md`](skills/project-scaffold/SKILL.md)

## Install it (one-time, per machine)

This only works if Claude Code is already set up and running locally (as
covered in the course). Open a Claude Code chat and paste this:

```
Fetch https://raw.githubusercontent.com/graftdmedia/project-build-user-level-skill-framework/main/skills/project-scaffold/SKILL.md
and save it to ~/.claude/skills/project-scaffold/SKILL.md on my machine.
```

Claude will create the folder if it doesn't exist yet. Once saved, the
skill works in any project folder, from then on, automatically. Nothing
else to run.

## Using it

Open a terminal in a new, empty folder for whatever you're building,
separate from your AI-Brain folder. Run `claude`, then just describe the
real problem in plain language. Claude will ask a couple of sharp
questions if anything's missing, then start building.
