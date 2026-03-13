---
name: "agent-memory-system"
description: "Provides a portable, disk-based project memory system. Invoke when you need persistent project context or to record decisions, bugs, key facts, testing, or security notes."
---

# Agent Memory System

This skill provides a lightweight, repo-local "memory system" stored in `agent-memory-system/`. It's designed to be committed to version control and used by humans and AI agents to keep decisions and project context consistent across sessions.

See `agent-memory-system/README.md` in the project repository for the comprehensive user guide.

## Use This Skill When

- You need to quickly align on a project's conventions, tech choices, and past decisions.
- You fixed a bug, made a decision, learned a key fact, or completed work that should be recorded.
- You want a consistent, auditable workflow for "what we learned" in a project.

## Quick Start

1. Ensure the `agent-memory-system/` directory is present at the project repository root.
2. At the start of work, read:
   - `agent-memory-system/tech_stack.md`
   - `agent-memory-system/decisions.md`
   - `agent-memory-system/key_facts.md` (if the work involves config/ports/URLs)
3. While working, consult the relevant file(s).
4. At the end of work, update the relevant file(s) with concise, dated entries.

## At Conversation Start (Always)

1. Read-first: `agent-memory-system/tech_stack.md` and `agent-memory-system/decisions.md`.
2. Scan other memory files for relevant context and recent updates.
3. Review recent code changes that might affect the task.
4. Verify current project state and environment details.
5. Identify ongoing work that needs continuation.
6. Check for conflicts with prior decisions, conventions, or patterns.

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

## Verification & Consistency Protocols

### Configuration Change Verification

For any configuration file changes:

1. Search official documentation first.
2. Verify multiple sources (official docs, version-specific notes, recent examples).
3. Check existing memory files for related decisions and constraints.
4. Cross-reference proposed changes with previous choices and patterns.
5. Share the sources you used.
6. State assumptions explicitly (use "I need to verify ..." when applicable). If an assumption materially affects the outcome, ask for confirmation before applying changes.
7. Avoid guessing configuration syntax, service names, and version-specific requirements.

### Change Integration Protocol

For any change that affects project behavior:

1. Search existing memory files for related decisions or patterns.
2. Create/update memory documenting the change rationale.
3. Cross-reference related entries to maintain a decision chain.
4. Update dependent facts that might be affected.
5. Verify consistency with established project patterns.

### Dependency Management Protocol

When adding or updating dependencies:

1. Check the latest stable version from official sources before installing.
2. Do not assume versions found in existing code or examples are current.
3. Verify compatibility with the core stack and existing constraints.
4. Update `agent-memory-system/tech_stack.md` immediately with the version change.
5. Run an appropriate vulnerability and dependency security check for the ecosystem (if available).

### Fact Verification Process

Before using any stored project fact:

1. Verify fact currency (check when it was last updated).
2. Cross-reference other memory entries for supporting context.
3. Validate against the current environment and codebase.
4. Check for conflicts with other stored information.
5. Update the fact if needed before proceeding.

## Memory-Aware Playbooks

- Before proposing architectural changes: check `agent-memory-system/decisions.md` and `agent-memory-system/tech_stack.md`, and call out conflicts and trade-offs.
- When writing code or naming things: check `agent-memory-system/glossary.md` for canonical domain terms and mappings.
- When writing or running tests: check `agent-memory-system/testing.md` for commands and patterns.
- When encountering errors: search `agent-memory-system/bugs.md` for similar issues, and record new fixes when resolved.
- When looking up configuration: check `agent-memory-system/key_facts.md` for non-sensitive constants; prefer documented facts over assumptions.
- When completing work: log outcomes and relevant URLs in `agent-memory-system/issues.md`.
- When asked to update memory: update the correct file and follow the established style (dates, bullets, concise entries).

## Style Guidelines

- Prefer bullet lists; use tables when they improve scanability.
- Keep entries concise (1–3 lines for descriptions).
- Always include dates for temporal context.
- Include URLs when relevant (tickets, documentation, dashboards).

## Memory Maintenance

Do not wait for specific phrases. If the information is valuable for future context, record it.

Proactively update memory whenever you:

- Fix a bug (update `agent-memory-system/bugs.md`)
- Make an architectural decision (update `agent-memory-system/decisions.md`)
- Discover a new key fact (update `agent-memory-system/key_facts.md`)
- Complete significant work (update `agent-memory-system/issues.md`)
- Resolve a security issue (update `agent-memory-system/security.md`)
- Change tooling or dependencies (update `agent-memory-system/tech_stack.md`)
- Define or refine a business term (update `agent-memory-system/glossary.md`)
- Update testing strategy or commands (update `agent-memory-system/testing.md`)

## Memory Triggers

| User phrase | Action | File |
| :--- | :--- | :--- |
| "log a bug", "fix bug", "bug squashed" | Record root cause, fix, and prevention notes | `agent-memory-system/bugs.md` |
| "track decision", "ADR", "architectural choice" | Record an architectural decision | `agent-memory-system/decisions.md` |
| "remember this", "key fact", "add config" | Store non-sensitive project constants | `agent-memory-system/key_facts.md` |
| "update status", "work log", "ticket update" | Record completed work and URLs | `agent-memory-system/issues.md` |
| "security fix", "vuln patched", "sast fix" | Record security findings and fixes | `agent-memory-system/security.md` |
| "update stack", "add library", "dep upgrade" | Update tooling choices and versions | `agent-memory-system/tech_stack.md` |
| "define term", "add glossary", "what is X" | Define domain terms and code mappings | `agent-memory-system/glossary.md` |
| "update test", "add test script", "QA script" | Update test commands and manual checks | `agent-memory-system/testing.md` |
| "rollover memory", "archive memory" | Archive older entries and reset active files | `agent-memory-system/archive/` |

## Archiving

To prevent memory files from becoming too large:

1. Check file size: if a file exceeds about 500 lines, archive it.
2. Archive: move older entries into a dated file in `agent-memory-system/archive/` (for example, `issues_YYYY-MM.md`).
3. Reset: keep the header and template structure in the active file.
4. Summary: summarize key unfinished items back into the active file.
5. Search: when looking for context, check both active files and relevant archives.
