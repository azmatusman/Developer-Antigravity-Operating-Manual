---
description: Create a new Knowledge Item file using the standard template (high-signal, long-term memory)
---

# New Knowledge Item (KI) Protocol

Use this workflow when you want to capture **durable project knowledge** (months-long relevance), not session progress.

---

## Step 0: Quick Gate (Avoid Memory Pollution)

Answer YES/NO:

- Did we make a non-obvious architectural decision?
- Did we discover a meaningful constraint/limitation?
- Did we find a subtle bug root cause that could reoccur?
- Did we define an invariant (Always/Never rule)?
- Did we evaluate tradeoffs and reject an option for a reason worth remembering?

If ALL are NO:

- STOP.
- Do NOT create a Knowledge Item.
- Use `SUMMARY.md` instead.

If ANY are YES:

- Continue.

---

## Step 1: Determine KI Title and Type

1) Choose a short title (max 8 words) that reads like a durable statement.
2) Choose ONE type:

- Architecture Decision
- Constraint / Limitation
- Bug Root Cause
- Operational Runbook
- Invariant / Rule (Always/Never)
- Tradeoff & Rejected Options
- Integration Note
- Performance Finding
- Security Finding

---

## Step 2: Create the Knowledge Item File

Create a new folder if it doesn’t exist:

- `docs/knowledge-items/`

Create a new Markdown file using this naming pattern:

`docs/knowledge-items/KI-YYYYMMDD-HHMM-<short-title-slug>.md`

Example:
`docs/knowledge-items/KI-20260505-1159-strategies-emit-signals-only.md`

---

## Step 3: Populate with the Standard Template

Insert the following template into the new KI file and prefill:

- Title
- Date
- Type checkbox

```markdown
# Knowledge Item — <Short Title>

## Type (choose one)
- [ ] Architecture Decision
- [ ] Constraint / Limitation
- [ ] Bug Root Cause
- [ ] Operational Runbook
- [ ] Invariant / Rule (Always/Never)
- [ ] Tradeoff & Rejected Options
- [ ] Integration Note
- [ ] Performance Finding
- [ ] Security Finding

## Context (2–4 lines)
**Problem / Situation:**  
<What triggered this KI? What were we trying to do?>

**Scope:**  
<Which module/subsystem/process does this affect?>

## Durable Statement (the “memory”)
**Decision / Insight:**  
<One clear sentence that should remain true in the future.>

## Why (brief rationale)
**Reasoning:**  
- <1–5 bullets; factual; no storytelling>

## Implications (how it changes future work)
**Do:**  
- <What future work should follow because of this?>

**Don’t:**  
- <What should be avoided to prevent regressions?>

## Verification / Evidence
**How we know this is correct:**  
- <Test added, log evidence, benchmark result, reproduction steps>
- <Links to artifacts or filenames>

## Reproduction / Steps (only if bug/ops-related)
**Minimal steps to reproduce / validate:**  
1) <Step>  
2) <Step>  
3) <Expected outcome>

## Known Alternatives (if applicable)
**Alternatives considered:**  
- Option A: <why rejected>
- Option B: <why rejected>

## Risks / Failure Modes
- <What breaks if ignored?>
- <Worst-case impact?>

## Follow-ups (optional, max 3)
- [ ] <Action 1>
- [ ] <Action 2>
- [ ] <Action 3>

## Metadata
- **Date:** <YYYY-MM-DD>
- **Owner:** <your name or “Team”>
- **Related artifacts:** <plan, PR, diagrams, reports>
- **Tags:** <architecture, debugging, security, performance, etc.>
