# System Migrations

> Instructions for AI agents to update `_system_memory` when `_system` is upgraded.

---

## How to Use

1. Check `./_system_memory/VERSION.md` for installed version
2. Check `./_system/VERSION` for current `_system` version
3. If versions differ, apply migrations in order

---

## Migration Format

Each migration section describes:
- **From**: Previous version
- **To**: New version
- **Changes**: What changed in `_system`
- **Actions**: What AI agent must do to update `_system_memory`

---

## Migrations

### 1.4.0 → 1.5.0

**Changes in _system:**
- Added `workflows/post_task.md` for post-task alignment verification
- Renamed to "Project Context System"

**Actions for AI agent:**
1. No structural changes to `_system_memory` required
2. Update `./_system_memory/VERSION.md` to `1.5.0`

---

### 1.3.0 → 1.4.0

**Changes in _system:**
- Added `VERSION` file
- Added `MIGRATIONS.md`
- Added `workflows/update.md`

**Actions for AI agent:**
1. Create `./_system_memory/VERSION.md` with current version
2. Update `./_system_memory/VERSION.md` to `1.4.0`

---

### 1.2.0 → 1.3.0

**Changes in _system:**
- Added `guides/setup.md`
- Added `workflows/setup.md`
- Added `guides/agent_entry_points.md`

**Actions for AI agent:**
1. Create `AGENTS.md` at repo root (if not exists)
2. Create `CLAUDE.md` at repo root (if not exists)
3. Update `./_system_memory/VERSION.md` to `1.3.0`

---

### 1.1.0 → 1.2.0

**Changes in _system:**
- Added `guides/workspace.md`

**Actions for AI agent:**
1. Create `./_system_memory/workspace/` directory (if not exists)
2. Create `./_system_memory/workspace/_notes.md` (if not exists)
3. Update `./_system_memory/VERSION.md` to `1.2.0`

---

### 1.0.0 → 1.1.0

**Changes in _system:**
- Added `CONTRIBUTING.md`
- Added `workflows/system_development.md`
- Made system fully portable

**Actions for AI agent:**
1. Move any project-specific content from `_system/` to `_system_memory/project/`
2. Update `./_system_memory/VERSION.md` to `1.1.0`

---

## After Migration

Update `./_system_memory/VERSION.md`:
```markdown
version: "[new version]"
installed: "[original install date]"
updated: "[today's date]"
```
