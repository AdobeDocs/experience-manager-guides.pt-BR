---
title: Gerenciar replicação de ativos de origem DITA
description: Saiba como fazer a replicação de ativos de origem DITA
feature: Publishing
role: User
exl-id: 71aec782-2cc1-4fd5-b35b-97a603c3dd48
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%
---
# Gerenciar replicação de ativos de origem DITA

Quando a saída gerada do conteúdo DITA é publicada usando o **Publicação rápida** ou o **Gerenciar publicação** em algum ambiente de publicação, o AEM também tenta publicar os ativos de origem DITA associados, como mapas DITA e, em alguns casos, tópicos DITA. Isso ocorre porque o AEM trata ativos DITA como dependências das páginas de sites geradas.

![](images/quick-publish-site-instance.png){width="350"}

Para impedir a replicação não intencional de conteúdo DITA no ambiente de publicação e evitar problemas de desempenho, os administradores devem gerenciar explicitamente a replicação de ativos DITA por meio do Configuration Manager. Essa configuração permite que os administradores controlem a replicação de tipos de ativos DITA compatíveis, incluindo mapas DITA, tópicos DITA, arquivos XML e arquivos Markdown (.md).

Para configurar o recurso de replicação de ativos DITA, exiba [Configurar a replicação de ativos DITA para o Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) ou [Configurar a replicação de ativos DITA para o No Local](../install-guide/configure-dita-asset-replication.md), dependendo da configuração que você está usando
