# Workflow: System Update

> AI agent workflow for updating `_system` to a newer version.

---

## When to Use

When:
- User says "Update the system"
- User pulled new `_system` changes (submodule update)
- Version mismatch detected between `_system/VERSION` and `_system_memory/VERSION.md`

---

## Update Steps

### Step 1: Check Versions

Read current installed version:
```
./_system_memory/VERSION.md
```

Read latest system version:
```
./_system/VERSION
```

If versions match, no update needed.

### Step 2: Find Applicable Migrations

Read `./_system/MIGRATIONS.md`

Find all migrations from installed version to latest version.

Example: If installed is `1.1.0` and latest is `1.3.0`:
- Apply `1.1.0 → 1.2.0`
- Apply `1.2.0 → 1.3.0`

### Step 3: Apply Migrations

For each migration (in order):
1. Read the "Actions for AI agent" section
2. Execute each action
3. Verify action completed

### Step 4: Update VERSION.md

Update `./_system_memory/VERSION.md`:
```markdown
# System Version

version: "[new version]"
installed: "[original install date]"
updated: "[today's date]"
```

### Step 5: Report to User

Tell user:
```
✅ System updated from [old] to [new]

Changes applied:
- [list of actions taken]
```

---

## If Migration Fails

1. Tell user what failed
2. Do not update VERSION.md
3. Ask user how to proceed

---

## Version Mismatch Detection

At session start, optionally check:
1. Read `_system/VERSION`
2. Read `_system_memory/VERSION.md`
3. If different, ask: "System update available. Run update?"
