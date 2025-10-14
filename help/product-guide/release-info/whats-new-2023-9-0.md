---
title: Notas de versão | Novidades na Adobe Experience Manager Guides, versão de setembro de 2023
description: Conheça os recursos novos e aprimorados da versão de setembro de 2023 do Adobe Experience Manager Guides as a Cloud Service
exl-id: d185d27f-0cbb-4ec6-ac65-cb69f7572c3f
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Novidades da versão de setembro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Este artigo aborda os recursos novos e aprimorados da versão de setembro de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *AEM Guides as a Cloud Service*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte as [Notas de versão](release-notes-2023-9-0.md).

## Conectar a uma fonte de dados e inserir os tópicos

O AEM Guides fornece conectores prontos para uso que ajudam você a se conectar com suas fontes de dados, tornando o AEM Guides um verdadeiro hub de conteúdo. Isso oferece a vantagem de economizar seu tempo e esforço que, de outra forma, seriam gastos na adição ou replicação manual de dados.

Juntamente com os conectores prontos para uso existentes, como JIRA e SQL (MySQL, PostgreSQL, SQL Server, SQLite), o administrador também pode configurar conectores para bancos de dados MariaDB, H2DB, AdobeCommerce e Elasticsearch. Eles também podem adicionar outros conectores estendendo as interfaces padrão.

Você pode exibir os conectores configurados no painel **Fontes de Dados** do Editor da Web.

<img src="assets/data-sources.png" alt="Lista de fontes de dados no painel" width="300">

*Exibir as fontes de dados conectadas.*

Agora também é possível criar um tópico a partir de uma fonte de dados conectada. Um tópico pode conter dados em vários formatos, como tabelas, listas e parágrafos. Também permite criar um mapa DITA para todos os tópicos. Você pode associar metadados ao tópico ao extrair de uma fonte de dados.

Para obter mais detalhes, consulte [Usar dados da sua fonte de dados](../user-guide/web-editor-content-snippet.md).

## Adicionar citações ao seu conteúdo

Citações são referências à fonte de informações adicionada ao conteúdo. Citações ajudam a estabelecer credibilidade e evitar plágios. As citações ajudam os leitores a localizar a fonte e verificar as informações apresentadas no texto.

No AEM Guides, é possível adicionar citações ou importar citações e aplicá-las ao conteúdo. É possível adicionar essas citações de qualquer fonte de livros, sites e diários.

Depois de inserir as citações nos tópicos, você pode visualizá-las no Editor da Web. Você também pode publicar conteúdo com citações usando o PDF nativo.

![Citações listadas em um painel](assets/citation-panel.png){width="300" align="left"}

*Exibir a lista de citações no painel Citações.*

Para obter mais detalhes, exiba [Adicionar e gerenciar citações no seu conteúdo](../user-guide/web-editor-apply-citations.md).


## Publish para um fragmento de conteúdo

Fragmentos de conteúdo são partes distintas do conteúdo no AEM. São conteúdos estruturados com base em um modelo de conteúdo. Fragmentos de conteúdo são conteúdo puro sem informações de design ou layout. Eles podem ser criados e gerenciados independentemente dos canais compatíveis com o AEM. A modularidade e a reutilização dos fragmentos de conteúdo levam a maior flexibilidade, consistência, eficiência e gerenciamento mais simples.

Agora, o AEM Guides oferece uma maneira de publicar um tópico ou os elementos dentro de um tópico em um fragmento de conteúdo. Você pode criar um mapeamento baseado em JSON entre um tópico e um modelo de fragmento de conteúdo. Use esse mapeamento para publicar em um fragmento de conteúdo o conteúdo presente em alguns ou todos os elementos de um tópico.

Aproveite o potencial do AEM Guides e dos fragmentos de conteúdo e use fragmentos de conteúdo em qualquer site de AEM. Também é possível extrair os detalhes por meio de APIs compatíveis com fragmentos de conteúdo.

![opção para publicar o fragmento de conteúdo](assets/content-fragment-publish.png){width="550" align="left"}

*Publish um tópico para um fragmento de conteúdo.*

Para obter mais detalhes, exiba [Publish em um fragmento de conteúdo](../user-guide//publish-content-fragment.md).

## Revisar melhorias

O AEM Guides agora oferece um recurso aprimorado de revisão com as seguintes funcionalidades:

### Pesquisar tópicos de revisão

Realizar revisões é um recurso essencial do AEM Guides. Ajuda os revisores a revisar os documentos atribuídos a eles .
Agora é possível pesquisar um tópico inserindo alguma parte do texto do título ou caminho de arquivo na barra de pesquisa da exibição de tópicos do painel de revisão. Você também pode optar por exibir todos os tópicos ou exibir tópicos com comentários. Por padrão, é possível exibir todos os tópicos presentes na tarefa de revisão. Para obter mais detalhes, consulte [Tópicos da revisão](../user-guide/review-topics.md).

![Pesquisar em um painel de tópicos de revisão](assets/review-search-topic.png){width="800" align="left"}

*Pesquisar um tópico de revisão no painel de revisão.*



## Estrutura de extensão do Guides

Crie pacotes personalizados sobre o AEM Guides para fornecer extensibilidade usando a Estrutura de extensão do AEM Guides. Esses pacotes são úteis para desenvolvedores e consultores e fornecem extensibilidade aos componentes no Editor. Eles podem direcionar botões, caixas de diálogo e listas suspensas e adicionar um JavaScript personalizado que pode interoperar facilmente com a interface do usuário do AEM Guides.



## Aprimoramentos de PDF nativo

Os seguintes aprimoramentos do PDF nativo foram feitos na versão de setembro de 2023 para tornar o AEM Guides um produto mais robusto:



### Ordenar páginas na saída do PDF

Você pode mostrar ou ocultar as seguintes seções no PDF e também organizar a ordem em que elas devem aparecer na saída final do PDF:

* TOC
* Capítulos e tópicos
* Lista de figuras
* Lista de tabelas
* Índice
* Glossário
* Citação
* Layouts de página

Se você não quiser mostrar uma seção específica na saída do PDF, oculte isso desativando o botão de alternância.

Para obter mais detalhes, consulte [Ordem das páginas](../native-pdf/components-pdf-template.md#page-order).

### Mesclar páginas

Em uma saída de PDF nativo por padrão, todas as seções começam em uma nova página. Agora é possível mesclar uma seção com sua página anterior ou com a próxima página. Isso publica a seção em continuação com a página selecionada na saída do PDF e não há quebra de página entre eles.

Para obter mais detalhes, exiba a descrição do recurso **Mesclar páginas** na seção [Ordem das páginas](../native-pdf/components-pdf-template.md#page-order).

### Iniciar qualquer capítulo da página atual

É possível definir as configurações básicas para iniciar um capítulo a partir de uma página ímpar ou par, a estrutura do sumário e definir o formato da linha de chamada para as entradas do sumário.

Agora, você também pode iniciar um capítulo da página atual. Se você optar por fazer isso, todos os capítulos serão publicados sem nenhuma quebra de página. Por exemplo, se um capítulo terminar no meio da página 15, o próximo capítulo também começará a partir da própria 15ª página.

Para obter mais detalhes, consulte a descrição da guia **Geral** em [Configurações Avançadas do PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings-advanced-pdf-settings).

### Páginas estáticas

Você também pode criar layouts de página personalizados e publicá-los como páginas estáticas na saída do PDF. Isso ajuda a adicionar qualquer conteúdo estático, como Notas ou páginas em branco.

Para obter mais detalhes, exiba a descrição do recurso **Páginas estáticas** na seção [Ordem das páginas](../native-pdf/components-pdf-template.md#page-order).


### Variáveis em referências cruzadas

Você pode usar variáveis para definir uma referência cruzada. Quando você usa uma variável, seu valor é extraído das propriedades.

Agora você também pode usar {figure} e {table}.
Use {figure}para adicionar uma referência cruzada ao número da figura. Ele escolhe o número de figura a partir dos estilos de numeração automática que você definiu para a legenda digital.

Use {table} para adicionar uma referência cruzada ao número da tabela. Ele escolhe o número da tabela a partir dos estilos de numeração automática definidos para a legenda.

Para obter mais detalhes, consulte [Referências cruzadas](../native-pdf/components-pdf-template.md##cross-references).



### Reformulação do editor de CSS

Agora, o editor de CSS foi reprojetado para obter uma melhor experiência do usuário com seletores e propriedades de estilo.

#### Aprimoramento da caixa de diálogo Adicionar estilo

Agora é possível usar seletores personalizados para adicionar estilos complexos. O novo campo Seletor ajuda você a adicionar seletores personalizados além da combinação Classe, Tag e Pseudo Classe. Por exemplo, você pode criar o estilo `table a.link` para todos os hiperlinks dentro de uma tabela.

![adicionando estilos nos modelos pdf nativos](assets/add-styles-native-pdf.png){width="300" align="left"}

*Adicionar os detalhes do novo estilo.*

#### Personalizar propriedades de estilo

Agora, o AEM Guides apresenta a você um novo painel de propriedades na seção de visualização para estilos. É possível editar as propriedades dos estilos de forma mais eficiente e rápida no painel de propriedades.


## Suporte para várias definições de assunto em uma única definição de lista discriminada

Agora é possível definir uma ou mais definições de assunto em um mapa e as definições de enumeração em outro mapa e, em seguida, adicionar a referência do mapa. As referências de enumeração de assunto são resolvidas no mesmo mapa ou no mapa referenciado.

Agora você também pode definir condições e aplicá-las a alguns elementos específicos em um tópico.  As condições são visíveis apenas para esses elementos específicos e não para todos os outros elementos.

Para obter mais detalhes sobre como manipular definições hierárquicas de definições de assunto e enumerações, exiba a descrição do recurso Esquema de assunto na seção [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).





## Selecionar todas as predefinições em uma coleção de mapas

É possível não apenas ativar uma predefinição individual e todas as predefinições de perfil de pasta, mas também ativar todas as predefinições de um mapa DITA de uma só vez.
![editar uma coleção de mapas](assets/edit-map-collection-cs.png){width="800" align="left"}\
*Selecione todas as predefinições em uma coleção de mapas.*

Para obter mais detalhes, consulte [Usar Coleção de Mapas para geração de saída](../user-guide/generate-output-use-map-collection-output-generation.md).


## Suporte nativo a PDF no painel Publish em massa


Com o recurso de Ativação em massa do AEM Guides, você pode ativar rápida e facilmente seu conteúdo, desde a criação até a instância de publicação. No mapa de Ativação em massa, é possível incluir a predefinição de saída de PDF nativo, o site AEM, PDF, HTML5, Personalizado e saída JSON.
Para obter mais detalhes, exiba [Ativação em massa do conteúdo publicado](../user-guide/conf-bulk-activation.md).

## Ferramenta de movimentação em massa aprimorada

Agora, como administrador, você pode usar a aprimorada Ferramenta de movimentação em massa para mover pastas com muitos arquivos de um local para outro.
Você pode usar a caixa de diálogo Procurar arquivo para selecionar as pastas de origem que deseja mover. Você também pode procurar e selecionar o local de destino para mover as pastas de origem. Selecione o ![ícone de informações](assets/info-icon.svg) {width="25" align="left"} próximo a um campo para exibir mais informações sobre ele.

Para obter mais detalhes, exiba [Mover arquivos em massa](../user-guide/authoring-file-management.md#move-files-bulk).


## Experiência de visualização aprimorada no menu de contexto

Use o menu de contexto para visualizar rapidamente o arquivo (.dita, .xml, áudio, vídeo ou imagem) sem abri-lo. Agora é possível redimensionar o painel de visualização e, se o conteúdo contiver qualquer link de referência, você poderá selecioná-lo para abri-lo em uma nova guia.

![Painel de visualização &#x200B;](assets/quick-preview_cs.png){width="800" align="left"}

*Visualizar o arquivo no painel.*

Para obter mais detalhes sobre o menu de contexto, consulte a descrição do recurso **Opções de um arquivo** na seção [Painel Esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Usar variáveis para data e hora atuais nas opções Caminho de destino, Nome do site ou Nome do arquivo

Ao gerar saídas no Site ou PDF AEM, você pode usar variáveis para definir as opções **Caminho de Destino**, **Nome do Site** ou **Nome do Arquivo**. Agora você também pode usar as variáveis `${system_date}` e `${system_time}`. Essas variáveis ajudam a anexar a data e a hora atuais a essas opções.

Saiba como [usar variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](../user-guide/generate-output-use-variables.md).
