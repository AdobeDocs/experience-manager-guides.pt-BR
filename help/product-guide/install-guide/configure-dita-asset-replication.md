---
title: Configurar a replicação DITA do Assets para serviços no local
description: Saiba como configurar a replicação de ativos essenciais para serviços no local
feature: Output Generation
role: Admin
level: Experienced
exl-id: 49fd9dfe-e1a5-4388-abbd-ec5d45669b45
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 2%

---

# Configurar a replicação de ativos DITA

Execute as seguintes etapas para configurar o recurso de processamento de ativos:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.config.ConfigManager*.

1. Defina a configuração `Replicate DITA assets` de acordo com seu requisito. A configuração é ativada por padrão.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Selecione **Salvar**.
