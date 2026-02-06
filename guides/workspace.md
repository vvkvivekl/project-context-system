# Workspace Guide

> Instructions for using the workspace directory.

---

## Location

User workspace is at: `./_system_memory/workspace/`

---

## Purpose

Users can drop files here for AI agent to use as context:
- Design mockups
- API specs
- Reference implementations
- Screenshots
- Requirements documents
- Any other reference material

---

## Structure

```
_system_memory/workspace/
├── _notes.md           # User's context notes (optional)
├── references/         # Docs, specs, mockups
├── scratch/            # Temporary files
└── attachments/        # Screenshots, diagrams
```

---

## AI Agent Behavior

### On Session Start
1. Check if `./_system_memory/workspace/_notes.md` exists
2. If exists, read it for context
3. Browse workspace for reference files

### On Session End
1. If workspace was used, ask: "Clean up workspace files?"
2. If user says yes, help remove files
3. Clear `_notes.md` if task is complete

---

## User Instructions

Tell users:
1. **Copy files** to `_system_memory/workspace/` 
2. **Add notes** in `_notes.md` explaining what files are for
3. **Clean up** when task is complete (or AI will ask)
