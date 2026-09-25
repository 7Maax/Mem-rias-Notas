---
title: "e ele pega de algum funil especifico"
data: 2026-09-25
tags:
  - auto-sync
  - memoria-ia
  - busca
projeto: Geral
tipo: registro-automatico
---

# 🔎 e ele pega de algum funil especifico

## ❓ Pergunta / Prompt
e ele pega de algum funil especifico ?


<ADDITIONAL_METADATA>
The current local time is: 2026-09-25T11:26:49-03:00.

The user's current state is as follows:
Active Document: /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Gmail - Validações/validação-vef-F (LANGUAGE_UNSPECIFIED)
Cursor is on line: 2090
Other open documents:
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Ouvidoria/main.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Delegar Condominio--IPTU/condominio_assignment.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Downloads/Projetos - Gabriel Max]]/appscript/webhoocks/Gmail - Validações/iptu.js (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Obsidian - Max/Gabriel Max/04 - Memória da IA/Perguntas e Aprendizados/2026-09-21 - Log de Dúvidas e Buscas.md (LANGUAGE_UNSPECIFIED)
- /home/gabrielrodrigues/Obsidian - Max/Gabriel Max/04 - Memória da IA/Perguntas e Aprendizados/Buscas Individuais/Mapeamento Colunas Aba Equipe Ouvidoria.md (LANGUAGE_UNSPECIFIED)
</ADDITIONAL_METADATA>

## 💡 Resposta / Resumo
**Não, ele não busca em nenhum funil específico.** A busca é **100% global** em toda a conta do Pipedrive.

---

### Detalhes técnicos da busca:

1. **Chamada de API sem filtro de funil**:
   Na função [`cefDevolutivaFindDealByPropertyCode_`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Gmail%20-%20Valida%C3%A7%C3%B5es/valida%C3%A7%C3%A3o-vef-F#L1076-L1077), a busca é executada da seguinte forma:
   ```javascript
   'deals/search?term=' + encodeURIComponent(code) + '&exact_match=1&fields=title,custom_fields&limit=20'
   ```
2. **Abrangência total**:
   - O endpoint `/deals/search` varre **todos os funis/pipelines** cadastrados no Pipedrive (como Desocupação, IPTU, Condomínio, Vendas, etc.).
   - Não é passado nenhum parâmetro `pipeline_id` na URL.
   - O código não valida a propriedade `deal.pipeline_id` ao receber os dados de retorno.

**Conclusão**: O script pega o primeiro negócio que der match no código do imóvel, independentemente de qual funil ele pertença.

## 🔗 Links
- [[2026-09-25 - Log de Dúvidas e Buscas]]
