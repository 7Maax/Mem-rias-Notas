# Funções que Definem a Criação de Atividades na Ouvidoria

**Data**: 2026-09-23  
**Projeto**: [[Visão Geral - Webhook Appscript]]  
**Tags**: #ouvidoria #pipedrive #atividades #validacao #criterios-criacao

---

## 📌 Contexto da Pergunta
Identificação das funções exatas no código de Ouvidoria ([`appscript/webhoocks/Ouvidoria/main.js`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js)) que definem e validam se uma atividade deve ou não ser criada no Pipedrive.

---

## 🔍 As 2 Funções Principais

1. **[`validateRowForActivityCreation_(rowValues)`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L919-L1001)**:
   - Valida se todos os campos obrigatórios da linha da planilha estão preenchidos:
     - `A`: Código do Imóvel
     - `D`: Data de Abertura (e se está dentro da janela de dias permitida)
     - `F`: Contato Realizado?
     - `R`: Descrição da Reclamação
     - `S`: Plano de Ação Efetiva
     - `U`: Setor/Etapa
     - `V`: Proprietário
     - `W`: Executor
     - `X`: Líder
     - `Y`: Origem

2. **[`criarAtividadesParaLinha_(sheet, row, options)`](file:///home/gabrielrodrigues/Downloads/Projetos%20-%20Gabriel%20Max%5D%5D/appscript/webhoocks/Ouvidoria/main.js#L640-L753)**:
   - Aplica os filtros de negócio antes de chamar a API:
     - Bloqueia se já tiver sido criada (`OK: atividades criadas`).
     - Bloqueia se a origem for **NPS** (`isOrigemNps_`).
     - Bloqueia se o imóvel for manual (`N/A`).
     - Bloqueia se o Deal não for localizado no Pipedrive.
     - Bloqueia se a atividade já existir para o responsável nas mesmas datas.

---
*Conexões*:
- Diário: [[2026-09-23 - Log de Dúvidas e Buscas]]
- Projeto: [[Visão Geral - Webhook Appscript]]
- Nota Relacionada: [[Templates Atividades Ouvidoria]]

