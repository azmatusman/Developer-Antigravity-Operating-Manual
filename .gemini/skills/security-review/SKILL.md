---
name: security-review
description: Security-focused code review using common vulnerability patterns
activation: manual
---

# Security Review Skill

## Purpose
Identify security vulnerabilities in code changes using universal security principles.

## Protocol

### Phase 1: Attack Surface Identification
1. What are the entry points? (APIs, forms, file uploads, webhooks)
2. What external data enters the system? (user input, third-party APIs, files)
3. What sensitive data does the system handle? (credentials, PII, financial)
4. What are the trust boundaries? (authenticated vs public, admin vs user)

### Phase 2: Vulnerability Scan
Check for each category:

#### Input Handling
- [ ] All external input validated (type, length, format, range)
- [ ] No raw user input in queries (parameterized/prepared statements)
- [ ] No raw user input in system commands
- [ ] No raw user input in template rendering (XSS prevention)
- [ ] File uploads validated (type, size, content, not just extension)

#### Authentication & Authorization
- [ ] Authentication required on all non-public endpoints
- [ ] Authorization checked for every protected operation
- [ ] No privilege escalation paths (user accessing admin functions)
- [ ] Session/token expiration configured
- [ ] Password/secret requirements enforced

#### Data Protection
- [ ] No secrets hardcoded in source code
- [ ] Sensitive data not logged (passwords, tokens, PII)
- [ ] Sensitive data not exposed in error messages
- [ ] Data encrypted in transit
- [ ] Sensitive data encrypted at rest (if applicable)

#### Configuration
- [ ] Debug mode disabled in production configurations
- [ ] Default credentials changed
- [ ] Unnecessary features/endpoints disabled
- [ ] Error messages do not reveal internal details
- [ ] Dependencies checked for known vulnerabilities

### Phase 3: Generate Security Report

| # | Location | Vulnerability | Severity | OWASP Category | Remediation |
|---|----------|--------------|----------|----------------|-------------|

Severity: 🔴 Critical / 🟡 High / 🟠 Medium / 🟢 Low

### Phase 4: Remediation Priority
1. 🔴 Critical — Fix immediately, block deployment
2. 🟡 High — Fix before next release
3. 🟠 Medium — Schedule for upcoming sprint
4. 🟢 Low — Add to backlog

## Rules
- Security issues are NEVER downgraded for convenience
- Every finding must include a concrete remediation step
- If unsure about severity → escalate to higher severity
- Check dependencies, not just your own code
