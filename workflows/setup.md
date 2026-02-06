# Workflow: System Setup

> AI agent workflow for initializing `_system_memory` in a new repo.

---

## When to Use

When user says:
- "Setup the system"
- "Initialize the AI agent system"
- "Setup _system_memory"
- Or similar requests after copying `_system/` to a repo

---

## Prerequisites

User must have:
1. Copied `_system/` folder to their repo root
2. `_system/BOOTSTRAP.md` exists

---

## Setup Steps

### Step 1: Create Directory Structure

Create these directories:
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

### Step 2: Create Project Config

Copy `./_system/config.template.yaml` to `./_system_memory/project/config.yaml`

Ask user:
- "What is the project name?"
- "Brief description?"
- "What tech stack? (language, framework)"
- "Key paths? (src, tests, etc.)"

Fill in the config with their answers.

### Step 3: Create Code Style

Create `./_system_memory/project/code_style.md`

Ask user:
- "What language(s) does this project use?"
- "Any specific naming conventions?"
- "Any patterns to follow?"

Create a basic code style guide based on answers.

### Step 4: Create State Files

Create `./_system_memory/state/todos.md`:
```markdown
# TODOs

## Pending
- [ ] Create initial context files

## In Progress
(none)

## Blocked
(none)
```

Create `./_system_memory/state/session.md`:
```markdown
# Session State

## Current Session
- Started: [current date]
- Focus: Initial setup complete
```

Create `./_system_memory/state/decisions.md`:
```markdown
# Decisions Log

## [today]: System Setup
**Decision:** Initialized AI Agent System
**Rationale:** To establish consistent workflows and context management
```

### Step 5: Create Pattern Files

Create `./_system_memory/patterns/errors.md`:
```markdown
# Error Patterns

> Common errors and solutions.

(Add patterns as errors are encountered)
```

Create `./_system_memory/patterns/code.md`:
```markdown
# Code Patterns

> Established code patterns for this project.

(Add patterns as they are established)
```

### Step 6: Create INDEX

Create `./_system_memory/INDEX.md`:
```markdown
# Project Index

## Overview
[Project description from config]

## Key Components
| Component | Path | Status |
|-----------|------|--------|
| (to be populated) | - | - |

## Recent Changes
| Date | Change |
|------|--------|
| [today] | Initial system setup |

## Context Status
0 files indexed
```

### Step 7: Create Workspace Notes

Create `./_system_memory/workspace/_notes.md`:
```markdown
# Workspace Notes

(No active task)
```

### Step 8: Create .agent Workflow Reference

Create `./.agent/workflows/system.md`:
```markdown
---
description: Initialize and follow the AI Agent System rules
---

# AI Agent System

Read `./_system/BOOTSTRAP.md` and follow the workflow.

## If _system_memory doesn't exist
Follow `./_system/workflows/setup.md`

## Every Session
1. Read `./_system_memory/project/config.yaml`
2. Read `./_system_memory/INDEX.md`
3. Read `./_system_memory/state/todos.md`
4. Check `./_system_memory/workspace/_notes.md`
```

This allows users to type `/system` to invoke the AI Agent System.

---

## Verification

After setup, verify all files exist:
- [ ] `_system_memory/project/config.yaml`
- [ ] `_system_memory/project/code_style.md`
- [ ] `_system_memory/state/todos.md`
- [ ] `_system_memory/state/session.md`
- [ ] `_system_memory/state/decisions.md`
- [ ] `_system_memory/patterns/errors.md`
- [ ] `_system_memory/patterns/code.md`
- [ ] `_system_memory/INDEX.md`
- [ ] `_system_memory/workspace/_notes.md`
- [ ] `.agent/workflows/system.md`

---

## Post-Setup

Tell user:
```
✅ System setup complete!

Next steps:
1. Review _system_memory/project/config.yaml
2. Review _system_memory/project/code_style.md
3. Start using the system - I'll follow BOOTSTRAP.md
```

---

## Quick Setup (Minimal Questions)

If user wants quick setup:
1. Create all directories
2. Create minimal config with project name only
3. Create all placeholder files
4. Ask user to fill in details later
