---
title: Compreender os tempos limite da sessão no Experience Manager Guides
description: Saiba mais sobre os tempos limite de sessões no Experience Manager Guides.
feature: Authoring, Publishing
role: User
exl-id: f09b1215-4753-4dfd-89ef-1629257e5efe
TQID: https://experienceleague.adobe.com/nrxkVxSUooy2-08PaUp1pjiH8w2kBBNGC9efarvepbQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 249
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
