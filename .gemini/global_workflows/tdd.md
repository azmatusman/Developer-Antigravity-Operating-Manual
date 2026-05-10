---
description: Implement a feature using strict Test-Driven Development
---

# TDD Protocol

1. Confirm feature requirements are clear (if not → run /plan first)
2. Invoke the **tdd-workflow** skill
3. For each unit of behavior:
   - RED: Write one failing test → verify it fails
   - GREEN: Write minimum code to pass → verify all tests pass
   - REFACTOR: Clean up → verify all tests still pass
4. Repeat until all acceptance criteria are covered
5. Run full test suite at the end — zero failures, zero skips
6. Report: number of tests written, coverage summary
