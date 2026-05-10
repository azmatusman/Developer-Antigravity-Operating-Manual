# Supporting & Meta Workflows *(Not Primary Entry Points)*

This folder contains **supporting / meta workflows** that are intentionally  
**NOT** part of the everyday development loop.

These workflows exist to:

- explicitly activate a skill,
- bootstrap or verify environment behavior,
- support skill authoring and validation,
- or enable controlled “meta” operations.

They should be used **only when intentionally selected**, not by default.

---

## Why these workflows live in `internal/`

The workflows in this folder are:

- highly prescriptive,
- frequently say “MUST” / “always”,
- often exist only to **load a skill and adopt a persona**,
- or duplicate concepts already covered by phase workflows.

If kept in the primary `global_workflows/` directory, they can:

- force unnecessary planning for trivial tasks,
- increase token usage and verbosity,
- blur which workflows represent real *phases* of work,
- encourage meta‑work instead of delivery.

Keeping them here preserves a **clean daily operating loop**: …and ensures meta behavior happens **only by intent**, not accident.

---

## Primary vs Internal Workflows (Clear Separation)

### ✅ Primary workflows (use daily, stay in root)

Primary workflows represent **phases of work** and are the normal entry points.

Examples:

- `/plan` — planning & architecture selection  
- `/tdd` — behavior changes via TDD  
- `/debug` — bug investigation & root-cause analysis  
- `/review` — quality gates  
- `/close-session` — handoff, summary, memory discipline  
- `/new-knowledge-item` — durable memory capture  
- `/refactor`, `/optimize`, `/hotfix`, `/document`, `/sprint`, `/onboard`

Mental model:  
**“What phase of work am I in?”**

---

### 🧠 Internal workflows (live here)

Internal workflows are **helpers**, not phases.
They usually exist to **activate a specific skill** or enforce a strict mode.

Mental model:  
**“I intentionally want this advanced or meta behavior.”**

---

## Internal Workflow Categories

### 1) Skill Activation Wrappers

These workflows do not define a phase.
They simply tell the agent to load a skill and follow it exactly.

Examples:

- `executing-plans.md`
- `dispatching-parallel-agents.md`
- `finishing-a-development-branch.md`
- `requesting-code-review.md`
- `receiving-code-review.md`
- `using-git-worktrees.md`
- `verification-before-completion.md`
- `writing-plans.md`
- `test-driven-development.md`

**Why internal:**  
They duplicate entry points already covered by `/plan`, `/tdd`, `/review`, etc.  
Keeping them internal prevents confusion about which workflow is canonical.

---

### 2) Bootstrapping / Orientation Helpers

Used to validate or enforce how the system works.

Examples:

- `using-superpowers.md`

**Why internal:**  
These are intentionally strict and override normal heuristics.  
They are useful for onboarding or verification — not daily work.

---

### 3) Skill Authoring & Maintenance Helpers

Used when creating or maintaining skills themselves.

Examples:

- `writing-skills.md`

**Why internal:**  
Skill authoring is “AI DevOps.”  
It should never compete with feature delivery workflows.

---

## Rules for Using `internal/` Workflows

1. **Never treat internal workflows as default entry points.**
2. Use them only when:
   - you explicitly want the behavior they enforce,
   - you are onboarding, validating, or doing meta‑work.
3. If an internal workflow becomes part of your daily loop:
   - promote it to the main workflow directory,
   - rewrite it as a phase-oriented workflow,
   - remove hardcoded paths and overly prescriptive language.
4. Internal workflows should clearly answer:
   > “Why is this NOT a primary workflow?”

---

## Quick Decision Guide

- “I need to build or change a feature”  
  → `/plan` → `/tdd`

- “Something broke”  
  → `/debug`

- “I’m about to claim this is done”  
  → `/verification-before-completion` (primary)

- “I want strict TDD enforcement beyond defaults”  
  → `internal/test-driven-development.md`

- “I need to execute an approved plan exactly as written”  
  → `internal/executing-plans.md`

- “I want to coordinate parallel independent tasks”  
  → `internal/dispatching-parallel-agents.md`

- “I’m onboarding or validating skill loading behavior”  
  → `internal/using-superpowers.md`

- “I am creating or editing a skill”  
  → `internal/writing-skills.md`

---

## Maintenance Guidance

Keep this folder **small**.

If it grows:

- consider subfolders such as:
  - `internal/bootstrap/`
  - `internal/authoring/`
  - `internal/reference/`
- periodically review and remove unused workflows.

Internal workflows are powerful — but power should be **explicit**, not implicit.
