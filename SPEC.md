# Project Specification: delphi-ag-dev

## Infrastructure & Standards for AI-Driven Delphi Development

### 🎯 Mission
To provide a production-grade context layer for AI agents (like Antigravity and Claude) that ensures generated Delphi code is safe, standard-compliant, and architectural sound.

### 🧩 Core Components

1.  **Delphi Standards Skill (`.agent/delphi-standards`)**
    -   Universal rules for naming, formatting, and safety.
    -   VCL/FMX component prefix mapping.
2.  **Workflows (`.agent/workflows`)**
    -   `/delphi-spec`: Architectural blueprinting.
    -   `/delphi-write`: Standardized code scaffolding.
    -   `/delphi-tdd`: Test-driven development loop.
    -   `/delphi-audit`: Automated quality enforcement.
3.  **Documentation**
    -   Trilingual READMEs (EN, PT, ES).
    -   GSD-Style operational manuals.

### 🏛️ Architecture Patterns
-   **Context Engineering**: Injection of rules via skill metadata.
-   **GSD Integration**: Utilization of Get Shit Done protocols for project management.
-   **Clean Code**: Enforcement of SOLID and Embarcadero/Adriano Santos style guides.

### 🔒 Safety & Compatibility
-   SQL Parameterization mandatory.
-   Resource protection (`try..finally`) mandatory.
-   Delphi 11+ compatibility.
-   FPC/Lazarus support (partial).
