---
name: brainstorming
description: Clarify problem space, constraints, and intent before planning or implementation
---

# Brainstorming

## Purpose

Use this skill **to clarify WHAT problem you are solving**, not HOW to implement it.

Brainstorming exists to:

- surface user intent
- clarify scope and constraints
- identify risks and unknowns
- prevent premature architecture decisions

This skill must occur **before /plan**, never after architecture approval.

---

## When to Use (Required)

Use brainstorming when **ANY of the following are true**:

- requirements are unclear or ambiguous
- scope spans multiple components or systems
- behavior changes may have irreversible impact
- tradeoffs are not yet understood
- stakeholder intent is uncertain
- cost of rework is high if misunderstood

---

## When to Skip (Allowed)

Do NOT use brainstorming for:

- trivial edits
- small refactors
- formatting, naming, comments, documentation
- well-understood extensions following existing patterns
- Fast Mode tasks

In these cases, proceed directly to implementation or the appropriate workflow.

---

## What Brainstorming Produces

Brainstorming must yield:

- a clear problem statement
- explicit in-scope items
- explicit out-of-scope items
- known constraints (technical, security, operational)
- open questions or unknowns

Brainstorming does NOT:

- design architecture
- write plans
- prescribe implementations

---

## Output

When complete, summarize in **3–6 bullets**:

- Problem to solve
- Constraints
- Assumptions
- Risks
- Success criteria

Then proceed to **/plan** if needed.

---

## Rules (Strict)

- Do not brainstorm after architecture is approved
- Do not over-elaborate
- Do not drift into solution design
- Stop once clarity is achieved

Brainstorming is a **tool for clarity**, not momentum.
