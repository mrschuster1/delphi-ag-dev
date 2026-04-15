---
name: delphi-standards
description: Enforce Delphi clean code rules, guidelines, and prefix standards (VCL/FMX).
---

# Delphi Development Standards (VCL & FMX)

<objective>
To govern all Delphi-related programming tasks in the workspace, ensuring the code complies with Delphi Style Guides, Clean Code, and SOLID patterns, with specific support for Delphi 11+ utilizing VCL (primary) and FMX.
</objective>

<rules>
## Formatting rules
- Use strictly 2-space indentation (no tabs allowed).
- Max line length is 120 characters limit.
- `begin` and `else` keywords must be placed on their own individual lines.
- One variable per line in `var` declarations.
- One unit per line in `uses` clause, sorted logically (e.g., RTL → VCL/FMX → FireDAC → Third-party → Project).

## Prohibited Commands & Practices
- **`with`**: Strictly prohibited due to scope ambiguity.
- **`Break` / `Continue`**: Prohibited. Always use proper loop conditions rather than breaking execution ungracefully.
- **`Real`**: Prohibited. Use `Double` or `Currency` instead.
- **`Exit`**: Only allowed at the very beginning of a method as a guard clause (early returns). Do not use deep within logic.

## Safety Constraints
- Require one dedicated resource allocation per `try..finally` block. Do not allocate multiple disjoint resources before a single `try`.
- Prohibit empty `except` blocks. All caught exceptions must be logged or adequately handled.
- Guarantee that all SQL commands use parameters (parameterized SQL). String concatenation for building SQL is strictly forbidden.
- Prohibit `const` specifier applied to interface type parameters to maintain full ARC compatibility.
- Ensure zero reliance on global variables - prefer `class var` or injected dependencies instead.

## Naming & Prefix Conventions
### Core Language Prefixes
- `F`: Private attributes/fields
- `A`: Method or function parameters
- `L`: Local variables
- `C_`: Constants (with UPPER_CASE body like `C_DEFAULT_TIMEOUT`)
- `T`: Classes and Types
- `I`: Interfaces
- `E`: Exceptions

### Component Prefixes
When naming visual or non-visual UI/Data components, you MUST refer to the official list of prefixes. 
Consult [references/component-prefixes.md](references/component-prefixes.md) to find the correct prefix (e.g., `btn` for `TButton`, `qry` for `TFDQuery`). Name components logically combining the prefix and a camelCased descriptive name (e.g., `edtNomeCliente`).
</rules>
