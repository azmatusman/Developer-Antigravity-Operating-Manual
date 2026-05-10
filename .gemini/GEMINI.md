# Antigravity-Specific Instructions

## Agent Behavior

- Use Fast Mode for simple tasks (single-file edits, docs, style fixes)
- Use Planning Mode only for multi-file features or architectural changes
- Check Knowledge Items before researching — prior context may already exist
- When creating artifacts, keep them focused — one artifact per concern
- Save important architectural decisions as Knowledge Items for future sessions
- Never auto-run destructive commands (delete, drop, reset) without explicit approval
- When asked to implement a feature, check if a plan exists first — suggest /plan if not
- When modifying existing code, preserve the existing style and patterns
- If a task is ambiguous, ask ONE clarifying question — do not guess
- When multiple approaches exist, briefly state the options and recommend one with reasoning
- Do not refactor code that isn't related to the current task
- Do not add dependencies without stating why and getting approval
- When creating files, follow the existing project naming conventions
- If you encounter a bug while working on something else, note it but don't fix it (stay focused)
- After completing a task, run the test suite before reporting done
- Use Sequential Thinking explicitly for:
  - proposing 2–3 architectures with tradeoffs during planning
  - hypothesis tracking during debugging (one hypothesis, one change at a time)

## Token Conservation

- Prefer surgical edits (find-and-replace, line-range edits) over full file rewrites
- Do not re-read files that haven't changed since the last read
- Skip opening pleasantries, closing summaries, and motivational commentary — be direct
- When the task is complete, stop immediately — do not suggest next steps unless asked
- Batch similar changes across files instead of narrating each one
- If multiple files need the same change, batch them — don't narrate each one
- Do not list what you're "about to do" — just do it
- Do not repeat back the user's instructions before executing them
- When reading large files (>200 lines), read only the relevant section or function
- Prefer editing existing files over creating new ones when appropriate
- Do not generate example usage code unless explicitly requested

## Workflow Integration

- Respect the skills in .agents/skills/ — invoke them when the task matches
- Follow the workflows in .agents/workflows/ — they define the process
- Follow the rules in .agent/rules/ — they are always active constraints
- Skills define HOW to do something (invoked on demand)
- Rules define what to ALWAYS or NEVER do (passive, always active)
- Workflows define the SEQUENCE of steps for a task type
- Brainstorming is for clarifying problem space only and must occur before /plan, never after architecture is approved

## Code Quality Rules

- Use clear, descriptive names for all variables, functions, and files
- Functions should do ONE thing and do it well
- Keep functions under 30 lines where possible — extract if longer
- Maximum nesting depth: 3 levels — use early returns or guard clauses
- No magic numbers or strings — use named constants
- No commented-out code — delete it (version control remembers)
- No console.log / print / debug statements in committed code
- Every function that can fail must handle errors explicitly
- Prefer composition over inheritance
- DRY: if code is duplicated 3+ times, extract to a shared utility
- Code should be self-documenting — comments explain WHY, not WHAT

## Documentation Standards

- Every new module/file must have a brief header comment explaining its purpose
- Public APIs must be documented with: description, parameters, return value, errors
- Complex algorithms must have a comment explaining the approach
- Configuration files must have comments explaining each setting
- README must be updated when new setup steps or dependencies are added
- Breaking changes must be documented in a changelog or migration guide
- Do not write redundant documentation (e.g., "this function adds two numbers" for an add function)
- Documentation must be updated when code behavior changes — stale docs are worse than no docs

## Security Guardrails

- Never hardcode secrets, API keys, passwords, or tokens in source code
- Always use parameterized queries — never concatenate user input into queries
- Validate and sanitize ALL external input (user input, API responses, file contents)
- Never log sensitive data (passwords, tokens, PII, financial data)
- Error messages must not expose internal system details (stack traces, file paths, versions)
- Always check authentication before processing protected operations
- Always check authorization (role/permission) for sensitive operations
- Set appropriate timeouts on all external calls (API, database, file I/O)
- Use environment variables or secret managers for configuration — never source code
- When handling files from users, validate type, size, and content — not just extension

## Git Discipline Rules

- Commit after each completed, tested unit of work — not after hours of changes
- Commit messages must be descriptive: "[scope]: [what changed and why]"
- Never commit failing tests
- Never commit debug/log statements
- Never commit secrets or credentials (even temporarily)
- Each commit should be atomic — one logical change per commit
- If a refactoring is needed, commit it separately from feature changes
- Before starting a new feature, ensure the working tree is clean

## Memory Discipline

- Save Knowledge Items only for durable decisions, constraints, or non-obvious lessons
- Use SUMMARY.md for session-to-session progress and handoff
- Do not misuse Knowledge Items as activity logs
