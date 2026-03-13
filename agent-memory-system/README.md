# Agent Memory System: User Guide

This directory acts as the **"long-term memory"** for this project. It is designed to bridge the context gap between AI sessions and human developers, ensuring that architectural choices, domain knowledge, and technical patterns are preserved and respected over time.

This folder is meant to be committed to the target repository and treated as a shared source of truth for humans and agents.

---

## Directory Structure & File Reference

| File | Purpose | When to Update |
| :--- | :--- | :--- |
| **`tech_stack.md`** | **The Single Source of Truth** for libraries, versions, and tools. | When adding a library, upgrading a version, or changing a tool. |
| **`decisions.md`** | **Architectural Decision Records (ADRs)**. The "Why" behind the code. | When making a significant technical choice (e.g., "Choose option A over option B"). |
| **`bugs.md`** | A knowledge base of **fixed bugs** and their solutions. | After fixing a tricky, recurring, or complex bug to prevent regression. |
| **`key_facts.md`** | Critical **non-sensitive** configuration facts and constraints. | When environment setups, port numbers, or path conventions change. |
| **`glossary.md`** | **Domain Dictionary**. Maps business terms to code variables. | When introducing new business logic or clearing up ambiguous terms. |
| **`security.md`** | Security vulnerability logs, patches, and policies. | When patching a vulnerability or implementing a new security control. |
| **`testing.md`** | Testing strategies, manual QA scripts, and coverage goals. | When adding a new test suite or changing testing frameworks. |
| **`issues.md`** | A high-level **Work Log** of completed tasks/tickets. | After completing a feature or a significant chunk of work. |
| **`references/`** | **Templates** for the files above. | Generally never, unless you are improving the memory system structure itself. |
| **`archive/`** | Historical data. | When a file becomes too large, move old entries here. |

---

## Canonical Documentation

To keep rules consistent over time, treat these as the canonical sources:

- How to use this system (read-first/update-last): [docs/usage.md](../docs/usage.md)
- File format requirements: [docs/format.md](../docs/format.md)

## Quick Rules

- Start of work: read `tech_stack.md` and `decisions.md`
- End of work: update the relevant memory file(s) with concise, dated entries
- Never store secrets (passwords, API keys, tokens, private keys) in this folder
