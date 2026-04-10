---
title: Configure nomes de arquivo válidos para a saída do site do AEM
description: Saiba como Configurar nomes de arquivo válidos para saída de site do AEM
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Configure nomes de arquivo válidos para a saída do site do AEM {#id214GK0X0KXA}

Semelhante à lista de caracteres válidos de nome de arquivo permitidos para tópicos DITA, você também pode configurar uma lista de caracteres de nome de arquivo válidos para a saída do AEM Site. Alguns dos caracteres conhecidos não permitidos em uma URL são: ```'<>`@$```. Esses caracteres são configurados para converter automaticamente em um sublinhado &quot;_&quot; quando são encontrados durante a geração de nomes de arquivo de saída de site do AEM. A configuração que permite definir caracteres válidos na saída do site do AEM está presente no pacote `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Defina a configuração Conjunto de Caracteres Não Permitido para Publicação no AEM Sites** para incluir caracteres que você deseja substituir por um sublinhado nos nomes de arquivo de saída do Site do AEM.

**Tópico pai:**&#x200B;[&#x200B; Configurar nomes de arquivo](conf-file-names.md)
