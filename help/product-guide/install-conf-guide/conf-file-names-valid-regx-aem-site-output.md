---
title: Configure nomes de arquivo válidos para a saída do site do AEM
description: Saiba como Configurar nomes de arquivo válidos para saída de site do AEM
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: b2bc5159-2144-4683-970d-738949ac9662
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# Configure nomes de arquivo válidos para a saída do site do AEM {#id214GK0X0KXA}

Semelhante à lista de caracteres válidos de nome de arquivo permitidos para tópicos DITA, você também pode configurar uma lista de caracteres de nome de arquivo válidos para a saída do AEM Site. Alguns dos caracteres conhecidos não permitidos em uma URL são: ``'<>`@$``. Esses caracteres são configurados para serem convertidos automaticamente em um sublinhado &quot;`_`&quot; quando são encontrados durante a geração de nomes de arquivo de saída de Site do AEM.

As guias a seguir fornecem instruções para configurar nomes de arquivo válidos para a saída do site do AEM com base na configuração do Experience Manager Guides: Cloud Service ou no local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para definir caracteres válidos na saída do AEM Site:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Adicione os caracteres que você deseja substituir por um sublinhado nos nomes de arquivo de saída do site do AEM. <br> **Valor padrão**: ``'<\>\`@$`` |

>[!TAB No local]

A configuração que permite definir caracteres válidos na saída do site do AEM está presente no pacote `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Defina a configuração Conjunto de Caracteres Não Permitido para Publicação no AEM Sites** para incluir caracteres que você deseja substituir por um sublinhado nos nomes de arquivo de saída do Site do AEM.

>[!ENDTABS]
