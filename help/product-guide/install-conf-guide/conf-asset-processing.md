---
title: Configurar o processamento de ativos para o serviço em nuvem
description: Saiba como configurar o processamento de ativos para o Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 0b66a515-d8f1-4ea6-913f-e152ae114698
source-git-commit: 5af3356dff3c42b8a93ed97b5ee20b23976769a4
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 3%

---

# Configurar o recurso de processamento de ativos

As guias a seguir fornecem instruções para configurar o recurso de processamento de ativos com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valor padrão:** &quot;true&quot; |

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.config.ConfigManager*.

1. Defina a configuração **Habilitar o trabalho agendado de processamento de ativos do Guides** (`enable.asset.processing.scheduler`) de acordo com sua necessidade. A configuração é ativada por padrão.

1. Selecione **Salvar**.

>[!ENDTABS]
