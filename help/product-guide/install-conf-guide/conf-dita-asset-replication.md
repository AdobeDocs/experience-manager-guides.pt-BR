---
title: Configurar a replicação DITA do Assets
description: Saiba como configurar a replicação de ativos essenciais
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 3%

---

# Configurar a replicação de ativos DITA

As guias a seguir fornecem instruções para configurar o recurso de replicação de ativos DITA com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use as instruções fornecidas em [Substituições de configuração](../install-conf-guide/download-install-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Valor padrão:** &quot;true&quot; |

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.config.ConfigManager*.

1. Defina a configuração `Replicate DITA assets` de acordo com seu requisito. A configuração é ativada por padrão.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Selecione **Salvar**.

>[!ENDTABS]
