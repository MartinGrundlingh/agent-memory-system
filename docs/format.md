# File Formats

This section summarizes the intended contents of each file. Use the templates in `agent-memory-system/references/` as examples.

## tech_stack.md

- Purpose: Track the official stack, versions, and tooling constraints.
- Update when: Dependencies/tools change.
- Good entries: language/runtime versions, package manager, linters/formatters, CI tools, hosting, database choices.

## decisions.md (ADRs)

- Purpose: Record architectural decisions and trade-offs.
- Update when: A significant technical choice is made or revisited.
- Required fields: ADR number, date, context, decision, consequences.

## bugs.md

- Purpose: Capture fixed bugs so they don't recur.
- Update when: A non-trivial bug is fixed (especially recurring issues).
- Required fields: date, description, root cause, solution, prevention (optional).

## key_facts.md

- Purpose: Store frequently-needed non-sensitive constants (URLs, ports, service names, paths).
- Update when: A fact changes or a new fact is discovered.
- Never store: passwords, API keys, tokens, private keys, credentials.

## issues.md

- Purpose: Keep a lightweight work log of completed tasks/tickets.
- Update when: Work is completed or a significant milestone is reached.
- Include: date, ticket/issue ID, short description, URL, status (optional).

## security.md

- Purpose: Record security findings and remediations.
- Update when: A vulnerability is fixed or a security control is added/changed.
- Include: date, vulnerability type, source/tool, issue summary, fix, prevention notes.

## testing.md

- Purpose: Document how to run tests and verify critical flows.
- Update when: Commands or frameworks change, or QA scripts are revised.
- Include: automated check commands and manual verification scripts.

## glossary.md

- Purpose: Define domain terms and how they map to code.
- Update when: Domain language changes or confusion arises due to synonyms.
- Include: term, definition, code usage, synonyms/notes.
