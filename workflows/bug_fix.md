# Workflow: Bug Fix

> Steps for fixing bugs.

---

## Investigation

1. Reproduce the issue
2. Check `patterns/errors.md` for known solutions
3. Read context files for affected components
4. Identify root cause

---

## Fix

1. Implement fix following core rules
2. Update context file with:
   - What was wrong
   - How it was fixed
3. Test the fix works

---

## Post-Fix

1. Add to `patterns/errors.md` if reusable solution
2. Update `todos.md` if resolves pending item
3. Log decision if non-obvious fix
