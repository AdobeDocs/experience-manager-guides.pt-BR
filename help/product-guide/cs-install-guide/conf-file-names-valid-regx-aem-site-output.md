---
title: Configurar nomes de arquivo válidos para saída do site AEM
description: Saiba como Configurar nomes de arquivo válidos para saída de site do AEM
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 1%

---

# Configurar nomes de arquivo válidos para saída do site AEM {#id214GK0X0KXA}

Semelhante à lista de caracteres de nome de arquivo válidos permitidos para tópicos DITA, você também pode configurar uma lista de caracteres de nome de arquivo válidos para saída do site AEM. Alguns dos caracteres conhecidos não permitidos em uma URL são: ``'<>`@$``. Esses caracteres são configurados para serem convertidos automaticamente em um sublinhado &quot;`_`&quot; quando são encontrados durante a geração de nomes de arquivo de saída do site AEM.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para definir caracteres válidos na saída do site AEM:

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Adicione caracteres que você deseja substituir por um sublinhado nos nomes de arquivo de saída do site AEM. <br> **Valor padrão**: ``'<\>\`@$`` |

**Tópico pai:**&#x200B;[ Configurar nomes de arquivo](conf-file-names.md)
