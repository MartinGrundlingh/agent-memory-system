# Usage

## Read-First (Start of Session)

Read these before you write code or propose changes:

- `agent-memory-system/tech_stack.md`
- `agent-memory-system/decisions.md`

Depending on the task, also read:

- `agent-memory-system/key_facts.md` (ports, URLs, paths, service names; never secrets)
- `agent-memory-system/testing.md` (commands, QA scripts)
- `agent-memory-system/glossary.md` (domain terminology and canonical names)

## Update-Last (End of Session)

Update the relevant file(s) with concise, dated entries:

- Bug fixed: `agent-memory-system/bugs.md`
- Architectural decision: `agent-memory-system/decisions.md`
- New/changed "facts" (non-sensitive): `agent-memory-system/key_facts.md`
- Completed work/ticket: `agent-memory-system/issues.md`
- Security fix: `agent-memory-system/security.md`
- Testing strategy/commands: `agent-memory-system/testing.md`
- Domain terminology changes: `agent-memory-system/glossary.md`
- Tooling/dependencies: `agent-memory-system/tech_stack.md`

## Writing Guidelines

- Prefer bullet lists; keep each entry short and factual.
- Always include dates when recording events, changes, fixes, or decisions.
- Link to tickets, PRs, dashboards, or docs where helpful.
- If you're unsure, record what is known plus what needs verification (avoid speculation).
- Never store secrets in any `agent-memory-system/*.md`.

## Archiving

If a file grows large (for example, 500+ lines), move older entries into `agent-memory-system/archive/` and keep the newest entries in the main file. When searching for context, check both active files and relevant archives.
