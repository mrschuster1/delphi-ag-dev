# System Architecture: delphi-ag-dev

## Agent-Driven Context Management

### Layered Context
The project operates by injecting rules into the AI context at different stages:

1.  **Rule Layer (`.agent/delphi-standards`)**: The "Legal" system. It contains the laws of the codebase (naming, safety).
2.  **Workflow Layer (`.agent/workflows`)**: The "Operating System". It defines the lifecycle of development (Spec -> Write -> TDD -> Audit).
3.  **Intelligence Layer (Skill Tooling)**: The "Enforcement". Scripts and patterns that the agent uses to verify compliance.

### The GSD Loop
The repository follows the **Get Shit Done** standard:
-   **Strategist**: Define the plan in `implementation_plan.md`.
-   **Architect**: Define the specs in `SPEC.md`.
-   **Engineer**: Execute code in small, atomic chunks.
-   **Auditor**: Verify everything via `walkthrough.md`.

### Delphi Integration
Designed specifically for the Borland/Embarcadero lineage:
-   Handles both visual (`.dfm`, `.fmx`) and logical (`.pas`) files.
-   Understands the Delphi initialization/finalization lifecycle.
