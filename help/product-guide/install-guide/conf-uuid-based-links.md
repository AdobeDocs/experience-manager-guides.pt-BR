---
title: Configurar a exibição de links baseados em UUID
description: Saiba como Configurar a exibição de links baseados em UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Configurar a exibição de links baseados em UUID {#id2035G20M0QN}

Por padrão, ao criar um link usando a opção Inserir referência ou Inserir conteúdo de reutilização no Editor da Web, o link é criado usando a UUID do conteúdo referenciado. A propriedade **Link** \(no painel Propriedades\) do conteúdo referenciado pode ser configurada para mostrar o caminho de arquivo relativo do conteúdo referenciado ou da UUID. Esta exibição é controlada pela opção **Habilitar UUIDs** no configMgr. Por padrão, está ATIVADO, o que implica que a UUID do conteúdo referenciado é mostrada no painel Propriedades.

Execute as seguintes etapas para mostrar o caminho relativo ou a UUID do conteúdo referenciado no Editor da Web:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nas configurações de *XmlEditorConfig*, a opção **Habilitar UUIDs** é habilitada por padrão. Isso implica que a UUID do conteúdo referenciado é mostrada na propriedade **Link** do painel Propriedades.

   Se quiser mostrar o caminho relativo do conteúdo vinculado, desmarque a opção **Habilitar UUIDs**.

1. Clique em **Salvar**.


**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
