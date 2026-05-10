---
description: Emergency bug fix with minimal risk
---

# Hotfix Protocol

1. **STOP** all other work in progress
2. Invoke the **systematic-debugging** skill to identify root cause
3. Once root cause is confirmed:
   - Write a test that reproduces the bug (must FAIL)
   - Implement the MINIMUM fix to pass the test
   - Run the FULL test suite — zero regressions
4. Document:
   - Root cause (one sentence)
   - Fix applied (one sentence)
   - Files changed
   - Risk assessment (Low / Medium / High)
5. Suggest: should this trigger a broader review of related code?
