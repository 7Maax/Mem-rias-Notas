# Regras da Coluna Q (Status) na Ouvidoria

**Data**: 2026-09-25  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #coluna-status #recorrencia #regras-planilha

---

## 📌 Análise da Coluna Q ("Status" - Coluna 17)

No projeto [`appscript/webhoocks/Ouvidoria`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria), a **Coluna Q (17)** possui a seguinte regra ativa:

---

### 1. Cálculo da Recorrência por Assunto (Coluna N)
A Coluna Q é utilizada como parâmetro de entrada na fórmula automática de **Recorrência por Assunto** ([`garantirFormulaRecorrenciaAssunto_`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L401-L418)):

```excel
=IF(OR($A{row}="", $Q{row}=""), "", COUNTIFS($A$2:$A{row}, $A{row}, $Q$2:$Q{row}, $Q{row}))
```

- **Comportamento**: Se o Imóvel (Coluna A) ou o Status (Coluna Q) estiverem em branco, o campo de recorrência fica vazio. Se preenchidos, o script conta quantas vezes aquele mesmo Status/Assunto já se repetiu para aquele imóvel da linha 2 até a linha atual.

---

### 2. Impacto em Atividades e Discord
- **Pipedrive**: Não é coluna obrigatória para a criação de atividades.
- **Discord**: Não é exigida nem enviada nos payloads de alerta do Discord.

---
*Conexões*:
- Diário: [[2026-09-25 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Notas Relacionadas: [[Colunas Obrigatorias Atividades e Discord Ouvidoria]]
