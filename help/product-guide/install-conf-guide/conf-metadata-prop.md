---
title: Configurar a lista para ignorar de propriedades de metadados
description: Saiba como configurar e ignorar listas para propriedades de metadados no AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: f74c71d6a4a293bfbae55e9e57c62b7478d0a88a
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# Configurar a lista para ignorar de propriedades de metadados

Quando um arquivo é editado, qualquer alteração nos campos de metadados disponíveis em **Propriedades do arquivo** ou aplicado no back-end aciona o asterisco (*) na versão do documento. Para evitar que atualizações de metadados geradas pelo sistema afetem esse indicador, os administradores podem configurar uma lista de itens a serem ignorados para propriedades de metadados.

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar a opção **Ignorar propriedade de metadados para versão suja**:


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

## Propriedades de metadados padrão na lista para ignorar

O AEM Guides inclui um conjunto padrão de propriedades de metadados na lista de itens a serem ignorados. É possível modificar essa lista para adicionar ou remover propriedades de metadados, conforme necessário.

* &quot;jcr:mixinTypes&quot;,
* &quot;jcr:primaryType&quot;,
* &quot;jcr:frozenMixinTypes&quot;,
* &quot;jcr:frozenPrimaryType&quot;,
* &quot;jcr:frozenUuid&quot;,
* &quot;jcr:uuid&quot;,
* &quot;dam:extracted&quot;,
* &quot;jcr:lastModified&quot;,
* &quot;jcr:lastModifiedBy&quot;,
* &quot;dc:modified&quot;,
* &quot;dam:sha1&quot;,
* &quot;dam:size&quot;,
* &quot;guias:wordCount&quot;,
* &quot;dam:scene7UploadTimeStamp&quot;,
* &quot;dam:scene7LastModified&quot;

Somente as propriedades de metadados que não estão incluídas na lista de itens a serem ignorados são consideradas para marcar a versão de um documento como suja.

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](customize-overview.md)
