---
title: REST APIs para fluxo de trabalho de conversão
description: Saiba mais sobre as REST APIs para fluxo de trabalho de conversão
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 9%

---

# REST APIs para fluxo de trabalho de conversão {#id175UB30E05Z}

As APIs REST a seguir permitem converter documentos do Word, HTML e InDesign para o formato DITA.

## Converter documentos do Word

Um método do GET que converte documentos do Word no formato DITA.

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

Um método do GET que converte documentos do HTML no formato DITA.

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

Um método do GET que converte documentos do InDesign no formato DITA.

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
