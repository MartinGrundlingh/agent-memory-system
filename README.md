# Agent Memory System (Agent Skill)

This repository folder contains a portable, repo-local "memory system" you can drop into a codebase so humans and AI agents can keep key project context consistent across sessions.

Version: 1.0.5

It also includes an Agent Skills-compatible [SKILL.md](SKILL.md) that describes how an agent should read from and write to the memory files.

## What You Get

- `agent-memory-system/`: the memory files (and templates) meant to live in your project repo
- `SKILL.md`: instructions for skills-compatible agents
- `docs/`: setup and usage documentation

## Quick Start (Drop-In)

1. Copy `agent-memory-system/` into the root of your target repository.
2. Commit it to version control.
3. Add a short instruction for your agent/tooling to always read these first:
   - `agent-memory-system/tech_stack.md`
   - `agent-memory-system/decisions.md`

## Agent Skills Install

If your agent supports the Agent Skills format, install this folder as a skill so the agent can load the instructions on demand:

- Install the folder that contains `SKILL.md` as the skill package (the exact install location/mechanism is tool-specific).
- Ensure the agent can also access your project repository so it can read and update the repo-local memory files in `agent-memory-system/`.

See [docs/setup.md](docs/setup.md) for concrete examples (TRAE, Claude Code, Copilot, Replit, and generic fallback).

## How To Use

- Start of work: read `agent-memory-system/tech_stack.md` and `agent-memory-system/decisions.md`.
- During work: consult `key_facts.md`, `testing.md`, and `glossary.md` as needed.
- End of work: update the relevant file(s) with concise, dated entries.

See [docs/usage.md](docs/usage.md).

## Security

Never store secrets (passwords, API keys, tokens, private keys, session cookies) in `agent-memory-system/`. Use `.env` and a secret manager instead.
