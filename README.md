# Antigravity Delphi Dev Plugin

Um plugin poderoso para o **Antigravity** (projetado nos moldes do Claude Code) que automatiza o desenvolvimento em **Delphi (VCL/FMX)** mantendo os mais altos padrões de qualidade, Clean Code e metodologias ágeis (TDD).

Baseado no projeto original para Claude Code (`adrianosantostreina/delphi-dev`).

## 🚀 O que este projeto faz?

O **Antigravity Delphi Dev** introduz uma "Skill" rigorosa e um conjunto de fluxos (`workflows`) nativos que forçam a IA (e a equipe) a escrever código Delphi seguindo estritamente regras pré-estabelecidas e arquiteturas modernas. 

Ele atua em 4 frentes principais:
1. **Auditoria (`/delphi-audit`)**: Verifica códigos existentes e garante que sigam o padrão.
2. **Desenvolvimento Orientado a Testes (`/delphi-tdd`)**: Força a escrita do teste em DUnitX antes da implementação do código (*Red-Green-Refactor*).
3. **Escrita Restrita (`/delphi-write`)**: Gera códigos novos (Formulários, DataModules, Units) sempre seguindo as convenções.
4. **Especificações Técnicas (`/delphi-spec`)**: Define a arquitetura antes da modelagem do banco.

## 📐 Padrões Enforcados (`delphi-standards`)

A Skill base (`.agent/skills/delphi-standards/SKILL.md`) garante ativamente:

* **Indentação:** 2 espaços. Nada de tabulações.
* **Margem:** Limite estrito de 120 caracteres por linha.
* **Proibido o uso de:** `with`, `Break`, `Continue`, e tipo `Real` (substituído por `Double` ou `Currency`).
* **Segurança na gestão de memória:** Uso OBRIGATÓRIO de `try..finally` para objetos instanciados (`Create`).
* **Segurança de Banco de Dados:** SQL Injection mitigado; o uso de *Parameterized Queries* é mandatório, concatenação natural é bloqueada.
* **Component Prefix VCL/FMX:** Segue a nomenclatura oficial do *Delphi Style Guide* (ex: `btnSalvar`, `edtNome`, `lblStatus`, `pnlBackground`).

## 🛠️ Workflows Disponíveis

| Comando | Descrição |
|---------|-----------|
| `/delphi-audit` | Audita uma *unit* ou escopo específico buscando violações aos padrões da equipe. |
| `/delphi-tdd` | Inicia o fluxo de TDD usando DUnitX. Escreve a classe de Teste que falha, e em seguida a Unit de implementação que passa. |
| `/delphi-spec` | Monta um plano arquitetural/especificação do que será construído antes de iniciar o código. |
| `/delphi-write` | Escreve código Delphi (arquivos `.pas`, `.dfm` e `.fmx`) utilizando os prefixos VCL e restrições. |

## 📦 Como Usar

Isso foi projetado para rodar nativamente juntamente ao **Antigravity**. Toda a configuração fica isolada nas pastas `.agent/skills/` e `.agent/workflows/`.

Basta estar neste diretório e digitar os workflows (ex: `/delphi-write Criar tela de Login FMX`) diretamente para a IA para que os arquivos sejam gerados magicamente e corretamente estruturados em Delphi.

---
> **Nota do Arquiteto**: As definições e regras foram extraídas do *Object Pascal Style Guide*, princípios *Clean Code* e *SOLID* aplicados às versões modernas do Delphi (11+). 
