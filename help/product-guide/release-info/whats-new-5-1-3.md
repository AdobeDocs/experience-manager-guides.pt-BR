---
title: Notas de versão | Novidades da versão 5.1.0 do Service Pack 3 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados na versão 5.1.0 Service Pack 3 do Adobe Experience Manager Guides
role: Leader
exl-id: 1b2e45a8-bea6-4b78-bd2e-cc02df86f40a
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 0%

---

# Novidades da versão 5.1.0 do Service Pack 3 (dezembro de 2025)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 5.1.0 do Service Pack 3 do Adobe Experience Manager Guides.

Para obter a lista de problemas que foram corrigidos nesta versão, consulte [Problemas corrigidos na versão 5.1.0 do Service Pack 3](fixed-issues-5-1-0-sp3.md).

Saiba mais sobre [as instruções de atualização para o 5.1.0 Service Pack 3 versão](../release-info/upgrade-instructions-5-1-0-sp3.md).


## Configurar representações de imagem personalizadas para predefinições de saída específicas

Agora é possível configurar diferentes representações de imagem para predefinições de saída individuais no mesmo tipo de saída usando o atributo `outputName` em `renditionmapping.xml`. Esse aprimoramento oferece maior flexibilidade ao publicar conteúdo que requer várias resoluções de imagem para diferentes cenários. Por exemplo, você pode querer uma imagem de alta resolução para a saída principal do HTML5 ao usar uma miniatura menor para uma predefinição leve.

Para obter mais detalhes, exiba [Manipular representação de imagem na geração de saída](../install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).
