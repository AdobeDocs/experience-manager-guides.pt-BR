---
title: Configurar nova linha de base para no local
description: Saiba como ativar ou desativar a Nova linha de base para No local
feature: Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 4abf673f636ffd20d087c99b5112d8504929a6ee
workflow-type: tm+mt
source-wordcount: '124'
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
>Depois de ativar esse recurso, você deverá migrar as linhas de base existentes para a nova linha de base. Para obter instruções passo a passo e um vídeo de apresentação, exiba a [Nova linha de base no Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

