# Fluxo de Remoção da Tag de Especialistas (esp.js)

**Data**: 2026-09-22  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #imoveis-especialistas #pipedrive #labels #fluxo-automacao

---

## 📌 Contexto da Pergunta
Análise detalhada do fluxo que executa a remoção da label de Imóveis Especialistas (`ID: 2827`) dentro do arquivo [`appscript/webhoocks/Imoveis-Especialistas/esp.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Imoveis-Especialistas/esp.js).

---

## 🔄 Fluxo Completo de Remoção

1. **Gatilho**:
   - Monitora eventos de atualização de negócios no Pipedrive quando as chaves `stage_id` ou `pipeline_id` são alteradas.

2. **Condições de Elegibilidade**:
   - Funil Destino: `pipeline_id === 6` (Pós-Arrematação).
   - Etapa Destino: `stage_id === 75` (Registrado. Pendente Débitos).
   - Houve mudança efetiva de etapa/funil.

3. **Detecção e Filtragem da Tag**:
   - Busca todas as tags do negócio (`imoveisEspecialistasDealLabelIds_`).
   - Se possuir a tag `2827` (`IMOVEIS_ESPECIALISTAS_LABEL_ID_`), gera uma nova lista de tags sem esse ID (`imoveisEspecialistasWithoutLabelId_`).

4. **Execução no Pipedrive**:
   - Busca os dados mais recentes do negócio (`GET /deals/{id}`).
   - Executa `PATCH /deals/{id}` com `{ label_ids: [...] }` usando a **API v2** (`apiVersion: 'v2'`).
   - Revalida se a tag realmente sumiu no retorno da API (se falhar, lança `Error`).

5. **Finalização e Auditoria**:
   - Grava log estruturado com labels anteriores e posteriores.

---
*Conexões*:
- Diário: [[2026-09-22 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Analise Remocao Tag Imoveis Especialistas]]

