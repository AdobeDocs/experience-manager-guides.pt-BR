---
title: REST APIs para fluxo de trabalho de conversão
description: Saiba mais sobre as REST APIs para fluxo de trabalho de conversão
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: d3b388b7-b49d-4f87-b444-9b6f7fc2ef0c
    internal-label: REST API Conversion Workflow
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 9%
---
# REST APIs para fluxo de trabalho de conversão {#id175UB30E05Z}

As APIs REST a seguir permitem converter documentos do Word, HTML e InDesign para o formato DITA.

## Converter documentos do Word

Um método GET que converte documentos do Word no formato DITA.

**Solicitar URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| ``operation`` | String | Sim | Nome da operação que está sendo chamada. O valor deste parâmetro é ``word2dita``. <br> **Observação:** o valor não diferencia maiúsculas de minúsculas. |
| `inputFile` | String | Sim | Caminho absoluto dos arquivos de origem do Word no repositório do AEM. |
| `destPath` | String | Sim | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `createRev` | Booleano | Sim | Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos. |
| `style2tagMap` | String | Sim | Caminho absoluto do arquivo de mapeamento de estilo que será usado para conversão. |

**Valores de resposta**:
Retorna uma resposta HTTP 200 \(Successful\).

## Converter documentos do HTML

Um método GET que converte documentos do HTML no formato DITA.

**Solicitar URL**:

http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/conversion

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `operation` | String | Sim | Nome da operação que está sendo chamada. O valor deste parâmetro é ``html2dita``. <br> **Observação:** o valor não diferencia maiúsculas de minúsculas. |
| `inputFile` | String | Sim | Caminho absoluto dos arquivos HTML de origem no repositório do AEM. |
| `destPath` | String | Sim | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `createRev` | Booleano | Sim | Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos. |

**Valores de resposta**:

Retorna uma resposta HTTP 200 \(Successful\).

## Converter documentos do InDesign

Um método GET que converte documentos do InDesign no formato DITA.

**Solicitar URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| ``operation`` | String | Sim | Nome da operação que está sendo chamada. O valor deste parâmetro é ``idml2dita``. <br> **Observação:** o valor não diferencia maiúsculas de minúsculas. |
| `inputFile` | String | Sim | Caminho absoluto dos arquivos InDesign de origem no repositório do AEM. |
| `destPath` | String | Sim | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `createRev` | Booleano | Sim | Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos. |

**Valores de resposta**:
Retorna uma resposta HTTP 200 \(Successful\).
