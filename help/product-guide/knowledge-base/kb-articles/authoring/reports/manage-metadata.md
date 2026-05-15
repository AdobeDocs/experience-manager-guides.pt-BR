---
title: Gerenciar tags para arquivos DITA no AEM Guides
description: Breve artigo para informar sobre o gerenciamento de cq:tags na AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
TQID: https://experienceleague.adobe.com/u3MZ3fUZIp-FYQE895I7kDRkF3l96KhwYMRMJ-rG2RE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: c1579802-ddd4-4214-8a91-97b2066abe11id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 0%

---

# Como adicionar, remover e gerenciar tags no conteúdo DITA

As tags são úteis para categorizar seu conteúdo. Se o conteúdo for marcado corretamente, ele poderá ajudá-lo a localizar tópicos exatos no mapa do editor e o usuário final encontrar o conteúdo apropriado mais rapidamente na saída publicada

> **_OBSERVAÇÃO:_** O artigo a seguir é para o AEM Guides Build 4.2 (no local) /Fev 2023 (versão na nuvem ) ou versões posteriores


## Criar tags

A marcação é um recurso nativo do AEM e o administrador do AEM pode ajudar na criação e configuração iniciais dessas tags.


## Adicionar, remover e gerenciar tags no conteúdo DITA

**Qualquer marca criada no AEM cq: marcas podem ser adicionadas, removidas e gerenciadas para seu conteúdo DITA**

Há várias maneiras de adicionar tags ao conteúdo DITA, mas este artigo se concentrará na interface do editor da Web do AEM Guides.

### Etapas:

1. Ir para a exibição de repositório na interface do usuário do Guides
2. Clique duas vezes em ditamap e abra na exibição de mapa
3. Acesse a guia Gerenciar
4. Na guia Gerenciar , vá para a opção Metadados
5. Toda a lista de arquivos ditamap diretos e indiretos é carregada aqui.
6. Selecione um ou mais arquivos e clique no ícone &#39;gerenciar&#39;. Aqui você pode adicionar tags aos arquivos selecionados.
Também é possível remover tags existentes que são comuns em arquivos selecionados.

<img title="Gerenciar tags na AEM Guides " alt="Gerenciar tags no DITA " src="ManageTags.jpg">

## Solução de problemas e perguntas frequentes

### A lista em gerenciar->metadados está vazia ou incompleta

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Instruções de atualização(Indexe seu conteúdo)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=en#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Os metadados personalizados não estão aparecendo na lista

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Outros recursos úteis

- [Marcação em massa usando o painel de mapa (interface do Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Relatórios Ditamap no editor da Web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- [Marcação no AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Contate seu respectivo CSM para quaisquer outras dúvidas**
