---
title: Usar Markdown no DITA AEM Guides
description: Migrar e usar markdown no DITA AEM Guides
author: Pulkit Nagpal(punagpal)
exl-id: a94c0129-df40-4b61-ac60-679b2ffe7e86
TQID: https://experienceleague.adobe.com/z41KjrBkAeDaH-iKXOFLH44qOQElziip1FqcRhnKaUI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 0%

---

# Usar Markdown no AEM Guides

## Opções disponíveis

Há duas opções para usar arquivos de marcação no AEM Guides:

- Opção 1: importe a marcação existente no AEM Guides e use-a diretamente no ditamap para publicar

- Opção 2: converter arquivos de marcação existentes em DITA

Vamos falar sobre cada opção:

### Opção 1: importe a marcação existente no AEM Guides e use-a diretamente no ditamap para publicar

Ele tem configuração mais simples e implementação mais rápida. Porém, a utilização de funcionalidade limitada do recurso do AEM Guides, como a reutilização de conteúdo.

O usuário precisa adicionar o atributo `format="markdown" ` ou `format="mdita"` para que os mecanismos de publicação entendam o tipo de arquivo e publiquem adequadamente.

Arquivo de exemplo: [Markdown Ditamap](https://acrobat.adobe.com/id/urn:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![captura de tela para referência](../../assets/authoring/markdown_map.png)


#### Publicar na saída do PDF e da Web

O AEM Guides oferece a opção da Web (Html5/Site do AEM) e do PDF (Native-PDF/DITA-OT) para publicar ditamap com conteúdo do Markdown

### Opção 2: converter Markdown para o formato DITA

Utilização total da funcionalidade do AEM Guides, que inclui reutilização de conteúdo, tradução de processamento condicional, linha de base etc. Mas seriam necessários esforços iniciais para converter `.md` para o formato `.dita`.

O Markdown em DITA pode ser convertido usando ferramentas externas, como Adobe FrameMaker e DITA-OT.


Para Adobe FrameMaker, consulte: [Importar markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Para DITA-OT, consulte: [Markdown como Entrada](https://www.dita-ot.org/dev/topics/markdown-input.html)

Arquivo de exemplo convertido usando Adobe FrameMaker: [Markdown para amostra DITA](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publicar na saída do PDF e da Web

Depois que os arquivos de marcação forem convertidos em DITA, o usuário poderá publicar a saída facilmente em qualquer formato disponível no AEM Guides.

Formatos disponíveis no AEM Guides: [Formatos de saída](../../../../user-guide/generate-output-understand-presets.md)
