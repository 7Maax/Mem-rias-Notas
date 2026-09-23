# 💡 Configuração do Visual Esfera de Estrelas 3D (Point Cloud)

- **Horário**: 12:13
- **Data**: 2026-09-16
- **Tags**: #busca #3d #visual #obsidian #esfera #constelacao
- **Log Diário**: [[2026-09-16 - Log de Dúvidas e Buscas]]
- **Projetos**: [[Visão Geral - Busca de Imóveis]], [[Visão Geral - Webhook Appscript]]

---

### [12:13] Calibração de Estilo 3D: Fundo Preto Absoluto e Partículas Brancas
- **❓ Dúvida / Pergunta**: "Ficou assim" (mostrando nós gigantes cinzas e fundo claro no 3D-Graph).
- **💡 Resposta / Aprendizado**:
  - Ajustamos o plugin `3d-graph` para o visual exato da imagem de referência:
    1. **Fundo**: Preto absoluto `#000000` forçado no container e na cena Three.js.
    2. **Nós**: Reduzidos de bolas gigantes (4.0) para pequenas partículas estelares (0.6).
    3. **Cor**: Branco brilhante luminescente (`#ffffff`) com filtro de glow e drop-shadow.
    4. **Linhas**: Reduzidas para espessura ultra-fina (0.1) com partículas de luz em trânsito.
- **🔗 Conexões**: [[Como configurar o estilo de Esfera Cósmica 3D no Obsidian]], [[Índice de Memória]]
