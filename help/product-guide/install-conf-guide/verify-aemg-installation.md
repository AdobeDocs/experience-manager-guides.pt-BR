---
title: Verificar a instalação do AEM Guides
description: Saiba como verificar a instalação do AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Verificar a instalação do AEM Guides {#id213BD030FBE}

Depois de instalar o AEM Guides, você precisa verificar se a instalação foi bem-sucedida ou não.

As guias a seguir fornecem instruções para verificar a instalação do AEM Guides com base na configuração do Experience Manager Guides: Cloud Service ou no local.

>[!BEGINTABS]

>[!TAB Cloud Service]

Execute as seguintes etapas para verificar a instalação:

1. Acesse o Developer Console do seu Cloud Service.

   Para obter detalhes sobre como acessar o Developer Console, consulte [Acesso ao Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) na documentação do AEM.

1. Acesse a lista de pacotes OSGi no AEM.

   Para obter detalhes sobre como acessar pacotes, consulte [Pacotes](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) na documentação do AEM.

1. Procure por fmdita na lista de pacotes e verifique seu status.

   O status deve mostrar *Ativo* para conjuntos implantados com êxito. Se algum dos pacotes não tiver um status Ativo, verifique os registros do AEM para solucionar o problema de instalação.

>[!TAB No local]

Execute as seguintes etapas para verificar a instalação:

1. Faça logon na instância do AEM e navegue até a página AEM Web Console Bundles. O URL padrão para acessar a página de pacotes é:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Uma lista de pacotes é exibida.

1. Filtre a lista de pacotes inserindo fmdita na caixa de texto de filtragem e pressione **Enter**.

   A lista de pacotes é filtrada para mostrar os pacotes instalados pelo AEM Guides. Se a instalação for bem-sucedida, todos os conjuntos instalados terão um **Status** de **Ativo**.

   Se algum dos pacotes não tiver o status **Ativo**, verifique os logs do AEM para solucionar o problema de instalação.


>[!IMPORTANT]
>
> Há várias recomendações de otimização de desempenho que você pode considerar para melhorar o desempenho do seu sistema. Consulte [Recomendações para otimização de desempenho](perf-optimization-on-prem.md#) para obter detalhes.

>[!ENDTABS]


