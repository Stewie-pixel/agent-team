# Agent Team Template

A small, file-based setup for giving AI agents project context, defined roles,
and persistent notes between sessions. Copy it into each project you want an
AI team to work on, then fill in the project-specific information before
giving the AI a task.

## What Is Included

- `CLAUDE.md` describes the team's session protocol and is an instruction entry
  point for Claude Code.
- `shared/context.md` records what the project is, its current state,
  architecture, and active problems.
- `team/brief.md` defines the team lead's role and how it coordinates work.
- `team/memory.md` tracks priorities, agent status, decisions, and next steps.
- `team/scratchpad.md` is temporary workspace for the team lead.
- `researcher/brief.md` defines how the researcher investigates questions and
  reports findings.
- `researcher/memory.md` tracks active research threads and conclusions.

The team lead coordinates and routes work; the researcher investigates assigned
questions. The briefs intentionally distinguish research and decision-making
from implementation. Adapt those boundaries to suit your project.

## Set Up For A Project

Repeat these steps for every project. Keep the files in that project's
repository so the AI can read them alongside the code.

1. Copy this template's `agent/` directory into the project root and name the
   copy `agents/`. The briefs refer to `agents/...` paths, so keep that name
   unless you also update those references.
2. Copy `CLAUDE.md` from the template to the project root. For Claude Code, it
   serves as the project's instruction file. With another AI tool, add an
   equivalent project instruction or use the first-session prompt below.
3. Replace every bracketed placeholder in `agents/shared/context.md`,
   `agents/team/brief.md`, `agents/team/memory.md`, and
   `agents/researcher/brief.md`. Remove prompts that do not apply.
4. In `agents/shared/context.md`, describe the project in concrete terms:
   purpose and users, maturity, stack, key constraints, a short architecture
   overview, and the problems that matter now. Link to existing project docs
   instead of duplicating them.
5. In `agents/team/brief.md` and `agents/researcher/brief.md`, replace the
   project name and adjust responsibilities, permissions, and reporting
   expectations to match the work you want each role to do.
6. Set the first priorities and research assignment in
   `agents/team/memory.md`. Clear or replace starter notes that no longer fit.
7. Add or remove roles as needed. For each role, create a brief and a
   `memory.md`, then update the team lead's routing instructions and memory
   protocol so the new role is included.
8. Check that the AI can read the project instructions and files. Keep secrets,
   credentials, and sensitive personal data out of context and memory files.

## Start The First Session

Before assigning work, ask the AI to load the team instructions and report any
missing setup details. For example:

```text
Before doing any task, read CLAUDE.md and the files under agents/ that define
the relevant roles and project context. Start with agents/shared/context.md,
then read agents/team/brief.md and agents/team/memory.md, plus each specialist's
brief and memory. Follow the session and memory protocols. Tell me which
placeholders or project details are still missing, and summarize the current
priorities and the agent roles available. Do not start implementation yet.
```

After filling any gaps, give the AI a specific task. State the desired outcome,
relevant constraints, and how you will know the work is complete. Direct
research through the team lead when it needs coordination; assign focused
investigations to the researcher.

## Use It Each Session

At the start of a session, the AI should read the applicable role brief and its
memory, shared context, and any assignment or relevant team memory. At the end,
it should update its own `memory.md` with durable findings and next actions,
update team priorities when appropriate, and clear the relevant scratchpad.
Memory is a concise handoff between sessions, not a transcript; keep detailed
research in a separate topic file when it needs to be retained.

Review memory changes and important decisions. The AI team supports your work;
you remain responsible for approving decisions and actions with real-world
impact.