---
title: PDF nativo | Configurar o local de saída básico para publicação do PDF para serviços em nuvem
description: Configurar o local de saída básico para os serviços em nuvem do PDF de publicação
feature: Output Generation
role: Admin
level: Experienced
exl-id: d79085d6-938a-4e80-84a2-03562e6b76e0
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Configurar o Local de saída base para a saída de publicação dos serviços em nuvem

Para configurar o local de saída base, execute as seguintes etapas:

1. Use as instruções fornecidas em [Substituições de configuração](../cs-install-guide/download-install-additional-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar o local de saída base:

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Valor padrão:** &quot;/content/dam/fmdita-outputs&quot; |
