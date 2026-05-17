---
description: Create a structured implementation plan before coding
---

# Feature Planning Protocol

## HARD CONSTRAINT — READ BEFORE ANYTHING ELSE

**This workflow produces PLANS and DOCUMENTS. It does NOT produce implementation code or execute implementation steps.**

Forbidden during `/plan`:
- Writing implementation code (even “starting with a simple version”)
- Creating/modifying source files
- Running tests
- Running commands that change the repo

Permitted during `/plan`:
- Architecture comparisons (text)
- API/interface contracts (documentation)
- Task breakdowns with done-criteria

When the plan is complete → **STOP and wait for explicit implementation instruction**.

---

## Steps

1. Analyze the feature requirements provided by the user.
2. Check existing Knowledge Items or prior artifacts for relevant decisions or constraints.
3. Explore the current codebase to understand:
   - Existing architecture patterns
   - Relevant modules/components
   - Integration points and dependencies

4. **Use Sequential Thinking** to propose **2–3 viable architecture options**:
   - Architecture A: description, strengths, weaknesses
   - Architecture B: description, strengths, weaknesses
   - (Optional) Architecture C: description, strengths, weaknesses
   - Compare tradeoffs (complexity, maintainability, extensibility, risk)
   - Recommend ONE architecture and explain why

5. Invoke the **feature-planning** skill to formalize the chosen approach.

6. Create `implementation_plan.md` containing:
   - Restated requirements
   - Explicit assumptions
   - Selected architecture + rationale
   - Module boundaries (files/components to change or add)
   - Data flow
   - API/interface contracts (if applicable)
   - Risks + mitigations
   - Testing strategy

7. Create `task_checklist.md` containing:
   - Ordered atomic subtasks
   - Dependencies
   - Parallelizable tasks
   - Done-criteria per task

8. **STOP — Do NOT proceed to implementation.**

State:
**“Plan complete. Ready to implement when you give the go-ahead via `/tdd`, `/execute`, or `subagent-driven-development`.”**

WAIT for explicit instruction to implement.
