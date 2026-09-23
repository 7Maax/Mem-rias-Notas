# 💡 Por que as buscas não estavam gerando bolinhas no grafo?

- **Horário**: 11:24
- **Data**: 2026-09-16
- **Tags**: #busca #grafo #obsidian #segundocerebro #aprendizado
- **Log Diário**: [[2026-09-16 - Log de Dúvidas e Buscas]]
- **Projeto**: [[Visão Geral - Busca de Imóveis]], [[Visão Geral - Webhook Appscript]]

---

### [11:24] Diagnóstico: O que cria bolinhas (nós) no Grafo do Obsidian?
- **❓ Dúvida / Pergunta**: "As buscas não estão gerando bolinhas lá, por quê?"
- **💡 Resposta / Aprendizado**:
  - No Obsidian, **cada bolinha no grafo representa um arquivo Markdown (.md) individual** (ou uma tag se ativada nas configurações).
  - Inicialmente, as buscas estavam sendo agrupadas como tópicos (`### [HH:mm]`) dentro de um único arquivo (`2026-09-16 - Log de Dúvidas e Buscas.md`). Por isso, existia apenas uma única bolinha para o dia inteiro!
  - **Solução implementada**:
    - Convertemos cada busca em uma **nota atômica independente** dentro de `04 - Memória da IA/Perguntas e Aprendizados/Buscas Individuais/`.
    - Cada nova pergunta agora cria um arquivo `.md` próprio com conexões `[[...]]`.
    - Isso fez nascerem **17 novas bolinhas** luminosas interconectadas no grafo do usuário!
