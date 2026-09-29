# [Project Name] — Agent Team

## How This Works
This project uses an AI agent team. Each agent has a defined role, its own
brief, and persistent memory across sessions.

## Team Structure
- **Team Lead** (`agents/team/brief.md`) — routes work, tracks priorities
- **Researcher** (`agents/researcher/brief.md`) — investigates questions,
  produces findings

## Session Protocol
1. Read the relevant agent's brief
2. Read that agent's `memory.md`
3. Do the work
4. Update `memory.md` with findings and next actions
5. Clear `scratchpad.md`

## Information Flow
- Team lead reads: all agent memory files, shared context
- Researcher reads: own memory, team lead's memory (for assignments),
  shared context
- Each agent writes only to its own directory