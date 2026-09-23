---
title: "compare ele com o sistema Processo Rapido para baixar proces"
data: 2026-09-23
tags:
  - auto-sync
  - memoria-ia
  - busca
projeto: Geral
tipo: registro-automatico
---

# 🔎 compare ele com o sistema Processo Rapido para baixar proces

## ❓ Pergunta / Prompt
compare ele com o sistema "Processo Rapido" para baixar processos judiciais 

<ADDITIONAL_METADATA>
The current local time is: 2026-09-23T11:50:35-03:00.

The user's current state is as follows:
Active Document: /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Ouvidoria/main.js (LANGUAGE_UNSPECIFIED)
Cursor is on line: 654
Other open documents:
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Ouvidoria/main.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Ouvidoria/config.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Ouvidoria/validacaoSetor.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Gmail - Validações/iptu.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Obsidian - Max/Gabriel Max/04 - Memória da IA/Perguntas e Aprendizados/2026-09-21 - Log de Dúvidas e Buscas.md (LANGUAGE_UNSPECIFIED)
</ADDITIONAL_METADATA>

## 💡 Resposta / Resumo
Aqui está o comparativo técnico entre o **`pre_arrematacao_assignment.js`** e o sistema **`Processo Rápido`**:

---

### 📊 Tabela Comparativa:

| Característica | `pre_arrematacao_assignment.js` | Sistema `Processo Rápido` |
| :--- | :--- | :--- |
| **Finalidade Principal** | **Distribuição de Leads (Rodízio)**:<br>Alterna os responsáveis pelo negócio. | **Automação Jurídica & Documental**:<br>Consulta, baixa PDFs de processos e anexa no Drive. |
| **Gatilho de Entrada** | Mudança para a **Etapa 49** (*Chegada do Imóvel*) do **Funil 5** (*Pré-Arrematação*). | Preenchimento ou edição do campo **N° do Processo (CNJ)** no Pipedrive. |
| **Ação Executada** | Atualiza o campo customizado "Atribuído" e altera o dono do deal (`user_id`) entre **Diego e Lara**. | Envia requisição para a API externa do Processo Rápido, faz o download do PDF completo e salva na pasta do imóvel no **Google Drive**. |
| **Criação de Atividades** | ❌ Não cria atividades (apenas define o proprietário). | ✅ Cria a atividade `"Processo Anexado na Pasta"` atribuída ao analista jurídico. |
| **Integrações Envolvidas** | Apenas Pipedrive API. | **API Processo Rápido + Pipedrive + Google Drive + Google Sheets**. |
| **Tipo de Execução** | **Síncrona**: Processamento imediato no momento do webhook. | **Assíncrona / Com Fila**: Usa retentativas com backoff (`retryScheduler.js`) e fila em planilha Google até o PDF ser liberado pelos tribunais. |
| **Controle de Estado** | `ScriptProperties` + `LockService` para ger

## 🔗 Links
- [[2026-09-23 - Log de Dúvidas e Buscas]]
