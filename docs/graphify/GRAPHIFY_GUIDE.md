# Graphify Guide

Graphify creates a **persistent architecture map** of your project.

## When to run
- project grows beyond ~20 files
- you frequently restart sessions
- you dispatch parallel agents
- you repeatedly ask “where is X?”

## Why it reduces tokens
Instead of re-reading raw files each time, agents query the graph outputs.

## How to use
1. Run Graphify on the repo.
2. Keep Graphify outputs out of normal agent context unless queried.
3. Re-run incrementally after milestones.

## What to do with Graphify outputs
- Use the report to identify “hot” modules and surprising dependencies.
- Use the graph to answer architecture questions quickly.
