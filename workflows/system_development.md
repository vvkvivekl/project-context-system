# Workflow: System Development

> Steps for modifying the `_system` framework itself.

---

## When to Use

Use this workflow when:
- Adding new rules or workflows
- Modifying framework behavior
- Fixing issues in `_system` files
- Making the system more portable

---

## Pre-Work

1. **Read `./_system/PROGRESS.md`** - Check current version and status
2. **Identify scope** - Is this a new feature, bug fix, or enhancement?
3. **Check portability** - Will this work in ANY repo?

---

## Key Principles

### Keep It Generic
- No project-specific content in `_system/`
- Use placeholders like `./path/to/file.ext`
- Project-specific goes in `_system_memory/`

### Version Tracking
- Update version in `PROGRESS.md` for significant changes
- Log changes in PROGRESS.md changelog

### Backward Compatibility
- Don't break existing `_system_memory/` structures
- Add new features as optional

---

## Implementation

1. **Plan the change**
   - What files to modify?
   - Does it affect `_system_memory/` structure?
   
2. **Make changes**
   - Update `_system/` files
   - Keep examples generic
   
3. **Test portability**
   - Would this work if copied to a fresh repo?
   - Are there any hardcoded paths?

---

## Post-Work

1. **Update PROGRESS.md**
   - Bump version if significant
   - Add to changelog
   
2. **Update BOOTSTRAP.md** if behavior changed

3. **Document in this workflow** if new patterns discovered

---

## Examples

### Example 1: Making System Generic (2026-02-06)

**What was done:**
1. Moved `config.yaml` → `config.template.yaml`
2. Created `./_system_memory/project/config.yaml` for actual config
3. Removed project examples from `rules/core.md`
4. Updated `PROGRESS.md` to track only system, not project

**Pattern:** Move project-specific content to `_system_memory/`

---

### Example 2: Adding Workspace Feature (2026-02-06)

**What was done:**
1. Created `./_system/guides/workspace.md` - AI instructions
2. Created `./_system_memory/workspace/` - User content
3. Added `_notes.md` template for user

**Pattern:** Instructions in `_system/`, content in `_system_memory/`

**Wrong approach (fixed):**
```
❌ _system_memory/workspace/README.md  ← AI instructions in wrong place
```

**Correct approach:**
```
✅ _system/guides/workspace.md         ← AI instructions (generic)
✅ _system_memory/workspace/_notes.md  ← User content only
```

---

## Common Patterns

### Pattern: Adding a New Feature with User Content

1. **Instructions** → `./_system/guides/feature.md`
2. **User content** → `./_system_memory/feature/`
3. **Update BOOTSTRAP.md** → Add to workflow
4. **Update PROGRESS.md** → Add to components

### Pattern: Adding a New Workflow

1. **Workflow file** → `./_system/workflows/name.md`
2. **Update PROGRESS.md** → Add to workflows table
3. **Reference in BOOTSTRAP.md** if core workflow

### Pattern: Adding a New Rule

1. **Rule file** → `./_system/rules/name.md`
2. **Reference in `rules/core.md`** or BOOTSTRAP.md
3. **Update PROGRESS.md** → Add to components

