---
title: Notas de versão | Adobe Experience Manager Guides as a Cloud Service, versão de abril de 2023
description: Versão de abril de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/c1aOcwHgxAs11yAalOnlW-ghsTP1Or32TnBwLsc59-M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 386
ht-degree: 0%

---

# Novidades da versão de abril de 2023 do Adobe Experience Manager Guides as a Cloud Service

Este artigo aborda os recursos novos e aprimorados da versão de abril de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *AEM Guides as a Cloud Service*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte o artigo [Notas de versão](release-notes-2023-4-0.md).

## Suporte a metadados avançados na publicação do PDF

O AEM Guides agora fornece suporte avançado para os metadados que são mapeados para os metadados na saída do PDF. As opções de metadados incluem informações sobre o documento e seu conteúdo, como nome do autor, título do documento, palavras-chave, informações de direitos autorais e outros campos de dados.

<img src="assets/pdf-metadata.png" alt=" metadados pdf nativos">

Você pode importar um arquivo do XMP e o AEM Guides pode selecionar as informações do arquivo. Também há a opção de fornecer os nomes e valores dos metadados usando a lista suspensa. Você também pode adicionar metadados personalizados digitando diretamente no campo de nome.


## Painel Modo de Exibição de Estrutura de Tópicos Avançado

O AEM Guides fornece um painel Modo de Exibição de Estrutura de Tópicos aprimorado no qual você obtém a exibição hierárquica dos elementos usados no documento.

<img src="assets/select-element-content-outline-view_cs.png" alt=" metadados pdf nativos">

A Exibição de estrutura de tópicos fornece as seguintes melhorias:

* A lista suspensa Opções de exibição é exibida na parte superior do painel Exibição de estrutura de tópicos. Se um elemento tiver uma ID, um atributo e um texto, você poderá selecioná-los na lista suspensa para exibi-los junto com o elemento. Os atributos que podem ser exibidos no painel Modo de Exibição de Estrutura de Tópicos são determinados pelas configurações de Atributos de Exibição definidas pelo administrador nas **Configurações do Editor**.

* Usando o recurso de pesquisa, você pode pesquisar um elemento por seu nome, id, texto ou valor de atributo.


## Publicação baseada em microsserviços para o AEM Guides as a Cloud Service

O AEM Guides as a Cloud Service fornece o recurso para executar grandes cargas de trabalho de publicação simultaneamente com a publicação baseada em microsserviços e aproveitar a plataforma Adobe I/O Runtime sem servidor, líder do setor.

Agora, na versão de abril, é possível executar várias solicitações de publicação simultaneamente e gerar saídas em massa do PDF com muita eficiência usando a publicação nativa do PDF baseada em microsserviços.
Para obter mais detalhes, consulte [Configurar nova publicação baseada em microsserviço para o AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
