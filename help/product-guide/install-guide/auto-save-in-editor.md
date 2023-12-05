---
title: Configurar o salvamento automático de arquivos no Editor da Web
description: Saiba como configurar o salvamento automático de arquivos no Editor da Web
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Configurar o salvamento automático de arquivos no Editor da Web {#id199CC0J0M5Z}

Um dos recursos mais comuns no editor baseado em navegador é a capacidade de salvar dados após um período específico. O Editor da Web do Guia AEM também oferece suporte ao salvamento automático de arquivos de tópico e mapa no intervalo de tempo especificado. Quando esse recurso é acionado, a cópia de trabalho do tópico ou mapa é salva. Não é criada uma nova versão do tópico ou mapa. Para criar uma nova versão, é necessário clicar no ícone Salvar revisão na barra de ferramentas do Editor da Web.

O recurso de salvamento automático não está habilitado por padrão e você precisa habilitá-lo no configMgr. Execute as seguintes etapas para ativar o recurso de salvamento automático no Editor da Web:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacote.

1. No *XmlEditorConfig* , selecione a **Salvamento automático** opção.

1. No **Intervalo de Salvamento Automático** especifique o intervalo em segundos para acionar o recurso de salvamento automático.

1. Clique em **Salvar**.


**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
