---
title: PDF nativo | Configurar sinalizadores JVM para publicação PDF nativa
description: Configurar sinalizadores JVM para publicação nativa no PDF
feature: Output Generation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 1%

---

# Configurar sinalizadores JVM para publicação nativa do PDF no local

A publicação nativa do PDF inicia um processo JVM separado para gerar um PDF. Talvez seja necessário ajustar as configurações dessa JVM para suportar diferentes cenários. Por exemplo, para executar cargas de trabalho maiores, você deve aumentar o tamanho máximo do heap disponível para o processo JVM gerado.

Execute as seguintes etapas para configurar os sinalizadores JVM de publicação PDF nativo do AEM Guides:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.config.ConfigManager*.

1. Atualize a propriedade **Opções de linha de comando Java para pdf nativo** (*native.pdf.java.opts*) para passar por sinalizadores JVM padrão.



1. Clique em **Salvar**.
