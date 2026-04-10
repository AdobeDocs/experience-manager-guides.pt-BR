---
title: Configurar o processamento de ativos para o serviço em nuvem
description: Saiba como configurar o processamento de ativos para o Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 219a096f-4087-489f-9b3b-104864817198
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 3%

---

# Configurar o recurso de processamento de ativos

Para configurar o recurso de processamento de ativos, execute as seguintes etapas:

1. Use as instruções fornecidas em [Substituições de configuração](../cs-install-guide/download-install-additional-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valor padrão:** &quot;true&quot; |
