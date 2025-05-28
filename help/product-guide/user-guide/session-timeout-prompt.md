---
title: Compreender os tempos limite da sessão no Experience Manager Guides
description: Saiba mais sobre os tempos limite de sessões no Experience Manager Guides.
feature: Authoring, Publishing
role: User
source-git-commit: a6e015817bc9a964e3ca6a83c50089e7fabcdd94
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# Por que a Experience Manager Guides me desconecta após determinado período?

O Experience Manager Guides encerra uma sessão de usuário após um período definido de inatividade (tempo limite de ociosidade). Essa funcionalidade de logout automático está configurada no Adobe Experience Manager. Quando a sessão expira, um alerta pop-up é exibido para notificar o usuário sobre a sessão expirada. Esse alerta impede que o usuário faça outras alterações no conteúdo.

**Como funciona o tempo limite da sessão?**

O Experience Manager Guides envia uma solicitação em segundo plano `token.json` a cada 30 segundos para validar a sessão. Se a sessão ainda estiver ativa, um token válido será retornado. Se a sessão tiver expirado devido à inatividade, um token vazio será retornado e a sessão será considerada inativa.

**O que acontece quando a sessão expira?**

Quando uma sessão inativa é detectada:

- Um alerta pop-up é exibido para notificar que você foi desconectado.

  ![](images/sign-out-prompt.png)

- O alerta desativa todas as interações com o aplicativo.

- Selecionar **OK** atualiza o navegador e o redireciona para a página de logon.
- Ao fazer logon, você é redirecionado para a última página aberta do Experience Manager Guides.

**Próximas etapas**

O alerta de expiração de sessão ajuda a impedir a perda de dados, restringindo você de fazer alterações no aplicativo durante uma sessão inativa. Para evitar a perda acidental de conteúdo, é recomendável salvar seu trabalho regularmente no Editor, especialmente antes de sair do sistema por um período estendido.





