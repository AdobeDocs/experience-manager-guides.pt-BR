---
title: PDF nativo | Configurar sinalizadores JVM para publicação de PDF nativo
description: Configurar sinalizadores JVM para publicação de PDF nativo
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# Configurar sinalizadores JVM para publicação de PDF nativo

A publicação de PDF nativo inicia um processo JVM separado para gerar um PDF. Talvez seja necessário ajustar as configurações dessa JVM para suportar diferentes cenários. Por exemplo, para executar cargas de trabalho maiores, você deve aumentar o tamanho máximo do heap disponível para o processo JVM gerado.

Execute as seguintes etapas para configurar os sinalizadores JVM de publicação de PDF nativo de guias AEM:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e selecione o *com.adobe.fmdita.config.ConfigManager* pacote.

1. Atualizar a propriedade **Opções de linha de comando Java para pdf nativo** (*native.pdf.java.opts*) para passar quaisquer flags JVM padrão.



1. Clique em **Salvar**.
