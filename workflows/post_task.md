# Post-Task Checklist

> Run through this after completing any task.

---

## Quick Checklist

After completing a task, verify:

### 1. Context Files
- [ ] Updated context files for modified code?
- [ ] Created context files for new code?
- [ ] Marked stale context files?

### 2. State Files
- [ ] Updated `state/todos.md`?
  - Mark completed items `[x]`
  - Add new incomplete items `[ ]`
  - Update blockers if any
- [ ] Updated `state/session.md` with current focus?
- [ ] Logged decisions in `state/decisions.md`?

### 3. INDEX.md
- [ ] Updated recent changes table?
- [ ] Added new components?
- [ ] Updated context status count?

### 4. Patterns (if applicable)
- [ ] Added error patterns to `patterns/errors.md`?
- [ ] Added code patterns to `patterns/code.md`?

### 5. Workspace
- [ ] Files in workspace still relevant?
- [ ] Ask user: "Clean up workspace files?"

---

## Session End Prompts

Ask user before ending:
1. "Any incomplete items to track?"
2. "Should I update context documentation?"
3. "Any decisions to log?"
4. "Clean up workspace files?" (if used)

---

## Quick Sync Command

If user says "sync" or "align":
1. Read `INDEX.md`
2. Check for stale context files
3. Review `state/todos.md` for accuracy
4. Report any misalignments
