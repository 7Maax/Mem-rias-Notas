# Funções de Normalização de Texto para Busca na Aba Equipe (Ouvidoria)

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #normalizacao #aba-equipe #regex #javascript

---

## 📌 Contexto da Pergunta
Identificação e exibição das funções de normalização de texto utilizadas para limpar o nome do Executor (Coluna W) e compará-lo com os nomes da aba **Equipe**.

---

## 💻 1. Função de Limpeza de Prefixos e Tags
Arquivo: [`config.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/config.js#L128-L138) (linhas 128 a 138)

```javascript
function normalizarExecutorParaBuscaLider_(executorRaw) {
  return String(executorRaw || '')
    .replace(/\(Você\)/gi, '')
    .replace(/^\s*(Interno|Externo)\s*[-–—:]\s*/i, '')
    .replace(/^\s*Propriet[aá]rio\s*[-–—:]\s*/i, '')
    .replace(/^\s*Parceiro\s*[-–—:]\s*/i, '')
    .replace(/^\s*Cart[oó]rio\s*[-–—:]\s*/i, '')
    .replace(/^\s*CCA\s*[-–—:]?\s*/i, '')
    .replace(/\s+/g, ' ')
    .trim();
}
```

---

## 💻 2. Função de Normalização para Comparação Exata
Arquivo: [`config.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/config.js#L467-L477) (linhas 467 a 477)

```javascript
function normalizarTextoComparacao_(texto) {
  return String(texto || '')
    .toLowerCase()
    .normalize('NFD')
    .replace(/[\u0300-\u036f]/g, '')
    .replace(/\u00a0/g, ' ')
    .replace(/[\u2010-\u2015]/g, '-')
    .replace(/[-_\/\\]+/g, ' ')
    .replace(/\s+/g, ' ')
    .trim();
}
```

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Fluxo Leitura Aba Equipe Ouvidoria]]

