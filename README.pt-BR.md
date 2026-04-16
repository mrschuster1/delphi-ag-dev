# delphi-ag-dev — Plugin Agent do Antigravity

> Um plugin para o Antigravity que transforma o sistema multi-agente em um especialista sênior em Delphi.
> 🇺🇸 [English](README.md) | 🇧🇷 [Português](README.pt-BR.md) | 🇪🇸 [Español](README.es.md)

---

## O que é

**delphi-ag-dev** é ativado automaticamente no Antigravity através de suas *skills* principais sempre que um conteúdo relacionado ao Delphi for detectado — arquivos `.pas`, `.dpr`, `.dfm`, `.dpk`, `.dproj`, ou qualquer menção a Object Pascal, FireMonkey, VCL, FireDAC, ou RAD Studio. Uma vez ativo, o Agente Antigravity aplica todo o *Delphi Style Guide*, princípios de *Clean Code* e padrões *SOLID* sem que seja solicitado.

---

## Recursos

| Comando | Descrição |
|---|---|
| **Modo Auto Delphi** | A leitura de qualquer arquivo `.pas`, `.dpr` ou `.dfm` ativa todo o contexto de padrões de codificação automaticamente via *skill* `delphi-standards` |
| **`/delphi-audit`** | Gera uma auditoria técnica profissional completa com pontuação por dimensão e um escopo priorizado de modernização |
| **`/delphi-tdd`** | Gera uma suíte completa de testes unitários DUnitX para o projeto e força a abordagem *Red-Green-Refactor* |
| **`/delphi-spec`** | Analisa o código-fonte do projeto atual e auto-gera um `SPEC.md` de arquitetura completo |
| **`/delphi-write`** | Escreve novos códigos com todos os padrões aplicados desde o início, criando a base para `.pas`, `.dfm`, `.fmx` |

---

## Instalação

Para adicionar esses recursos a qualquer projeto Antigravity, basta copiar o diretório `.agent/` (que contém as habilidades e fluxos de trabalho) para a pasta raiz do seu projeto:

```bash
# Clone este repositório
git clone https://github.com/mrschuster1/delphi-ag-dev.git

# Copie as skills e workflows para o seu projeto
# (Windows / PowerShell)
Copy-Item -Recurse -Force .\delphi-ag-dev\.agent\* .\SeuProjeto\.agent\

# (Linux / Mac)
cp -R delphi-ag-dev/.agent/* /path/to/your/project/.agent/
```

### Pós-instalação

Através dessa cópia, o agente passará a reconhecer nativamente os fluxos de trabalho (`/delphi-write`, etc.) e a *skill* principal `delphi-standards` será carregada automaticamente sempre que houver interação com código Delphi.

---

## Padrões Aplicados Automaticamente

### Prefixos
- `F` — propriedades da classe (F de *Fields*, ex: atributos privados)
- `A` — parâmetros de métodos (A de *Arguments*)
- `L` — variáveis locais
- `C_` — constantes (+ TUDO_MAIUSCULO)
- `T` — classes e tipos
- `I` — interfaces
- `E` — exceções

### Formatação
- ✅ Identação de 2 espaços (sem tabulações)
- ✅ Limite rigoroso de 120 caracteres por linha
- ✅ `begin` e `else` em suas próprias linhas isoladas
- ✅ Uma declaração de variável por linha
- ✅ Uma unit por linha na cláusula `uses` ordenada (RTL → VCL/FMX → FireDAC → Terceiros → Projeto)

### Comandos Proibidos
- ❌ `with` — causa ambiguidade no código e problemas graves de debug
- ❌ `Break` / `Continue` — interrupções de laço (utilize laços `while` com condições adequadas)
- ❌ `Real` — utilize `Double` ou `Currency`
- ⚠️ `Exit` — é permitido apenas como guard clauses no topo de um método

### Regras de Segurança
- ✅ Um único recurso por bloco `try..finally`
- ✅ Proibido blocos `except` vazios
- ✅ SQL sempre parametrizado (sem concatenação de strings)
- ✅ `const` nunca é aplicado a parâmetros de interface (para manter a conformidade com o ARC)
- ✅ Sem variáveis globais (migradas para escopo orientado a objetos ou `class var`)

### Prefixos de Componentes (VCL / FMX)
`btn`, `edt`, `lbl`, `mmo`, `cbx`, `grd`, `qry`, `cnn`, `dts`, `pnl`, `tmr`, entre outros (Padrão Oficial Embracadero).

---

## Skills e Workflows Incluídos

| Tipo | Nome | Finalidade |
|---|---|---|
| Skill | `delphi-standards` | Auto-ativada na detecção de código/arquivos Delphi para impor regras |
| Workflow | `/delphi-write` | Escreve código Delphi completo e pronto para produção seguindo o padrão |
| Workflow | `/delphi-spec` | Gera o documento SPEC a partir da análise sintática do código-fonte |
| Workflow | `/delphi-tdd` | Cria métodos de suítes de teste DUnitX e executa regras de TDD |
| Workflow | `/delphi-audit` | Realiza auditoria técnica profunda — busca violações de padrão |

---

## Baseado em

- *Delphi Coding Standards v4.0.1* — Adriano Santos
- *Clean Code and Best Practices in Delphi* — Adriano Santos
- *Clean Code* — Robert C. Martin
- *Delphi Style Guide* — Embarcadero

---

## Licença

MIT © 2026
