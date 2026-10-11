---
title: Configurar trabalho de limpeza do armazenamento de referência
description: Configurar trabalho de limpeza do armazenamento de referência
feature: Output Generation
role: Admin
level: Experienced
exl-id: 58f98313-fc91-43b3-9553-aa5ab4946925
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 3%
---
# Configurar limpeza do armazenamento de referência

Configure o trabalho de limpeza do repositório de Referência e gerencie a configuração `Guides BTree deletion` para manter o sistema otimizado e o armazenamento limpo.

## Configurar trabalho de limpeza de armazenamento de referência

As guias a seguir fornecem instruções para configurar o trabalho de limpeza da loja de referência com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Valor padrão:** &quot;0 0 0 * * * ?&quot; |

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob*.

1. Atualize a expressão cron para configurar a frequência de execução do trabalho do agendador de limpeza de armazenamento de referência.

1. Configure o Agendador de limpeza de armazenamento de referência conforme mostrado abaixo.

   ![](assets/btree-cleanup-config.png)

1. Selecione **Salvar**.

>[!ENDTABS]

## Configurar a opção de ativação da exclusão da árvore B dos guias

As guias a seguir fornecem instruções para ativar a configuração com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use as instruções fornecidas em [Substituições de configuração](download-install-config-override.md) para criar o arquivo de configuração.

1. No arquivo de configuração, forneça os seguintes detalhes (propriedade):

   | PID | Chave de propriedade | Valor de propriedade |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Valor padrão:** &quot;True&quot; |

>[!TAB No local]

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.config.ConfigManager*.
1. Habilitar a configuração **Exclusão de btree de guias habilitada** (btree.deletion.enabled).

   ![](assets/btree-cleanup-setting.png)

1. Selecione **Salvar**.

>[!ENDTABS]
