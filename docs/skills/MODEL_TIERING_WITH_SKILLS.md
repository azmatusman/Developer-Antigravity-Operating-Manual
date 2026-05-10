# Model Tiering + Skills (Token Reduction)

Use the least powerful model that can do the work reliably.

## Pattern
- Fast model: mechanical edits, small scaffolding, doc updates
- Standard model: multi-file implementation, typical debugging
- Most capable model: architecture decisions, deep debugging, security review

## Skill mapping
- `feature-planning` + `/plan` → most capable model
- `tdd-workflow` + `/tdd` → standard model (fast only if trivial)
- `systematic-debugging` + `/debug` → standard; escalate if stuck
- `security-review` → most capable
- `code-review` → most capable (or strong reviewer)

## Token rule
If a task is mechanical, do not pay for deep reasoning.
