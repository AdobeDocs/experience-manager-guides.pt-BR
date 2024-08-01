---
title: Usar Markdown no DITA AEM Guides
description: Migrar e usar markdown no DITA AEM Guides
source-git-commit: b4235841798fb12b3d0491e33b4466073ac02ef3
workflow-type: tm+mt
source-wordcount: '256'
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


#### Publish para PDF e saída da Web

O AEM Guides oferece a opção da Web (Html5/AEM Site) e PDF (Native-PDF/DITA-OT) para publicar ditamap com conteúdo do Markdown

### Opção 2: converter Markdown para o formato DITA

Utilização total da funcionalidade do AEM Guides, que inclui reutilização de conteúdo, tradução de processamento condicional, linha de base etc. Mas seriam necessários esforços iniciais para converter `.md` para o formato `.dita`.

O Markdown em DITA pode ser convertido usando ferramentas externas, como Adobe FrameMaker e DITA-OT.


Para Adobe FrameMaker, consulte: [Importar markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Para DITA-OT, consulte: [Markdown como Entrada](https://www.dita-ot.org/dev/topics/markdown-input.html)

Arquivo de exemplo convertido usando Adobe FrameMaker: [Markdown para amostra DITA](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publish para PDF e saída da Web

Depois que os arquivos de marcação forem convertidos em DITA, o usuário poderá publicar a saída facilmente em qualquer formato disponível no AEM Guides.

Formatos disponíveis no AEM Guides: [Formatos de saída](../../../../user-guide/generate-output-understand-presets.md)
