---
name: "agent-memory-system"
description: "Provides a portable, disk-based project memory system. Invoke when you need persistent project context or to record decisions, bugs, key facts, testing, or security notes."
---

# Agent Memory System

This skill provides a lightweight, repo-local "memory system" stored in `agent-memory-system/`. It's designed to be committed to version control and used by humans and AI agents to keep decisions and project context consistent across sessions.

## Use This Skill When

- You need to quickly align on a project's conventions, tech choices, and past decisions.
- You fixed a bug, made a decision, learned a key fact, or completed work that should be recorded.
- You want a consistent, auditable workflow for "what we learned" in a project.

## Quick Start

1. Ensure the `agent-memory-system/` directory is present at the repository root.
2. At the start of work, read:
   - `agent-memory-system/tech_stack.md`
   - `agent-memory-system/decisions.md`
   - `agent-memory-system/key_facts.md` (if the work involves config/ports/URLs)
3. While working, consult the relevant file(s).
4. At the end of work, update the relevant file(s) with concise, dated entries.

## Files

- `agent-memory-system/tech_stack.md`: official technologies, versions, and tooling constraints
- `agent-memory-system/decisions.md`: Architectural Decision Records (ADRs)
- `agent-memory-system/bugs.md`: bug log with root causes and fixes
- `agent-memory-system/key_facts.md`: non-sensitive configuration facts (never secrets)
- `agent-memory-system/issues.md`: work log / ticket notes
- `agent-memory-system/security.md`: security fixes and prevention notes
- `agent-memory-system/testing.md`: testing strategy and manual QA scripts
- `agent-memory-system/glossary.md`: domain terms and their code equivalents
- `agent-memory-system/references/`: templates and examples
- `agent-memory-system/archive/`: archived older entries when files grow too large

## Operating Rules

- Prefer confirmed facts over speculation. If unsure, write what is known and what needs verification.
- Never store secrets (passwords, API keys, tokens, private keys, session cookies) in `agent-memory-system/`.
- Keep entries short and scannable. Bullets and small tables are preferred.

## Memory Triggers

| User phrase | Action | File |
| :--- | :--- | :--- |
| "log a bug", "bug squashed" | Record root cause, fix, and prevention notes | `agent-memory-system/bugs.md` |
| "track decision", "ADR" | Record an architectural decision | `agent-memory-system/decisions.md` |
| "remember this", "key fact", "add config" | Store non-sensitive project constants | `agent-memory-system/key_facts.md` |
| "update status", "work log", "ticket update" | Record completed work and URLs | `agent-memory-system/issues.md` |
| "security fix", "vuln patched" | Record security findings and fixes | `agent-memory-system/security.md` |
| "update stack", "add library" | Update tooling choices and versions | `agent-memory-system/tech_stack.md` |
| "define term", "glossary" | Define domain terms and code mappings | `agent-memory-system/glossary.md` |
| "update test", "QA script" | Update test commands and manual checks | `agent-memory-system/testing.md` |

## Archiving

When a memory file becomes large (for example, 500+ lines), move older entries into `agent-memory-system/archive/` and keep the most recent entries in the active file.

