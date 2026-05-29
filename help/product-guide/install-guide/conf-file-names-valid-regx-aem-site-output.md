---
title: Configure nomes de arquivo válidos para a saída do site do AEM
description: Saiba como Configurar nomes de arquivo válidos para saída de site do AEM
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/vGe4--XJ9VL5q74J7hVFCmD0vrBRnUkBAdZDCFcUxeU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 179e9016b12edb14c09ce9352a318e06a4fc628a
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 0%

---

# Configure nomes de arquivo válidos para a saída do site do AEM {#id214GK0X0KXA}

Semelhante à lista de caracteres válidos de nome de arquivo permitidos para tópicos DITA, você também pode configurar uma lista de caracteres de nome de arquivo válidos para a saída do AEM Site. Alguns dos caracteres conhecidos não permitidos em uma URL são: `<>``@$`. Esses caracteres são configurados para converter automaticamente em um sublinhado &quot;_&quot; quando são encontrados durante a geração de nomes de arquivo de saída de site do AEM. A configuração que permite definir caracteres válidos na saída do site do AEM está presente no pacote `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Defina a configuração Conjunto de Caracteres Não Permitido para Publicação no AEM Sites** para incluir caracteres que você deseja substituir por um sublinhado nos nomes de arquivo de saída do Site do AEM.

**Tópico pai:**[ Configurar nomes de arquivo](conf-file-names.md)
