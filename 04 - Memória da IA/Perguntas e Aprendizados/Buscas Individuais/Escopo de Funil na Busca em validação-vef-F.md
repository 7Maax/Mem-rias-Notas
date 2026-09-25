---
tipo: busca_individual
data: 2026-09-25
projeto: "[[Gmail - Validações]]"
tags:
  - appscript
  - pipedrive
  - funil
  - busca-global
---

# Escopo de Funil na Busca de Imóveis em validação-vef-F

## Pergunta
O script `appscript/webhoocks/Gmail - Validações/validação-vef-F` busca ou filtra os imóveis a partir de algum funil (*pipeline*) específico?

## Resposta e Análise Técnica
**Não, a busca é global em toda a conta do Pipedrive (abrange todos os funis).**

### Detalhes da Execução da API:
1. **Endpoints Utilizados**:
   ```javascript
   'deals/search?term=' + encodeURIComponent(code) + '&exact_match=1&fields=title,custom_fields&limit=20'
   'deals/search?term=' + encodeURIComponent(code) + '&fields=title,custom_fields&limit=50'
   ```
2. **Sem Parâmetro `pipeline_id`**:
   A API de busca do Pipedrive (`/deals/search`) pesquisa todos os negócios em todos os funis cadastrados (ex: Desocupação, IPTU, Condomínio, Vendas, etc.). Como nenhum parâmetro `pipeline_id` é fornecido na requisição e nenhuma verificação de `deal.pipeline_id` é feita no retorno, o script aceitará o primeiro Deal retornado pela busca, independente do funil a que pertença.

## Referências
- [[validação-vef-F]]
- [[Verificação de Funil em validação-vef-F]]
- [[Comportamento Múltiplos Imóveis Mesmo Código validação-vef-F]]
- [[2026-09-25 - Log de Dúvidas e Buscas]]
