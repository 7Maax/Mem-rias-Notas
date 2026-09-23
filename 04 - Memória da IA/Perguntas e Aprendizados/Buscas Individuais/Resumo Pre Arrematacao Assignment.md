# Resumo do Script pre_arrematacao_assignment.js

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #pre-arrematacao #rodizio #pipedrive #automacao #atribuicao

---

## 📌 Visão Geral do Arquivo

O script [`appscript/webhoocks/Pré/pre_arrematacao_assignment.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Pr%C3%A9/pre_arrematacao_assignment.js) é responsável pelo **rodízio automático de responsáveis** no funil de Pré-Arrematação.

---

## ⚙️ Regras de Funcionamento

1. **Condições de Ativação**:
   - **Funil**: `5` (Pré-Arrematação).
   - **Etapa**: `49` (Chegada do Imóvel).
   - Ativa em negócios recém-criados ou movidos para a etapa 49.
2. **Filtro de Bloqueio**:
   - Pula a atribuição se o campo *Assessoria/Intermediação* estiver marcado como **"Imobiliária Externa"** (`id: 2740`).
3. **Membros do Rodízio**:
   - 1. **Diego Vitorino** (`id: 2958`, `userId: 28387317`)
   - 2. **Lara Souza** (`id: 2978`, `userId: 25575200`)
4. **Mecanismo de Concorrência**:
   - Usa `LockService` com timeout de 20s para evitar colisões e grava o índice do próximo na `ScriptProperties` (`PRE_ARREMATACAO_ASSIGNEE_ROTATION_INDEX`).
5. **Atualização no Pipedrive**:
   - Preenche o campo customizado *Atribuído* (`74f1bf...c4d6`) e altera o dono do deal (`user_id`).

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]

