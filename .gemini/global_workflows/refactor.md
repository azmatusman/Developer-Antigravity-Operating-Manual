---
description: Safe incremental code refactoring
---

# Refactoring Protocol

1. Identify the target code for refactoring
2. Invoke the **refactoring** skill
3. Before any changes:
   - Verify existing tests pass (green baseline)
   - If test coverage is insufficient → write characterization tests first
4. Apply ONE refactoring move at a time
5. After each move → run tests → if green, continue; if red, revert
6. When complete:
   - Run full test suite
   - Summarize what changed and why
   - Confirm no behavior changes occurred
