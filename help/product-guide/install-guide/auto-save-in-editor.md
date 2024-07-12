---
title: Configurar o salvamento automático de arquivos no Editor da Web
description: Saiba como configurar o salvamento automático de arquivos no Editor da Web
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Configurar o salvamento automático de arquivos no Editor da Web {#id199CC0J0M5Z}

Um dos recursos mais comuns no editor baseado em navegador é a capacidade de salvar dados após um período específico. O Editor da Web do AEM Guides também oferece suporte ao salvamento automático de arquivos de tópico e de mapa no intervalo de tempo especificado. Quando esse recurso é acionado, a cópia de trabalho do tópico ou mapa é salva. Não é criada uma nova versão do tópico ou mapa. Para criar uma nova versão, é necessário clicar no ícone Salvar revisão na barra de ferramentas do Editor da Web.

O recurso de salvamento automático não está habilitado por padrão e você precisa habilitá-lo no configMgr. Execute as seguintes etapas para ativar o recurso de salvamento automático no Editor da Web:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nas configurações de *XmlEditorConfig*, selecione a opção **Salvar Automaticamente**.

1. No campo **Intervalo de Salvamento Automático**, especifique o intervalo de tempo em segundos para acionar o recurso de salvamento automático.

1. Clique em **Salvar**.


**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
