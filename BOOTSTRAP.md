# Project Context System

> **Read this file at the start of every conversation.**

## Purpose
This system provides persistent context and consistent workflows for AI agents working on any codebase.

---

## Quick Start

### 1. Read Project Config
```
Read: ./_system_memory/project/config.yaml
```
This shows project stack, paths, and settings.

### 2. Check Current State
```
Read: ./_system_memory/INDEX.md
```
This shows active work, recent changes, and component overview.

### 3. Check Pending Work
```
Read: ./_system_memory/state/todos.md
```
This shows incomplete items, blockers, and pending tasks.

### 4. Check Workspace
```
Read: ./_system_memory/workspace/_notes.md
Browse: ./_system_memory/workspace/
```
User-provided reference files. See `./_system/guides/workspace.md` for details.

### 5. Find Relevant Context
```
Browse: ./_system_memory/context/
```
Structure mirrors the repo.

---

## Core Rules

Full rules: `./_system/rules/core.md`

### Key Principles
1. **Relative paths only** - Use `./path/to/file` from repo root
2. **Auto-scaffold context** - Create context files when touching new code
3. **Update memory** - Keep context files in sync with code changes
4. **No temporary code** - Unless explicitly requested
5. **No dummy data** - Mark incomplete if unavoidable

---

## Directory Structure

```
./_system/                    # Framework (generic, portable)
├── BOOTSTRAP.md              # This file
├── PROGRESS.md               # System version/status
├── CONTRIBUTING.md           # Framework development guide
├── config.template.yaml      # Config template
├── rules/core.md             # Generic rules
├── guides/                   # Usage guides
│   └── workspace.md          # Workspace guide
├── workflows/                # Task workflows
└── templates/                # File templates

./_system_memory/             # Project-specific state
├── INDEX.md                  # Quick lookup
├── project/
│   ├── config.yaml           # Project config
│   └── code_style.md         # Code style rules
├── workspace/                # User-provided files (content only)
│   ├── _notes.md             # User's context notes
│   ├── references/           # User's docs, specs
│   ├── scratch/              # User's temp files
│   └── attachments/          # User's screenshots
├── state/
│   ├── todos.md              # Pending work
│   ├── session.md            # Current session
│   └── decisions.md          # Decision log
├── patterns/
│   ├── errors.md             # Error solutions
│   └── code.md               # Code patterns
└── context/                  # Mirrors repo structure
```

---

## Session Workflow

### Start
1. Read this file
2. Read `./_system_memory/project/config.yaml`
3. Read `./_system_memory/INDEX.md`
4. Read `./_system_memory/state/todos.md`

### During Work
1. Follow rules in `./_system/rules/core.md`
2. Update context files when modifying code
3. Log decisions in `state/decisions.md`

### End
1. Update `INDEX.md` with changes
2. Update `state/todos.md` with incomplete items
3. Ask user about documentation sync
4. Ask user: "Clean up workspace files?" (if workspace was used)

---

## Portability

This `_system/` folder is **framework-only** and can be copied to any repo.

Project-specific content lives in `_system_memory/`:
- `project/config.yaml` - Stack, paths, settings
- `project/code_style.md` - Language-specific rules
- `context/` - Codebase documentation
