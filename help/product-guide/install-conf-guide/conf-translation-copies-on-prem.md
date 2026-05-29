---
title: Configurar inicialização da cópia de destino no fluxo de trabalho de tradução para No local
description: Saiba como habilitar ou desabilitar a inicialização da cópia de destino no fluxo de trabalho de tradução para No local
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 1%

---

# Configurar inicialização da cópia de destino no fluxo de trabalho de tradução para No local

As etapas a seguir explicam como habilitar a inicialização da cópia de destino no fluxo de trabalho de tradução para seu ambiente no local.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote **com.adobe.fmdita.config.ConfigManager**.

1. Habilite ou desabilite a configuração **Inicializar cópia do idioma de destino com conteúdo de origem** (translation.workflow.propagate.source.content) de acordo com seu requisito. Essa configuração é aplicável somente quando o fluxo de trabalho de tradução herdado está desativado.

1. Selecione **Salvar**.
