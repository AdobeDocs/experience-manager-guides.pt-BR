---
title: Gerenciar replicação de ativos de origem DITA
description: Saiba como fazer a replicação de ativos de origem DITA
feature: Publishing
role: User
exl-id: 71aec782-2cc1-4fd5-b35b-97a603c3dd48
source-git-commit: 12ba7129255257970ddd7a0989149be664ce9803
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Gerenciar replicação de ativos de origem DITA

Quando a saída gerada do conteúdo DITA é publicada usando o **Publicação rápida** ou o **Gerenciar publicação** em algum ambiente de publicação, o AEM também tenta publicar os ativos de origem DITA associados, como mapas DITA e, em alguns casos, tópicos DITA. Isso ocorre porque o AEM trata ativos DITA como dependências das páginas de sites geradas.

![](images/quick-publish-site-instance.png){width="350"}

Para impedir a replicação não intencional de conteúdo DITA no ambiente de publicação e evitar problemas de desempenho, os administradores devem gerenciar explicitamente a replicação de ativos DITA por meio do Configuration Manager. Essa configuração permite que os administradores controlem a replicação de tipos de ativos DITA compatíveis, incluindo mapas DITA, tópicos DITA, arquivos XML e arquivos Markdown (.md).

Para configurar o recurso de replicação de ativos DITA, exiba [Configurar a replicação de ativos DITA para o Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) ou [Configurar a replicação de ativos DITA para o No Local](../install-guide/configure-dita-asset-replication.md), dependendo da configuração que você está usando
