# Diagnóstico de Erro na Busca de Líder para "Interno CCA - Yara Anjos"

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #bug #regex #normalizacao #aba-equipe

---

## 📌 Descrição do Problema
Ao inserir `"Interno  CCA - Yara Anjos"` na coluna W (Executor), o sistema não encontra o líder na aba Equipe (onde o nome cadastrado é `"Yara Anjos"`).

---

## 🔍 Causa Raiz

No arquivo [`config.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/config.js#L128-L138), a função `normalizarExecutorParaBuscaLider_`:

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

### Por que falha em `"Interno  CCA - Yara Anjos"`?
1. O regex `/^\s*(Interno|Externo)\s*[-–—:]\s*/i` exige um traço (`-`, `:`, etc.) imediatamente após `Interno`. Como tem a palavra `CCA` logo após `Interno` sem hífen intermediário (`Interno  CCA`), o regex **não dá match** e não remove `"Interno"`.
2. O regex `/^\s*CCA\s*[-–—:]?\s*/i` exige que `CCA` esteja no início da string (`^`). Como `"Interno"` continuou no início da frase, o regex de `CCA` **também não dá match**.
3. O resultado final fica `"Interno CCA - Yara Anjos"`, que normaliza para `"interno cca yara anjos"`, falhando ao comparar com `"yara anjos"` na aba Equipe.

---

## 💡 Solução Recomendada

Utilizar uma limpeza iterativa de prefixos que suporte múltiplos prefixos encadeados com ou sem separadores:

```javascript
function normalizarExecutorParaBuscaLider_(executorRaw) {
  var texto = String(executorRaw || '')
    .replace(/\(Você\)/gi, '');

  var regexPrefixos = /^\s*(Interno|Externo|Propriet[aá]rio|Parceiro|Cart[oó]rio|CCA)\s*([-–—:]\s*)?/i;
  while (regexPrefixos.test(texto)) {
    texto = texto.replace(regexPrefixos, '');
  }

  return texto
    .replace(/\s+/g, ' ')
    .trim();
}
```

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Funcoes Normalizacao Texto Ouvidoria]]

