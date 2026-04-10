---
title: Configure nomes de arquivo válidos para a saída do site do AEM
description: Saiba como Configurar nomes de arquivo válidos para saída de site do AEM
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '217'
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
