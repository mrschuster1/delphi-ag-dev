---
phase: 4
plan: 1
wave: 1
---

# Plan 4.1: Create Delphi Spec Workflow

## Objective
Develop the `/delphi-spec` workflow which will act as the design specification phase enforcing modern Delphi architecture.

## Context
- .gsd/SPEC.md
- .agent/skills/delphi-standards/SKILL.md

## Tasks

<task type="auto">
  <name>Create Delphi Spec Workflow</name>
  <files>.agent/workflows/delphi-spec.md</files>
  <action>
    Create `.agent/workflows/delphi-spec.md` that instructs the agent to:
    1. Read arbitrary user requirements provided via arguments.
    2. Convert those requirements into a structured markdown document (or multiple).
    3. Ensure architectural patterns (like MVC, MVVM or clean architecture typical for Delphi) are suggested correctly.
    4. Provide expected form/datamodule names respecting the `delphi-standards` (e.g., `TfrmCustomer` or `TdmBilling`).
  </action>
  <verify>Test-Path .agent/workflows/delphi-spec.md</verify>
  <done>The `/delphi-spec` workflow file exists and defines structural documentation generation for Delphi.</done>
</task>

## Success Criteria
- [ ] `/delphi-spec` workflow is defined in `.agent/workflows/`.
