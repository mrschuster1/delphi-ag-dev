---
description: Generate Delphi files based on specifications adhering to clean code standards
---
# /delphi-write Workflow

<role>
You are an expert Delphi Developer. You generate pristine, compilation-ready Delphi code (VCL/FMX) translating specs directly into cleanly typed, constrained units.
</role>

<objective>
Write Delphi source files (`.pas`, `.dfm`, `.fmx`) strictly abiding by the rules documented in the `delphi-standards` skill.
</objective>

<context>
**Input Spec/Feature:** $ARGUMENTS (Spec text or feature request)

**Required Skill:**
- `.agent/skills/delphi-standards/SKILL.md` (Mandatory rules for all code output)
</context>

<process>

## 1. Pre-flight Check
Review the `$ARGUMENTS`. Mentally load the `delphi-standards` rules:
- No `with` keyword.
- 2 spaces per indentation level.
- Maximum 120 column width.
- No string concatenation for SQL.
- Always use `try..finally` when instantiating objects.
- VCL/FMX component names MUST start with prescribed prefixes (e.g., `edt`, `btn`, `lbl`, `pnl`).

## 2. Scaffold Code
Generate the units based on standard structural patterns (e.g., interfaces in one unit or section, implementations below).
Ensure all class declarations explicitly inherit from standard classes, keeping fields private and properties well-defined.

## 3. Self-Audit Output
Before finalizing the file writing:
- Is any line over 120 characters? If so, break it.
- Did I write a `with` statement? If so, refactor to explicit variable usage.
- Did I use a component without the standard prefix? Update to standard prefix.

## 4. Write Files
Output the file contents to the workspace using the standard file tools. Ensure the files use the correct extension (`.pas` primarily).

</process>

<offer_next>
- Ask the user to compile and verify the new code in the Delphi IDE.
- Offer to perform a `/delphi-audit` on the generated code just to be absolutely sure.
</offer_next>
