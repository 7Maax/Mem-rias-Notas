# Colunas Obrigatórias para Criação de Atividades e Envio Discord (Ouvidoria)

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #colunas-obrigatorias #pipedrive #discord #validacao

---

## 📌 Visão Geral das Colunas Obrigatórias

A planilha de **Ouvidoria** possui dois motores de validação independentes dependendo do destino da ação:

---

### 1️⃣ Para Criar Atividade no Pipedrive (`main.js`)
*Aplicável para origens que NÃO sejam NPS (ex: Ouvidoria, Reclame Aqui, Ligação, etc.)*

| Coluna | Letra | Nome do Campo | Condição de Validação |
| :---: | :---: | :--- | :--- |
| **1** | **A** | Imóvel / Código do Imóvel | Não pode ser vazio e deve existir no Pipedrive (se "N/A", pula) |
| **4** | **D** | Data Abertura Ouvidoria | Deve ser data válida dentro da janela máxima de abertura |
| **6** | **F** | Contato Realizado? | Não pode estar pendente/vazio |
| **18** | **R** | Descrição da reclamação | Obrigatório (texto não vazio) |
| **19** | **S** | Ação efetiva | Obrigatório (texto não vazio) |
| **21** | **U** | Setor | Obrigatório |
| **22** | **V** | Proprietário | Obrigatório |
| **23** | **W** | Executor | Obrigatório (usado para resolver o usuário no Pipe) |
| **24** | **X** | Líder | Obrigatório |
| **25** | **Y** | Origem | Obrigatório e **NÃO pode ser NPS / NPS 1 / NPS 2** |

---

### 2️⃣ Para Enviar Mensagem no Discord (`discord_atualizado.js`)
*Aplicável para notificações de NPS (NPS Padrão ou NPS Atendimento)*

| Coluna | Letra | Nome do Campo | Condição de Validação |
| :---: | :---: | :--- | :--- |
| **1** | **A** | Imóvel / Código do Imóvel | Obrigatório (aceita "N/A") |
| **6** | **F** | Contato Realizado? | Obrigatório |
| **18** | **R** | Descrição da reclamação | Obrigatório |
| **20** | **T** | Causa raiz / Análise do caso | **Obrigatório para o Discord** |
| **21** | **U** | Setor | Obrigatório (define se vai pro canal Atendimento ou Padrão) |
| **23** | **W** | Executor / Responsável | Obrigatório |
| **24** | **X** | Líder | Obrigatório e **deve ter ID do Discord mapeado** |
| **25** | **Y** | Origem | Deve ser `NPS`, `NPS 1` ou `NPS 2` |

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Notas Relacionadas: [[Templates Atividades Ouvidoria]]

