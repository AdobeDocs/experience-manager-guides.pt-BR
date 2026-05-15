---
title: Configurar o trabalho de limpeza da árvore B para serviços no local
description: Configurar o trabalho de limpeza da árvore B para serviços no local
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
TQID: https://experienceleague.adobe.com/qvOHGtHbgKS3xUv0pEXKTqeWblIDj8JKJwik8heXwPo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 2%

---

# Configurar limpeza da árvore B

Configure o trabalho de limpeza da árvore B e gerencie a configuração `Guides B-tree deletion` para manter o sistema otimizado e o armazenamento limpo.

## Configurar trabalho de limpeza da árvore B

Execute as seguintes etapas para configurar o trabalho de limpeza da árvore B:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob*.

1. Atualize a expressão cron para configurar a frequência de execução do trabalho do agendador de limpeza da árvore B.

1. Configure o programador de limpeza da árvore B como mostrado abaixo.

   ![](assets/btree-cleanup-config.png)

1. Selecione **Salvar**.


## Configurar a opção de ativação da exclusão da árvore B dos guias

Execute as seguintes etapas para ativar a configuração:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.config.ConfigManager*.
1. Habilitar a configuração `Guides btree deletion enabled`.

   ![](assets/btree-cleanup-setting.png)

1. Selecione **Salvar**.
