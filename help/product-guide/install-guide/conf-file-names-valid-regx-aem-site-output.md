---
title: Configurar nomes de arquivo válidos para saída do site AEM
description: Saiba como Configurar nomes de arquivo válidos para saída de site do AEM
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Configurar nomes de arquivo válidos para saída do site AEM {#id214GK0X0KXA}

Semelhante à lista de caracteres de nome de arquivo válidos permitidos para tópicos DITA, você também pode configurar uma lista de caracteres de nome de arquivo válidos para saída do site AEM. Alguns dos caracteres conhecidos não permitidos em uma URL são: ```'<>`@$```. Esses caracteres são configurados para converter automaticamente em um sublinhado &quot;_&quot; quando são encontrados durante a geração de nomes de arquivo de saída do site AEM. A configuração que permite definir caracteres válidos na saída do site AEM está presente no pacote `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Defina a configuração Conjunto de Caracteres Não Permitido para Publicação no AEM Sites** para incluir caracteres que você deseja substituir por um sublinhado nos nomes de arquivo de saída do site AEM.

**Tópico pai:**[ Configurar nomes de arquivo](conf-file-names.md)
