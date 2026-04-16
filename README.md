# delphi-ag-dev — Antigravity Agent Plugin

> An Antigravity plugin that turns the multi-agent system into a **senior Delphi expert**.
>
> 🇺🇸 [English](README.md) · 🇧🇷 [Português](README.pt-BR.md) · 🇪🇸 [Español](README.es.md)

---

## What is it?

**delphi-ag-dev** is a plugin for the **Antigravity** multi-agent AI system that loads a set of **Skills** and **Workflows** to make any AI agent behave like a senior Delphi engineer.

Once installed, the agent automatically enforces:
- The official **Delphi Style Guide** (Embarcadero)
- **Clean Code** principles adapted for Object Pascal
- **SOLID** design patterns applied to Delphi architectures
- **DUnitX** test-driven development methodology
- **VCL / FMX** component naming conventions

The plugin activates whenever Delphi-related content is detected — `.pas`, `.dpr`, `.dfm`, `.dpk`, `.dproj` files, or any mention of Object Pascal, FireMonkey, VCL, FireDAC, or RAD Studio.

> **Based on** the original [adrianosantostreina/delphi-dev](https://github.com/adrianosantostreina/delphi-dev) Claude Code plugin, fully ported and adapted for the Antigravity framework.

---

## Features

| Command | Description |
|---|---|
| **Auto Delphi Mode** | Any interaction with `.pas`, `.dpr` or `.dfm` files automatically loads the full Delphi code-quality context via the `delphi-standards` skill |
| **`/delphi-audit`** | Runs a professional technical audit with dimensional scoring and a prioritized modernization roadmap — similar to a senior architect's code review |
| **`/delphi-tdd`** | Full TDD flow using DUnitX: writes the failing test first (Red), then the implementation (Green), then refactors |
| **`/delphi-spec`** | Analyzes existing source code and auto-generates a complete `SPEC.md` architectural document |
| **`/delphi-write`** | Scaffolds new Delphi units (`.pas`, `.dfm`, `.fmx`) with all naming conventions, prefixes, and safety rules applied from line 1 |

---

## Installation

Copy the `.agent/` directory (containing skills and workflows) into your project's root folder.

```bash
# 1. Clone this repository
git clone https://github.com/mrschuster1/delphi-ag-dev.git

# 2. Copy skills and workflows into your project
# Windows / PowerShell
Copy-Item -Recurse -Force .\delphi-ag-dev\.agent\* .\YourProject\.agent\

# Linux / macOS
cp -R delphi-ag-dev/.agent/* /path/to/your/project/.agent/
```

That's it. The agent will now recognize the Delphi workflows and automatically apply the `delphi-standards` skill to any Delphi interaction.

---

## Standards Applied Automatically

### Naming Prefixes

| Prefix | Applies To | Example |
|---|---|---|
| `F` | Class fields (private attributes) | `FClientName: string` |
| `A` | Method parameters | `procedure Save(const AName: string)` |
| `L` | Local variables | `LQuery: TFDQuery` |
| `C_` | Constants (+ UPPER_CASE body) | `C_MAX_RETRIES = 3` |
| `T` | Types and classes | `TClientRepository` |
| `I` | Interfaces | `IClientRepository` |
| `E` | Exception classes | `EClientNotFound` |

### Formatting Rules

- ✅ **2-space indentation** — tabs are forbidden
- ✅ **120-character line limit** — strict enforcement
- ✅ `begin` and `else` always on their **own lines**
- ✅ **One variable per line** in `var` blocks
- ✅ `uses` clause ordered: `RTL → VCL/FMX → FireDAC → Third-party → Project`

### Prohibited Constructs

| Construct | Reason | Alternative |
|---|---|---|
| `with` | Creates ambiguity, makes debugging impossible | Explicit variable references |
| `Break` / `Continue` | Hidden control flow | Redesign loop with proper conditions |
| `Real` | Deprecated, imprecise | Use `Double` or `Currency` |
| `Exit` (mid-method) | Reduces readability | Only allowed as guard clauses at the method top |

### Safety Rules

- ✅ **One resource per `try..finally`** — never group multiple objects
- ✅ **No empty `except` blocks** — exceptions must be handled or logged
- ✅ **SQL always parameterized** — string concatenation for queries is blocked
- ✅ **No `const` on interface parameters** — maintains ARC compatibility
- ✅ **No global variables** — use `class var` or dependency injection instead

### Component Prefixes (VCL / FMX)

| Prefix | Component |
|---|---|
| `btn` | TButton |
| `edt` | TEdit |
| `lbl` | TLabel |
| `mmo` | TMemo |
| `cbx` | TComboBox |
| `grd` | TDBGrid / TStringGrid |
| `qry` | TFDQuery |
| `cnn` | TFDConnection |
| `dts` | TDataSource |
| `pnl` | TPanel |
| `tmr` | TTimer |
| `img` | TImage |
| `pgc` | TPageControl |
| `tab` | TTabSheet |
| `tbar` | TToolBar |
| `sbar` | TStatusBar |

---

## Architecture

```
.agent/
├── skills/
│   └── delphi-standards/
│       └── SKILL.md          ← Core Delphi coding rules (single source of truth)
└── workflows/
    ├── delphi-audit.md       ← /delphi-audit command
    ├── delphi-tdd.md         ← /delphi-tdd command
    ├── delphi-spec.md        ← /delphi-spec command
    └── delphi-write.md       ← /delphi-write command
```

---

## Included Skills & Workflows

| Type | Name | Purpose |
|---|---|---|
| Skill | `delphi-standards` | Loaded automatically on Delphi content detection — enforces all code quality rules |
| Workflow | `/delphi-write` | Scaffolds complete, production-ready Delphi units following all standards |
| Workflow | `/delphi-spec` | Generates an architectural SPEC document from source code analysis |
| Workflow | `/delphi-tdd` | Orchestrates full Red-Green-Refactor TDD cycle with DUnitX |
| Workflow | `/delphi-audit` | Deep technical code review — scores quality across multiple dimensions |

---

## Based on

- *Delphi Coding Standards v4.0.1* — Adriano Santos
- *Clean Code and Best Practices in Delphi* — Adriano Santos
- *Clean Code* — Robert C. Martin
- *Delphi Style Guide* — Embarcadero

---

## License

MIT © 2026

---

## Privacy Policy

[View Privacy Policy](privacy-policy.md)
