# delphi-ag-dev — Plugin Agent de Antigravity

> Un plugin de Antigravity que convierte el sistema multi-agente en un **experto senior en Delphi**.
>
> 🇺🇸 [English](README.md) · 🇧🇷 [Português](README.pt-BR.md) · 🇪🇸 [Español](README.es.md)

---

## ¿Qué es?

**delphi-ag-dev** es un plugin para el sistema de IA multi-agente **Antigravity** que carga un conjunto de **Skills** y **Workflows** para hacer que cualquier agente de IA se comporte como un desarrollador Delphi de nivel senior.

Una vez instalado, el agente aplica automáticamente:
- La **Guía de Estilo de Delphi** oficial (Embarcadero)
- Principios de **Clean Code** adaptados para Object Pascal
- Patrones de diseño **SOLID** aplicados a arquitecturas Delphi
- Metodología de desarrollo guiado por pruebas con **DUnitX**
- Convenciones de nomenclatura de componentes **VCL / FMX**

El plugin se activa siempre que se detecte contenido relacionado con Delphi — archivos `.pas`, `.dpr`, `.dfm`, `.dpk`, `.dproj`, o cualquier mención de Object Pascal, FireMonkey, VCL, FireDAC o RAD Studio.

> **Basado en** el plugin original [adrianosantostreina/delphi-dev](https://github.com/adrianosantostreina/delphi-dev) para Claude Code, completamente portado y adaptado para el framework Antigravity.

---

## Características

| Comando | Descripción |
|---|---|
| **Modo Auto Delphi** | Cualquier interacción con archivos `.pas`, `.dpr` o `.dfm` carga automáticamente todo el contexto de calidad de código Delphi a través de la *skill* `delphi-standards` |
| **`/delphi-audit`** | Ejecuta una auditoría técnica profesional completa con puntuación por dimensión y una hoja de ruta de modernización priorizada — similar a la revisión de código de un arquitecto senior |
| **`/delphi-tdd`** | Flujo TDD completo con DUnitX: escribe primero el test que falla (Red), luego la implementación (Green) y finalmente refactoriza |
| **`/delphi-spec`** | Analiza el código fuente existente y genera automáticamente un documento arquitectónico completo `SPEC.md` |
| **`/delphi-write`** | Crea la estructura de nuevas unidades Delphi (`.pas`, `.dfm`, `.fmx`) con todas las convenciones de nomenclatura, prefijos y reglas de seguridad aplicadas desde la línea 1 |

---

## Instalación

Copia el directorio `.agent/` (que contiene skills y workflows) en la carpeta raíz de tu proyecto.

```bash
# 1. Clona este repositorio
git clone https://github.com/mrschuster1/delphi-ag-dev.git

# 2. Copia skills y workflows en tu proyecto
# Windows / PowerShell
Copy-Item -Recurse -Force .\delphi-ag-dev\.agent\* .\TuProyecto\.agent\

# Linux / macOS
cp -R delphi-ag-dev/.agent/* /ruta/a/tu/proyecto/.agent/
```

Listo. El agente reconocerá los flujos de trabajo de Delphi y aplicará automáticamente la *skill* `delphi-standards` a cualquier interacción con Delphi.

---

## Estándares Aplicados Automáticamente

### Prefijos de nomenclatura

| Prefijo | Se aplica a | Ejemplo |
|---|---|---|
| `F` | Campos de clase (atributos privados) | `FNombreCliente: string` |
| `A` | Parámetros de métodos | `procedure Guardar(const ANombre: string)` |
| `L` | Variables locales | `LQuery: TFDQuery` |
| `C_` | Constantes (+ CUERPO_MAYUSCULAS) | `C_MAX_INTENTOS = 3` |
| `T` | Tipos y clases | `TRepositorioCliente` |
| `I` | Interfaces | `IRepositorioCliente` |
| `E` | Clases de excepción | `EClienteNoEncontrado` |

### Reglas de formato

- ✅ **Sangría de 2 espacios** — las tabulaciones están prohibidas
- ✅ **Límite de 120 caracteres por línea** — aplicado estrictamente
- ✅ `begin` y `else` siempre en **sus propias líneas**
- ✅ **Una variable por línea** en bloques `var`
- ✅ Cláusula `uses` ordenada: `RTL → VCL/FMX → FireDAC → Terceros → Proyecto`

### Construcciones prohibidas

| Construcción | Motivo | Alternativa |
|---|---|---|
| `with` | Crea ambigüedad e imposibilita la depuración | Referencias explícitas de variable |
| `Break` / `Continue` | Flujo de control oculto | Rediseña el bucle con condiciones adecuadas |
| `Real` | Obsoleto e impreciso | Usa `Double` o `Currency` |
| `Exit` (en el medio del método) | Reduce la legibilidad | Solo permitido como *guard clauses* al inicio del método |

### Reglas de seguridad

- ✅ **Un recurso por `try..finally`** — nunca agrupar múltiples objetos
- ✅ **Sin bloques `except` vacíos** — las excepciones deben ser manejadas o registradas
- ✅ **SQL siempre parametrizado** — la concatenación de cadenas para queries está bloqueada
- ✅ **Sin `const` en parámetros de interfaz** — mantiene compatibilidad con ARC
- ✅ **Sin variables globales** — usa `class var` o inyección de dependencias

### Prefijos de componentes (VCL / FMX)

| Prefijo | Componente |
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

## Arquitectura

```
.agent/
├── skills/
│   └── delphi-standards/
│       └── SKILL.md          ← Reglas centrales de codificación Delphi (fuente única de la verdad)
└── workflows/
    ├── delphi-audit.md       ← Comando /delphi-audit
    ├── delphi-tdd.md         ← Comando /delphi-tdd
    ├── delphi-spec.md        ← Comando /delphi-spec
    └── delphi-write.md       ← Comando /delphi-write
```

---

## Skills y Workflows incluidos

| Tipo | Nombre | Propósito |
|---|---|---|
| Skill | `delphi-standards` | Se carga automáticamente al detectar contenido Delphi — aplica todas las reglas de calidad de código |
| Workflow | `/delphi-write` | Crea unidades Delphi completas y listas para producción siguiendo todos los estándares |
| Workflow | `/delphi-spec` | Genera un documento SPEC arquitectónico a partir del análisis del código fuente |
| Workflow | `/delphi-tdd` | Orquesta el ciclo completo de TDD Red-Green-Refactor con DUnitX |
| Workflow | `/delphi-audit` | Revisión técnica profunda del código — puntúa la calidad en múltiples dimensiones |

---

## Basado en

- *Delphi Coding Standards v4.0.1* — Adriano Santos
- *Clean Code and Best Practices in Delphi* — Adriano Santos
- *Clean Code* — Robert C. Martin
- *Delphi Style Guide* — Embarcadero

---

## Licencia

MIT © 2026

---

## Política de Privacidad

[Ver Política de Privacidad](privacy-policy.es.md)
