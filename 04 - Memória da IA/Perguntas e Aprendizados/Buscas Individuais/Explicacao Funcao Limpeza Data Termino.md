# Função de Limpeza de Data Término (Análise Documental)

**Data**: 2026-09-18  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #appscript #pipedrive #analise-documental #limpeza-campos

---

## 📌 Contexto da Pergunta
Explicação e exibição do código da função `cefDevolutivaClearDataTerminoIfFilled_` implementada no arquivo `validação-vef-F`, detalhando seu funcionamento passo a passo.

---

## 💻 Código da Função

```javascript
/**
 * Limpa o campo "Data término" (IPTU ou Condomínio) no patch do deal,
 * caso ele já esteja preenchido. Aplica-se SOMENTE ao fluxo de Análise
 * Documental – nunca ao fluxo de Ateste de Pagamento.
 */
function cefDevolutivaClearDataTerminoIfFilled_(deal, relation, patch) {
  var fieldKey = ''
  if (relation === CEF_DEVOLUTIVA_REL_IPTU_) {
    fieldKey = CEF_DEVOLUTIVA_DATA_TERMINO_IPTU_FIELD_KEY_
  } else if (relation === CEF_DEVOLUTIVA_REL_CONDOMINIO_) {
    fieldKey = CEF_DEVOLUTIVA_DATA_TERMINO_CONDOMINIO_FIELD_KEY_
  }
  if (!fieldKey) return

  var currentValue = cefDevolutivaGetDealFieldValue_(deal, fieldKey)
  if (!cefDevolutivaIsEmptyPipedriveValue_(currentValue)) {
    patch[fieldKey] = ''
    cefDevolutivaLog_('INFO', deal.id || '', '', 'data_termino_cleared', {
      relation: relation,
      fieldKey: fieldKey,
      previousValue: currentValue
    })
  }
}
```

---

## ⚙️ Como Ela Funciona Passo a Passo

1. **Seleção da Chave do Campo Conforme a Relação**:
   - Se `relation === CEF_DEVOLUTIVA_REL_IPTU_`, seleciona a chave `46f5eea72dbdcd18c9c19d2ddee73bff046fc14b` (`Data término: IPTU`).
   - Se `relation === CEF_DEVOLUTIVA_REL_CONDOMINIO_`, seleciona a chave `2c3da637bcb6a12f68f20a24f734c89698d98f81` (`Data término: Condomínio`).

2. **Leitura do Valor Atual no Negócio**:
   - Usa `cefDevolutivaGetDealFieldValue_(deal, fieldKey)` para inspecionar se o negócio no Pipedrive já possui algum valor preenchido nesse campo específico.

3. **Verificação Condicional**:
   - Usa `!cefDevolutivaIsEmptyPipedriveValue_(currentValue)` para conferir se o campo não está nulo/vazio.
   - **Se estiver preenchido**: Insere no objeto `patch` a chave com valor `''` (string vazia), o que comanda a API do Pipedrive a zerar/limpar o campo no `PUT /deals/{id}`, além de registrar um log informativo contendo o valor anterior.
   - **Se já estiver vazio**: Nenhuma chave é adicionada ao `patch`, mantendo o campo intacto.

---
*Conexões*:
- Diário: [[2026-09-18 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Acao Executada na Analise Documental CEF]]

