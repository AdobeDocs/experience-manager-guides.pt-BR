---
title: Configurar o trabalho de limpeza da árvore B para serviços no local
description: Configurar o trabalho de limpeza da árvore B para serviços no local
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e1b332b100cc8e3937557e4617d66352c1a0dc3c
workflow-type: tm+mt
source-wordcount: '145'
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

   ![](assets/btree-cleanup-config.png){align="left"}

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

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Selecione **Salvar**.

