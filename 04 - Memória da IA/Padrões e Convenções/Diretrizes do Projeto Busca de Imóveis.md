# 📐 Diretrizes do Projeto Busca de Imóveis

- **Tags**: #convencoes #padroes #codigo #nextjs #python
- **Contexto**: Regras obrigatórias seguidas pela IA ao desenvolver no projeto.

---

## 1. Next.js 16 & React 19
- Respeitar a nova arquitetura do Next.js (ver alertas em `AGENTS.md` e `node_modules/next/dist/docs/`).
- Tipagem estrita: sempre manter compatibilidade com `npm run lint` (`tsc --noEmit`).
- Server Components por padrão; `use client` apenas onde há interatividade, hooks de estado ou eventos de DOM.

## 2. Coletor Python & Workers
- Utilizar o ambiente virtual `.venv` (`.venv/bin/python`).
- Tratamento de exceções robusto em scrapers para não derrubar o worker contínuo.
- Separar lógica de orquestração da lógica de extração de dados brutos.

## 3. Banco de Dados & Modelagem
- Migrações controladas via `scripts/migrate.ts`.
- Manter consistência nas variáveis de ambiente em `.env.local` e nos exemplos de produção.

## 4. Memória Contínua
- Ao aprender um novo padrão de código ou resolver um bug complexo, atualizar a pasta `04 - Memória da IA`.
