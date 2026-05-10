# Antigravity Skills — Global Catalog & Usage Guide

This directory contains **Skills** used by Antigravity agents.
Skills are **reusable capability packages** (procedures and checklists) invoked on demand.

## How to Think About Skills

- **Skills** define **HOW** to do a task (procedural know-how).
- **Workflows** define the **SEQUENCE** of steps for a task type (your /commands).
- **Rules** define what to **ALWAYS** or **NEVER** do (always-on constraints).

**Golden rule:** Keep the *daily* skill set small, stable, and predictable.

---

## Directory Structure

Recommended global layout:

---

## Canonical Daily Skills (Primary)

These are safe, technology-agnostic, and aligned to disciplined development.
They are intended to be used frequently.

### 1) feature-planning

**Use when:** requirements need structuring before implementation.  
**Output:** implementation plan + task breakdown + assumptions + testing strategy.

### 2) tdd-workflow (Canonical TDD)

**Use when:** implementing or changing behavior.  
**Protocol:** Red → Green → Refactor.

> Note: This is the **official** TDD skill. Avoid multiple competing TDD skills.

### 3) systematic-debugging

**Use when:** encountering bugs, test failures, unexpected behavior.  
**Protocol:** define → gather evidence → hypotheses → test → fix → validate.

### 4) code-review

**Use when:** reviewing code changes against plan and quality standards.  
**Output:** severity-based review report + verdict.

### 5) verification-before-completion

**Use when:** about to claim “done”, “fixed”, “passing”, or before PR/merge.  
**Purpose:** enforce evidence (tests/logs) before assertions.

### 6) refactoring

**Use when:** improving structure without changing behavior.  
**Rule:** refactor only with a green test baseline; one refactor move at a time.

### 7) security-review

**Use when:** validating code changes for common vulnerability patterns.  
**Output:** security findings + remediation steps.

### 8) performance-audit

**Use when:** performance concerns exist or before major release.  
**Rule:** measure before optimizing; prioritize high-impact, low-effort fixes.

### 9) api-design (optional but recommended)

**Use when:** designing interfaces/contracts that multiple components depend on.  
**Output:** endpoint/contract documentation + error structure + consistency rules.

---

## Situational / Coordination Skills (Primary if you actively use them)

These are safe but not required daily. Keep them global if you regularly run parallel work.

### dispatching-parallel-agents

**Use when:** there are 2+ independent tasks with no shared state or dependencies.

### subagent-driven-development

**Use when:** executing a plan with independent subtasks; coordinate specialized agents.

### executing-plans

**Use when:** you have an approved implementation plan and need checkpointed execution.

### using-git-worktrees (optional)

**Use when:** you need safe isolation or parallel feature work without polluting current workspace.

### requesting-code-review / receiving-code-review / finishing-a-development-branch (optional)

**Use when:** you want explicit rituals around review, applying feedback, and integration choices.

---

## Internal Skills (Use Rarely — Not Primary Entry Points)

The `internal/` folder contains skills that are:

- meta-level onboarding helpers
- skill authoring tools
- strict doctrine references
- intentionally prescriptive

They are powerful but should NOT compete with your daily operating loop.

See: `internal/README.md` for the exact rationale and usage rules.

Typical internal skills include:

- using-superpowers (bootstrap/orientation)
- writing-skills (skill authoring & verification)
- writing-plans (heavy planning doctrine reference)
- test-driven-development (strict doctrine reference; not canonical)

---

## How to Choose a Skill (Quick Decision Guide)

- “I’m not clear on requirements/scope” → feature-planning
- “I’m implementing behavior” → tdd-workflow
- “Something broke” → systematic-debugging
- “I’m about to say it’s done” → verification-before-completion
- “I want to improve structure without behavior change” → refactoring
- “I want a quality gate” → code-review
- “I suspect security issues” → security-review
- “It’s slow / scaling concerns” → performance-audit
- “I’m defining an interface/contract” → api-design
- “I have parallelizable tasks” → dispatching-parallel-agents / subagent-driven-development

---

## Maintenance Rules (Keep This Folder Clean)

1. **One canonical skill per capability.**  
   If two skills do the same thing, pick one as canonical and move the other to `internal/`.

2. **Skills should be technology/stack independent (by default).**  
   Project-specific exceptions belong in project-local skills, not global.

3. **Avoid hardcoded absolute paths in skill instructions.**  
   Prefer relative paths or “read the skill folder you are in”.

4. **Prefer short skills.**  
   If a skill grows too large, split into:
   - a primary skill (daily use)
   - a reference appendix (internal)

5. **Review quarterly.**  
   Remove unused skills. Stale skills create misalignment and confusion.

---

## Optional: Pairing Skills With Workflows

Common pairing pattern:

- Workflow defines sequence: `/plan`, `/tdd`, `/debug`, `/review`, `/close-session`
- Workflow invokes the appropriate skill(s) inside the sequence
- Skills remain reusable across workflows

---

## Versioning / Change Control (Recommended)

If these are global skills:

- keep a simple changelog file or commit history in a private repo
- treat changes like code: small diffs, tested by real usage, no large rewrites
