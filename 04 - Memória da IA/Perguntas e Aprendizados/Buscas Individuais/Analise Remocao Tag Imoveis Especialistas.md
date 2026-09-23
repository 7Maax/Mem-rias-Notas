# Análise da Função de Remoção de Label em Imóveis Especialistas

**Data**: 2026-09-21  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #appscript #pipedrive #imoveis-especialistas #labels #remocao-tag

---

## 📌 Contexto da Pergunta
Análise do arquivo [`appscript/webhoocks/Imoveis-Especialistas/esp.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Imoveis-Especialistas/esp.js) para verificar se a função de remover a label/tag (`2827`) já está completa e funcional.

---

## 🔍 Diagnóstico e Conclusão

A função de remoção da label está **100% COMPLETA e IMPLEMENTADA**, cobrindo todas as etapas necessárias:

1. **Constante Definida**: `IMOVEIS_ESPECIALISTAS_LABEL_ID_ = 2827`.
2. **Detecção e Construção do Patch** ([`buildImoveisEspecialistasPatch_`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Imoveis-Especialistas/esp.js#L178)):
   - Valida etapa (`75`) e funil (`6`).
   - Extrai as labels atuais do deal através de múltiplos formatos ([`imoveisEspecialistasDealLabelIds_`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Imoveis-Especialistas/esp.js#L542)).
   - Remove o ID `2827` gerando a lista atualizada de labels.
3. **Execução no Pipedrive** ([`imoveisEspecialistasRemoveEspecialistasLabel_`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Imoveis-Especialistas/esp.js#L327)):
   - Busca o estado mais recente do deal via `GET`.
   - Executa `PATCH /deals/{id}` com `label_ids` via API v2 (`{ apiVersion: 'v2' }`).
   - Valida ativamente se a label foi de fato removida no retorno. Lança exceção explícita se a remoção falhar.
4. **Idempotência**: Se a label já não estiver presente, pula a requisição (`label_already_removed`).

---
*Conexões*:
- Diário: [[2026-09-21 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]

