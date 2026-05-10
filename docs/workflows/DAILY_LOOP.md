# Daily Loop (How to build any new application)

This is the exact step-by-step method to use for **every project**.

## Step 0 — Frame the task (you)
Write 2–6 sentences:
- problem statement
- in-scope
- out-of-scope
- constraints

## Step 1 — (Optional) Brainstorm (only if unclear)
Use brainstorming when requirements are ambiguous or risky.
Output: a clear problem statement + success criteria.

## Step 2 — `/plan` (mandatory for non-trivial work)
Run `/plan` and require:
- Sequential Thinking proposes **2–3 architectures** with tradeoffs
- one recommended architecture
- artifacts: `implementation_plan.md`, `task_checklist.md`
- STOP for approval

## Step 3 — Implement (small loops)
- Behavior changes → `/tdd`
- Trivial edits → Fast mode

## Step 4 — Debug (when broken)
Run `/debug`:
- evidence first
- hypotheses tracked
- one change at a time

## Step 5 — Review gate
Run `/review`:
- structured severity list
- verdict

## Step 6 — Document if needed
Run `/document` for README/API/onboarding/architecture updates.

## Step 7 — Close session (always)
Run `/close-session`:
- write SUMMARY.md
- run KI gate
- create KI only if justified

---

## Visual workflow

```mermaid
flowchart LR
  A[/plan] --> B[/tdd or Fast]
  B --> C[/review]
  B --> D[/debug]
  D --> B
  C --> E[/close-session]
  E --> F[/new-knowledge-item (optional)]
```
