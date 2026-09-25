---
title: "analiose appscriptwebhoocksOuvidoria , existe alguma regra p"
data: 2026-09-25
tags:
  - auto-sync
  - memoria-ia
  - busca
projeto: Geral
tipo: registro-automatico
---

# 🔎 analiose appscriptwebhoocksOuvidoria , existe alguma regra p

## ❓ Pergunta / Prompt
analiose appscript/webhoocks/Ouvidoria , existe alguma regra para a coluna Q "Status" ?

<ADDITIONAL_METADATA>
The current local time is: 2026-09-25T09:30:37-03:00.

The user's current state is as follows:
Active Document: /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Ouvidoria/main.js (LANGUAGE_UNSPECIFIED)
Cursor is on line: 679
Other open documents:
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Delegar Condominio--IPTU/condominio_assignment.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Gmail - Validações/iptu.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Obsidian - Max/Gabriel Max/04 - Memória da IA/Perguntas e Aprendizados/2026-09-21 - Log de Dúvidas e Buscas.md (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Obsidian - Max/Gabriel Max/04 - Memória da IA/Perguntas e Aprendizados/Buscas Individuais/Mapeamento Colunas Aba Equipe Ouvidoria.md (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/webhook-smartleiloesimobiliaria-appscript/src/10_automations/cef/devolutiva.js (LANGUAGE_UNSPECIFIED)
</ADDITIONAL_METADATA>

## 💡 Resposta / Resumo
Sim! Na pasta [`appscript/webhoocks/Ouvidoria`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria), a **Coluna Q ("Status" / Coluna 17)** possui **1 regra específica** associada:

---

### 📊 Regra de Recorrência por Assunto (Coluna N)
- **Função no código:** [`garantirFormulaRecorrenciaAssunto_`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L401-L418) (linhas 401 a 418 de `main.js`)
- A Coluna Q é utilizada como chave para calcular a **recorrência acumulada daquele status/assunto** para o mesmo imóvel na **Coluna N** através da fórmula:

```excel
=IF(OR($A{row}="", $Q{row}=""), "", COUNTIFS($A$2:$A{row}, $A{row}, $Q$2:$Q{row}, $Q{row}))
```

#### Como ela funciona:
1. Se o **Imóvel (Coluna A)** ou o **Status (Coluna Q)** estiverem vazios, a célula de recorrência fica em branco (`""`).
2. Se ambos estiverem preenchidos, o sistema conta automaticamente quantas vezes aquele mesmo Status já apareceu para aquele mesmo imóvel desde a linha 2 até a linha atual.

---

### 📌 Outros Comportamentos da Coluna Q:
- **Criação de Atividades no Pipedrive**: **Não é obrigatória**. O script não bloqueia a criação de atividade se a coluna Q estiver vazia (os campos obrigatórios são A, D, F, R, S, U, V, W, X, Y).
- **Notificações do Discord**: **Não é utilizada nem exigida** nos payloads de mensagens de NPS.

## 🔗 Links
- [[2026-09-25 - Log de Dúvidas e Buscas]]
