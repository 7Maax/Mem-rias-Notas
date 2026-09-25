---
tipo: busca_individual
data: 2026-09-25
projeto: "[[Financeiro-terceiros]]"
tags:
  - appscript
  - pipedrive
  - financeiro
  - terceiros
  - parceiros
  - webhook
---

# Visão Geral do Projeto Financeiro-terceiros

## Pergunta
Qual é o objetivo e o que faz o projeto `appscript/webhoocks/Financeiro-terceiros`?

## Resumo e Arquitetura do Projeto
O projeto automatiza o controle, cálculo de remuneração e validação de pendências de **parceiros/despachantes terceirizados** vinculados aos imóveis no Pipedrive.

### Principais Componentes:
1. **Cálculo de Remuneração dos Parceiros (`Pagamento-Parceiro`)**:
   - Analisa negócios no Pipedrive e calcula os valores a pagar com base nos executores das etapas (*ITBI, Contrato, Registro, Titularidade e Leilões*).
   - Aplica regras financeiras e tabelas de valores dependendo do tipo de pagamento (*Escritura Pública, CCV, Financiamento, FGTS*) e da data de preenchimento do formulário de arrematantes (marcos temporais).
   - Calcula a competência mensal de pagamento com base nas datas de término de titularidade e registro.

2. **Exportação e Sincronização de Planilha (`Planilha-Pagamento`)**:
   - Extrai negócios via filtros da API do Pipedrive (filtro `35331`) e popula uma planilha de pagamentos com dados dos imóveis, executores e valores consolidados.

3. **Notificação de Pendências de Executores (`Notif-Executores-Pendentes`)**:
   - Monitora negócios no Pipedrive (filtro `35328` ou via webhook) para verificar se todos os campos de executores e documentos foram preenchidos.
   - Gera atividades de alta prioridade ("*Verificar Executores com Pendência*") para o responsável quando faltam informações obrigatórias.

4. **Infraestrutura de Webhook e Logs (`webhook`, `webhook-events`, `config`)**:
   - Recebe eventos do Pipedrive em tempo real, gerencia locks de concorrência e grava logs detalhados de execução em planilha Google.

## Referências
- [[Pagamento-Parceiro]]
- [[Planilha-Pagamento]]
- [[Notif-Executores-Pendentes]]
- [[2026-09-25 - Log de Dúvidas e Buscas]]
