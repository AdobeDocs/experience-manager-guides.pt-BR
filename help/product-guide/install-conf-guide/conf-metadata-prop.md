---
title: Configurar a lista para ignorar de propriedades de metadados
description: Saiba como configurar e ignorar listas para propriedades de metadados no AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%
---
# Configurar a lista para ignorar de propriedades de metadados

Quando um arquivo é editado, qualquer alteração nos campos de metadados disponíveis em **Propriedades do arquivo** ou aplicado no back-end aciona o asterisco (*) na versão do documento. Para evitar que atualizações de metadados geradas pelo sistema afetem esse indicador, os administradores podem configurar uma lista de itens a serem ignorados para propriedades de metadados.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar a opção **Ignorar propriedade de metadados para versão suja**.


| PID | Chave de propriedade | Valor de propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e clique no pacote **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nas configurações de *XmlEditorConfig*, navegue até a opção **Ignorar propriedade de metadados para versão suja**.

   Revise a lista de propriedades de metadados padrão atualmente configuradas para serem ignoradas.

1. Adicionar ou remover propriedades de metadados de acordo com os requisitos.
1. Selecione **Salvar** para salvar a configuração atualizada.


>[!ENDTABS]

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

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor](customize-overview.md)
