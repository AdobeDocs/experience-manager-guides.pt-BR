---
title: Substituições de configuração para o Cloud Service
description: Saiba como configurar substituições
feature: Installation
role: Admin
level: Experienced
exl-id: baf48913-ced7-444f-a125-661c0213d847
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%
---
# Substituições de configuração para o Cloud Service {#id216IFC003XA}

Para fazer atualizações de configuração no Experience Manager Guides as a Cloud Service, a seguinte abordagem genérica deve ser usada:

1. Acesse o repositório Git do Cloud Manager.

1. Crie um novo arquivo JSON no seguinte local:

   `src/main/content/jcr\_root/apps/fmditaCustom/config/`

1. Nomeie o arquivo no seguinte formato:

   `$\{PID\}.cfg.json`

   Aqui, o PID é a ID do processo da configuração.

1. Adicione propriedades no arquivo JSON usando o seguinte formato:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Confirme as alterações e execute o pipeline do Cloud Manager para implantar a configuração atualizada.
