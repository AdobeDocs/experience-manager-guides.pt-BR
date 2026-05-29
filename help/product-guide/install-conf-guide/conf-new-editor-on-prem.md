---
title: Configurar novo editor
description: Saiba como ativar ou desativar o novo editor
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Configurar novo editor para no local

>[!IMPORTANT]
>
> Implante as configurações do sistema por meio do código, em vez de aplicá-las manualmente no ambiente de tempo de execução.

As etapas a seguir explicam como ativar o novo editor no ambiente local.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote **com.adobe.fmdita.config.ConfigManager**.

1. Habilitar a configuração **Habilitar Editor 2.0** (`enable.markup.editor`).

1. Selecione **Salvar**.

