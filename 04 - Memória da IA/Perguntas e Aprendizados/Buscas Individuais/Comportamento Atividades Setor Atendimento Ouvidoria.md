# Comportamento de Criação de Atividades no Setor Atendimento (Ouvidoria)

**Data**: 2026-09-22  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #pipedrive #atividades #setor-atendimento #origem

---

## 📌 Dúvida do Usuário
Saber se o setor "Atendimento" (Atendimento - Pós-arrematação) nunca cria atividade no Pipedrive ou se isso depende da origem.

---

## 🔍 Resumo da Regra

| Cenário | Origem | Cria Atividade no Pipedrive? | Onde é Tratado? |
| :--- | :--- | :---: | :--- |
| **Setor: Atendimento** | **NPS** (`NPS`, `NPS 1`, `NPS 2`) | ❌ **NÃO** | **Discord** (`discord_nps_atendimento`) |
| **Setor: Atendimento** | **Outra Origem** (ex: *Ouvidoria*, *Reclame Aqui*, *Ligação*, etc.) | ✅ **SIM** | **Pipedrive** (Atividade criada no Deal) |

### Conclusão:
O critério de bloqueio de atividade é **exclusivamente a Origem (NPS)**, e **não o Setor**. Se a origem não for NPS e os campos obrigatórios estiverem preenchidos, o setor Atendimento gera atividades no Pipedrive normalmente.

---
*Conexões*:
- Diário: [[2026-09-22 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Regra Criacao Atividades Origem NPS Ouvidoria]]

