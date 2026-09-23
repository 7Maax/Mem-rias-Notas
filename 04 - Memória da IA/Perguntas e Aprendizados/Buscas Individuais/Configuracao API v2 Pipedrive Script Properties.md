# Configuração de URL e Suporte a API v2 no Pipedrive (Script Properties)

**Data**: 2026-09-22  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #pipedrive #api-v2 #script-properties #imoveis-especialistas

---

## 📌 Dúvida do Usuário
Saber se as propriedades do script (`Script Properties`) precisam ser alteradas manualmente para a URL da API v2 do Pipedrive para o funcionamento da remoção de tags.

---

## 💡 Resposta e Explicação Técnica

**NÃO precisa alterar as Script Properties.**

### Motivos:
1. **Troca Dinâmica no Código**: O código do script ([`esp.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Imoveis-Especialistas/esp.js#L394-L401) e [`pipedrive.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/pipedrive.js#L361-L368)) intercepta o parâmetro `{ apiVersion: 'v2' }` e substitui automaticamente `/v1` por `/v2` (ou `/api/v2`) na URL de requisição em tempo de execução.
2. **Mesmo Token**: O token de autenticação (`PIPEDRIVE_API_TOKEN`) é universal no Pipedrive e funciona tanto na v1 quanto na v2.
3. **Prevenção de Quebras**: Manter a base como `v1` nas propriedades garante que os demais endpoints legados (como buscas, atividades e webhooks) continuem funcionando normalmente sem erros de incompatibilidade de versão.

---
*Conexões*:
- Diário: [[2026-09-22 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Fluxo Remocao Tag Especialistas esp.js]]

