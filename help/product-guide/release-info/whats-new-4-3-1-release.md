---
title: Notas de versão | Novidades na versão 4.3.1 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados das versões 4.3.1 do Adobe Experience Manager Guides
exl-id: 14db7453-ccc1-4709-903f-677f55c263b2
feature: What's New
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Novidades da versão 4.3.1 do Adobe Experience Manager Guides (outubro de 2023)

Este artigo aborda os recursos novos e aprimorados da versão 4.3.1 do Adobe Experience Manager Guides (mais tarde conhecido como *Experience Manager Guides*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte as [Notas de versão](./release-notes-4-3-1.md).

## Conectar a uma fonte de dados e inserir os tópicos

O Experience Manager Guides fornece conectores prontos para uso que ajudam você a se conectar com suas fontes de dados, tornando o Experience Manager Guides um verdadeiro hub de conteúdo. Isso oferece a vantagem de economizar seu tempo e esforço que, de outra forma, seriam gastos na adição ou replicação manual de dados.

Juntamente com os conectores prontos para uso existentes, como JIRA e SQL (MySQL, PostgreSQL, SQL Server, SQLite), o administrador também pode configurar conectores para bancos de dados MariaDB, H2DB, AdobeCommerce e Elasticsearch. Eles também podem adicionar outros conectores estendendo as interfaces padrão.

Você pode exibir os conectores configurados no painel **Fontes de Dados** do Editor da Web.

<img src="assets/data-sources.png" alt="Lista de fontes de dados no painel" width="300">

*Exibir as fontes de dados conectadas.*

Agora também é possível criar um tópico a partir de uma fonte de dados conectada. Um tópico pode conter dados em vários formatos, como tabelas, listas e parágrafos. Também permite criar um mapa DITA para todos os tópicos. Você pode associar metadados ao tópico ao extrair de uma fonte de dados.

Para obter mais detalhes, consulte [Usar dados da sua fonte de dados](../user-guide/web-editor-content-snippet.md).

## Configurar um conector de fonte de dados na interface do usuário

O Experience Manager Guides agora também fornece uma ferramenta de **Fontes de Dados** que ajuda a configurar conectores prontos para uso para fontes de dados. Você pode criar facilmente os conectores para bancos de dados JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce e Elasticsearch.

Você também pode editar, reconectar, duplicar ou excluir facilmente um conector de origem de dados. Saiba como [configurar facilmente um conector de fonte de dados na interface do usuário](../install-guide/conf-data-source-connector-tools.md).

![conectores de fonte de dados listados no painel de fontes de dados](assets/data-sources-create-window.png){width="550" align="left"}

*Crie e exiba os conectores de fonte de dados a partir do painel de fontes de dados.*

## Exibir logs do gerador de tópico

Agora você também pode exibir o arquivo de log da geração de conteúdo. Este arquivo de log ajuda a verificar avisos, erros e exceções.  Saiba mais sobre como as [opções de um gerador de tópico](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) ajudam você a gerar e gerenciar facilmente os geradores de tópico.

## Compatibilidade com ferramentas do Velocity em modelos de fonte de dados

Agora você pode usar as ferramentas do Velocity nos modelos do Experience Manager Guides. Essas ferramentas ajudam a aplicar várias funções aos dados obtidos nas fontes de dados. Você pode usar os modelos ao criar um trecho de conteúdo ou um tópico. Esse recurso ajuda a economizar tempo e esforço para aplicar manualmente a mesma função a cada conjunto de dados.  Também garante resultados precisos.
Por exemplo, você pode usar a $mathTool para executar funções matemáticas.
Saiba mais sobre como [usar as ferramentas do Velocity nos modelos de fonte de dados](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Aprimoramentos de PDF nativo

Os seguintes aprimoramentos do PDF nativo foram feitos na versão de outubro de 2023:

### Redefinir o número de página para a primeira página de um layout

Na saída de PDF nativa, é possível reiniciar os números de página e especificar o número a partir do qual a numeração começa. Agora, você também pode iniciar a numeração somente para a primeira ocorrência de uma seção.
Saiba mais sobre como [trabalhar com as propriedades de página de um layout de página](../native-pdf/design-page-layout.md#page-props-page-layout).


### Exibir capítulos sem números automáticos no sumário

O Experience Manager Guides exibe os números dos capítulos junto com os nomes dos capítulos no índice. Agora você pode optar por publicar somente os nomes dos capítulos sem os números dos capítulos. Veja mais detalhes sobre como definir as [configurações avançadas de PDF de um modelo](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Baixar um mapa no Editor da Web

Agora, você não pode apenas editar um mapa na exibição de mapa do Editor da Web, mas também baixá-lo. Você pode optar por baixar o mapa usando uma linha de base específica. Você também tem a opção de nivelar a hierarquia e salvar todos os arquivos e pastas em uma única pasta.

Para obter mais detalhes, consulte a descrição do recurso **Exibição de mapa** na seção [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

![menu de opções de um arquivo no modo de exibição de repositório](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Selecione um arquivo na exibição de repositório e escolha a opção para executar uma ação no arquivo.*


## Suporte para várias definições de assunto em uma única definição de lista discriminada

Agora é possível definir uma ou mais definições de assunto em um mapa e as definições de enumeração em outro mapa e, em seguida, adicionar a referência do mapa. As referências de enumeração de assunto são resolvidas no mesmo mapa ou no mapa referenciado.

Agora você também pode definir condições e aplicá-las a alguns elementos específicos em um tópico.  As condições são visíveis apenas para esses elementos específicos e não para todos os outros elementos.

Para obter mais detalhes sobre como manipular definições hierárquicas de definições de assunto e enumerações, exiba a descrição do recurso Esquema de assunto na seção [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).




## Experiência de visualização aprimorada no menu de contexto

Use o menu de contexto para visualizar rapidamente o arquivo (.dita, .xml, áudio, vídeo ou imagem) sem abri-lo. Agora é possível redimensionar o painel de visualização e, se o conteúdo contiver qualquer link de referência, você poderá selecioná-lo para abri-lo em uma nova guia.

![Painel de visualização ](assets/quick-preview_cs.png){width="800" align="left"}

*Visualizar o arquivo no painel.*

Para obter mais detalhes sobre o menu de contexto, consulte a descrição do recurso **Opções de um arquivo** na seção [Painel Esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Editar um arquivo no plug-in do conector Oxygen

O Experience Manager Guides agora permite selecionar um arquivo no Editor da Web e editar o arquivo no plug-in do conector Oxygen. Essa opção não está ativada como parte do suporte pronto para uso.

Para obter mais detalhes, consulte a descrição do recurso **Opções de um arquivo** na seção [Painel Esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Usar variáveis para data e hora atuais nas opções Caminho de destino, Nome do site ou Nome do arquivo

Ao gerar saídas no Site ou PDF AEM, você pode usar variáveis para definir as opções **Caminho de Destino**, **Nome do Site** ou **Nome do Arquivo**. Agora você também pode usar as variáveis `${system_date}` e `${system_time}`. Essas variáveis ajudam a anexar a data e a hora atuais a essas opções.

Saiba como [usar variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](../user-guide/generate-output-use-variables.md).


## Atalhos de teclado para mover o cursor no Editor da Web

O Experience Manager Guides agora também permite usar atalhos de teclado para mover o cursor no Editor da Web. Você pode usar os atalhos de teclado para mover rapidamente uma palavra para a esquerda ou direita. Também é possível mover para o início ou o fim da linha com a ajuda de atalhos de teclado.

Saiba mais sobre os [atalhos de teclado no Editor da Web](../user-guide/web-editor-keyboard-shortcuts.md).
