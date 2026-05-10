---
name: performance-audit
description: Systematic performance analysis and optimization recommendations
activation: manual
---

# Performance Audit Skill

## Purpose
Identify performance bottlenecks and provide actionable optimization recommendations.

## Protocol

### Phase 1: Define Performance Goals
1. What is the current performance? (response time, throughput, memory)
2. What is the target performance?
3. What are the critical paths (user-facing operations that must be fast)?
4. What is the expected load (concurrent users, data volume)?

### Phase 2: Static Analysis (Code Review for Performance)
Scan for common bottlenecks:

#### Computation
- Unnecessary loops within loops (O(n²) or worse)
- Redundant calculations (same result computed multiple times)
- Blocking operations on critical paths
- Missing caching for expensive, repeatable operations

#### Data Access
- N+1 query patterns (fetching related data in a loop)
- Missing indexes on frequently queried fields
- Fetching more data than needed (SELECT * when only 2 fields are used)
- No pagination on large datasets
- Missing connection pooling

#### Memory
- Large objects held in memory unnecessarily
- Event listeners or subscriptions not cleaned up
- Accumulating data in collections without bounds
- Large file processing without streaming

#### Network
- Sequential API calls that could be parallel
- Missing compression on large payloads
- No caching headers for static/semi-static data
- Chatty protocols (many small requests vs fewer batched requests)

### Phase 3: Generate Report

| # | Location | Issue | Impact | Fix | Effort |
|---|----------|-------|--------|-----|--------|

Impact: 🔴 High / 🟡 Medium / 🟢 Low
Effort: Quick fix / Moderate / Major refactor

### Phase 4: Prioritize
1. Sort by Impact DESC, Effort ASC (high impact + quick fix = do first)
2. Group into: Quick Wins / Planned Improvements / Architectural Changes
3. Estimate expected improvement for each fix

## Rules
- Measure before optimizing — never optimize based on assumptions
- Focus on critical paths first (what users actually experience)
- One optimization at a time — measure after each change
- Document the before/after metrics for each optimization
