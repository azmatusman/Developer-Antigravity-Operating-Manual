---
name: code-review
description: Thorough code review against implementation plan and quality standards
activation: manual
---

# Code Review Skill

## Purpose
Provide an unbiased, thorough review of code changes against the implementation plan and universal quality standards.

## Prerequisites
- Code changes are complete (all files saved)
- Implementation plan exists (if applicable)
- Tests have been written and executed

## Review Protocol

### Step 1: Context Gathering
1. Read the implementation plan or feature description
2. Identify all changed/added/deleted files
3. Understand the scope — what SHOULD have changed vs what DID change

### Step 2: Plan Adherence Check
1. Does the implementation match what was planned?
2. Are there any deviations? If yes, are they justified?
3. Is there scope creep — code changes outside the feature boundary?
4. Are all planned items implemented (nothing missing)?

### Step 3: Code Quality Audit
Review each changed file for:

#### Correctness
- Logic errors, off-by-one errors, null/undefined handling
- Edge cases: empty inputs, boundary values, concurrent access
- Error handling: are all failure paths covered?
- Resource cleanup: are connections, files, streams properly closed?

#### Security
- Input validation on all external data
- No hardcoded secrets, keys, or credentials
- No SQL/command injection vectors
- Authentication and authorization checks where needed
- Sensitive data not logged or exposed in errors

#### Maintainability
- Clear naming (variables, functions, classes, files)
- Single Responsibility — each unit does one thing
- No deep nesting (>3 levels = refactor candidate)
- No magic numbers or strings — use named constants
- Comments explain WHY, not WHAT

#### Performance
- No unnecessary loops within loops (O(n²) when O(n) is possible)
- No redundant data fetches or computations
- Appropriate data structures for the use case
- No memory leaks (event listeners, subscriptions cleaned up)

### Step 4: Test Coverage Review
- Do tests exist for all new logic?
- Do tests cover edge cases and error paths?
- Are tests independent (no shared mutable state)?
- Do test names clearly describe the behavior being tested?

### Step 5: Generate Review Report

Output as a structured table:

| # | File | Issue | Severity | Recommendation |
|---|------|-------|----------|----------------|

Severity Levels:
- 🔴 **Critical**: Security vulnerability, data loss, crash
- 🟡 **Major**: Logic error, missing validation, poor error handling
- 🟢 **Minor**: Style, naming, documentation, optimization opportunity

### Step 6: Verdict
- ✅ **APPROVE** — No critical or major issues
- ⚠️ **APPROVE WITH COMMENTS** — Minor issues only, document them
- ❌ **REQUEST CHANGES** — Critical or major issues must be fixed first

## Rules
- Review the code as if you did NOT write it (fresh perspective)
- Every criticism must include a concrete fix suggestion
- Do not nitpick style if a linter/formatter handles it
- Security issues are always Critical, never downgraded
