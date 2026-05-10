---
name: tdd-workflow
description: Test-Driven Development — Red → Green → Refactor cycle enforcement
activation: manual
---

# Test-Driven Development Workflow

## Purpose
Enforce disciplined test-first development to produce reliable, well-tested code.

## Prerequisites
- Feature requirements clearly defined (use /plan workflow first if unclear)
- Testing framework configured in the project
- Clear acceptance criteria for the feature

## Protocol

### Phase 1: RED — Write a Failing Test
1. Identify the smallest unit of behavior to implement
2. Write ONE test that describes the expected behavior
3. Run the test suite — confirm the new test FAILS
4. If the test passes without new code → the test is wrong or the feature already exists
5. Do NOT proceed to Phase 2 until the test fails for the RIGHT reason

### Phase 2: GREEN — Make It Pass
1. Write the MINIMUM code necessary to make the failing test pass
2. Do not optimize, refactor, or add extras
3. Do not modify the test file during this phase
4. Run the full test suite — ALL tests must pass (not just the new one)
5. If other tests break → fix the regression before proceeding

### Phase 3: REFACTOR — Clean Up
1. Review the implementation for duplication, naming, structure
2. Apply improvements WITHOUT changing behavior
3. Run the full test suite after each refactoring step
4. If any test fails → revert the last change immediately

### Phase 4: REPEAT
1. Return to Phase 1 for the next unit of behavior
2. Continue until all acceptance criteria are covered

## Rules
- Never write production code before a failing test exists
- Each test should test ONE behavior, not multiple
- Test names must describe the behavior, not the implementation
- No skipped or pending tests allowed at completion
- If stuck for >3 cycles, escalate to /debug workflow

## Completion Criteria
- All acceptance criteria have corresponding tests
- All tests pass
- No skipped or commented-out tests
- Code is clean and refactored
