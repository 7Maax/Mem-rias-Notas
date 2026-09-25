---
tipo: busca_individual
data: 2026-09-25
projeto: "[[Gmail - Validações]]"
tags:
  - appscript
  - pipedrive
  - funil
  - condicoes
---

# Verificação de Funil em validação-vef-F

## Pergunta
Existe algum funil definido ou verificado como condição para realizar alterações no script `appscript/webhoocks/Gmail - Validações/validação-vef-F`?

## Resposta e Análise Técnica
**Não.** Não existe nenhuma verificação de **funil (`pipeline_id`)**, **etapa (`stage_id`)** ou **status do deal** (aberto/ganho/perdido) no script `validação-vef-F`.

### Como o script localiza e altera o Deal:
1. **Busca por Código do Imóvel**: O script busca o negócio no Pipedrive via endpoint de busca (`deals/search?term=...`).
2. **Critério de Correspondência**:
   - Compara o código extraído do e-mail com o campo customizado `5c3aac951d1281021e01c13aa7a11a449efeabd1` (Número do Imóvel) ou com o título do Deal (`deal.title`).
   - O primeiro Deal correspondente é selecionado, independentemente do funil ou fase onde se encontra.
3. **Condições Verificadas antes da Alteração**:
   - Elegibilidade do e-mail (Assunto/Labels como "Análise Documental" ou "Ateste de Pagamento").
   - Origem confirmada da Caixa/CEF.
   - Identificação da relação (`DÉBITOS/IPTU` ou `DÉBITOS/CONDOMÍNIO`).
   - Resolução do usuário responsável (`Atribuído IPTU` / `Atribuído Condomínio`) para criação da atividade.

## Referências
- [[validação-vef-F]]
- [[2026-09-25 - Log de Dúvidas e Buscas]]
