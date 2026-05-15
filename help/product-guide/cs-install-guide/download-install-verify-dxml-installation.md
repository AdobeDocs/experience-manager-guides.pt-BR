---
title: Verificar a instalação do AEM Guides
description: Saiba como verificar a instalação do AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/WDiYcOCdCuaJCrGYCupOS0TEk5TV-1q6Zi5z-S7KWLA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 0%

---

# Verificar a instalação do AEM Guides {#id213BD030FBE}

Depois de instalar o AEM Guides, você precisa verificar se a instalação foi bem-sucedida ou não. Execute as seguintes etapas para verificar a instalação:

1. Acesse o Developer Console do seu Cloud Service.

   Para obter detalhes sobre como acessar o Developer Console, consulte [Acesso ao Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=pt-BR) na documentação do AEM.

1. Acesse a lista de pacotes OSGi no AEM.

   Para obter detalhes sobre como acessar pacotes, consulte [Pacotes](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=pt-BR#bundles) na documentação do AEM.

1. Procure por fmdita na lista de pacotes e verifique seu status.

   O status deve mostrar *Ativo* para conjuntos implantados com êxito. Se algum dos pacotes não tiver um status Ativo, verifique os registros do AEM para solucionar o problema de instalação.


**Tópico pai:**&#x200B;[&#x200B; Baixar e instalar](download-install.md)
