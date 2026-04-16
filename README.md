# delphi-ag-dev — Antigravity Agent Plugin

> An Antigravity plugin that turns the multi-agent system into a senior Delphi expert.
> 🇧🇷 [Leia em Português](README.pt-BR.md)

---

## What is it

**delphi-ag-dev** activates automatically in Antigravity through its core skills whenever Delphi-related content is worked on — `.pas`, `.dpr`, `.dfm`, `.dpk`, `.dproj` files, or any mention of Object Pascal, FireMonkey, VCL, FireDAC, or RAD Studio. Once active, the Antigravity Agent applies the full Delphi Style Guide, Clean Code principles, and SOLID patterns without being asked.

---

## Features

| Command | Description |
|---|---|
| **Auto Delphi Mode** | Reading any `.pas`, `.dpr` or `.dfm` file activates the full coding standards context automatically via `delphi-standards` skill |
| **`/delphi-audit`** | Generates a complete professional technical audit with per-dimension scoring and a prioritized modernization roadmap |
| **`/delphi-tdd`** | Generates a complete DUnitX unit test suite for the project and enforces Red-Green-Refactor approach |
| **`/delphi-spec`** | Analyzes the current project source code and auto-generates a complete architectural `SPEC.md` |
| **`/delphi-write`** | Writes new code with all standards applied from the start, scaffolding `.pas`, `.dfm`, `.fmx` |

---

## Installation

To add these capabilities to any Antigravity project, simply copy the `.agent/` directory (containing the skills and workflows) into your project's root folder:

```bash
# Clone this repository
git clone https://github.com/mrschuster1/delphi-ag-dev.git

# Copy the skills and workflows to your project
# (Windows / PowerShell)
Copy-Item -Recurse -Force .\delphi-ag-dev\.agent\* .\SeuProjeto\.agent\

# (Linux / Mac)
cp -R delphi-ag-dev/.agent/* /path/to/your/project/.agent/
```

### After installation

The agent will now recognize the workflows (`/delphi-write`, etc.) and the core skill `delphi-standards` will be loaded automatically when it interacts with Delphi code.

---

## Standards Applied Automatically

### Prefixes
- `F` — fields (private attributes)
- `A` — method parameters
- `L` — local variables
- `C_` — constants (+ UPPER_CASE body)
- `T` — classes and types
- `I` — interfaces
- `E` — exceptions

### Formatting
- ✅ 2-space indentation (no tabs)
- ✅ 120-character line limit
- ✅ `begin` and `else` on their own lines
- ✅ One variable per line
- ✅ One unit per line in `uses` clause (RTL → VCL/FMX → FireDAC → Third-party → Project)

### Prohibited Commands
- ❌ `with` — causes ambiguity and debugging issues
- ❌ `Break` / `Continue` — use loop conditions instead
- ❌ `Real` — use `Double` or `Currency`
- ⚠️ `Exit` — allowed only as guard clauses at the top of a method

### Safety Rules
- ✅ One resource per `try..finally` block
- ✅ No empty `except` blocks
- ✅ SQL always parameterized (no string concatenation)
- ✅ `const` never applied to interface parameters (ARC compatibility)
- ✅ No global variables — use `class var` instead

### Component Prefixes (VCL / FMX)
`btn`, `edt`, `lbl`, `mmo`, `cbx`, `grd`, `qry`, `cnn`, `dts`, `pnl`, `tmr`, and more.

---

## Included Skills & Workflows

| Type | Name | Purpose |
|---|---|---|
| Skill | `delphi-standards` | Auto-activated on Delphi file/code detection to enforce rules |
| Workflow | `/delphi-write` | Writes complete, production-ready Delphi code following all standards |
| Workflow | `/delphi-spec` | Generates the SPEC document from source code analysis |
| Workflow | `/delphi-tdd` | Creates DUnitX unit test suites and applies TDD flow |
| Workflow | `/delphi-audit` | Deep technical audit — finding standards violations |

---

## Based on

- *Delphi Coding Standards v4.0.1* — Adriano Santos
- *Clean Code and Best Practices in Delphi* — Adriano Santos
- *Clean Code* — Robert C. Martin
- *Delphi Style Guide* — Embarcadero

---

## License

MIT © 2026
