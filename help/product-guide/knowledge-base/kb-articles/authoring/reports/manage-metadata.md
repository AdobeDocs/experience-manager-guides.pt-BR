---
title: Gerenciar tags para arquivos DITA no AEM Guides
description: Breve artigo para informar sobre o gerenciamento de cq:tags na AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: f971be4be9e2d32618616727cd9c682941dd3fb2
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# Como adicionar, remover e gerenciar tags no conteúdo DITA

As tags são úteis para categorizar seu conteúdo. Se o conteúdo for marcado corretamente, ele poderá ajudá-lo a localizar tópicos exatos no mapa do editor e o usuário final encontrar o conteúdo apropriado mais rapidamente na saída publicada

> **_OBSERVAÇÃO:_** O artigo a seguir é para o AEM Guides Build 4.2 (no local) /Fev 2023 (versão na nuvem ) ou versões posteriores


## Criar tags

A marcação é um recurso nativo de AEM, e seu administrador de AEM pode ajudar na criação e configuração iniciais dessas tags.


## Adicionar, remover e gerenciar tags no conteúdo DITA

**Quaisquer marcas criadas no AEM cq: podem ser adicionadas, removidas e gerenciadas para seu conteúdo DITA**

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

- [Marcação em Massa usando o Painel do Mapa (Interface do Usuário do Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Relatórios de Ditamap no editor da Web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- [Marcação com AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Contate seu respectivo CSM para quaisquer outras dúvidas**
