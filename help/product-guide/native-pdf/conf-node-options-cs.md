---
title: PDF nativo | Configurar processo de nó para publicação PDF nativa
description: Saiba como configurar o processo de Nó para Publicação nativa no PDF
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 1%

---

# Configurar o processo de nó para publicação nativa do PDF para Cloud Service

A publicação nativa do PDF inicia um processo NodeJs separado para converter os arquivos gerados no processo de publicação em um PDF final. Talvez seja necessário ajustar as configurações desse processo de Nó que executa a publicação do PDF nativo para suportar cenários diferentes. Por exemplo, para executar cargas de trabalho maiores, você deve aumentar o tamanho máximo do heap disponível para o processo NodeJs gerado.

Use as instruções fornecidas em [Substituições de configuração](../install-conf-guide/download-install-config-override.md) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

| PID | Chave de propriedade | Valor de propriedade |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valor da cadeia de caracteres para definir qualquer padrão `NODE_OPTIONS`.<BR> Valor padrão: &quot;&quot; |
