---
title: Configurar o Local de Saída Base para Saída de Publicação para Serviços no Local
description: Configurar o Local de Saída Base para Saída de Publicação para Serviços no Local
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%

---

# Configurar Local de Saída Base para saída de publicação para serviços no Local

Execute as seguintes etapas para configurar o local de saída base:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure e selecione o pacote *com.adobe.fmdita.config.ConfigManager*.

1. Atualize a propriedade **Local de Saída Base** para especificar o caminho padrão no repositório do AEM em que o PDF será salvo após a publicação. Além disso, se um caminho inválido for inserido, ele reverterá automaticamente para o caminho padrão: /content/dam/fmdita-outputs.

1. Clique em **Salvar**.


