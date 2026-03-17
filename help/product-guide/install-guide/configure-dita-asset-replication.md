---
title: Configurar a replicação DITA do Assets para serviços no local
description: Saiba como configurar a replicação de ativos essenciais para serviços no local
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 356ea6edd5e688fb1f77e737c705ed0bd4d2e7f0
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
