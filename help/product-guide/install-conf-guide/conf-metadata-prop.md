---
title: Configurar a lista para ignorar de propriedades de metadados
description: Saiba como configurar e ignorar listas para propriedades de metadados no AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
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

**Tópico pai:**[ Personalizar editor](customize-overview.md)
