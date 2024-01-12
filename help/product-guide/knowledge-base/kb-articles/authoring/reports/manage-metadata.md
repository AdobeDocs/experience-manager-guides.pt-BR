---
title: Gerenciar tags para arquivos DITA nos Guias AEM
description: Breve artigo para informar sobre o gerenciamento de cq:tags em guias AEM
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# Como adicionar, remover e gerenciar tags no conteúdo DITA

As tags são úteis para categorizar seu conteúdo. Se o conteúdo for marcado corretamente, ele poderá ajudá-lo a localizar tópicos exatos no mapa do editor e o usuário final encontrar o conteúdo apropriado mais rapidamente na saída publicada

> **_NOTA:_**  O artigo a seguir é para o AEM Guides Build 4.2 (no local) /Fev 2023 (versão em nuvem ) ou versões posteriores


## Criar tags

A marcação é um recurso nativo de AEM, e seu administrador de AEM pode ajudar na criação e configuração iniciais dessas tags.


## Adicionar, remover e gerenciar tags no conteúdo DITA

**Quaisquer tags criadas no AEM cq: tags podem ser adicionadas, removidas e gerenciadas para o conteúdo DITA**

Há várias maneiras de adicionar tags ao conteúdo DITA, mas este artigo se concentrará na interface do editor da Web do AEM Guides.

### Etapas:

1. Ir para a exibição de repositório na interface do usuário do Guides
2. Clique duas vezes em ditamap e abra na exibição de mapa
3. Acesse a guia Gerenciar
4. Na guia Gerenciar , vá para a opção Metadados
5. Toda a lista de arquivos ditamap diretos e indiretos é carregada aqui.
6. Selecione um ou mais arquivos e clique no ícone &#39;gerenciar&#39;. Aqui você pode adicionar tags aos arquivos selecionados.
Também é possível remover tags existentes que são comuns em arquivos selecionados.

<img title="Gerenciar tags em guias AEM " alt="Gerenciar tags no DITA " src="ManageTags.jpg">

## Solução de problemas e perguntas frequentes

### A lista em gerenciar->metadados está vazia ou incompleta

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Instruções de atualização (indexar o conteúdo)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=en#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Os metadados personalizados não estão aparecendo na lista

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Outros recursos úteis

- [Marcação em massa usando o painel de mapa (interface do usuário do Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Relatórios Ditamap no editor da Web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- [Marcação no AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Entre em contato com o respectivo CSM para tirar qualquer dúvida**
