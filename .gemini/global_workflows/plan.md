---
description: Create a structured implementation plan before coding
---

# Feature Planning Protocol

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
   - Explicitly compare tradeoffs (complexity, maintainability, extensibility, risk).
   - Clearly recommend **ONE** architecture and explain why it is preferred.

5. Invoke the **feature-planning** skill to formalize the chosen approach.

6. Create an `implementation_plan.md` artifact containing:
   - Restated requirements (in your own words)
   - Explicit assumptions
   - Selected architecture and rationale
   - Module boundaries (files/components to change or add)
   - Data flow description
   - API or interface contracts (if applicable)
   - Risks and mitigations
   - Testing strategy

7. Create a `task_checklist.md` artifact with:
   - Ordered, atomic subtasks
   - Dependencies between tasks
   - Identification of tasks that can run in parallel
   - Clear “done” criteria for each task

8. **STOP** — wait for explicit user review and approval before writing any code.