# Contributing to AI Agent System

> Guide for evolving the `_system` framework.

---

## Architecture

```
_system/                      # FRAMEWORK (portable)
├── BOOTSTRAP.md              # Entry point
├── PROGRESS.md               # Version & changelog
├── CONTRIBUTING.md           # This file
├── config.template.yaml      # Config template
├── rules/                    # Generic rules
├── workflows/                # Task workflows
└── templates/                # File templates

_system_memory/               # PROJECT STATE (per-repo)
├── project/                  # Project config
├── state/                    # Runtime state
├── patterns/                 # Learned patterns
└── context/                  # Code documentation
```

---

## Golden Rules

### 1. No Project-Specific Content
```
❌ stack.backend.framework: "FastAPI"
✅ stack.backend.framework: ""  # or example comment
```

### 2. Relative Paths Only
```
❌ C:\Users\project\file.py
✅ ./path/to/file.ext
```

### 3. Examples Are Generic
```
❌ "See ./backend/app/worker.py"
✅ "See ./path/to/your/file.ext"
```

---

## Adding New Components

### New Rule
1. Create `./_system/rules/your_rule.md`
2. Reference in `BOOTSTRAP.md` if core
3. Update `PROGRESS.md` changelog

### New Workflow
1. Create `./_system/workflows/your_workflow.md`
2. Follow existing workflow structure
3. Update `PROGRESS.md` changelog

### New Template
1. Create `./_system/templates/your_template.md`
2. Keep placeholders generic
3. Update `PROGRESS.md` changelog

---

## Version Bumping

In `PROGRESS.md`:

| Change Type | Version Bump |
|-------------|--------------|
| Bug fix | Patch (1.0.x) |
| New feature | Minor (1.x.0) |
| Breaking change | Major (x.0.0) |

---

## Testing Portability

Before committing changes:
1. Would this work in a fresh repo?
2. Are there any hardcoded paths?
3. Does `BOOTSTRAP.md` still make sense?
