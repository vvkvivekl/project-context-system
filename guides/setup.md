# Setup Guide

> How to initialize the AI Agent System in a new repository.

---

## Quick Start

```
1. Copy _system/ folder to your repo root
2. Tell AI agent: "Setup the system"
3. Answer the agent's questions about your project
4. Done! Agent will create all _system_memory files
```

---

## What the AI Agent Does

When you say "Setup the system", the agent follows `./_system/workflows/setup.md`:

1. Creates `_system_memory/` directory structure
2. Asks about your project (name, stack, paths)
3. Creates `config.yaml` with your answers
4. Creates `code_style.md` based on your stack
5. Creates all state and pattern files
6. Creates `INDEX.md`
7. Verifies setup is complete

### Step 2: Create Memory Structure

Create the `_system_memory/` directory structure:

```
_system_memory/
├── project/
├── workspace/
│   ├── references/
│   ├── scratch/
│   └── attachments/
├── state/
├── patterns/
└── context/
```

### Step 3: Configure Project

1. Copy config template:
   ```bash
   cp _system/config.template.yaml _system_memory/project/config.yaml
   ```

2. Edit `_system_memory/project/config.yaml`:
   - Set project name and description
   - Define your tech stack
   - Set key paths

### Step 4: Create Code Style

Create `./_system_memory/project/code_style.md`:
- Define language conventions
- Add project patterns
- Document naming rules

### Step 5: Initialize State Files

Create initial state files:

**`_system_memory/state/todos.md`:**
```markdown
# TODOs

## Pending
- [ ] Initial setup

## In Progress
(none)

## Blocked
(none)
```

**`_system_memory/state/session.md`:**
```markdown
# Session State

## Current Session
- Started: [date]
- Focus: Initial setup
```

**`_system_memory/state/decisions.md`:**
```markdown
# Decisions Log

(No decisions yet)
```

### Step 6: Initialize Patterns

**`_system_memory/patterns/errors.md`:**
```markdown
# Error Patterns

(No patterns yet)
```

**`_system_memory/patterns/code.md`:**
```markdown
# Code Patterns

(No patterns yet)
```

### Step 7: Create INDEX

Create `./_system_memory/INDEX.md`:
```markdown
# Project Index

## Overview
[Brief project description]

## Key Components
| Component | Path | Status |
|-----------|------|--------|
| - | - | - |

## Recent Changes
| Date | Change |
|------|--------|
| [today] | Initial setup |
```

### Step 8: Create Workspace Notes

Create `./_system_memory/workspace/_notes.md`:
```markdown
# Workspace Notes

(No active task)
```

---

## Verification

After setup, verify:
- [ ] `_system/BOOTSTRAP.md` exists
- [ ] `_system_memory/project/config.yaml` is configured
- [ ] `_system_memory/INDEX.md` exists
- [ ] `_system_memory/state/` has todos, session, decisions
- [ ] `_system_memory/patterns/` has errors, code
- [ ] `_system_memory/workspace/_notes.md` exists

---

## First Session

Tell the AI agent:
```
Read ./_system/BOOTSTRAP.md and follow the workflow.
```

The agent will:
1. Read your project config
2. Check INDEX for context
3. Check todos for pending work
4. Start following the system
