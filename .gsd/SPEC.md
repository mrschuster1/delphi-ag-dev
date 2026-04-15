# SPEC.md — Project Specification

> **Status**: `FINALIZED`

## Vision
Create a comprehensive suite of Antigravity skills, agents, and workflows for Delphi development (focused on Delphi 11+ and VCL/FMX) inspired by the `adrianosantostreina/delphi-dev` Claude Code plugin. This will enforce Clean Code, SOLID principles, and the Delphi Style Guide automatically via specialized commands and contexts.

## Goals
1. Reproduce the full set of coding rules (styles, component prefixes, prohibited commands, safety rules).
2. Create specialized workflows and skills for tasks such as Code Writing (`/delphi-write`), Auditing (`/delphi-audit`), TDD (`/delphi-tdd`), and Specification (`/delphi-spec`).
3. Optimize the instructions for Delphi 11+ ensuring compatibility with modern VCL (primary) and FMX frameworks.

## Non-Goals (Out of Scope)
- Legacy Delphi support (below Delphi 11).
- Applying rules directly to the local project's `PROJECT_RULES.md` (everything must be self-contained in reusable isolated Antigravity skills/workflows).

## Users
Delphi Developers requesting automated assistance via Antigravity inside modern Delphi codebases.

## Constraints
- Must follow Antigravity's `.agent/skills/` and `.agent/workflows/` architecture conventions.
- Must accurately port all safety guards (e.g., prohibition of `with`, strict `try..finally` scope).

## Success Criteria
- [ ] At least one core Delphi standards skill is created outlining all code-level principles.
- [ ] Workflows for auditing, writing, and testing are functional and available as commands.
- [ ] Accurate transfer of specific FMX/VCL component prefix mappings.
