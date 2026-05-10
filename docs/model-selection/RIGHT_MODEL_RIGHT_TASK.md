# Right Model for the Right Task (Token Reduction)

## Core principle

> Use the **least powerful model** that can do the task **reliably**.

This reduces tokens while preserving quality.

---

## 3-tier model strategy

### Tier 1 — Fast model (cheap)
Use for:
- mechanical edits (rename, formatting)
- simple scaffolding
- documentation updates
- single-file changes with clear intent

### Tier 2 — Standard model (balanced)
Use for:
- multi-file implementation
- typical debugging
- integration work
- moderate refactors

### Tier 3 — Most capable model (expensive)
Use for:
- architecture decisions
- deep debugging with repeated failures
- security review
- complex refactors
- high-risk changes

---

## Practical mapping (workflow → model)

- `/plan` → Tier 3
- `/tdd` → Tier 2 (Tier 1 if truly trivial)
- `/debug` → Tier 2 (escalate to Tier 3 after repeated failures)
- `/review` → Tier 3
- `/document` → Tier 1
- `/optimize` → Tier 2

---

## Token reduction checklist
- Did you avoid rereading unchanged files?
- Did you batch similar edits?
- Did you stop when done?
- Did you use Graphify for architecture questions?
- Did you consult Context7 for unknown APIs?
