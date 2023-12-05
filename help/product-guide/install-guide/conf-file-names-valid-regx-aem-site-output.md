---
title: Configurar nomes de arquivo válidos para saída do site AEM
description: Saiba como Configurar nomes de arquivo válidos para saída de site do AEM
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Configurar nomes de arquivo válidos para saída do site AEM {#id214GK0X0KXA}

Semelhante à lista de caracteres de nome de arquivo válidos permitidos para tópicos DITA, você também pode configurar uma lista de caracteres de nome de arquivo válidos para saída do site AEM. Alguns dos caracteres conhecidos que não são permitidos em um URL são: ```'<>`@$```. Esses caracteres são configurados para converter automaticamente em um sublinhado &quot;_&quot; quando são encontrados durante a geração de nomes de arquivo de saída do site AEM. A configuração que permite definir caracteres válidos na saída do site AEM está presente no `com.adobe.fmdita.common.SanitizeNodeNameImpl` pacote. **Definir o conjunto de caracteres não permitidos para publicação no AEM Sites** configuração para incluir caracteres que você deseja substituir por um sublinhado nos nomes de arquivo de saída do site AEM.

**Tópico pai:**[ Configurar nomes de arquivo](conf-file-names.md)
