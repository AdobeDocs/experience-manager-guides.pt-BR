---
title: Verificar a instalação do AEM Guides
description: Saiba como verificar a instalação do AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 19cded6f-6545-42af-8511-7c32cf4ddf2d
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '311'
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
