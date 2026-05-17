---
name: brainstorming
description: "Clarify problem space, constraints, and user intent ONLY. Produces questions and clarity — NEVER code, architecture, or solutions."
version: 1.1.1
---

# Brainstorming Protocol

## HARD CONSTRAINT — READ BEFORE ANYTHING ELSE

**This workflow produces ZERO code. ZERO architecture. ZERO file structures. ZERO schemas.**

If at ANY point you feel the urge to:
- Write code (even “example” or “sketch” code)
- Propose file structures or directory layouts
- Design database schemas or API contracts
- Suggest specific libraries, frameworks, or implementation approaches
- Write pseudocode (unless explicitly requested by the user)

→ **STOP.** You are leaving brainstorming and entering planning or implementation.

Brainstorming answers: **“WHAT problem are we solving and WHY?”**
Brainstorming does NOT answer: “HOW do we solve it?”

---

## Protocol

### Step 1: Load Brainstorming Skill
Read and internalize:
`C:/Users/Md. Usman Azmat/.gemini/antigravity/skills/brainstorming/SKILL.md`

### Step 2: Engage in Socratic Dialogue
Ask ONE question at a time to surface:
- User intent
- Scope (in/out)
- Constraints (technical/security/operational/time/budget)
- Stakeholders
- Risks/unknowns
- Success criteria

### Step 3: Produce Clarity Summary
Summarize in 3–6 bullets:
- **Problem:** [one sentence]
- **Constraints:** [known limits]
- **Assumptions:** [what we're assuming]
- **Risks:** [what could go wrong]
- **Success criteria:** [how we know it’s done]
- **Open questions:** [remaining unknowns]

### Step 4: STOP — Suggest Next Step
Say: **“Brainstorming complete. Ready for `/plan` when you are.”**

Do NOT:
- Start planning
- Propose architectures
- Create task breakdowns
- Write any code
- Suggest implementation approaches

WAIT for the user to explicitly invoke `/plan` or provide another instruction.

---

## Forbidden Outputs (Violations)

- **Code** (any language)
- **Pseudocode** (unless explicitly requested)
- **File structures** (directories, filenames)
- **Architecture** (system design, tech stack)
- **Task breakdowns**
- **Library/framework suggestions**
- **API design** (endpoints, request/response)
- **Database schema**

If the user asks for any forbidden output during brainstorming, respond:
> “That’s an implementation question — we’ll capture it and address it in `/plan`. For now, let’s make sure we fully understand the problem.”

---

## Completion Criteria

Brainstorming is done when:
- Problem statement is clear and agreed
- Scope boundaries are explicit
- Constraints are documented
- Success criteria are defined
- No critical open questions remain

Brainstorming is NOT done when:
- You proposed a solution
- You wrote code
- You designed architecture
