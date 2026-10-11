---
title: Configurar inicialização da cópia de destino no fluxo de trabalho de tradução para No local
description: Saiba como habilitar ou desabilitar a inicialização da cópia de destino no fluxo de trabalho de tradução para No local
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
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
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
