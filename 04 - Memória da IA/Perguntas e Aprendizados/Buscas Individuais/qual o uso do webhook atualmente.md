---
title: "qual o uso do webhook atualmente"
data: 2026-09-25
tags:
  - auto-sync
  - memoria-ia
  - busca
projeto: Geral
tipo: registro-automatico
---

# 🔎 qual o uso do webhook atualmente

## ❓ Pergunta / Prompt
qual o uso do webhook atualmente ?

<ADDITIONAL_METADATA>
The current local time is: 2026-09-25T12:54:05-03:00.

The user's current state is as follows:
Active Document: /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Financeiro-terceiros/Pagamento-Parceiro (LANGUAGE_UNSPECIFIED)
Cursor is on line: 1
Other open documents:
- /home/gabrielrodrigues/Obsidian - Max/Gabriel Max/04 - Memória da IA/Perguntas e Aprendizados/Buscas Individuais/Abertura PR 26 correções-script-max.md (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Gmail - Validações/validação-vef-F (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Ouvidoria/main.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Delegar Condominio--IPTU/condominio_assignment.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Gmail - Validações/iptu.js (LANGUAGE_UNSPECIFIED)
</ADDITIONAL_METADATA>

## 💡 Resposta / Resumo
No projeto [`Financeiro-terceiros`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Financeiro-terceiros), o **Webhook** atua com o seguinte papel:

---

### 1. O que o Webhook faz em tempo real:
* **Auditoria de Executores Pendentes ([`validarExecutoresPendentesPagamentoMensal`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Financeiro-terceiros/Notif-Executores-Pendentes#L56)):**
  - **Gatilhos**: Escuta a criação de negócios (`added.deal`), alteração de campos dos executores (`updated.deal`) e atualização de atividades (`updated.activity`).
  - **Ação**: Se um imóvel for criado ou editado sem algum dos executores preenchidos (*ITBI, Contrato, Registro, Titularidade, Leilões ou Data do Formulário*), o webhook cria imediatamente uma atividade de alta prioridade (*"Verificar Executores com Pendência"*) no Pipedrive para o responsável resolver.

---

### 2. O que NÃO passa pelo Webhook (Roda por Agendamento/Gatilhos de Tempo):
* **Extração para Planilha**:
  - Roda via **Trigger Semanal** (segundas e sextas-feiras às 08:00) pela função `extrairImoveisPagamentoParceirosAutomatico()`.
* **Cálculo e Envio de Valores ao Pipedrive**:
  - Roda via execução manual/fechamento com a função `enviarValoresPagamentoMensalParceirosParaPipedrive()`.

---

### Resumo:
O webhook serve exclusivamente como um **auditor em tempo real**, garantindo que nenhum negócio avance ou fique sem os executores pr

## 🔗 Links
- [[2026-09-25 - Log de Dúvidas e Buscas]]
