---
title: Configurar a exibição de links baseados em UUID
description: Saiba como Configurar a exibição de links baseados em UUID
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 1%

---

# Configurar a exibição de links baseados em UUID {#id2035G20M0QN}

Por padrão, ao criar um link usando a opção Inserir referência ou Inserir conteúdo de reutilização no Editor, o link é criado usando a UUID do conteúdo referenciado. A propriedade **Link** \(no painel Propriedades\) do conteúdo referenciado pode ser configurada para mostrar o caminho de arquivo relativo do conteúdo referenciado ou da UUID. Para o Cloud Service, por padrão, a UUID do conteúdo referenciado é mostrada no painel Propriedades. Para No Local, essa exibição é controlada pela opção **Habilitar UUIDs** em `configMgr`. Por padrão, está ATIVADO, o que implica que a UUID do conteúdo referenciado é mostrada no painel Propriedades.

As guias a seguir fornecem instruções para mostrar o caminho relativo ou a UUID do conteúdo referenciado no Editor com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para mostrar o caminho relativo ou a UUID do conteúdo referenciado no Editor.

| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booleano \(true/false\). Se quiser mostrar o caminho relativo do conteúdo vinculado, defina essa propriedade como false. <br> **Valor padrão**: verdadeiro |


>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nas configurações de *XmlEditorConfig*, a opção **Habilitar UUIDs** é habilitada por padrão. Isso implica que a UUID do conteúdo referenciado é mostrada na propriedade **Link** do painel Propriedades.

   Se quiser mostrar o caminho relativo do conteúdo vinculado, desmarque a opção **Habilitar UUIDs**.

1. Clique em **Salvar**.

>[!ENDTABS]

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](customize-overview.md)
