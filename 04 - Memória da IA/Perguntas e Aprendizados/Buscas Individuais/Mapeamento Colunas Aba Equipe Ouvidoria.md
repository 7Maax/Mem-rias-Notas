# Ordem e Mapeamento das Colunas da Aba Equipe (Ouvidoria)

**Data**: 2026-09-21  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #appscript #planilha #equipe #mapeamento

---

## 📌 Contexto da Pergunta
Análise dos scripts da pasta `appscript/webhoocks/Ouvidoria` para identificar a ordem e o mapeamento das colunas consultadas na aba **Equipe**.

---

## 📊 Mapeamento das Colunas da Aba Equipe

Nos arquivos [`config.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/config.js) e [`validacaoSetor.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/validacaoSetor.js):

| Índice | Letra | Campo / Descrição | Constante no Código | Aliases de Cabeçalho |
| :---: | :---: | :--- | :--- | :--- |
| **2** | **B** | **Nome do Funcionário / Executor** | `EQUIPE_COL_NOME = 2` / `COL_EQUIPE_FUNCIONARIO = 2` | `['NOME']` |
| **5** | **E** | *Tutor (mencionado em comentário)* | *(E é TUTOR)* | — |
| **6** | **F** | **Líder** | `EQUIPE_COL_LIDER = 6` / `COL_EQUIPE_LIDER = 6` | `['LIDER', 'LÍDER']` |

---
*Conexões*:
- Diário: [[2026-09-21 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]

