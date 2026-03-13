# Setup

This memory system is designed to work in two modes:

- **Agent Skill (recommended when supported):** Install this folder as an Agent Skill so compatible agents can load instructions on demand.
- **Drop-in (fallback if skills are not supported):** Copy `agent-memory-system/` into your repository and commit it.

## Why "Agent Skill" Depends on Tooling

The core of this project is the on-disk `agent-memory-system/` folder. Any agent that can read and edit files can use it, even if it does not support the Agent Skills standard.

Installing this as an Agent Skill is an instruction-delivery mechanism that only works if your tool supports Agent Skills:

- Not all tools support Agent Skills (or they support a different mechanism for agent instructions).
- A skill install does not replace the need for repository access. The agent still needs to read and update `agent-memory-system/*.md` in your repo.
- Drop-in is the most portable setup and requires the fewest tool-specific steps.

## Agent Skill Install (Recommended When Supported)

Agent Skills are folders containing a `SKILL.md` plus any resources. To install this as a skill, place this folder into your agent's "skills" directory.

### TRAE

- Copy this folder to: `.trae/skills/agent-memory-system/`
- Ensure your repo has `agent-memory-system/` at its root.
- Note: The `.trae/skills/...` path is TRAE-specific. Other tools use different locations (or may not support Agent Skills).

### Claude Code

- Install this folder as a skill in whatever directory Claude Code uses for skills in your environment.
- If you don't have skills enabled, use the Drop-In install and add the snippet below to your `CLAUDE.md` (or equivalent).

### GitHub Copilot

- Use Drop-In install.
- Add the snippet below to `.github/copilot-instructions.md` (or your organization's equivalent).

### Replit

- Use Drop-In install.
- Add the snippet below to the project's agent instruction file (for example, `replit.md` if your setup uses it).

### Generic (Works Everywhere)

- Use Drop-In install.
- If your agent/tool has no special instruction file, paste the snippet below into the first prompt of each session.

## Drop-In Install (Fallback)

1. Copy `agent-memory-system/` into the root of your target repository.
2. Commit it to version control.
3. Tell your agent (via its instruction file or chat) to use it:
   - Read first: `agent-memory-system/tech_stack.md`, `agent-memory-system/decisions.md`
   - Update last: write changes back into the relevant file(s)

### Suggested Agent Instruction Snippet (Drop-In)

Copy/paste this into your tool's instruction mechanism (examples below). This is the most reliable way to get consistent behavior across tools that do not support Agent Skills.

```text
Project uses a repo-local memory system in agent-memory-system/.
At the start of work, read agent-memory-system/tech_stack.md and agent-memory-system/decisions.md.
Use agent-memory-system/key_facts.md for non-sensitive config facts.
When you fix bugs, make decisions, learn key facts, change testing, or complete work, update the relevant agent-memory-system/*.md file with concise, dated entries.
Never store secrets in agent-memory-system/.
```
