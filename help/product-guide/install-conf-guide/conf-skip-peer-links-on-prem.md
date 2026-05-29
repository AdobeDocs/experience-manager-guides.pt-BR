---
title: Configurar o cancelamento de links de mesmo nível para a Linha de Base V1 no Local
description: Saiba como ativar ou desativar o cancelamento de links de mesmo nível para a Linha de base V1 no Local
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

---

# Configurar o cancelamento de links de mesmo nível para a Linha de Base Antiga no Local

As etapas a seguir explicam como ativar o cancelamento de links de mesmo nível para a Linha de base antiga no seu ambiente Local.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote **com.adobe.fmdita.config.ConfigManager**.

1. Habilitar a configuração **Ignorar links de mesmo nível para a Linha de Base V1** (guides.baseline.v1.skip.peer.links). Por padrão, essa configuração está desativada.

1. Selecione **Salvar**.
