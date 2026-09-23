# Validação da Função Final normalizarExecutorParaBuscaLider_

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #validacao #testes #regex #normalizacao

---

## 📌 Contexto da Pergunta
Validação e teste da versão final da função `normalizarExecutorParaBuscaLider_` proposta pelo usuário para cobrir prefixos combinados como `Interno CCA -`.

---

## 🧪 Resultados dos Testes de Validação

```javascript
function normalizarExecutorParaBuscaLider_(executorRaw) {
  return String(executorRaw || '')
    .replace(/\(Você\)/gi, '')
    .replace(/^\s*(Interno|Externo)\s*[-–—:]\s*/i, '')
    .replace(/^\s*Propriet[aá]rio\s*[-–—:]\s*/i, '')
    .replace(/^\s*Parceiro\s*[-–—:]\s*/i, '')
    .replace(/^\s*Cart[oó]rio\s*[-–—:]\s*/i, '')
    .replace(/^\s*Interno\s*[-–—:]?\s*CCA\s*[-–—:]?\s*/i, '')
    .replace(/^\s*CCA\s*[-–—:]?\s*/i, '')
    .replace(/\s+/g, ' ')
    .trim();
}
```

| Cenário Testado | Entrada | Saída | Status |
| :--- | :--- | :--- | :---: |
| 1 | `Interno  CCA - Yara Anjos` | `Yara Anjos` | ✅ PASS |
| 2 | `Interno - CCA - Yara Anjos` | `Yara Anjos` | ✅ PASS |
| 3 | `Interno - Yara Anjos` | `Yara Anjos` | ✅ PASS |
| 4 | `CCA - Yara Anjos` | `Yara Anjos` | ✅ PASS |
| 5 | `Externo - Yara Anjos` | `Yara Anjos` | ✅ PASS |
| 6 | `Parceiro - Yara Anjos` | `Yara Anjos` | ✅ PASS |
| 7 | `Cartório - Yara Anjos` | `Yara Anjos` | ✅ PASS |
| 8 | `Proprietário - Yara Anjos` | `Yara Anjos` | ✅ PASS |
| 9 | `Yara Anjos (Você)` | `Yara Anjos` | ✅ PASS |

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Analise Regex Prefixo Interno CCA]]

