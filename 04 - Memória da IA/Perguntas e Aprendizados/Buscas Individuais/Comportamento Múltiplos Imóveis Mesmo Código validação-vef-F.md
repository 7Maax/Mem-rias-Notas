---
tipo: busca_individual
data: 2026-09-25
projeto: "[[Gmail - Validações]]"
tags:
  - appscript
  - pipedrive
  - busca-imoveis
  - duplicidade
---

# Comportamento em Caso de Múltiplos Imóveis com Mesmo Código em validação-vef-F

## Pergunta
O que acontece quando o script `appscript/webhoocks/Gmail - Validações/validação-vef-F` encontra mais de um imóvel com o mesmo código no Pipedrive?

## Resposta e Análise Técnica
O script **não trata duplicidade ou ambiguidade de negócios**. Ele adota a estratégia **First-Match** (primeiro encontrado):

1. **Interrupção Imediata da Busca**:
   Na função `cefDevolutivaFindDealByPropertyCode_`, ao iterar sobre a lista de resultados da API de busca do Pipedrive (`/deals/search`), assim que encontra o primeiro registro cujo campo customizado de número do imóvel (`5c3aac951d1281021e01c13aa7a11a449efeabd1`) ou título contenha os dígitos do código, ele executa um `return deal;`.
2. **Impacto Prático**:
   - Apenas o **primeiro Deal retornado pela busca da API** recebe as alterações (criação de atividade de devolutiva, atualização de status/pendência de IPTU/Condomínio, limpeza de data de término ou preenchimento de data do primeiro ateste).
   - Todos os outros Deals que porventura possuam o mesmo código são **completamente ignorados**.
   - Não há emissão de alerta ou log específico de duplicidade/conflito para o operador.

## Trecho de Código Referência
```javascript
for (let i = 0; i < items.length; i++) {
  const item = items[i] && items[i].item ? items[i].item : (items[i] || {})
  const deal = item.id ? cefDevolutivaCallPipedrive_('deals/' + encodeURIComponent(String(item.id)), 'GET', null) : null
  if (!deal || !deal.id) continue

  const dealCode = cefDevolutivaNormalizeCode_(cefDevolutivaGetDealFieldValue_(deal, CEF_DEVOLUTIVA_NUMERO_IMOVEL_FIELD_KEY_))
  const titleCode = cefDevolutivaNormalizeCode_(deal.title || item.title || '')
  if (dealCode === codeDigits || (titleCode && titleCode.indexOf(codeDigits) >= 0)) return deal // <-- Retorna o primeiro e encerra
}
```

## Referências
- [[validação-vef-F]]
- [[Verificação de Funil em validação-vef-F]]
- [[2026-09-25 - Log de Dúvidas e Buscas]]
