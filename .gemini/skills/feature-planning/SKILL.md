---
name: feature-planning
description: Structured feature planning with requirements exploration and task breakdown
activation: manual
---

# Feature Planning Skill

## Purpose
Transform a feature idea into a clear, actionable implementation plan before any code is written.

## Protocol

### Phase 1: Requirements Exploration (Socratic)
1. Restate the feature in your own words — confirm understanding
2. Ask clarifying questions about:
   - Who uses this feature? (user roles, permissions)
   - What triggers it? (user action, scheduled, event-driven)
   - What are the inputs and outputs?
   - What happens on success? On failure?
   - What are the boundaries? (what is explicitly OUT of scope)
3. Identify assumptions and state them explicitly
4. List unknowns that need resolution before implementation

### Phase 2: Architecture Analysis
1. Analyze the existing codebase for:
   - Where this feature fits in the current architecture
   - Which existing modules/components will be affected
   - What new modules/components need to be created
   - Shared utilities or patterns that should be reused
2. Define module boundaries — which files will change
3. Define data flow — how data moves through the system
4. Define API contracts (if applicable) — inputs, outputs, errors

### Phase 3: Task Breakdown
1. Break the feature into ordered subtasks
2. Mark dependencies between subtasks
3. Identify which subtasks can run in PARALLEL
4. Estimate complexity per subtask: Low / Medium / High
5. Identify risks per subtask

Output format:
```
TASK BREAKDOWN:
├── Task 1: [description] — Complexity: Low — Dependencies: None
├── Task 2: [description] — Complexity: Medium — Dependencies: Task 1
├── Task 3: [description] — Complexity: Low — Dependencies: None (PARALLEL with Task 2)
└── Task 4: [description] — Complexity: High — Dependencies: Task 2, Task 3
```

### Phase 4: Testing Strategy
1. Define what needs unit tests
2. Define what needs integration tests
3. Define acceptance criteria (when is this feature DONE?)
4. Identify edge cases that must be tested

### Phase 5: Output Artifacts
Generate the following:
1. **implementation_plan.md** — Full plan artifact
2. **task_checklist.md** — Ordered checklist for execution
3. **api_contracts.md** — If applicable

## Rules
- NEVER write code during planning
- Every assumption must be stated explicitly
- Every task must have clear "done" criteria
- If requirements are ambiguous after Phase 1 → STOP and ask the user
- Plans should be executable by someone who wasn't in the planning session
