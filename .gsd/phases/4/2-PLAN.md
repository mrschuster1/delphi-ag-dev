---
phase: 4
plan: 2
wave: 1
---

# Plan 4.2: Create Delphi Write Workflow

## Objective
Develop the `/delphi-write` workflow designed to generate standard Delphi code files based on specs, enforcing coding conventions from the start.

## Context
- .gsd/SPEC.md
- .agent/skills/delphi-standards/SKILL.md

## Tasks

<task type="auto">
  <name>Create Delphi Write Workflow</name>
  <files>.agent/workflows/delphi-write.md</files>
  <action>
    Create `.agent/workflows/delphi-write.md` that instructs the agent to:
    1. Scaffold Delphi units (.pas, .dfm/.fmx) given a user prompt or spec output.
    2. Completely prohibit writing forbidden statements like `with`, limit lines to 120 chars, and enforce 2-space indentation.
    3. Adopt best practices inherently (safe resource freeing with `try..finally`).
    4. Auto-generate standard GUI or component boilerplate using the specified component prefixes.
  </action>
  <verify>Test-Path .agent/workflows/delphi-write.md</verify>
  <done>The `/delphi-write` workflow file exists and defines code generation constraints for Delphi.</done>
</task>

## Success Criteria
- [ ] `/delphi-write` workflow is defined in `.agent/workflows/`.
