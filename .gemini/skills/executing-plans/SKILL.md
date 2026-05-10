---
name: executing-plans
description: Execute a written implementation plan with discipline, verification, and review checkpoints
---

# Executing Plans

## Overview

Use this skill **only when a written implementation plan already exists and is approved**.

Purpose:

- load and critically review the plan
- execute tasks exactly as written
- stop immediately on blockers
- verify completion before claiming success

**Announce at start:**  
"I'm using the executing-plans skill to implement this plan."

If parallel execution capability is available and tasks are independent, prefer **subagent-driven-development** to speed up execution.

---

## The Process

### Step 1: Load and Review the Plan

- Read the plan file fully
- Review critically for:
  - unclear steps
  - missing dependencies
  - risky assumptions
- If concerns exist:
  - raise them with your human partner
  - **STOP** and wait for plan update
- If no concerns:
  - create a task checklist
  - proceed to execution

---

### Step 2: Execute Tasks

For each task in the plan:

- Mark task as **in_progress**
- Follow steps **exactly as written**
- Do NOT:
  - improvise
  - add scope
  - refactor beyond the task
- Run all specified verifications
- Mark task as **completed** only after verification passes

---

### Step 3: Complete Development

After **all tasks** are completed and verified:

- Announce:  
  "I'm completing this work using the finishing-a-development-branch skill."

- Use **finishing-a-development-branch** to:
  - confirm all tests pass
  - present merge/integration options
  - execute the chosen completion path

---

## When to Stop and Ask for Help

**STOP executing immediately if:**

- a blocker is encountered (missing dependency, failing tests)
- an instruction is unclear
- the plan has gaps preventing progress
- verification fails repeatedly

**Do NOT guess. Do NOT force progress.**

Escalate for clarification.

---

## When to Revisit Earlier Steps

Return to **Step 1: Load and Review** if:

- the plan is updated by your partner
- a foundational assumption proves invalid
- the approach requires reconsideration

Never grind through uncertainty.

---

## Operating Rules (Strict)

- Follow the plan **exactly**
- Never skip verifications
- Never change architecture while executing
- Use isolated workspaces if required (e.g., git worktrees)
- Never start implementation on main/master without explicit approval

---

## Integration Notes

This skill commonly integrates with:

- planning workflows that produce the plan
- subagent-driven-development for parallel task execution
- finishing-a-development-branch for safe completion

This skill is **situational**, not a daily default.
