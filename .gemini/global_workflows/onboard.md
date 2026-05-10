---
description: Analyze and explain an unfamiliar codebase
---

# Codebase Onboarding Protocol

1. Scan the project structure (directories, key files, config files)
2. Identify:
   - Entry points (main files, app bootstrap)
   - Architecture pattern (MVC, microservices, monolith, event-driven)
   - Key modules and their responsibilities
   - Data models and relationships
   - External dependencies and integrations
   - Testing setup and patterns
3. Generate a **Project Map** artifact:
   ```
   project-root/
   ├── [module] — [responsibility]
   ├── [module] — [responsibility]
   └── [module] — [responsibility]
   ```
4. Identify:
   - Code conventions and patterns used
   - Potential technical debt or areas of concern
   - Key files a new developer should read first
5. Present as a structured onboarding guide
