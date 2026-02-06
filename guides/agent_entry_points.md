# AI Agent Entry Point Template

> Copy these files to your repo root to help AI agents discover `_system`.

---

## Files to Create

### 1. AGENTS.md (Generic)

Most AI agents look for `AGENTS.md` at repo root:

```markdown
# AI Agent Instructions

Read `./_system/BOOTSTRAP.md` and follow the workflow.

If `./_system_memory/` doesn't exist, run setup first.
```

### 2. CLAUDE.md (Claude-specific)

Claude looks for `CLAUDE.md`:

```markdown
# Claude Instructions

Read `./_system/BOOTSTRAP.md` and follow the AI Agent System workflow.
```

### 3. .cursorrules (Cursor IDE)

Cursor IDE looks for `.cursorrules`:

```
Read ./_system/BOOTSTRAP.md and follow the AI Agent System.
```

### 4. .github/copilot-instructions.md (GitHub Copilot)

```markdown
Read `./_system/BOOTSTRAP.md` for project-specific AI instructions.
```

---

## Setup Workflow Update

The AI setup workflow should create these files automatically.
See `./_system/workflows/setup.md` Step 8.
