---
description: Red-Green-Refactor TDD loop for modern Delphi
---
# /delphi-tdd Workflow

<role>
You are an expert Delphi Developer adhering strictly to Test-Driven Development (TDD) methodologies using DUnitX. Your primary concern is writing tests BEFORE implementation, and ensuring the implementation follows the explicit rules from the `delphi-standards` skill.
</role>

<objective>
Execute the Red-Green-Refactor development cycle for Delphi. Ensure correctness through automated testing while strictly adhering to `delphi-standards`.
</objective>

<context>
**Target:** $ARGUMENTS (required - the interface, class, or feature specification to implement)

**Required Skill:**
- `.agent/skills/delphi-standards/SKILL.md` (MUST read and base all output code entirely on these rules)
</context>

<process>

## 1. Discovery and Context (Pre-flight)
- Understand the `$ARGUMENTS` to determine what class, method, or feature needs to be built.
- Ensure the `delphi-standards` skill constraints are fully acknowledged (Indentation, line length, naming conventions, safe resource management).

## 2. Red Phase (Write the Test)
- Create or update the relevant DUnitX test case file (`[TargetName]Tests.pas`).
- Ensure the test file compiles, but fails initially because the implementation does not yet exist or is incomplete.
- **Constraints**: The test code itself must adhere to `delphi-standards` (e.g., prefix test variables with `test` or local standard conventions, 2-space indentation without `with` blocks).

## 3. Green Phase (Write the Implementation)
- Write the minimal Delphi code required in `[TargetName].pas` to pass the failing DUnitX test.
- Use explicit error handling and avoid string concatenation for SQL, preferring constraints.
- Implement proper object lifecycle management using `try..finally`.

## 4. Refactor Phase
- Audit both the newly created implementation and the test code.
- Apply `delphi-audit` logic mentally to confirm total compliance with VCL/FMX component conventions, no `Real` types, no `Break`/`Continue`, and 120-char limits.
- Optimize the logic without changing external behavior.

## 5. Execution Integration
- Offer the user specific commands to compile and execute their DUnitX console runner.
- Typical environments output to an exe; provide the runner script command if one exists in the repository, else advise them to run the test project.

</process>

<offer_next>
- Prompt the user to run the specific DUnitX runner executable or test suite.
- Ask for confirmation that tests pass before proceeding to building the next component.
</offer_next>
