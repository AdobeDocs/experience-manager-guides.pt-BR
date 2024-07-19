---
title: REST APIs para fluxo de trabalho de conversão
description: Saiba mais sobre as REST APIs para fluxo de trabalho de conversão
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: add4730e396fe7384a20fb2c6c04730c20a83e71
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 6%

---

# REST APIs para fluxo de trabalho de conversão {#id175UB30E05Z}

As APIs REST a seguir permitem converter documentos do Word, HTML e InDesign para o formato DITA.

## Converter documentos do Word

Um método GET que converte documentos do Word no formato DITA.

**Solicitar URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| ``operation`` | String | Sim | Nome da operação que está sendo chamada. O valor deste parâmetro é ``word2dita``. <br> **Observação:** o valor não diferencia maiúsculas de minúsculas. |
| `inputFile` | String | Sim | Caminho absoluto dos arquivos de origem do Word no repositório AEM. |
| `destPath` | String | Sim | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `createRev` | Booleano | Sim | Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos. |
| `style2tagMap` | String | Sim | Caminho absoluto do arquivo de mapeamento de estilo que será usado para conversão. |

**Valores de resposta**:
Retorna uma resposta HTTP 200 \(Successful\).

## Converter documentos do HTML

Um método GET que converte documentos HTML no formato DITA.

**Solicitar URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parâmetros**:

| Nome | Tipo | Obrigatório | Descrição |
|----|----|--------|-----------|
| `operation` | String | Sim | Nome da operação que está sendo chamada. O valor deste parâmetro é ``html2dita``. <br> **Observação:** o valor não diferencia maiúsculas de minúsculas. |
| `inputFile` | String | Sim | Caminho absoluto dos arquivos HTML de origem no repositório AEM. |
| `destPath` | String | Sim | Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos. |
| `createRev` | Booleano | Sim | Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos. |

**Valores de resposta**:
Retorna uma resposta HTTP 200 \(Successful\).

## Converter documentos do InDesign

Um método GET que converte documentos do InDesign no formato DITA.

**Solicitar URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parâmetros**:
|Nome|Tipo|Obrigatório|Descrição|
|—|—|—|—|
|``operation``|Cadeia de Caracteres|Sim|Nome da operação que está sendo chamada. O valor deste parâmetro é ``idml2dita``. <br> **Observação:** o valor não diferencia maiúsculas de minúsculas.|
|`inputFile`|String|Yes|Caminho absoluto dos arquivos de InDesign de origem no repositório AEM.|
|`destPath`|String|Yes|Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos.|
|`createRev`|Booleano|Sim|Especifique se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos.|

**Valores de resposta**:
Retorna uma resposta HTTP 200 \(Successful\).
