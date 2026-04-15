---
phase: 3
plan: 1
wave: 1
---

# Plan 3.1: Create Delphi TDD Workflow

## Objective
Develop the `/delphi-tdd` workflow to enforce a Test-Driven Development (Red-Green-Refactor) process for modern Delphi using methodologies aligned with the `delphi-standards` skill.

## Context
- .gsd/SPEC.md
- .agent/skills/delphi-standards/SKILL.md

## Tasks

<task type="auto">
  <name>Create Delphi TDD Workflow</name>
  <files>.agent/workflows/delphi-tdd.md</files>
  <action>
    Create `.agent/workflows/delphi-tdd.md` that instructs the agent to:
    1. Adopt the TDD lifecycle: Red (write failing DUnitX test first), Green (write minimal code to pass), Refactor (align code with `delphi-standards`).
    2. Read target interface/spec from user arguments.
    3. Ensure generated test and implementation files adhere strictly to the clean code constraints (e.g., 2-space indentation, 120 char limit).
    4. If applicable, recommend the execution of DUnitX runner or provide integration points.
  </action>
  <verify>Test-Path .agent/workflows/delphi-tdd.md</verify>
  <done>The `/delphi-tdd` workflow file exists and defines a clear test-first approach for Delphi.</done>
</task>

## Success Criteria
- [ ] `/delphi-tdd` workflow is defined in `.agent/workflows/`.
