---
tipo: busca_individual
data: 2026-09-25
projeto: "[[Financeiro-terceiros]]"
tags:
  - appscript
  - pipedrive
  - webhook
  - executores-pendentes
  - rotinas
---

# Uso Atual do Webhook no Projeto Financeiro-terceiros

## Pergunta
Qual é o uso real do Webhook atualmente no projeto `appscript/webhoocks/Financeiro-terceiros`?

## Análise Técnica de Uso

### 1. O que o Webhook REALMENTE executa em tempo real:
- **Auditoria de Executores Pendentes (`validarExecutoresPendentesPagamentoMensal`)**:
  - Escuta eventos `added.deal` e alterações de campos de executores (`updated.deal`).
  - Escuta atualizações de atividades (`updated.activity`).
  - Se um negócio for criado ou editado sem algum dos executores obrigatórios (*ITBI, Contrato, Registro, Titularidade, Leilões ou Data do Formulário*), o webhook cria imediatamente uma atividade de alta prioridade ("*Verificar Executores com Pendência*") no Pipedrive.

### 2. O que NÃO roda via Webhook (Roda por Gatilhos de Tempo / Agendador):
- **Extração para Planilha (`extrairImoveisPagamentoParceirosAutomatico`)**:
  - Roda via **Trigger Semanal** (segundas e sextas-feiras às 08:00) ou execução manual.
- **Envio de Valores ao Pipedrive (`enviarValoresPagamentoMensalParceirosParaPipedrive`)**:
  - Roda via execução manual ou trigger de fechamento mensal após conferência da planilha.

### 3. Estrutura do Roteador (`webhook-events`):
- O roteador contém declarações de várias automações legadas com guards `typeof fn === 'function'`. No escopo local deste projeto, apenas a função de validação de executores está ativa e vinculada.

## Referências
- [[Visão Geral Financeiro-terceiros]]
- [[Fluxo e Conexões Financeiro-terceiros]]
- [[2026-09-25 - Log de Dúvidas e Buscas]]
