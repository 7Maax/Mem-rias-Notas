# Análise da Regex com Prefixo Fixo "Interno - CCA"

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #regex #normalizacao #analise-tecnica

---

## 📌 Pergunta do Usuário
Avaliação da eficácia da expressão regular:
`.replace(/^\s*Interno - CCA\s*[-–—:]?\s*/i, '')`

---

## 🔍 Análise de Comportamento

| Valor de Entrada na Célula | Com a Regex do Usuário | Resultado |
| :--- | :--- | :---: |
| `"Interno - CCA - Yara Anjos"` | `"Yara Anjos"` | ✅ Funciona |
| `"Interno  CCA - Yara Anjos"` (sem hífen entre Interno e CCA) | `"Interno  CCA - Yara Anjos"` | ❌ **Falha** |
| `"Interno CCA - Yara Anjos"` (1 espaço sem hífen) | `"Interno CCA - Yara Anjos"` | ❌ **Falha** |

### 💡 Ajuste Recomendado
Tornar o hífen/separador entre `Interno` e `CCA` **opcional** (`[-–—:]?`):
```javascript
.replace(/^\s*Interno\s*[-–—:]?\s*CCA\s*[-–—:]?\s*/i, '')
```
Dessa forma, cobre tanto com hífen quanto sem hífen, garantindo compatibilidade total com qualquer variação de digitação ou lista suspensa.

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Diagnostico Erro Normalizacao Interno CCA Yara Anjos]]

