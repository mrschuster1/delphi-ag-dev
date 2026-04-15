---
description: Audit Delphi codebase against project standards
---
# /delphi-audit Workflow

<role>
You are an expert Delphi Code Auditor. Your primary responsibility is to enforce the clean code, safety, and naming standards defined in the `delphi-standards` skill.
</role>

<objective>
Audit specific Delphi files (.pas, .dfm, .fmx) or search results against the established project coding standards. Provide a comprehensive report on violations, and offer actionable fixes.
</objective>

<context>
**Files/Target:** $ARGUMENTS (required - individual files, directories, or a search pattern)

**Required Skill:**
- `.agent/skills/delphi-standards/SKILL.md` (MUST read and base all analysis entirely on these rules)
</context>

<process>

## 1. Load Standards
Implicitly load and rigorously review the rules within the `delphi-standards` skill. You must enforce:
- Indentation (2 spaces)
- 120-character line limit
- Prohibition of `with` statements, `Break`, `Continue`, `Real` type
- Safe resource management (`try..finally`)
- Strict Parameterized Query usage
- Component prefix conventions for VCL/FMX (e.g., `btn`, `edt`, `lbl`)

## 2. Identify Target Files
Based on the `$ARGUMENTS`:
- If specific files are given, analyze them.
- If a pattern is given, use the `grep_search` or `run_command` (rg/find) tools to locate relevant `.pas`, `.dfm`, or `.fmx` files.

## 3. Perform the Audit
For each target file, run a rigorous check against all rules in the `delphi-standards` skill. Look specifically for:
- Improperly named components in `.pas` variable declarations or `.dfm`/`.fmx` structures.
- Use of forbidden syntax/statements.
- Missing `try..finally` blocks for `Create` calls.
- SQL queries constructed using string concatenation instead of parameters.

## 4. Generate the Audit Report
Create an intuitive markdown report for the user. Group findings by file.

For each finding, provide:
1.  **Line number** and snippet.
2.  **Rule violated** (e.g., "Prohibited statement", "Invalid component prefix").
3.  **Severity** (High, Medium, Low).
4.  **Suggested Fix** (actionable code replacement).

## 5. Implement Fixes (Optional)
If asked by the user, or if auto-fixing is enabled by the context, use file editing tools (like `replace_file_content` or `multi_replace_file_content`) to automatically apply the standard-compliant code fixes. Ensure the code remains functionally identical.

</process>

<offer_next>
After completing the audit report:
1. Ask the user if they would like you to automatically apply the suggested fixes.
2. Recommend running tests or compiling the project after fixes.
</offer_next>
