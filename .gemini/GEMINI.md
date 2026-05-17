# Antigravity-Specific Instructions



## Agent Behavior
- Use Fast Mode for simple tasks (single-file edits, docs, style fixes)
- Use Planning Mode only for multi-file features or architectural changes
- Check Knowledge Items before researching — prior context may already exist
- When creating artifacts, keep them focused — one artifact per concern
- Save important architectural decisions as Knowledge Items for future sessions
- Never auto-run destructive commands (delete, drop, reset) without explicit approval
- When asked to implement a feature, check if a plan exists first — suggest `/plan` if not
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

## No Code in Discovery Phases (Always-Active Rule)

**Always active.** It cannot be overridden by Fast Mode, skills, workflows, or momentum.

**Code generation is FORBIDDEN during:** `/brainstorming`, `/plan`, `/review`, `/document`, `/onboard`

**Code generation is PERMITTED during:** `/tdd`, `/debug`, `/hotfix`, `/refactor`, `/optimize`, `/sprint` (execution after approval), `executing-plans`, `subagent-driven-development`

**What counts as “code” (forbidden in discovery):**
- Implementation code, “example” code, sketches
- Pseudocode (unless explicitly requested)
- File creation commands, shell commands that modify source
- Test creation/execution, migrations, config creation

**Transition protocol:**
- “Looks good” / “That’s correct” → approves current artifact only. **Do NOT start coding.**
- `/plan` → switch to planning (still no code)
- `/tdd` OR “Start implementing” OR `/execute` OR “Execute the plan” → code allowed (implementation phase)
- “Go ahead” → ambiguous → ask: “Proceed with `/tdd` or `executing-plans`?”

**If you feel the urge to write code during brainstorming/planning → STOP.**

### Model Selection (Token-Optimized)

Use the lowest-cost model that can reliably complete the task.

- **`/brainstorming`** → Pro (Low): best comprehension, minimal “thinking” waste
- **`/plan`** → Pro (High): pay here to reduce rework later
- **`/tdd`** → Flash by default; escalate to Pro (Low) if stuck; Pro (High) only for complex integration or repeated failures
- **`/review`** → Pro (Low): quality gate, catch subtle issues
- **Verification / logs / summaries** → Flash-Lite: cheapest for non-reasoning tasks

Escalation ladder:
1) Flash / Flash-Lite → 2) Pro (Low) → 3) Pro (High) → de-escalate immediately after

### Token Conservation
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

### Workflow Integration
- Respect skills (project `.agents/skills/` or global `~/.gemini/antigravity/skills/`) — invoke when relevant
- Follow workflows (project `.agents/workflows/` or global `~/.gemini/antigravity/global_workflows/`) — they define the process
- Workspace rules belong in `.agents/rules/` (project root). Global rules live in this file (`~/.gemini/GEMINI.md`).
- Skills define **HOW** to do something (invoked on demand)
- Rules define what to **ALWAYS** or **NEVER** do (always active)
- Workflows define the **SEQUENCE** of steps for a task type
- Brainstorming clarifies problem space ONLY — NO code, NO architecture proposals, NO file structures
- Planning produces plans/checklists/decisions — NO implementation code, NO source file creation, NO test execution
- Code generation is ONLY permitted in: `/tdd`, `/hotfix`, `/refactor`, `/debug`, `/optimize`, or when explicitly executing an approved plan

### Code Quality Rules
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
- Do not write redundant documentation
- Documentation must be updated when code behavior changes — stale docs are worse than no docs

## Security Guardrails

- Never hardcode secrets, API keys, passwords, or tokens in source code
- Always use parameterized queries — never concatenate user input into queries
- Validate and sanitize ALL external input
- Never log sensitive data
- Error messages must not expose internal system details
- Always check authentication and authorization for sensitive operations
- Set appropriate timeouts on external calls
- Use environment variables or secret managers for configuration
- When handling files from users, validate type, size, and content — not just extension

## Git Discipline Rules

- Commit after each completed, tested unit of work — not after hours of changes
- Commit messages must be descriptive: "[scope]: [what changed and why]"
- Never commit failing tests
- Never commit debug/log statements
- Never commit secrets or credentials
- Each commit should be atomic — one logical change per commit
- If a refactoring is needed, commit it separately from feature changes
- Before starting a new feature, ensure the working tree is clean

## Memory Discipline

- Save Knowledge Items only for durable decisions, constraints, or non-obvious lessons
- Use SUMMARY.md for session-to-session progress and handoff
- Do not misuse Knowledge Items as activity logs
