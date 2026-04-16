# delphi-ag-dev — Plugin Agent de Antigravity

> Un plugin de Antigravity que convierte el sistema de múltiples agentes en un programador experto senior de Delphi.
> 🇺🇸 [English](README.md) | 🇧🇷 [Português](README.pt-BR.md) | 🇪🇸 [Español](README.es.md)

---

## Qué es

**delphi-ag-dev** se activa automáticamente en Antigravity a través de sus habilidades (*skills*) principales siempre que se trabaje en contenido relacionado con Delphi: archivos `.pas`, `.dpr`, `.dfm`, `.dpk`, `.dproj`, o cualquier mención de Object Pascal, FireMonkey, VCL, FireDAC o RAD Studio. Una vez activo, el Agente Antigravity aplica de forma nativa la Guía de Estilo Oficial de Delphi, principios de *Clean Code* y patrones *SOLID* sin necesidad de pedirlo.

---

## Características destacadas

| Comando | Descripción |
|---|---|
| **Auto Delphi Mode** | Leer cualquier archivo `.pas`, `.dpr` o `.dfm` activa automáticamente todo el contexto estándar de codificación a través de la destreza `delphi-standards` |
| **`/delphi-audit`** | Genera una auditoría técnica profesional completa con puntuación por dimensión y una hoja de ruta de modernización priorizada |
| **`/delphi-tdd`** | Genera por completo una suite de pruebas unitarias DUnitX para el proyecto aplicando un enfoque *Red-Green-Refactor* |
| **`/delphi-spec`** | Analiza el código fuente del proyecto actual y autogenera una documentación arquitectónica en `SPEC.md` |
| **`/delphi-write`** | Escribe código nuevo con todos los estándares aplicados desde el inicio generados para `.pas`, `.dfm` y `.fmx` |

---

## Instalación

Para agregar estas capacidades a cualquier proyecto de Antigravity, simplemente copia el directorio `.agent/` (que incluye las habilidades y los flujos de trabajo) a la carpeta raíz temporal o principal de su proyecto:

```bash
# Clona este repositorio
git clone https://github.com/mrschuster1/delphi-ag-dev.git

# Copia las skills y workflows en el proyecto
# (Windows / PowerShell)
Copy-Item -Recurse -Force .\delphi-ag-dev\.agent\* .\SuProyecto\.agent\

# (Linux / Mac)
cp -R delphi-ag-dev/.agent/* /path/to/your/project/.agent/
```

### Después de la instalación

El agente de inmediato reconocerá los flujos de trabajo (`/delphi-write`, etc.) y la *skill* base `delphi-standards` se cargará de forma automática cuando interactúe con el código de Delphi.

---

## Estándares que se aplican automáticamente

### Prefijos de codificación
- `F` — propiedades de clase (*Fields*) (atributos privados)
- `A` — parámetros de métodos (*Arguments*)
- `L` — variables locales (*Local variables*)
- `C_` — constantes (+ CUERPO_EN_MAYUSCULAS)
- `T` — clases y tipos personalizados
- `I` — interfaces
- `E` — excepciones

### Formato y estilo visual
- ✅ Indentación de 2 espacios estrictamente (nada de tabs)
- ✅ Límite estricto de margen a 120 caracteres por línea
- ✅ `begin` y `else` en sus propias líneas y bloques independientes
- ✅ Una variable separada y declarada por línea
- ✅ Una unidad (unit) por línea en la cláusula `uses` organizada estructuralmente (RTL → VCL/FMX → FireDAC → Herramientas Externas → Proyecto)

### Comandos Prohibidos
- ❌ Uso de `with`: provoca ambigüedad y problemas graves de depuración
- ❌ Uso de `Break` / `Continue`: se deben emplear condiciones lógicas en los bucles
- ❌ El tipo `Real`: obsoleto, se debe usar siempre `Double` o `Currency`
- ⚠️ Instrucción `Exit`: se permite exclusivamente al inicio del método como mecanismo de cláusulas protectoras (Guard clauses)

### Reglas de Prevención y Seguridad
- ✅ Apenas un único recurso liberado por cada bloque de `try..finally`
- ✅ Prohibidos drásticamente los bloques `except` ocultos/vacíos
- ✅ Código de bases de datos/SQL siempre manejado a través de parámetros (QQuery Params), sin concatenación vulgar de cadenas para evadir SQL Injections
- ✅ Empleo de `const` no se aplica globalmente a parámetros bajo el cuidado de interfaces para mantener retrocompatibilidad (ARC)
- ✅ Desuso estricto de variables globales, adaptadas a ámbito local, clases u objetos dinámicos `class var`

### Prefijos y estandarización de Componentes (VCL / FMX)
`btn`, `edt`, `lbl`, `mmo`, `cbx`, `grd`, `qry`, `cnn`, `dts`, `pnl`, `tmr`, entre otros guiados de cerca por la normativa oficial de la IDE.

---

## Workflows y Skills Disponibles

| Categoría | Nombre | Propósito |
|---|---|---|
| Skill | `delphi-standards` | Se activa de forma reactiva al localizarse detección de archivos o sintaxis Delphi para asimilar normativas de calidad |
| Workflow | `/delphi-write` | Elabora código Delphi completo y apto para producción sin violar reglas preestablecidas |
| Workflow | `/delphi-spec` | Compilador automático de informes con documentación algorítmica desde lecturas de código natural |
| Workflow | `/delphi-tdd` | Molde arquitectónico creador de TDD a través de DUnitX suites |
| Workflow | `/delphi-audit` | Escáner algorítmico intensivo sobre fallos técnicos o deuda estructural — enuncia fallos de convenciones de código |

---

## Basado y fundamentado bajo

- *Delphi Coding Standards v4.0.1* — Adriano Santos
- *Clean Code and Best Practices in Delphi* — Adriano Santos
- *Clean Code* — Robert C. Martin
- *Delphi Style Guide* — Embarcadero

---

## Licencia

MIT © 2026
