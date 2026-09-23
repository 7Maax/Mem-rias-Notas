# Funções de Normalização para Busca de Usuário no Pipedrive (Ouvidoria)

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #pipedrive #usuarios #atividades #normalizacao

---

## 📌 Contexto da Pergunta
Identificação das funções utilizadas para limpar e normalizar o nome do executor da coluna W antes de buscar o `user_id` correspondente no Pipedrive para criação da atividade.

---

## 💻 Funções Utilizadas

### 1. Limpeza de Prefixos e Tags do Executor
Arquivo: [`main.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L1220-L1228)

```javascript
function normalizeExecutorText_(s) {
  var t = (s || '').toString().replace(/\s+/g, ' ').trim();
  t = t.replace(/\(Você\)/gi, '').trim();
  t = t.replace(/^(Interno|Externo)\s*-\s*/i, '').trim();
  t = t.replace(/^CCA\s*[-–—:]?\s*/i, '').trim();
  t = t.replace(/^(Prop|Propriet[aá]rio|Propriet[aá]ria|Proprietario|Proprietaria|Proponente|Arrematante)\s*-\s*/i, '').trim();
  t = t.replace(/^(Prop|Propriet[aá]rio|Propriet[aá]ria|Proprietario|Proprietaria|Proponente|Arrematante)\s*:\s*/i, '').trim();
  return t;
}
```

### 2. Normalização Textual (Sem Acento / Minúsculas)
Arquivo: [`main.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L1302-L1305)

```javascript
function normalizeText_(s) {
  var x = String(s || '').trim().toLowerCase();
  try { 
    return x.normalize('NFD').replace(/[\u0300-\u036f]/g, ''); 
  } catch (e) { 
    return x; 
  }
}
```

### 3. Resolução do ID do Usuário no Pipedrive
Arquivo: [`main.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L1389-L1420) — `resolveUserIdFromName_(name)`

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Funcoes Normalizacao Texto Ouvidoria]]

