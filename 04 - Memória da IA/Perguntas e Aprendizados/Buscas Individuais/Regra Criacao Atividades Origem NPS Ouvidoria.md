# Regra de Criação de Atividades para Origem NPS (Ouvidoria)

**Data**: 2026-09-22  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #pipedrive #nps #discord #atividades

---

## 📌 Dúvida do Usuário
Verificar se linhas com **Origem NPS** (inclusive quando o setor é Atendimento) criam atividade no Pipedrive na automação de Ouvidoria.

---

## 🔍 Resposta e Análise do Código

**NÃO.** Linhas cuja coluna **Origem** seja `NPS`, `NPS 1` ou `NPS 2` **NÃO criam nenhuma atividade no Pipedrive**, mesmo quando o setor for *Atendimento - Pós-arrematação*.

### Motivo e Localização no Código:
No arquivo [`main.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L679-L688), a função `criarAtividadesParaLinha_` possui um bloqueio explícito logo no início:

```javascript
// Reclamações de origem NPS são tratadas exclusivamente no Discord. Este
// bloqueio acontece antes das demais validações para não exigir executor ou
// líder em uma linha que jamais deve criar atividade no Pipedrive.
var origemDaLinha = rowValues[CONFIG.COL_ORIGEM - 1];
if (isOrigemNps_(origemDaLinha)) {
  sheet.getRange(row, logCol).setValue(
    'Não criou: origem NPS é tratada somente pelo Discord; atividade no Pipe não será criada'
  );
  return;
}
```

### O que acontece com essas linhas?
Esses casos são direcionados e tratados **exclusivamente via Discord** através do arquivo [`discord_atualizado.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/discord_atualizado.js#L916-L970) (`enviarNotificacaoDiscordNpsAtendimento` / `enviarNotificacaoDiscordNps`).

---
*Conexões*:
- Diário: [[2026-09-22 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]

