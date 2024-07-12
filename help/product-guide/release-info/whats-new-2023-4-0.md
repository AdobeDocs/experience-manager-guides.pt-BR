---
title: Notas de versão | Versão as a Cloud Service do Adobe Experience Manager Guides de abril de 2023
description: Versão de abril de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Novidades da versão de abril de 2023 do Adobe Experience Manager Guides as a Cloud Service

Este artigo aborda os recursos novos e aprimorados da versão de abril de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *AEM Guides as a Cloud Service*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte o artigo [Notas de versão](release-notes-2023-4-0.md).

## Suporte a metadados avançados na publicação do PDF

O AEM Guides agora fornece suporte avançado para os metadados que são mapeados para os metadados na saída do PDF. As opções de metadados incluem informações sobre o documento e seu conteúdo, como nome do autor, título do documento, palavras-chave, informações de direitos autorais e outros campos de dados.

<img src="assets/pdf-metadata.png" alt=" metadados pdf nativos">

Você pode importar um arquivo XMP e o AEM Guides pode selecionar as informações do arquivo. Também há a opção de fornecer os nomes e valores dos metadados usando a lista suspensa. Você também pode adicionar metadados personalizados digitando diretamente no campo de nome.


## Painel Modo de Exibição de Estrutura de Tópicos Avançado

O AEM Guides fornece um painel Modo de Exibição de Estrutura de Tópicos aprimorado no qual você obtém a exibição hierárquica dos elementos usados no documento.

<img src="assets/select-element-content-outline-view_cs.png" alt=" metadados pdf nativos">

A Exibição de estrutura de tópicos fornece as seguintes melhorias:

* A lista suspensa Opções de exibição é exibida na parte superior do painel Exibição de estrutura de tópicos. Se um elemento tiver uma ID, um atributo e um texto, você poderá selecioná-los na lista suspensa para exibi-los junto com o elemento. Os atributos que podem ser exibidos no painel Modo de Exibição de Estrutura de Tópicos são determinados pelas configurações de Atributos de Exibição definidas pelo administrador nas **Configurações do Editor**.

* Usando o recurso de pesquisa, você pode pesquisar um elemento por seu nome, id, texto ou valor de atributo.


## Publicação baseada em microsserviços para o AEM Guides as a Cloud Service

O AEM Guides as a Cloud Service fornece o recurso para executar grandes cargas de trabalho de publicação simultaneamente com a publicação baseada em microsserviços e aproveitar a plataforma Adobe I/O Runtime sem servidor, líder do setor.

Agora, na versão de abril, você pode executar várias solicitações de publicação simultaneamente e gerar saídas de PDF em massa de maneira muito eficiente, usando a publicação de PDF nativo baseada em microsserviços.
Para obter mais detalhes, consulte [Configurar nova publicação baseada em microsserviço para o AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
