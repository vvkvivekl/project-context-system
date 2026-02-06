# Workflow: New Feature

> Steps for implementing a new feature.

---

## Pre-Work

1. **Check INDEX.md** for related components
2. **Read context files** for affected areas
3. **Check todos.md** for related pending items
4. **Identify affected files** and list them

---

## Planning

1. Create brief implementation plan
2. Identify:
   - Files to create
   - Files to modify
   - Dependencies
   - Tests needed
3. Get user approval if significant

---

## Implementation

1. Implement in logical order (dependencies first)
2. After each file change:
   - Update or create context file
   - Test the change works
3. Follow core rules:
   - No temporary code
   - No dummy data
   - Proper error handling

---

## Post-Work

1. Update `INDEX.md` with new components
2. Update `todos.md`:
   - Mark completed items
   - Add any new incomplete items
3. Log decisions in `decisions.md`
4. Add patterns to `patterns/` if reusable
5. Ask user about documentation sync
