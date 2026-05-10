---
description: Thorough code review of recent changes
---

# Code Review Protocol

1. Identify all files changed since the last commit (or as specified)
2. Invoke the **code-review** skill
3. Review every changed file against:
   - The implementation plan (if one exists)
   - Code quality standards (correctness, security, maintainability, performance)
   - Test coverage for new logic
4. Generate a review report table with findings by severity
5. Provide a verdict: ✅ APPROVE / ⚠️ APPROVE WITH COMMENTS / ❌ REQUEST CHANGES
6. If critical issues found → list them first and STOP
