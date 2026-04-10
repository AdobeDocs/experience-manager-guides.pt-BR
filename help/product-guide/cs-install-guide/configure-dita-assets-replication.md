---
title: Configurar a replicação DITA do Assets para o serviço em nuvem
description: Saiba como configurar a replicação de ativos essenciais para o Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 1eafc6b2-2b85-486a-bb2c-0038fae1fef9
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 3%

---

# Configurar a replicação de ativos DITA

Para configurar o recurso de processamento de ativos, execute as seguintes etapas:

1. Use as instruções fornecidas em [Substituições de configuração](../cs-install-guide/download-install-additional-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Valor padrão:** &quot;true&quot; |
