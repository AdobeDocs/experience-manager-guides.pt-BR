---
title: Configure nomes de arquivo válidos para a saída do site do AEM
description: Saiba como Configurar nomes de arquivo válidos para saída de site do AEM
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/hhc9Q8A-Eq3e8PAHHDXf1jXf8qVb-p4sU3Cum53ra9M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 145
ht-degree: 1%

---

# Configure nomes de arquivo válidos para a saída do site do AEM {#id214GK0X0KXA}

Semelhante à lista de caracteres válidos de nome de arquivo permitidos para tópicos DITA, você também pode configurar uma lista de caracteres de nome de arquivo válidos para a saída do AEM Site. Alguns dos caracteres conhecidos não permitidos em uma URL são: ``'<>`@$``. Esses caracteres são configurados para serem convertidos automaticamente em um sublinhado &quot;`_`&quot; quando são encontrados durante a geração de nomes de arquivo de saída de Site do AEM.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para definir caracteres válidos na saída do AEM Site:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Adicione os caracteres que você deseja substituir por um sublinhado nos nomes de arquivo de saída do site do AEM. <br> **Valor padrão**: ``'<\>\`@$`` |

**Tópico pai:**&#x200B;[&#x200B; Configurar nomes de arquivo](conf-file-names.md)
