---
name: brainstorming
description: Clarify problem space, constraints, and intent before planning or implementation. Produces clarity ONLY — NEVER code, architecture, or solutions.
---

# Brainstorming

## Purpose

Use this skill **to clarify WHAT problem you are solving**, not HOW to implement it.

Brainstorming exists to:

- surface user intent
- clarify scope and constraints
- identify risks and unknowns
- prevent premature architecture decisions

This skill must occur **before /plan**, never after architecture approval.

---

## When to Use (Required)

Use brainstorming when **ANY of the following are true**:

- requirements are unclear or ambiguous
- scope spans multiple components or systems
- behavior changes may have irreversible impact
- tradeoffs are not yet understood
- stakeholder intent is uncertain
- cost of rework is high if misunderstood

---

## When to Skip (Allowed)

Do NOT use brainstorming for:

- trivial edits
- small refactors
- formatting, naming, comments, documentation
- well-understood extensions following existing patterns
- Fast Mode tasks

In these cases, proceed directly to implementation or the appropriate workflow.

---

## What Brainstorming Produces

Brainstorming must yield:

- a clear problem statement
- explicit in-scope items
- explicit out-of-scope items
- known constraints (technical, security, operational)
- open questions or unknowns

## What Brainstorming Does NOT Produce (Forbidden Outputs)

Brainstorming **NEVER** produces:

- **Code** — not even "example code", "sketch code", or "pseudocode"
- **Architecture** — no component diagrams, no system design, no tech stack choices
- **File structures** — no directory layouts, no "we'll create these files"
- **Task breakdowns** — no "Step 1: Create..., Step 2: Implement..."
- **Database schemas** — no table designs, no ER diagrams
- **API designs** — no endpoints, no request/response schemas
- **Library/framework recommendations** — no "we should use X"
- **Implementation approaches** — no "we could use the strategy pattern here"

If you catch yourself producing any of these → STOP. You have left brainstorming.

**The correct response:** "That's an implementation detail — let's capture it as a consideration for `/plan`. For now, what problem are we actually solving?"

---

## Output

When complete, summarize in **3–6 bullets**:

- Problem to solve
- Constraints
- Assumptions
- Risks
- Success criteria

Then state: **"Brainstorming complete. Ready for `/plan` when you are."**

## Hard Stop Gate

After producing the summary:

- **Do NOT** transition to planning automatically
- **Do NOT** propose architectures
- **Do NOT** create task breakdowns
- **Do NOT** write any code
- **WAIT** for the user to explicitly say `/plan` or give a different instruction

If the user says "that looks right" or "good summary" — that confirms the **brainstorming output**, not permission to plan or implement.

---

## Rules (Strict)

- Do not brainstorm after architecture is approved
- Do not over-elaborate
- Do not drift into solution design
- Stop once clarity is achieved
- **NEVER produce code, architecture, file structures, or implementation details**
- **NEVER transition automatically to /plan — always STOP and wait**
- If the user asks "how would we build this?" during brainstorming, answer: "Let's make sure we have the problem nailed down first. Once we're clear, `/plan` will answer the how."

Brainstorming is a **tool for clarity**, not momentum.

---

## Red Flags — You Are Leaving Brainstorming

If you catch yourself thinking any of these, STOP:

| Thought | Reality |
|---------|---------|
| "Let me sketch out the architecture" | That's /plan, not brainstorming |
| "Here's a quick code example" | That's /tdd, not brainstorming |
| "We could use X library for this" | That's an implementation choice |
| "The file structure would look like..." | That's architecture |
| "Task 1 would be..." | That's planning |
| "Let me just show a simple version" | That's implementation |
| "Here's how the API would work" | That's API design (/plan) |
| "The user asked how to build it" | Redirect to /plan. Brainstorming answers WHAT, not HOW |
