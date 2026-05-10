---
description: Systematic debugging using evidence-based methodology
---

# Debugging Protocol

1. Invoke the **systematic-debugging** skill.

2. **Use Sequential Thinking to track hypotheses explicitly**:
   - Maintain a clear list of hypotheses (ranked by likelihood).
   - Test **one hypothesis at a time**.
   - Make **one change at a time**.
   - After each test, record whether the hypothesis is CONFIRMED or ELIMINATED.
   - Do not proceed to the next hypothesis until the current one is resolved.

3. Follow the 4-phase methodology strictly:

   **Phase 1: Define the Problem**
   - Clearly state expected vs actual behavior.
   - Identify when the issue occurs and the minimal reproduction path.

   **Phase 2: Gather Evidence**
   - Collect logs, stack traces, error messages, and relevant inputs.
   - Trace code and data flow to the failure point.

   **Phase 3: Hypothesize and Test**
   - Form exactly 3 hypotheses.
   - Test them in order using Sequential Thinking discipline.
   - Change ONE variable per test.

   **Phase 4: Fix and Validate**
   - Implement the minimal fix for the confirmed root cause.
   - Run the failing test and then the full test suite.
   - Ensure no regressions are introduced.

4. If the fix fails after **3 Sequential Thinking cycles**:
   - STOP.
   - Document what was tried and what was ruled out.
   - Escalate for architectural review or deeper analysis.

5. After a successful fix:
   - Recommend a regression test to prevent recurrence.
   - Summarize the root cause in one concise sentence.