# Setup

This memory system is designed to work in two modes:

- **Agent Skill (recommended when supported):** Install this folder as an Agent Skill so compatible agents can load instructions on demand.
- **Drop-in (fallback if skills are not supported):** Copy `agent-memory-system/` into your repository and commit it.

When installing a skill or adding agent instructions, follow your agent/tool's official documentation. Tool UIs, file locations, and supported formats change over time.

## Why "Agent Skill" Depends on Tooling

The core of this project is the on-disk `agent-memory-system/` folder. Any agent that can read and edit files can use it, even if it does not support the Agent Skills standard.

Installing this as an Agent Skill is an instruction-delivery mechanism that only works if your tool supports Agent Skills:

- Not all tools support Agent Skills (or they support a different mechanism for agent instructions).
- A skill install does not replace the need for repository access. The agent still needs to read and update `agent-memory-system/*.md` in your repo.
- Drop-in is the most portable setup and requires the fewest tool-specific steps.

## Agent Skill Install (Recommended When Supported)

Agent Skills are folders containing a `SKILL.md` plus any resources. To install this as a skill, place the folder that contains `SKILL.md` into your agent's "skills" directory.

### TRAE

- A common convention is copying this folder to: `.trae/skills/agent-memory-system/`
- Ensure your repo has `agent-memory-system/` at its root.
- Verify the correct location/mechanism in TRAE's official docs for your version and environment.

### Claude Code

- Follow Claude Code's official docs for skill installation (locations and enablement vary).
- If skills are not available, use the Drop-In install and add the snippet below to your agent instruction mechanism (for example, `CLAUDE.md` if your setup uses it).

### GitHub Copilot

- Use Drop-In install.
- Add the snippet below to Copilot's instruction mechanism (some setups use `.github/copilot-instructions.md`, but verify in official docs).

### Replit

- Use Drop-In install.
- Add the snippet below to the project's agent instruction mechanism (some setups use `replit.md`, but verify in official docs).

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
