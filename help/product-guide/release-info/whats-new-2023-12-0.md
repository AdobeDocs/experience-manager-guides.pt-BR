---
title: Notas de versão | Novidades na Adobe Experience Manager Guides, versão de dezembro de 2023
description: Saiba mais sobre os recursos novos e aprimorados da versão de dezembro de 2023 do Adobe Experience Manager Guides as a Cloud Service.
feature: What's New
role: Leader
exl-id: bf8d98e9-97fe-4195-9286-60d8517ab19c
TQID: https://experienceleague.adobe.com/FUb8uzzWMsJKvvnyA-ZjhZzlAKZcM7qTELbBjZQlE-o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: afb45297-4313-4f67-818e-bc0b03abe086
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: cda0baeb-996e-4aaa-92d1-41032e34fd68
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 975
ht-degree: 0%

---

# Novidades da versão de dezembro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Este artigo aborda os recursos novos e aprimorados da versão de dezembro de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *Experience Manager Guides as a Cloud Service*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte as [Notas de versão](release-notes-2023-12-0.md).


## Usar variáveis na saída do PDF

Você pode usar variáveis para inserir e gerenciar dinamicamente informações reutilizáveis. O Experience Manager Guides ajuda a criar, editar e visualizar variáveis enquanto você gera a saída do PDF. Você pode modificar rapidamente os valores das variáveis e tornar seus documentos portáteis e fáceis de atualizar.

![variáveis pdf nativas](assets/add-variable-default.png){width="800"}

*Criar e gerenciar variáveis no Editor da Web.*

Você também pode criar conjuntos de variáveis que substituam os valores padrão e atribuam valores alternativos às variáveis. Insira essas variáveis no layout da página e use o mesmo layout do PDF; não é necessário criar layouts separados para cada conjunto de valores. Por exemplo, é possível criar um conjunto de variáveis para cada versão do produto. Esse conjunto de variáveis pode consistir em variáveis para diferentes detalhes do produto, como nome do produto, número da versão e data de lançamento. Em seguida, é possível adicionar valores diferentes para essas variáveis.

**Conjunto de variáveis 1: Adobe-set1**

* ProductName: Experience Manager Guides
* VersionNumber: 2311
* Data de lançamento: 02/11/2023

**Conjunto de variáveis 2: Adobe-set2**

* ProductName: Experience Manager Guides
* VersionNumber: 2310
* Data de lançamento: 27/09/2023



<img src="./assets/native-pdf-variable-output.png" alt="Rodapé na saída do PDF" width="500" border="2px">

*Gere a saída do PDF usando variáveis no layout do PDF.*

Aplique estilos e use a marcação HTML para formatar as variáveis.  Você também pode atualizar rapidamente os valores de qualquer variável sempre que necessário e gerar novamente a saída. Por exemplo, se você precisar atualizar os detalhes de uma versão, poderá editar o valor da versão na variável VersionNumber e gerar novamente a saída.


Saiba mais sobre como usar [variáveis na saída do PDF](../native-pdf/native-pdf-variables.md).





## Experiência remodelada para editar os atributos

Agora, você obtém uma experiência renovada para adicionar ou editar os atributos de um elemento no painel **Propriedades de conteúdo** no Editor da Web.

![Painel de atributos](assets/attributes-multiple-properties.png){width="300"}

*Adicionar atributos do painel Propriedades de Conteúdo.*

Também é possível editar e excluir facilmente os atributos.

Para obter mais detalhes, consulte a descrição do recurso **Propriedades de Conteúdo** na seção [Painel Direito](../user-guide/web-editor-features.md#id2051EB003YK).


## Editar metadados durante a criação

Agora, durante a criação, você pode atualizar as marcas de metadados do arquivo usando a lista suspensa das **Propriedades do arquivo** no painel direito. Você também pode selecionar **Editar mais propriedades** para atualizar mais metadados.

![propriedades-arquivo](assets/file-properties-general.png){width="300"}

*Atualize os metadados e edite as propriedades do arquivo no painel direito.*

Para obter mais detalhes, consulte a descrição do recurso **Propriedades do Arquivo** na seção [Painel Direito](../user-guide/web-editor-features.md#id2051EB003YK).

## Capacidade de publicar conteúdo na base de conhecimento do ServiceNow

Agora você também pode publicar seu conteúdo na plataforma da base de conhecimento ServiceNow.

Com a versão de dezembro de 2023, como administrador, você pode criar um perfil de publicação para o servidor da base de conhecimento ServiceNow. Em seguida, como autor ou editor, você pode escolher esse perfil de publicação do ServiceNow na predefinição de saída para publicar a saída na base de conhecimento especificada.

Esse recurso ajuda a publicar conteúdo, como texto, vídeos e imagens, na plataforma da base de conhecimento ServiceNow e manter um repositório abrangente.


![predefinição da base de dados de conhecimento do service now](assets/knowledgebase--output-preset.png){width="300"}

*Criar uma predefinição de saída para a base de dados de conhecimento ServiceNow.*

Saiba mais sobre as predefinições de saída da [Base de Dados de Conhecimento](../user-guide/generate-output-knowledge-base.md).

## Painel de coleção do mapa aprimorado

O Experience Manager Guides fornece um painel de coleção de mapa aprimorado. Em uma coleção de mapas, é possível configurar rapidamente as propriedades de metadados em massa para os mapas DITA. Esse recurso é útil, pois não é necessário atualizar as propriedades de metadados de cada mapa DITA individualmente.

Agora é possível exibir o nome do arquivo do mapa DITA. Também é possível exibir as Linhas de Base. Isso ajuda a localizar rapidamente a linha de base usada para uma predefinição.

![Painel da coleção de mapas](assets/map-collection-dashboard.png){width="800"}

*Exiba, edite e gere saída a partir do painel da coleção de mapas.*

Saiba como [usar a Coleção de Mapas para geração de saída](../user-guide/generate-output-use-map-collection-output-generation.md).

## Exibir atributos-chave na Exibição de Mapa

Ao definir atributos principais para o tópico ou referências de mapa, você também pode visualizar o título, o ícone correspondente e a chave no painel esquerdo. A chave é exibida como `key=<key-name>`.

Para obter mais detalhes, consulte a descrição do recurso **Exibição de Mapa** na seção [Painel Esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

![chaves na exibição de mapa](assets/view-key-title-map-view.png) {width="300"}

*Exibir o atributo de chave na Exibição de Mapa.*

## Capacidade de duplicar uma linha de base com base no rótulo

O Experience Manager Guides agora fornece uma experiência do usuário aprimorada para criar as linhas de base no Editor da Web.\
![criar nova linha de base](assets/create-new-baseline.png) {width="300"}
*Criar linha de base a partir do Editor da Web.*

Também permite duplicar uma linha de base com base no rótulo. A versão de referência é separada com base no rótulo fornecido (se existir) durante a duplicação, ou então escolhe a versão da linha de base duplicada.


![duplicar uma linha de base &#x200B;](assets/duplicate-baseline.png) {width="300"}

*Duplique uma linha de base com base em um rótulo ou crie uma cópia exata.*

Saiba mais sobre como [criar e gerenciar linhas de base do Editor da Web](../user-guide/web-editor-baseline.md).

## Resolver links entre mapas na saída do site do AEM

Os links entre mapas (XREF com peer de escopo) que são renderizados na saída do site do AEM agora são resolvidos de acordo com o título do arquivo do conjunto de contexto de publicação do mapa gerado.


## Configure o URL da saída do site do AEM para usar o título do documento

O Experience Manager Guides permite que você, como administrador, configure o URL da saída do site do AEM. Se o nome do arquivo não existir ou contiver todos os caracteres especiais, você pode configurar o para substituí-los por um separador no URL da saída do site do AEM. Você também pode substituí-los pelo nome do primeiro tópico filho. Saiba como [configurar a URL de saída do site do AEM para usar o título do documento](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).
