# 🌌 Configuração do Grafo Cósmico Galáctico (Estilo Asimov / Fundação)

**Data**: 2026-09-18
**Tags**: #obsidian #css #graphview #design #astronomy #scifi #customizacao
**Links**: [[2026-09-18 - Log de Dúvidas e Buscas]] | [[README - Meu Segundo Cérebro]]

---

## 📌 Visão Geral da Configuração
Implementação completa da estilização **Galactic / Cosmic Knowledge Graph** inspirada nos mapas estelares de *Fundação* de Isaac Asimov (Trantor central e constelações periféricas).

### 🛠️ O que foi configurado:
1. **Snippet CSS `cosmic-galaxy.css`**:
   - Fundo cósmico preto absoluto (`#000000` / `#010004`).
   - Filtros de brilho neon (drop-shadow estelar roxo/violeta em 3 camadas) nos nós e filamentos do Canvas.
   - Rótulos HUD / Sci-Fi com cantoneiras, sublinhado neon e fonte monospace.
   - Efeito de amplificação luminosa ao passar o mouse.
   - Estilização de tags e links internos no editor com tema roxo cósmico.

2. **Aparência (`appearance.json`)**:
   - Accent color: `#c084fc` (Lilás Galáctico).
   - Snippet ativado: `cosmic-galaxy`.

3. **Física & Cores do Grafo (`graph.json`)**:
   - `showArrow: false` (linhas estelares contínuas e limpas).
   - `lineSizeMultiplier: 0.75` (feixes de luz finos e densos).
   - `nodeSizeMultiplier: 1.45` (tamanho de estrelas principais).
   - `centerStrength: 0.75` (gravidade central formando o disco galáctico).
   - `repelStrength: 13.5` e `linkDistance: 220` (distribuição orbital balanceada).
   - Grupos de cores estelares (Branco radiante para Hubs/MOCs, Rosa neon para Projetos, Lilás/Violeta para Memória e Recursos).
