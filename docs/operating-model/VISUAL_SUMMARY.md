# Visual Summary

## The operating loop

```mermaid
flowchart LR
  A[/plan] --> B[/tdd or Fast]
  B --> C[/review]
  B --> D[/debug]
  D --> B
  C --> E[/close-session]
  E --> F[/new-knowledge-item (optional)]
```

## The model selection overlay

```mermaid
flowchart TD
  A[Task arrives] --> B{Scope & risk?}
  B -- Small / mechanical --> C[Fast model]
  B -- Multi-file / integration --> D[Standard model]
  B -- Architecture / deep debug / security --> E[Most capable model]
  C --> F[Run workflow/skill]
  D --> F
  E --> F
```
