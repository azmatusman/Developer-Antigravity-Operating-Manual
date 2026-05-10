---
name: api-design
description: Design clean, consistent, well-documented API contracts
activation: manual
---

# API Design Skill

## Purpose
Design API contracts that are consistent, intuitive, well-documented, and implementation-agnostic.

## Protocol

### Phase 1: Requirements
1. Who are the API consumers? (frontend, mobile, third-party, internal service)
2. What operations are needed? (CRUD, search, batch, real-time)
3. What are the data entities involved?
4. What are the authorization requirements per operation?
5. What are the expected data volumes and performance constraints?

### Phase 2: Design Contracts
For each endpoint/operation, define:

```
Endpoint: [method] [path]
Description: [what it does]
Auth: [required role/permission]
Request:
  Headers: [required headers]
  Parameters: [path/query params with types]
  Body: [schema with types, required/optional markers]
Responses:
  Success: [status code, response schema]
  Errors:
    - [status code]: [when this occurs, error schema]
    - [status code]: [when this occurs, error schema]
```

### Phase 3: Consistency Check
- Naming: consistent pluralization, casing, verb usage
- Error format: same structure across all endpoints
- Pagination: same pattern for all list endpoints
- Filtering/sorting: consistent query parameter patterns
- Versioning strategy defined
- Rate limiting documented

### Phase 4: Edge Cases
- What happens with empty inputs?
- What happens with very large payloads?
- What happens with concurrent modifications?
- What happens when referenced entities don't exist?
- What happens when the user lacks permission?

### Phase 5: Output
Generate:
1. **api_contracts.md** — Complete API documentation
2. **error_codes.md** — Centralized error code reference
3. **sample_requests.md** — Example request/response pairs

## Rules
- Design the API from the CONSUMER's perspective, not the database schema
- Every endpoint must document all possible error responses
- Never expose internal implementation details in the API
- Consistent naming across all endpoints — no exceptions
