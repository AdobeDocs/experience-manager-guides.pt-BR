---
title: Configurar nova linha de base para no local
description: Saiba como ativar ou desativar a Nova linha de base para No local
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# Configurar nova linha de base para no local

>[!IMPORTANT]
>
> Implante as configurações do sistema por meio do código, em vez de aplicá-las manualmente no ambiente de tempo de execução.

As etapas a seguir explicam como ativar a Nova linha de base no seu ambiente no local.

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote **com.adobe.fmdita.config.ConfigManager**.

1. Habilitar a configuração **Habilitar Linha de Base mais rápida (v2)**. Você também pode pesquisar com o nome exato da configuração `enable.baseline.v2`.

1. Selecione **Salvar**.

>[!NOTE]
>
>Depois de ativar esse recurso, você deverá migrar as linhas de base existentes para a nova linha de base. Para obter instruções passo a passo e um vídeo de apresentação, exiba a [Nova linha de base (Beta) no Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

