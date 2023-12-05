---
title: PDF nativo | Configurar processo de nó para publicação de PDF nativo
description: Saiba como configurar o processo de nó para publicação de PDF nativo
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 1%

---

# Configurar processo de nó para publicação de PDF nativo

A publicação de PDF nativo inicia um processo NodeJs separado para converter os arquivos gerados no processo de publicação em um PDF final. Talvez seja necessário ajustar as configurações desse processo de Nó que executa a publicação de PDF nativo para suportar cenários diferentes. Por exemplo, para executar cargas de trabalho maiores, você deve aumentar o tamanho máximo do heap disponível para o processo NodeJs gerado.

Use as instruções fornecidas em [Substituições de configuração](../cs-install-guide/download-install-additional-config-override.md) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

| PID | Chave de propriedade | Valor da propriedade |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valor da string para definir qualquer padrão `NODE_OPTIONS`.<BR> Valor padrão: &quot;&quot; |
