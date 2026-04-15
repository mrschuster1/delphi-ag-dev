---
phase: 2
plan: 1
wave: 1
---

# Plan 2.1: Create Delphi Audit Workflow

## Objective
Develop the `/delphi-audit` workflow prioritizing automated reviews of existing Delphi (.pas, .dfm) files against the newly created `delphi-standards` skill.

## Context
- .gsd/SPEC.md
- .agent/skills/delphi-standards/SKILL.md

## Tasks

<task type="auto">
  <name>Create Delphi Audit Workflow</name>
  <files>.agent/workflows/delphi-audit.md</files>
  <action>
    Create `.agent/workflows/delphi-audit.md` that instructs the agent to:
    1. Read the provided Delphi source file(s) from arguments.
    2. Base its analysis entirely on the rules defined in `delphi-standards`.
    3. Perform a rigorous stylistic, safety, and component-prefix audit.
    4. Provide Markdown-based reports and suggest/implement actionable code fixes.
  </action>
  <verify>Test-Path .agent/workflows/delphi-audit.md</verify>
  <done>Workflow exists and correctly bridges the auditing intent to the delphi-standards skill constraints.</done>
</task>

## Success Criteria
- [ ] `/delphi-audit` workflow is defined in `.agent/workflows/`.
