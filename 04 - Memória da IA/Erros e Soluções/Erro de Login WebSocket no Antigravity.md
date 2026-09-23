# 🐛 Erro: WebSocket Connection Closed Unexpectedly no Antigravity

- **Data**: 2026-09-16
- **Severidade**: Média
- **Tags**: #bug #antigravity #oauth #login #troubleshooting

---

## 🛑 Sintoma
Tela de onboarding/login exibe:
> *"There was an unexpected issue setting up your account. WebSocket connection closed unexpectedly."*
> Botão: *"Continue with different account"*

## 🔬 Causa Raiz
Ao tentar alternar ou autenticar uma nova conta Google no Antigravity, o app inicia um bridge local via WebSocket (`websocket_bridge.go`) para aguardar o callback de autorização do navegador. Se a aba do navegador for fechada antes de concluir, houver timeout ou bloqueio de pop-up/redirect local, a conexão fecha com `close 1005` e o token não é recebido.

## 🩹 Solução Aplicada
1. Clicar no botão **"Continue with different account"** (ou **"Previous"** para reiniciar o fluxo).
2. Garantir que a aba do Google OAuth seja concluída no navegador, selecionando a conta e clicando em "Permitir".
3. Se necessário, reiniciar a janela do IDE (`Ctrl + R`) para reiniciar o listener local de autenticação.
