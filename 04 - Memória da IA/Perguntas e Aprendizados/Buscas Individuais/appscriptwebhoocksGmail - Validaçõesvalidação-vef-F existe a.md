---
title: "appscriptwebhoocksGmail - Validaçõesvalidação-vef-F existe a"
data: 2026-09-25
tags:
  - auto-sync
  - memoria-ia
  - busca
projeto: Geral
tipo: registro-automatico
---

# 🔎 appscriptwebhoocksGmail - Validaçõesvalidação-vef-F existe a

## ❓ Pergunta / Prompt
appscript/webhoocks/Gmail - Validações/validação-vef-F existe algum funil definido ou verificado como condição para realizar alterações?

<ADDITIONAL_METADATA>
The current local time is: 2026-09-25T09:49:57-03:00.

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
**Não.** Não existe nenhum funil (`pipeline_id`), etapa (`stage_id`) ou status de negócio (aberto/ganho/perdido) definido ou verificado como condição para aplicar alterações no [validação-vef-F](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Gmail%20-%20Valida%C3%A7%C3%B5es/valida%C3%A7%C3%A3o-vef-F).

---

### Como o script localiza e decide alterar o Deal:

1. **Busca por Código do Imóvel** ([`cefDevolutivaFindDealByPropertyCode_`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Gmail%20-%20Valida%C3%A7%C3%B5es/valida%C3%A7%C3%A3o-vef-F#L1067-L1096)):
   - Faz uma busca global no endpoint `/deals/search?term=<codigo>`.
   - Compara o código extraído do e-mail com o campo customizado `5c3aac951d1281021e01c13aa7a11a449efeabd1` (*Número do Imóvel*) ou no título do Deal (`deal.title`).
   - O primeiro Deal correspondente é selecionado, **independentemente do funil em que esteja**.

2. **Condições que são realmente verificadas antes da alteração**:
   - **E-mail**: Assunto/Labels válidos (ex.: *"Análise Documental"* ou *"Ateste de pagamento"*), data do e-mail dentro da janela de corte e remetente/corpo contendo *"CEF"* ou *"Caixa"*.
   - **Relação da Despesa**: Identificada como `DÉBITOS/IPTU` ou `DÉBITOS/CONDOMÍNIO`.
   - **Responsável**: Resolução do usuário do Pipedrive via campos *Atribuído IPTU* / *Atribuído Condomínio* para criação da atividade.

## 🔗 Links
- [[2026-09-25 - Log de Dúvidas e Buscas]]
