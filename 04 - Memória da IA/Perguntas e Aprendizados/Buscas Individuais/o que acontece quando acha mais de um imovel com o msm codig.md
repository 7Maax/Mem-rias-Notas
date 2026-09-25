---
title: "o que acontece quando acha mais de um imovel com o msm codig"
data: 2026-09-25
tags:
  - auto-sync
  - memoria-ia
  - busca
projeto: Geral
tipo: registro-automatico
---

# 🔎 o que acontece quando acha mais de um imovel com o msm codig

## ❓ Pergunta / Prompt
o que acontece quando acha mais de um imovel com o msm codigo 

<ADDITIONAL_METADATA>
The current local time is: 2026-09-25T11:20:25-03:00.

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
Quando existem múltiplos negócios (*deals*) no Pipedrive com o mesmo código de imóvel, o script adota a estratégia **First-Match** (primeiro que der *match*):

### O que acontece na prática:
1. **Pega apenas o primeiro**: A função [`cefDevolutivaFindDealByPropertyCode_`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Gmail%20-%20Valida%C3%A7%C3%B5es/valida%C3%A7%C3%A3o-vef-F#L1067-L1096) itera sobre os resultados retornados pela API de busca do Pipedrive e, assim que o primeiro negócio bate o código no campo customizado `5c3aac951d1281021e01c13aa7a11a449efeabd1` ou no título (`deal.title`), ele executa um `return deal;` imediatamente.
2. **Ignora os demais**: Todos os outros negócios com o mesmo código são **completamente ignorados**.
3. **Aplica as alterações somente nele**:
   - A atividade de devolutiva é criada **apenas no primeiro Deal**.
   - Os status de pendência, limpeza da *Data Término* ou preenchimento do *1º Ateste* são enviados via `PUT` **apenas para esse primeiro Deal**.
4. **Sem aviso de duplicidade**: O script não gera erro nem emite alerta de duplicidade/conflito quando há múltiplos registros.

## 🔗 Links
- [[2026-09-25 - Log de Dúvidas e Buscas]]
