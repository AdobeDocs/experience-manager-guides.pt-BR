---
title: Verificar a instalação do AEM Guides
description: Saiba como verificar a instalação do AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verificar a instalação do AEM Guides {#id213BD030FBE}

Depois de instalar o AEM Guides, você precisa verificar se a instalação foi bem-sucedida ou não. Execute as seguintes etapas para verificar a instalação:

1. Acesse o Developer Console do seu Cloud Service.

   Para obter detalhes sobre como acessar o Developer Console, consulte [acesso ao Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=pt-BR) na documentação do AEM.

1. Acesse a lista de pacotes OSGi no AEM.

   Para obter detalhes sobre como acessar pacotes, consulte [Pacotes](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=pt-BR#bundles) na documentação do AEM.

1. Procure por fmdita na lista de pacotes e verifique seu status.

   O status deve mostrar *Ativo* para conjuntos implantados com êxito. Se algum dos pacotes não tiver um status Ativo, verifique os registros de AEM para solucionar o problema de instalação.


**Tópico pai:**&#x200B;[ Baixar e instalar](download-install.md)
