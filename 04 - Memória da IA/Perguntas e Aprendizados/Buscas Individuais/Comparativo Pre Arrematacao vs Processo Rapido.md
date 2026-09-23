# Comparativo: pre_arrematacao_assignment.js vs Processo Rápido

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #comparativo #pre-arrematacao #processo-rapido #arquitetura #automacoes

---

## 📌 Visão Geral do Comparativo

| Aspecto | `pre_arrematacao_assignment.js` | `Processo Rápido` |
| :--- | :--- | :--- |
| **Objetivo Principal** | Rodízio interno de corretores/analistas (*Lead Routing*) | Automação e extração de processos judiciais em PDF |
| **Gatilho** | Mudança de etapa (`stage_id = 49`, funil `5`) | Preenchimento/alteração do número CNJ do processo |
| **Ação Principal** | Altera o campo "Atribuído" e o `user_id` (Diego / Lara) | Dispara busca na API externa, baixa PDF e sobe no Drive |
| **Integrações Externas** | Apenas Pipedrive API | API Processo Rápido, Pipedrive, Google Drive, Google Sheets |
| **Natureza da Execução** | Síncrona e imediata via Webhook | Assíncrona com agendador de retentativas (*Backoff / Queue*) |
| **Armazenamento de Estado** | `ScriptProperties` + `LockService` | Planilha Google de auditoria/fila + Cache + Properties |
| **Criação de Atividade** | Não cria atividade (apenas muda o dono do deal) | Cria atividade `"Processo Anexado na Pasta"` |

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Notas Relacionadas: [[Resumo Pre Arrematacao Assignment]]

