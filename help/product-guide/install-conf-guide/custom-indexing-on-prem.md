---
title: Implantação de indexação personalizada para configuração no local
description: Saiba como personalizar o conteúdo de índice para configuração no local
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 87c0519d-120a-4bb7-b70f-7d217bcd7580
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 0%
---
# Reindexação para o recurso Localizar e substituir (exibição do Source) no local

A reindexação é necessária para habilitar o recurso **Localizar e substituir (modo de exibição Source)**, que permite verificar todo o conteúdo visível no modo de exibição Autor e também o conteúdo Source subjacente (estrutura XML, incluindo elementos, marcas e valores de atributo) da cadeia de caracteres pesquisada.

## Reindexação

Para configurações no local, a definição de índice é incluída no pacote. Para habilitar o recurso, você deve reindexar o conteúdo.

Inicie a reindexação definindo a propriedade `reindex=true (Boolean)` no nó: ` /oak:index/guidesAssetLucene` para reindexar o conteúdo capturado anteriormente.

O processo de reindexação continuará até que o sistema altere automaticamente essa propriedade de volta para false. Você pode monitorar o progresso da operação de reindexação nos logs do sistema.
