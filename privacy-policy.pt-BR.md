# Política de Privacidade — delphi-ag-dev

> 🇺🇸 [English](privacy-policy.md) · 🇧🇷 [Português](privacy-policy.pt-BR.md) · 🇪🇸 [Español](privacy-policy.es.md)

**Última atualização:** Abril de 2026

---

## Visão Geral

**delphi-ag-dev** é um plugin de código aberto para o sistema de IA multi-agente [Antigravity](https://github.com/mrschuster1/delphi-ag-dev). Este documento explica quais dados o plugin processa, como eles são tratados e seus direitos como usuário.

---

## Quais Dados o Plugin Processa

O plugin **delphi-ag-dev** opera inteiramente dentro do contexto do seu ambiente de desenvolvimento local e da sessão do agente de IA. Ele **não** possui nenhum serviço de backend, banco de dados ou API externa própria.

O plugin pode processar os seguintes tipos de dados **somente dentro da sua sessão de IA**:

| Tipo de Dado | Finalidade | Armazenado Externamente? |
|---|---|---|
| Arquivos de código-fonte (`.pas`, `.dfm`, etc.) | Revisão de código, auditoria, geração de testes | ❌ Não |
| Nomes e estrutura de arquivos do projeto | Geração de Spec, análise de arquitetura | ❌ Não |
| Descrições em linguagem natural que você fornece | Geração de novo código via `/delphi-write` | ❌ Não |

---

## Como os Dados São Tratados

- Todo o processamento de dados ocorre **localmente dentro da sua sessão do agente de IA**.
- O plugin **não** envia, armazena ou transmite nenhum código-fonte ou dado do seu projeto para servidores externos.
- Os únicos dados que saem do sua máquina são os enviados ao **provedor do modelo de IA** (ex: Anthropic, Google, etc.) como parte da sessão normal de IA — regidos pelas políticas de privacidade deles.
- Este plugin é puramente uma camada de configuração (Skills + Workflows) — não possui código executável, chamadas de rede ou persistência de dados própria.

---

## Provedores de IA de Terceiros

Quando você interage com um agente de IA que tem este plugin carregado, seus prompts e qualquer código que você compartilha são processados pelo provedor do modelo de IA subjacente. Consulte as políticas de privacidade deles:

- [Política de Privacidade da Anthropic](https://www.anthropic.com/privacy)
- [Política de Privacidade do Google](https://policies.google.com/privacy)

---

## Dados que Você Compartilha Voluntariamente

Este é um projeto de código aberto hospedado no GitHub. Se você:

- **Abrir uma issue** ou **enviar um pull request**, seu nome de usuário do GitHub e o conteúdo que você enviar estarão visíveis publicamente no GitHub, sujeito à [Política de Privacidade do GitHub](https://docs.github.com/pt/site-policy/privacy-policies/github-privacy-statement).
- **Dar uma estrela ou fazer um fork** do repositório, esta atividade também é pública no GitHub.

---

## Sem Análises ou Telemetria

**delphi-ag-dev** **não** coleta nenhuma telemetria, estatísticas de uso ou dados analíticos. Não há rastreamento algum.

---

## Privacidade de Crianças

Este plugin é destinado ao uso por desenvolvedores de software. Ele não foi projetado para, e não processa conscientemente dados de, crianças menores de 13 anos.

---

## Alterações nesta Política

Esta política de privacidade pode ser atualizada periodicamente. As alterações serão refletidas pela data de "Última atualização" no topo deste documento. O uso continuado do plugin após as alterações constitui aceitação da política atualizada.

---

## Contato

Para dúvidas ou preocupações sobre esta política de privacidade, por favor abra uma issue no repositório GitHub:

👉 [https://github.com/mrschuster1/delphi-ag-dev/issues](https://github.com/mrschuster1/delphi-ag-dev/issues)
