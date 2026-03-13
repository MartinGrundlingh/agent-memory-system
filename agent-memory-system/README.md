# Memory System: User Guide

This directory acts as the **"long-term memory"** for this project. It is designed to bridge the context gap between AI sessions and human developers, ensuring that architectural choices, domain knowledge, and technical patterns are preserved and respected over time.

This folder is meant to be committed to the target repository and treated as a shared source of truth for humans and agents.

---

## Core Philosophy

1.  **Persistence**: Information shouldn't die when a chat session ends. Critical context must be saved to disk.
2.  **Consistency**: By documenting the "why" and "how" (decisions, patterns, stack), we prevent the codebase from becoming a patchwork of different coding styles.
3.  **Hybrid Usage**: This system is designed to be read and written by **both** AI agents and human developers. It serves as a shared source of truth.

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

## Workflow: How to Use This System

### For AI Agents (The Protocol)

1.  **Read-First**: Before writing code, **always** read `tech_stack.md` and `decisions.md`.
    *   *Why?* To ensure you don't install duplicate libraries or violate architectural constraints.
2.  **Update-Last**: Before ending your turn or completing a task, **update the relevant memory files**.
    *   *Did you fix a bug?* -> Update `bugs.md`.
    *   *Did you add a library?* -> Update `tech_stack.md`.
    *   *Did you make a hard choice?* -> Update `decisions.md`.
3.  **Cross-Reference**: If the user uses a specific term (e.g., "User" vs "Account"), check `glossary.md` to see which is the canonical term in the code.

### For Humans

1.  **Onboarding**: Read `tech_stack.md` and `decisions.md` first. This gives you the "what" and the "why" of the project history.
2.  **Triggering the AI**: If the AI forgets a pattern, tell it: *"Check decisions.md for our policy on styling."*
3.  **Explicit Instruction**: You can force the AI to remember things by saying:
    *   *"Record this in the memory system."*
    *   *"Log this bug fix in bugs.md."*
    *   *"Update the tech stack."*
4.  **Manual Overrides**: **You are the ultimate source of truth.** If the AI writes something incorrect in `key_facts.md`, edit the file manually. The AI will read your correction in the next session and align with it.

---

## Detailed File Guidelines

### 1. `tech_stack.md`
*   **Goal**: Prevent "dependency drift" (e.g., having multiple libraries that solve the same problem).
*   **Format**: Group by Frontend, Backend, Dev Tools.
*   **Rule**: If it's not in `package.json`, it shouldn't be here. If it IS here, the AI should use it.

### 2. `decisions.md` (ADRs)
*   **Goal**: Prevent re-litigating settled debates.
*   **Format**:
    *   **Context**: What was the problem?
    *   **Decision**: What did we choose?
    *   **Consequences**: What are the trade-offs (pros/cons)?
*   **Template**: See `references/decisions_template.md`.

### 3. `bugs.md`
*   **Goal**: Save time on future debugging.
*   **Content**: Focus on the *root cause* and the *fix*, not just the error message.
*   **Example**: "Error: `heap out of memory`. Fix: Increased Node max_old_space_size to 4096MB in build script."

### 4. `glossary.md`
*   **Goal**: Unify language.
*   **Example**:
    *   **Term**: `Customer`
    *   **Code Definition**: `interface Client` (Note: The DB uses 'clients', business calls them 'customers').

---

## Maintenance & Archiving

*   **Size Limits**: If a file (like `issues.md` or `bugs.md`) exceeds **500 lines**, it becomes hard for the AI to digest.
*   **Archiving Process**:
    1.  Create a new file in `archive/` (e.g., `archive/2024-bugs.md`).
    2.  Cut and paste the older entries from the main file to the archive file.
    3.  Keep the header and the most recent ~50 entries in the main file.
*   **Pruning**: Regularly delete obsolete entries from `key_facts.md` if they no longer apply.

---

## Important Warnings

1.  **NO SECRETS**: Never write API keys, passwords, or tokens into these files. Use `.env` for that.
2.  **Be Concise**: AI context windows are precious. Keep entries factual and brief.
3.  **Truthfulness**: Do not speculate. Only record facts and confirmed decisions.
