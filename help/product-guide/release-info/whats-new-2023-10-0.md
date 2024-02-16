---
title: Notas de versão | Novidades no Adobe Experience Manager Guides, versão de outubro de 2023
description: Conheça os recursos novos e aprimorados da versão de outubro de 2023 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: 41bfed0d-5901-4ada-b6d7-a5be93b25ba8
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Novidades da versão de outubro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Este artigo aborda os recursos novos e aprimorados da versão de outubro de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *Guias de AEM as a Cloud Service*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte [Notas de versão](release-notes-2023-10-0.md).


## Configurar um conector de fonte de dados na interface do usuário

Os Guias do Experience Manager agora fornecem um **Fontes de dados** ferramenta que ajuda a configurar conectores prontos para uso para fontes de dados. Você pode criar facilmente os conectores para bancos de dados JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce e Elasticsearch.

Você também pode editar, reconectar, duplicar ou excluir facilmente um conector de origem de dados. Saiba como [configurar facilmente um conector de fonte de dados na interface do usuário](../cs-install-guide/conf-data-source-connector-tools.md).

![conectores de fonte de dados listados no painel fontes de dados](assets/data-sources-create-window.png){width="550" align="left"}

*Crie e visualize os conectores de fonte de dados no painel fontes de dados.*

## Exibir logs do gerador de tópico

Agora você também pode exibir o arquivo de log da geração de conteúdo. Este arquivo de log ajuda a verificar avisos, erros e exceções.  Saiba mais sobre como o [opções para um gerador de tópico](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) O ajuda a gerar e gerenciar facilmente os geradores de tópicos.

## Compatibilidade com ferramentas do Velocity em modelos de fonte de dados

Agora você pode usar as ferramentas do Velocity nos modelos de Guias de Experience Manager. Essas ferramentas ajudam a aplicar várias funções aos dados obtidos nas fontes de dados. Você pode usar os modelos ao criar um trecho de conteúdo ou um tópico. Esse recurso ajuda a economizar tempo e esforço para aplicar manualmente a mesma função a cada conjunto de dados.  Também garante resultados precisos.
Por exemplo, você pode usar a $mathTool para executar funções matemáticas.
Saiba como [usar ferramentas do Velocity nos modelos de fonte de dados](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Aprimoramentos de PDF nativo

Os seguintes aprimoramentos do PDF nativo foram feitos na versão de outubro de 2023:

### Redefinir o número de página para a primeira página de um layout

Na saída de PDF nativa, é possível reiniciar os números de página e especificar o número a partir do qual a numeração começa. Agora, você também pode iniciar a numeração somente para a primeira ocorrência de uma seção.
Saiba como [trabalhar com as propriedades de página de um layout de página](../native-pdf/design-page-layout.md#page-props-page-layout).


### Exibir capítulos sem números automáticos no sumário

Os Guias de Experience Manager exibem os números de capítulo juntamente com os nomes de capítulo no Índice. Agora você pode optar por publicar somente os nomes dos capítulos sem os números dos capítulos. Exibir mais detalhes sobre como configurar o [configurações avançadas de PDF de um modelo](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Baixar um mapa no Editor da Web

Agora, você não pode apenas editar um mapa na exibição de mapa do Editor da Web, mas também baixá-lo. Você pode optar por baixar o mapa usando uma linha de base específica. Você também tem a opção de nivelar a hierarquia e salvar todos os arquivos e pastas em uma única pasta.

Para obter mais detalhes, consulte **Exibição de mapa** descrição do recurso na [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS) seção.

![menu de opções de um arquivo na exibição repositório](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Selecione um arquivo na exibição de repositório e escolha a opção para executar uma ação no arquivo.*

## Editar um arquivo no plug-in do conector Oxygen

O Experience Manager Guides agora permite que você selecione um arquivo no Editor da Web e, em seguida, escolha editar o arquivo no plug-in do conector Oxygen. Essa opção não está ativada como parte do suporte pronto para uso.

Para obter mais detalhes, consulte **Opções de um arquivo** descrição do recurso na [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS) seção.
