# skills/internal/ — Supporting Skills (Not Primary Entry Points)

This folder contains **supporting / meta skills** that are intentionally **NOT** part of the daily build loop.
They exist for **bootstrapping**, **skill authoring**, **strict doctrine reference**, or **special-case operations**.

Your primary goal is:

- keep global behavior predictable,
- avoid over-prescriptive defaults,
- reduce token waste,
- and prevent agents from doing “AI DevOps” when you just want to build features.

These skills are powerful, but **too strong** or **too niche** to be allowed as primary default behavior. 【1-8b8f9c】【2-a46c21】【3-735bbe】

---

## Why these skills live in `internal/`

Internal skills often:

- contain strong “MUST always” language,
- enforce tool-specific workflows,
- hardcode paths or locations,
- increase planning overhead for small tasks,
- or duplicate a simpler canonical skill.

If treated as default skills, they can conflict with your global operating model:

- Fast Mode for simple tasks
- Planning Mode only for multi-file/architectural work
- One intent per conversation
- Minimize narration and re-reading
- Memory discipline (SUMMARY.md vs Knowledge Items) 【2-a46c21】【3-735bbe】

---

## Primary Skills vs Internal Skills (Separation of Concerns)

### Primary skills (use daily)

These are stable, technology-agnostic, and align with your global rules:

- `feature-planning` (plan before coding) 【1-8b8f9c】
- `tdd-workflow` (canonical TDD cycle) 【1-8b8f9c】
- `systematic-debugging` (evidence-first debugging) 【1-8b8f9c】
- `code-review` (structured, severity-based review) 【1-8b8f9c】
- `verification-before-completion` (evidence before claiming “done”) 【1-8b8f9c】
- `security-review` / `performance-audit` / `refactoring` (specialized but safe) 【1-8b8f9c】

### Internal skills (use rarely, intentionally)

These are meta-level tools and should not be used as the default “first move.”

---

## Internal Skill Catalog (and when to use each)

### 1) `using-superpowers` (Bootstrap / onboarding only)

**What it is:**
A strong meta skill that enforces “if a skill might apply, you must invoke it,” and promotes skill invocation even before clarifying questions. 【1-8b8f9c】

**Use it when:**

- onboarding a new machine/user
- verifying skill discovery/loading behavior
- establishing the philosophy of skills usage for a new setup

**Do NOT use it when:**

- doing normal feature work
- doing small edits / Fast Mode work
- you already have your daily workflow habits established

**Why internal:**
It is intentionally strict and can create unnecessary overhead and token usage if treated as a primary behavior. It can also conflict with “Fast Mode for simple tasks” and “one intent per conversation.” 【1-8b8f9c】【2-a46c21】【3-735bbe】

---

### 2) `writing-skills` (Expert-only: skill authoring & validation)

**What it is:**
A skill creation methodology (TDD for documentation), intended for writing or editing skills and verifying they work under pressure scenarios. 【1-8b8f9c】

**Use it when:**

- creating a new skill package
- editing an existing skill safely
- validating a skill before promoting it to primary/global use

**Do NOT use it when:**

- building application features
- debugging application logic
- doing normal code review

**Why internal:**
Skill authoring is “AI DevOps.” Keeping it internal prevents agents from drifting into meta-work during normal development. 【1-8b8f9c】【2-a46c21】

---

### 3) `writing-plans` (Advanced planning style guide — not the default)

**What it is:**
A very detailed plan-authoring discipline, including plan structure, anti-placeholder rules, and (often) opinionated storage locations. 【1-8b8f9c】

**Use it when:**

- writing large, multi-day plans
- plans that will be executed by multiple agents or multiple sessions
- you need strict “no placeholders” plan quality

**Do NOT use it when:**

- normal features where `/plan` and `feature-planning` are sufficient

**Why internal:**
It can be too heavy for everyday work, and it contains opinionated conventions that might not match every repository. Primary planning should remain `/plan` + `feature-planning`. 【1-8b8f9c】【2-a46c21】

---

### 4) `test-driven-development` (Strict doctrine reference; not canonical)

**What it is:**
A long-form, highly strict TDD doctrine that includes strong enforcement language and non-agnostic examples. 【1-8b8f9c】

**Canonical daily TDD skill:**
✅ `tdd-workflow` is the official, global TDD skill. 【1-8b8f9c】

**Use this internal doctrine when:**

- you need a “TDD reset” under pressure
- you are mentoring/standardizing strict TDD behavior
- you want a more forceful anti-rationalization reference

**Do NOT use it when:**

- normal feature work where `tdd-workflow` is sufficient

**Why internal:**
It duplicates TDD capability and increases confusion if both are treated as primary. Keeping it internal preserves a single canonical entry point (`tdd-workflow`). 【1-8b8f9c】【2-a46c21】

---

## Rules for Maintaining `internal/`

1. **Internal skills must not be assumed as default entry points.**
2. If an internal skill becomes part of your daily loop:
   - promote it to primary skills,
   - reduce prescriptive language,
   - remove tool-specific paths,
   - keep it short and technology-agnostic.
3. Keep internal small. If it grows, split into:
   - `internal/bootstrap/`
   - `internal/authoring/`
   - `internal/reference/`

---

## Quick Decision Guide

- Need to build a feature → `feature-planning` then `tdd-workflow` 【1-8b8f9c】
- Something broke → `systematic-debugging` 【1-8b8f9c】
- About to claim “done” → `verification-before-completion` 【1-8b8f9c】
- Need strict onboarding of skills usage → internal `using-superpowers` 【1-8b8f9c】
- Need to create/edit a skill → internal `writing-skills` 【1-8b8f9c】
- Need a heavy multi-session plan → internal `writing-plans` 【1-8b8f9c】
- Need strict TDD “reset” → internal `test-driven-development` (reference) 【1-8b8f9c】

---

## Location Guidance (Global)

Recommended structure:

~/.gemini/antigravity/skills/
├── feature-planning/
├── tdd-workflow/
├── systematic-debugging/
├── code-review/
├── verification-before-completion/
├── security-review/
├── performance-audit/
├── refactoring/
└── internal/
    ├── using-superpowers/
    ├── writing-skills/
    ├── writing-plans/
    └── test-driven-development/
