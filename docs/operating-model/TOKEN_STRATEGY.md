# Token Strategy (How to reduce cost)

Token reduction is not only about shorter prompts. It is a system:

1. **Workflows** prevent re-explaining steps.
2. **Skills** prevent random thrashing.
3. **Graphify** prevents rereading the repo.
4. **MCPs** prevent hallucinated APIs.
5. **Model Selection** prevents using expensive models on mechanical work.

## Practical rules
- Prefer *surgical edits* over rewriting entire files.
- Do not re-read unchanged files.
- Stop when done.
- Batch similar changes.

See also:
- [model-selection/RIGHT_MODEL_RIGHT_TASK.md](../model-selection/RIGHT_MODEL_RIGHT_TASK.md)
- [graphify/GRAPHIFY_GUIDE.md](../graphify/GRAPHIFY_GUIDE.md)
