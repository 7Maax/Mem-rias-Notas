# Log de Dúvidas e Buscas - 2026-09-23

## Registros do Dia
- [[Funcoes Validacao Criacao Atividades Ouvidoria]] - Identificação e explicação das funções que definem os critérios para criação de atividades no fluxo da Ouvidoria (`validateRowForActivityCreation_` e `criarAtividadesParaLinha_`).
- [[Funcoes Normalizacao Texto Ouvidoria]] - Exibição das funções de normalização (`normalizarExecutorParaBuscaLider_` e `normalizarTextoComparacao_`) usadas para buscar o executor na aba Equipe.
- [[Diagnostico Erro Normalizacao Interno CCA Yara Anjos]] - Causa raiz identificada: regex não remove prefixos combinados como `Interno  CCA -`, impedindo a busca de `Yara Anjos` na aba Equipe.
- [[Analise Regex Prefixo Interno CCA]] - Avaliação da proposta de regex `.replace(/^\s*Interno - CCA\s*[-–—:]?\s*/i, '')` e sugestão de separador opcional.
- [[Validacao Funcao Final normalizarExecutorParaBuscaLider]] - Teste com 9 cenários confirmando 100% de sucesso da função `normalizarExecutorParaBuscaLider_`.
- [[Funcoes Normalizacao Busca Pipedrive Ouvidoria]] - Exibição das funções `normalizeExecutorText_` e `normalizeText_` usadas para resolver o usuário no Pipedrive.
- [[Resumo Tecnico Geral Automacoes]] - Consolidação técnica de todo o trabalho realizado nos módulos de Pré-Arrematação, Devolutivas CEF, Imóveis Especialistas e Ouvidoria.
- Commit `d08721c` no repositório `Gabriel-Max-Automa-es-Appscript` (`ouvidoria`): Atualização de todos os scripts da pasta `Ouvidoria/`.








