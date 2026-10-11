---
title: Verificar a instalação do AEM Guides
description: Saiba como verificar a instalação do AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/sniTYknUIyJH0D1moIL3olj3AeBT08kLH52Gba27sqs'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
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
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 0%
---
# Verificar a instalação do AEM Guides {#id213BD030FBE}

Depois de instalar o AEM Guides, você precisa verificar se a instalação foi bem-sucedida ou não. Execute as seguintes etapas para verificar o processo de instalação:

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
> Há várias recomendações de otimização de desempenho que você pode considerar para melhorar o desempenho do seu sistema. Consulte [Recomendações para otimização de desempenho](download-install-recommend-perf-optimiz.md#) para obter detalhes.

**Tópico pai:**[ Baixar e instalar](download-install.md)
