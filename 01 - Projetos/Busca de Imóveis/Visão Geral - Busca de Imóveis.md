# 🏢 Projeto: Busca de Imóveis (Smart Leilões)

- **Status**: Em Desenvolvimento Ativo
- **Repositório**: `/home/gabrielrodrigues/Projeto - Busca de Imóveis `
- **Tags**: #projeto #imoveis #leilao #nextjs #python #fullstack

---

## 🧭 Visão do Produto
Sistema inteligente para agregação, raspagem, análise e busca avançada de imóveis em leilão.
Oferece filtros analíticos, orquestração de buscas, histórico e métricas de oportunidade de mercado.

---

## 💻 Stack Tecnológica
- **Frontend / Fullstack**: [[Next.js 16]] (App Router), [[React 19]], TypeScript.
- **Backend / Workers**: 
  - Scripts TypeScript (`tsx`) para orquestração e ingestão.
  - Python 3 (`scripts/collector-python/`) para raspagem avançada e automação de navegadores.
- **Bancos de Dados**:
  - PostgreSQL (`pg`, migrações em `scripts/migrate.ts`).
  - MongoDB (`mongodb`).
- **Testes & Qualidade**:
  - Vitest para testes unitários.
  - Playwright para testes End-to-End (E2E).
  - TypeScript strict check (`tsc --noEmit`).
- **Deploy & Nuvem**: Google Cloud Run, Cloud Build, Docker.

---

## 🔗 Links Rápidos de Memória e Aprendizado
- [[Diretrizes do Projeto Busca de Imóveis]]
- [[2026-09-16 - Setup Obsidian e VS Code]]
- [[Índice de Memória]]

---

## 📌 Comandos Chave
- Dev local unificado: `npm run dev` (`bash scripts/dev-local.sh`)
- Web Next.js: `npm run dev:web`
- Worker do coletor Python: `npm run collector:worker`
- Testes: `npm test` e `npm run test:e2e`
