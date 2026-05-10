---
description: Close the current work session with explicit handoff, memory capture, and next-step clarity
---

# Close Session Protocol

This workflow **MUST** be run at the end of any meaningful session or **before intentionally starting a new chat**.

Its purpose is to:

- prevent context loss
- avoid memory pollution
- make the *next* session productive within 60 seconds

This workflow does **not** plan future work and does **not** solve open problems.
It creates a clean, truthful stopping point.

---

## Step 1: Identify Session Scope (Internal Only)

Briefly determine and state internally:

- What was the **PRIMARY intent** of this session?
- Was the session focused on:
  - Planning
  - Implementation
  - Debugging
  - Review
  - Documentation
  - Mixed (list phases in order)

Do **NOT** restate earlier prompts or instructions verbatim.
This step is for orientation, not narration.

---

## Step 2: Write or Update `SUMMARY.md`

Create or update a `SUMMARY.md` file in the **project root**.

### Required structure

```markdown
## SUMMARY — YYYY-MM-DD

### Intent
- One sentence describing the primary goal of the session

### Completed
- Concrete tasks/features completed (facts only)

### Decisions
- Architectural or design decisions made (if any)

### Open Items
- Known incomplete work, bugs, risks, or questions

### Next Steps
- 1–3 specific actions for the next session

### Artifacts
- Key files/documents created or modified
