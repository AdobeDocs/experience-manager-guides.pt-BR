---
title: REST APIs para fluxo de trabalho de conversão
description: Saiba mais sobre as REST APIs para fluxo de trabalho de conversão
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# REST APIs para fluxo de trabalho de conversão {#id175UB30E05Z}

As APIs REST a seguir permitem converter documentos do Word, HTML e InDesign para o formato DITA.

## Converter documentos do Word

Um método GET que converte documentos do Word no formato DITA.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |``operation``|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é ``word2dita``. <br> **Nota:** O valor não diferencia maiúsculas de minúsculas. | |`inputFile`|String|Sim|Caminho absoluto dos arquivos de origem do Word no repositório AEM.| |`destPath`|String|Sim|Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos.| |`createRev`|Booleano|Sim|Especificar se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos.| |`style2tagMap`|String|Sim|Caminho absoluto do arquivo de mapeamento de estilo que será usado para conversão.|

**Valores de resposta**: retorna uma resposta HTTP 200 \(Successful\).

## Converter documentos do HTML

Um método GET que converte documentos HTML no formato DITA.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é ``html2dita``. <br> **Nota:** O valor não diferencia maiúsculas de minúsculas.| |`inputFile`|String|Yes|Caminho absoluto dos arquivos HTML de origem no repositório AEM.| |`destPath`|String|Sim|Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos.| |`createRev`|Booleano|Sim|Especificar se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos.|

**Valores de resposta**: retorna uma resposta HTTP 200 \(Successful\).

## Converter documentos do InDesign

Um método GET que converte documentos do InDesign no formato DITA.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |``operation``|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é ``idml2dita``. <br> **Nota:** O valor não diferencia maiúsculas de minúsculas.| |`inputFile`|String|Yes|Caminho absoluto dos arquivos de InDesign de origem no repositório AEM.| |`destPath`|String|Sim|Caminho absoluto do local de destino onde os arquivos DITA convertidos serão salvos.| |`createRev`|Booleano|Sim|Especificar se uma revisão dos arquivos foi criada \( `true`\) no destino especificado ou não \( `false`\). Isso é considerado somente quando o local de destino contém uma versão existente dos arquivos convertidos.|

**Valores de resposta**: retorna uma resposta HTTP 200 \(Successful\).
