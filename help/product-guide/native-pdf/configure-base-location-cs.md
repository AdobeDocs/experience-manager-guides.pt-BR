---
title: PDF nativo | Configurar o local de saída básico para a publicação do PDF para serviços em nuvem
description: Configurar o local de saída básico para os serviços em nuvem do PDF de publicação
feature: Output Generation
role: Admin
level: Experienced
exl-id: d79085d6-938a-4e80-84a2-03562e6b76e0
TQID: https://experienceleague.adobe.com/E4J5BCDQBZdyqfQ-ksOCrMZYO1Bg9BMI-wQZRK96yqY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 80
ht-degree: 2%

---

# Configurar o Local de saída base para a saída de publicação dos serviços em nuvem

Para configurar o local de saída base, execute as seguintes etapas:

1. Use as instruções fornecidas em [Substituições de configuração](../cs-install-guide/download-install-additional-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar o local de saída base:

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Valor padrão:** &quot;/content/dam/fmdita-outputs&quot; |
