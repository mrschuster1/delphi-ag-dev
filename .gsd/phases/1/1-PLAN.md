---
phase: 1
plan: 1
wave: 1
---

# Plan 1.1: Create Core Delphi Standards Skill

## Objective
Build the core `delphi-standards` skill containing all stylistic, safety, and component prefix rules explicitly designed for Antigravity logic.

## Context
- .gsd/SPEC.md
- .gsd/phases/1/RESEARCH.md

## Tasks

<task type="auto">
  <name>Create Delphi Standards Skill</name>
  <files>.agent/skills/delphi-standards/SKILL.md, .agent/skills/delphi-standards/references/component-prefixes.md</files>
  <action>
    - Create `.agent/skills/delphi-standards/references/component-prefixes.md` and populate it with the full VCL/FMX component prefixes mapping from the research.
    - Create `.agent/skills/delphi-standards/SKILL.md` outlining the core rules: FMX/VCL support (Delphi 11+), formatting rules (2-space intent, max 120 lines), prohibited commands (`with`, `Break`, `Continue`, `Real`), specific safety constraints (no global vars, parameterized SQL, proper try/finally).
    - It must explicitly state how these rules govern all Delphi coding tasks in the agent.
  </action>
  <verify>Test-Path .agent/skills/delphi-standards/SKILL.md</verify>
  <done>SKILL.md successfully defines all required Delphi style and code-safety constraints.</done>
</task>

## Success Criteria
- [ ] `delphi-standards/SKILL.md` exists and defines formatting, naming, and safety rules.
- [ ] Component prefixes are externalized into a reference MD file within the skill directory.
