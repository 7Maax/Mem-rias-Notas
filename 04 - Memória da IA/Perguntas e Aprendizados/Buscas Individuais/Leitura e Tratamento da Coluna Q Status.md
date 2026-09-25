# Como o Status (Coluna Q) é Lido e Processado na Ouvidoria

**Data**: 2026-09-25  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #coluna-status #leitura-dados #sheets

---

## 📌 Forma de Leitura da Coluna Q

1. **Tipo de Dado**: É lido como **texto simples (String)** diretamente da célula da planilha.
2. **Sem Enum Rígido no Código**: O código Apps Script não restringe nem valida palavras-chave específicas para o Status (aceita qualquer valor preenchido pelo usuário ou dropdown da planilha, como "Em andamento", "Pendente", "Concluído", etc.).
3. **Uso na Fórmula do Sheets**: A fórmula `=COUNTIFS($A$2:$A{row}, $A{row}, $Q$2:$Q{row}, $Q{row})` usa o texto da célula como chave de agrupamento, diferenciando status/assuntos distintos para contar a repetição daquele mesmo texto no mesmo imóvel.

---
*Conexões*:
- Diário: [[2026-09-25 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Regras Coluna Q Status Ouvidoria]]
