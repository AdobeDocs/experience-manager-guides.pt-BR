---
title: Verificar a instalação dos Guias do AEM
description: Saiba como verificar a instalação dos Guias do AEM
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verificar a instalação dos Guias do AEM {#id213BD030FBE}

Depois de instalar os Guias do AEM, é necessário verificar se a instalação foi bem-sucedida ou não. Execute as seguintes etapas para verificar a instalação:

1. Acesse o Developer Console do seu Cloud Service.

   Para obter detalhes sobre como acessar o Console do desenvolvedor, consulte [Acesso ao Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) na documentação do AEM.

1. Acesse a lista de pacotes OSGi no AEM.

   Para obter detalhes sobre o acesso a pacotes, consulte [Pacotes](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) na documentação do AEM.

1. Procure por fmdita na lista de pacotes e verifique seu status.

   O status deve mostrar *Ativo* para pacotes implantados com êxito. Se algum dos pacotes não tiver um status Ativo, verifique os registros de AEM para solucionar o problema de instalação.


**Tópico pai:**[ Baixar e instalar](download-install.md)
