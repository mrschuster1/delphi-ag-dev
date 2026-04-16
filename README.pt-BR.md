# delphi-ag-dev — Plugin Agent do Antigravity

> Um plugin para o Antigravity que transforma o sistema multi-agente em um **especialista sênior em Delphi**.
>
> 🇺🇸 [English](README.md) · 🇧🇷 [Português](README.pt-BR.md) · 🇪🇸 [Español](README.es.md)

---

## O que é?

**delphi-ag-dev** é um plugin para o sistema de IA multi-agente **Antigravity** que carrega um conjunto de **Skills** e **Workflows** para fazer qualquer agente de IA se comportar como um desenvolvedor Delphi de nível sênior.

Uma vez instalado, o agente passa a impor automaticamente:
- O **Delphi Style Guide** oficial (Embarcadero)
- Princípios de **Clean Code** adaptados para Object Pascal
- Padrões de design **SOLID** aplicados a arquiteturas Delphi
- Metodologia de desenvolvimento orientado a testes com **DUnitX**
- Convenções de nomenclatura de componentes **VCL / FMX**

O plugin é ativado sempre que um conteúdo relacionado ao Delphi for detectado — arquivos `.pas`, `.dpr`, `.dfm`, `.dpk`, `.dproj`, ou qualquer menção a Object Pascal, FireMonkey, VCL, FireDAC ou RAD Studio.

> **Baseado no** plugin original [adrianosantostreina/delphi-dev](https://github.com/adrianosantostreina/delphi-dev) para Claude Code, totalmente portado e adaptado para o framework Antigravity.

---

## Recursos

| Comando | Descrição |
|---|---|
| **Modo Auto Delphi** | Qualquer interação com arquivos `.pas`, `.dpr` ou `.dfm` carrega automaticamente todo o contexto de qualidade de código Delphi através da *skill* `delphi-standards` |
| **`/delphi-audit`** | Executa uma auditoria técnica profissional com pontuação por dimensão e um roadmap de modernização priorizado — semelhante à revisão de código de um arquiteto sênior |
| **`/delphi-tdd`** | Fluxo completo de TDD com DUnitX: escreve o teste que falha primeiro (Red), depois a implementação (Green) e então refatora |
| **`/delphi-spec`** | Analisa o código-fonte existente e gera automaticamente um documento arquitetural completo `SPEC.md` |
| **`/delphi-write`** | Cria a estrutura de novas unidades Delphi (`.pas`, `.dfm`, `.fmx`) com todas as convenções de nomenclatura, prefixos e regras de segurança aplicados desde a linha 1 |

---

## Instalação

Copie o diretório `.agent/` (contendo skills e workflows) para a pasta raiz do seu projeto.

```bash
# 1. Clone este repositório
git clone https://github.com/mrschuster1/delphi-ag-dev.git

# 2. Copie skills e workflows para o seu projeto
# Windows / PowerShell
Copy-Item -Recurse -Force .\delphi-ag-dev\.agent\* .\SeuProjeto\.agent\

# Linux / macOS
cp -R delphi-ag-dev/.agent/* /caminho/para/seu/projeto/.agent/
```

Pronto. O agente passará a reconhecer os fluxos de trabalho Delphi e aplicará automaticamente a *skill* `delphi-standards` a qualquer interação Delphi.

---

## Padrões Aplicados Automaticamente

### Prefixos de Nomenclatura

| Prefixo | Aplica-se a | Exemplo |
|---|---|---|
| `F` | Atributos da classe (campos privados) | `FNomeCliente: string` |
| `A` | Parâmetros de métodos | `procedure Salvar(const ANome: string)` |
| `L` | Variáveis locais | `LQuery: TFDQuery` |
| `C_` | Constantes (+ CORPO_MAIUSCULO) | `C_MAX_TENTATIVAS = 3` |
| `T` | Tipos e classes | `TRepositorioCliente` |
| `I` | Interfaces | `IRepositorioCliente` |
| `E` | Classes de exceção | `EClienteNaoEncontrado` |

### Regras de Formatação

- ✅ **Indentação de 2 espaços** — tabulações são proibidas
- ✅ **Limite de 120 caracteres por linha** — aplicado rigorosamente
- ✅ `begin` e `else` sempre em **linhas próprias**
- ✅ **Uma variável por linha** em blocos `var`
- ✅ Cláusula `uses` ordenada: `RTL → VCL/FMX → FireDAC → Terceiros → Projeto`

### Construções Proibidas

| Construção | Motivo | Alternativa |
|---|---|---|
| `with` | Cria ambiguidade e impossibilita o debug | Referências explícitas de variável |
| `Break` / `Continue` | Fluxo de controle oculto | Redesenhe o laço com condições adequadas |
| `Real` | Obsoleto e impreciso | Use `Double` ou `Currency` |
| `Exit` (meio do método) | Reduz a legibilidade | Permitido apenas como *guard clauses* no início do método |

### Regras de Segurança

- ✅ **Um recurso por `try..finally`** — nunca agrupe múltiplos objetos
- ✅ **Sem blocos `except` vazios** — exceções devem ser tratadas ou registradas
- ✅ **SQL sempre parametrizado** — concatenação de strings para queries é bloqueada
- ✅ **Sem `const` em parâmetros de interface** — mantém compatibilidade com ARC
- ✅ **Sem variáveis globais** — use `class var` ou injeção de dependência

### Prefixos de Componentes (VCL / FMX)

| Prefixo | Componente |
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

## Arquitetura

```
.agent/
├── skills/
│   └── delphi-standards/
│       └── SKILL.md          ← Regras centrais de codificação Delphi (fonte única da verdade)
└── workflows/
    ├── delphi-audit.md       ← Comando /delphi-audit
    ├── delphi-tdd.md         ← Comando /delphi-tdd
    ├── delphi-spec.md        ← Comando /delphi-spec
    └── delphi-write.md       ← Comando /delphi-write
```

---

## Skills e Workflows Incluídos

| Tipo | Nome | Finalidade |
|---|---|---|
| Skill | `delphi-standards` | Carregada automaticamente na detecção de conteúdo Delphi — impõe todas as regras de qualidade de código |
| Workflow | `/delphi-write` | Cria unidades Delphi completas e prontas para produção seguindo todos os padrões |
| Workflow | `/delphi-spec` | Gera um documento SPEC arquitetural a partir da análise do código-fonte |
| Workflow | `/delphi-tdd` | Orquestra o ciclo completo de TDD Red-Green-Refactor com DUnitX |
| Workflow | `/delphi-audit` | Revisão técnica aprofundada do código — pontua a qualidade em múltiplas dimensões |

---

## Baseado em

- *Delphi Coding Standards v4.0.1* — Adriano Santos
- *Clean Code and Best Practices in Delphi* — Adriano Santos
- *Clean Code* — Robert C. Martin
- *Delphi Style Guide* — Embarcadero

---

## Licença

MIT © 2026

---

## Política de Privacidade

[Ver Política de Privacidade](privacy-policy.pt-BR.md)
