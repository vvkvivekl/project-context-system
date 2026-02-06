# Project Context System

> A portable framework for AI agents to maintain context and follow consistent workflows.

---

## ⚠️ This README is for HUMANS

**AI Agents:** Read `BOOTSTRAP.md` instead, not this file.

---

## What is this?

A framework that gives AI coding assistants:
- **Persistent memory** across sessions
- **Consistent workflows** for common tasks
- **Project context** that stays in sync with code

## Quick Start

### Option 1: Copy (Simple)

```bash
# Copy _system folder to your repo
cp -r /path/to/ai-agent-system/_system ./

# Tell AI: "Setup the system" (or /system)
```

### Option 2: Git Submodule (Recommended)

```bash
# Add as submodule
git submodule add https://github.com/vvkvivekl/project-context-system.git _system

# After cloning a project with this submodule
git clone --recurse-submodules <your-repo-url>

# Or if already cloned
git submodule update --init
```

### After Adding

1. Tell your AI agent: **"Setup the system"** (or `/system`)
2. Answer the setup questions
3. Done! Agent will create `_system_memory/` with your project config

---

## Structure

```
_system/                      # This repo (framework)
├── BOOTSTRAP.md              # AI entry point
├── PROGRESS.md               # Version tracking
├── CONTRIBUTING.md           # Framework development
├── config.template.yaml      # Config template
├── rules/                    # Rules for AI to follow
├── guides/                   # Usage guides
├── workflows/                # Task workflows
└── templates/                # File templates

_system_memory/               # Created per-project (not in this repo)
├── project/                  # Project config
├── state/                    # Session state
├── patterns/                 # Learned patterns
├── workspace/                # User reference files
└── context/                  # Code documentation
```

---

## Updating

### If using submodule:
```bash
cd _system
git pull origin main
cd ..
git add _system
git commit -m "Update AI Agent System"
```

### If copied:
Manually copy new files from the source.

---

## Contributing

See `CONTRIBUTING.md` for how to modify the framework itself.

---

## License

MIT
