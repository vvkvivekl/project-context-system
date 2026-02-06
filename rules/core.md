# Core Rules

> Generic best-practice rules for AI agents. These apply to any codebase.

---

## 1. Path Conventions

### Always Use Relative Paths
All paths should be relative to repo root using `./` notation.

```
✅ ./src/module.ts
✅ ./_system_memory/context/src/module.md
❌ C:\Users\...\src\module.ts
❌ /home/user/project/src/module.ts
```

### Reference Patterns
- Code files: `./path/to/file.ext`
- Context files: `./_system_memory/context/path/to/file.md`
- System rules: `./_system/rules/...`
- Memory state: `./_system_memory/state/...`

---

## 2. Memory Management

### Auto-Scaffold Context
When editing a code file for the first time:
1. Check if context file exists at `./_system_memory/context/{path}.md`
2. If not, create from `./_system/templates/context_file.md`
3. Add entry to `./_system_memory/INDEX.md`

### Update on Change
After modifying code:
1. Update the corresponding context file
2. Update `last_updated` in INDEX.md
3. Note what changed and why

### Staleness Detection
- ✅ **Current**: Context updated after last code change
- ⚠️ **Stale**: Code changed since last context update
- ❌ **Missing**: No context file exists

---

## 3. Quality Standards

### No Temporary Code
- Don't create quick fixes intended to be replaced
- If user explicitly requests temporary solution, mark in `todos.md`
- All code should be production-ready

### No Dummy Data
- Never add placeholder/fake data
- If data is needed:
  1. Ask user for real data source
  2. Use environment variables for configuration
  3. If unavoidable, mark as **incomplete** in `todos.md`

### Error Handling
- All async operations need try/catch or equivalent
- Log errors with context
- Provide user-friendly error messages
- Never silently swallow exceptions

### Testing
- Test changes before marking complete
- Document how to verify in context files
- Add to patterns if reusable test approach

---

## 4. Communication

### Progress Updates
- Summarize after each major step
- Explain non-obvious decisions
- Acknowledge mistakes and backtracking

### Session End Prompts
Ask user before ending:
1. "Any incomplete items to track?"
2. "Should I update context documentation?"
3. "Any decisions to log?"
4. "Clean up workspace files?" (if workspace was used)

### Blocking Issues
- If blocked on user input, add to `state/todos.md` under Blockers
- Clearly state what information is needed
- Suggest alternatives if possible

---

## 5. Code Style

> Language-specific style rules should be defined in:
> `./_system_memory/project/code_style.md`

Follow these generic principles:
- Use explicit types where the language supports them
- Follow existing patterns in the codebase
- Add documentation for public APIs
- Prefer descriptive names over comments

---

## 6. Decision Logging

For significant decisions, log in `state/decisions.md`:

```markdown
### [Date]: [Brief Title]
- **Context**: Why this decision was needed
- **Decision**: What was decided
- **Alternatives**: Other options considered
- **Rationale**: Why this option was chosen
- **Trade-offs**: Known downsides
```

---

## 7. Pattern Library

When discovering reusable solutions:
1. Add to `patterns/errors.md` for error solutions
2. Add to `patterns/code.md` for code patterns
3. Include:
   - Problem description
   - Solution
   - Example
   - Files where applicable
