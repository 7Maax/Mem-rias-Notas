---
title: "analise a pasta appscriptwebhoocksOuvidoria e me retorne qua"
data: 2026-09-23
tags:
  - auto-sync
  - memoria-ia
  - busca
projeto: Geral
tipo: registro-automatico
---

# 🔎 analise a pasta appscriptwebhoocksOuvidoria e me retorne qua

## ❓ Pergunta / Prompt
analise a pasta appscript/webhoocks/Ouvidoria e me retorne quasi colunas d aplanilha sao necessárias/obrigatorias para criar atividade ou enviar msg no discord 

<ADDITIONAL_METADATA>
The current local time is: 2026-09-23T12:18:12-03:00.

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
Na planilha de **Ouvidoria**, as colunas obrigatórias são divididas em dois fluxos diferentes:

---

### 1️⃣ Para Criar Atividade no Pipedrive ([`main.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L919-L1001))
*(Válido para origens que **NÃO sejam NPS**, ex: Ouvidoria interna, Reclame Aqui, Ligação, etc.)*

| Coluna | Letra | Nome do Campo | Condição Obrigatória |
| :---: | :---: | :--- | :--- |
| **1** | **A** | **Imóvel** (Código) | Não pode ser vazio e deve existir no Pipedrive *(se for `"N/A"`, ignora a criação)* |
| **4** | **D** | **Data Abertura Ouvidoria** | Deve ser uma data válida e dentro da janela permitida |
| **6** | **F** | **Contato Realizado?** | Não pode estar vazio/pendente |
| **18** | **R** | **Descrição da reclamação** | Não pode estar vazia |
| **19** | **S** | **Ação efetiva** | Não pode estar vazia |
| **21** | **U** | **Setor** | Não pode estar vazio |
| **22** | **V** | **Proprietário** | Não pode estar vazio |
| **23** | **W** | **Executor** | Não pode estar vazio *(usado para achar o usuário no Pipe)* |
| **24** | **X** | **Líder** | Não pode estar vazio |
| **25** | **Y** | **Origem** | Não pode estar vazia e **NÃO pode ser NPS / NPS 1 / NPS 2** |

---

### 2️⃣ Para Enviar Mensagem no Discord ([`discord_atualizado.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/discord_atualizado.js#L916-L1028))
*(Válido exclusivam

## 🔗 Links
- [[2026-09-23 - Log de Dúvidas e Buscas]]
