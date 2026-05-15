---
title: Configurar o Local de Saída Base para Saída de Publicação para Serviços no Local
description: Configurar o Local de Saída Base para Saída de Publicação para Serviços no Local
feature: Output Generation
role: Admin
level: Experienced
exl-id: ae1d805a-7b79-4b76-8be2-a19c5552530c
TQID: https://experienceleague.adobe.com/qf1UZh14gvlc7ZHUUBaDlHe1U3zDvzGlGjYavYKITWY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 112
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
