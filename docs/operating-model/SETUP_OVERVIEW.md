# Setup Overview

This manual assumes a global Antigravity setup that includes:

## Rules
- **AGENTS.md**: cross-tool agent constitution (portable rules)
- **GEMINI.md**: Antigravity-specific operating policy (modes, token discipline, workflow integration)

## Global Workflows
Workflows are reusable phase entry points (slash commands) stored globally, with an `internal/` folder for supporting wrappers.

## Global Skills
Skills are reusable protocols. You maintain a **small canonical set** for daily use and an `internal/` set for meta/authoring/strict references.

## MCPs
- **Sequential Thinking** for structured planning and hypothesis-driven debugging
- **Context7** for documentation injection to avoid hallucinated APIs

## Graphify
Graphify creates a persistent project knowledge graph so agents can answer questions without re-reading the repo each session.

---

## Visual summary

```mermaid
flowchart TD
  A[Idea / Task] --> B{Requirements clear?}
  B -- No --> C[Brainstorm (optional)]
  B -- Yes --> D[/plan]
  C --> D
  D --> E{Plan approved?}
  E -- No --> D
  E -- Yes --> F[/tdd or Fast Mode]
  F --> G[/review]
  F --> H[/debug if broken]
  H --> F
  G --> I[/document if needed]
  I --> J[/close-session]
  J --> K{KI Gate Passes?}
  K -- Yes --> L[/new-knowledge-item]
  K -- No --> M[Stop]
  L --> M
```
