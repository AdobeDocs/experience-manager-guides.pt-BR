---
title: Inserir um trecho de conteúdo da sua fonte de dados
description: Use dados da sua fonte de dados em Guias do AEM. Saiba como inserir um trecho de conteúdo da sua fonte de dados. Crie um tópico usando o gerador de tópicos.
exl-id: fbd5eff2-451b-49d6-ba77-6eb271e94349
feature: Authoring, Features of Web Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '2066'
ht-degree: 0%

---

# Usar dados da sua fonte de dados

A **fonte de dados** O é um sistema no qual você armazena e gerencia os dados de sua organização. Esses são seus sistemas de registro como JIRA, bancos de dados SQL, PIM ou PLM. Guias de AEM fornece o recurso para se conectar com sua fonte de dados e usar os dados deles.

## Painel Fontes de dados

Selecionar **Fontes de dados** ![](images/data-source-icon.svg) no painel esquerdo para exibir as fontes de dados conectadas. O painel Fontes de dados é aberto e exibe todas as fontes de dados conectadas.

Com base na sua configuração, o administrador pode configurar um conector de fonte de dados:

<details>
<summary> Cloud Services </summary>


- Se estiver usando a versão de outubro de 2023 ou posterior, saiba como [configurar um conector de fonte de dados na interface do usuário](../cs-install-guide/conf-data-source-connector-tools.md) no Guia de instalação e configuração do Cloud Service.

- Se estiver usando a versão de julho de 2023 ou setembro de 2023, saiba como [configurar um conector de fonte de dados](../cs-install-guide/conf-data-source-connector.md) no Guia de instalação e configuração do Cloud Service.

</details>

<details>    
<summary>  Software local </summary>

- Se estiver usando a versão 4.3.1 ou posterior, saiba como [configurar um conector de fonte de dados na interface do usuário](../cs-install-guide/conf-data-source-connector-tools.md) no Guia de instalação e configuração no local.

- Se estiver usando a versão 4.3, saiba como [configurar um conector de fonte de dados](../cs-install-guide/conf-data-source-connector.md) no Guia de instalação e configuração no local.
</details>


>[!NOTE]
>
> Você verá as fontes de dados para as quais o administrador configurou o conector.


## Mostrar Exibição de Lista ou Exibição de Bloco

Você pode alternar entre a Exibição de lista ou Exibição em bloco para exibir as várias fontes de dados no formato de uma lista ou como blocos.

Selecione uma fonte de dados para exibir os geradores de trechos de conteúdo e os geradores de tópicos disponíveis para a fonte de dados selecionada.

### Exibição de lista  ![](images/data-sources-list-view-icon.svg)

![](images/data-sources-list-view.png){width="300" align="left"}

*Lista de fontes de dados conectadas.*

### Exibição lado a lado   ![](images/data-sources-tile-view-icon.svg)

![](images/data-sources-tile-view.png){width="300" align="left"}

*Exibir as fontes de dados conectadas como mosaicos.*

Você pode usar os dados das fontes de dados de duas maneiras:
- Inserir um trecho de conteúdo
- Criar um tópico



## Inserir um trecho de conteúdo da sua fonte de dados

O Guias do AEM fornece o recurso para se conectar com sua fonte de dados. Você pode buscar seus dados, inseri-los em seus tópicos e editá-los. Você pode criar facilmente um trecho de conteúdo usando o gerador de trecho de conteúdo e reutilizá-lo em seus tópicos.

Execute as seguintes etapas para criar um trecho de conteúdo usando o gerador de trecho de conteúdo e insira-o em seu tópico:

1. Selecionar **Fontes de dados** ![](images/data-source-icon.svg)   no painel esquerdo para exibir as fontes de dados conectadas.

1. Selecione uma fonte de dados para exibir os geradores de trecho de conteúdo disponíveis para a fonte de dados selecionada.

   ![](images/code-snippet-generator.png){width="300" align="left"}
   *O painel Fontes de dados lista os geradores de snippet de conteúdo disponíveis.*

1. Selecionar **Adicionar** para adicionar um novo gerador de trecho de conteúdo. A variável **Adicionar gerador de trecho de conteúdo** é aberto.

1. Insira a consulta na caixa de texto Data query.
1. Selecione o modelo que mapeia com sua fonte de dados na **Modelo de mapeamento de dados** lista suspensa.
Os modelos prontos para uso da fonte de dados selecionada são exibidos na lista suspensa. Por exemplo, você pode exibir o modelo &quot;sql-table&quot; para a origem de dados denominada &quot;PostgreSQL&quot;.

   >[!NOTE]
   >  
   > Se o administrador tiver configurado modelos personalizados, esses modelos também serão exibidos na lista suspensa (com base nas configurações de caminho do modelo feitas pelo administrador).
   >   
   >Também é possível usar as ferramentas do Velocity nos modelos. Saiba como [usar as ferramentas do Velocity](#use-velocity-tools).

1. Clique em **Buscar** para buscar os dados da fonte de dados e aplicar o modelo nos dados resultantes da consulta SQL.

1. É possível exibir os dados na visualização ou na exibição da fonte DITA.

   1. A visualização mostra como os dados serão exibidos quando inseridos no conteúdo. A visualização exibe uma pequena fração dos dados no formato do modelo selecionado.
Por exemplo:
      - Se você selecionou o template sql-table, é possível exibir os dados SQL em formato tabular.
      - Se você selecionou o modelo jira-ordered-list, é possível visualizar uma lista ordenada para os problemas do Jira.

   1. A exibição fonte mostra os dados na exibição fonte DITA.
      ![](images/add-content-snippet-generator.png){width="800" align="left"}
      *Adicione um gerador de snippet de conteúdo. Exibir os dados no modo de origem ou de visualização.*

1. Para salvar os resultados da consulta, digite o nome do gerador e clique em **ADICIONAR**.   Um novo gerador de trecho de conteúdo é adicionado à lista.

   >[!NOTE]
   >
   > Você precisa seguir a convenção de nomenclatura de arquivo para o nome do novo gerador de conteúdo. Você não pode ter um espaço no nome do gerador de trecho de conteúdo. Além disso, não é possível salvar um novo gerador de conteúdo com o nome de um gerador de conteúdo existente. Ocorre um erro.

### Opções para um gerador de snippet de conteúdo

Clique com o botão direito do mouse em um gerador de trecho de conteúdo para abrir as Opções. Usando as opções, você pode executar as seguintes operações:

- **Visualizar**: use essa opção para abrir um painel e visualizar uma pequena fração de como os dados são exibidos na saída.
- **Inserir**: use essa opção para inserir o trecho de conteúdo selecionado no tópico aberto para edição no Editor da Web. À medida que os dados são inseridos como um trecho, você também pode editar os dados dentro do tópico no Editor da Web.

  >[!NOTE]
  > 
  > A opção Inserir é exibida somente enquanto você está editando um tópico.

- **Editar**: use essa opção para fazer alterações no gerador de snippet de conteúdo e salvá-lo.
- **Excluir**: use essa opção para excluir o gerador de trecho de conteúdo selecionado.
- **Duplicar**: use essa opção para criar uma duplicata ou uma cópia do gerador de snippet de conteúdo selecionado. A duplicata é criada com um sufixo (como generator_1) por padrão.

### Inserir um trecho de consulta

Você também pode usar a variável **Inserir trecho da consulta** ![](images/data-source-icon.svg)   na barra de ferramentas principal para inserir o trecho de dados nos tópicos.  Você pode selecionar um gerador na lista suspensa, editar sua query ou alterar o modelo e inserir os dados em seu tópico.

![](images/insert-content-snippet.png){width="800" align="left"}

*Editar e inserir um trecho de dados.*

## Criar um tópico usando o gerador de tópicos

Um gerador de tópicos ajuda a criar tópicos contendo dados de suas fontes. Você pode criar rapidamente um gerador de tópico e, em seguida, gerar os tópicos usando o gerador. Cada tópico pode conter dados em vários formatos, como tabelas, listas e parágrafos.   Por exemplo, em um tópico, você pode adicionar uma tabela que inclui os detalhes de todos os novos produtos e uma lista de todos os produtos que serão descontinuados para venda.

O gerador de tópicos pode criar os tópicos que contêm os dados e um mapa DITA para todos os tópicos. Você também pode `<conref>` esses tópicos no seu conteúdo. Isso ajuda a manter os dados sincronizados com a fonte de dados e permite atualizá-los facilmente.



### Criar um tópico

Execute as seguintes etapas para criar um tópico usando o gerador de tópicos:

1. Selecione uma fonte de dados para exibir os geradores de trechos de conteúdo e os geradores de tópicos disponíveis para a fonte de dados selecionada.

   ![](images/data-sources.png){width="300" align="left"}

   *Adicione um gerador de tópico para uma origem de dados conectada.*

1. Selecionar **Adicionar** ![](images/Add_icon.svg) e selecione **Gerador de tópico** na lista suspensa para adicionar um novo gerador de tópico. A variável **Adicionar gerador de tópico** é aberto.



1. Insira os valores nos campos sob as três guias do **Adicionar gerador de tópico** painel:

   **Buscar configuração**

   ![](images/topic-generator-fetch-configuration.png){width="300" align="left"}

   *Adicione a Consulta de dados, o modelo de mapeamento de dados e os detalhes do nó Raiz do gerador de tópicos e dê a ele um nome exclusivo no painel Buscar configuração.*

   1. Insira a consulta no **Consulta de dados** texto.
   1. Selecione o modelo que mapeia com sua fonte de dados na **Modelo de mapeamento de dados** lista suspensa.

      >[!NOTE]
      >
      > Se o administrador tiver configurado modelos personalizados, esses modelos também serão exibidos na lista suspensa (com base nas configurações de caminho do modelo feitas pelo administrador). Por exemplo, você pode criar um modelo de tópico contendo uma lista ordenada, tabelas, parágrafos ou outros elementos DITA.

   1. Insira o **Nó raiz**. Esse é o nó no qual você deseja acessar seus dados. O gerador de tópicos cria cada tópico no nível definido no nó raiz. Por exemplo, você pode adicionar ‘problemas’ como o nó raiz no Jira. Portanto, se um query retornar 13 problemas, você terá 13 tópicos, um tópico para cada problema.

   1. Clique em **Buscar** para buscar os dados da fonte de dados e aplicar o modelo nos dados resultantes da consulta SQL. A visualização mostra uma pequena fração de como o tópico aparece no formato do modelo selecionado. Por exemplo, você pode visualizar um único problema do Jira com todos os campos resultantes da query.
   1. Informe o nome do gerador de tópico.

      >[!NOTE]
      > 
      > Você precisa seguir a convenção de nomenclatura de arquivo para o nome do novo gerador de tópico. Você não pode ter um espaço no nome do gerador de tópico. Além disso, não é possível salvar um novo gerador de tópicos com o nome de um gerador de tópicos existente. Ocorre um erro.

   **Configuração de saída**

   ![](images/topic-generator-output-configuration.png){width="300" align="left"}

   *Insira os detalhes do Caminho de saída e da Convenção de nomenclatura do tópico no painel Configuração de saída. Gere um mapa DITA e nomeie-o.*

   1. Insira o **Caminho de saída** detalhes em que você deseja salvar seus tópicos.
   1. No **Convenção de nomenclatura de tópico**, você pode inserir um valor ou uma variável com tags do velocity. Os novos tópicos seguirão a convenção. Por exemplo, você pode inserir a variável `$key` para criar tópicos com base em chaves Jira.
   1. Ativar a opção **Gerar um mapa** se quiser criar um mapa que contenha todos os tópicos gerados.
   1. Insira o nome do novo mapa DITA.

   >[!NOTE]
   >
   > O gerador de Tópico gera o mapa DITA no mesmo caminho de saída dos tópicos.

   **Metadados**

   Selecione as propriedades de metadados no menu suspenso para transmitir aos tópicos. **Nome** lista suspensa as propriedades personalizadas e padrão.

   Por exemplo, na captura de tela a seguir, `dc:description`, `dc:language`, `dc:title`, e `docstate` são as propriedades padrão para as quais você pode definir os valores. Você pode criar uma propriedade personalizada como autor e definir seu valor.

   ![](images/topic-generator-metadata.png){width="300" align="left"}

   *Adicione as propriedades dos metadados no painel Metadados para passar para os tópicos.*

1. Insira o nome do gerador e clique em **Salvar** para salvar os resultados da consulta. Um novo gerador de tópico é adicionado à lista.

1. Clique em **Salvar e gerar** para salvar o gerador de tópicos e gerar novos tópicos a partir dele.



   ![](images/edit-topic-generator.png){width="650" align="left"}

   *Gerar novos tópicos a partir de um gerador de tópicos existente.*

   >[!NOTE]
   >
   > Se os tópicos já existirem, o gerador atualizará os dados nos tópicos existentes.

### Opções para um gerador de tópico

Clique com o botão direito do mouse em um gerador de tópico para abrir o **Opções**. Usando as opções, você pode executar as seguintes operações:

- **Gerar**: Essa opção gera os tópicos para o gerador de tópicos selecionado. Também é possível usar essa opção para atualizar os tópicos existentes. Ele se conecta à fonte de dados e busca os dados atualizados. Ao gerar o conteúdo, essa opção é desativada e você visualiza um carregador.
  >[!NOTE]
  >
  >Se o tópico já existir, você poderá substituir os dados nele contidos ou salvá-lo como uma nova versão.

  ![](images/generate-topic-options.png)

  *Gere um tópico e, se o arquivo já existir, salve-o como uma nova versão ou substitua-o.*
- **Exibir registro**: selecione esta opção para exibir o arquivo de log de geração de conteúdo. O arquivo de log é aberto em uma nova guia. Você pode exibir os erros, avisos, mensagens de informações e exceções no arquivo de log. Essa opção estará ativada se você tiver gerado o conteúdo para o gerador de tópicos selecionado.

- **Visualizar**: use essa opção para abrir um painel e visualizar uma pequena fração de como os dados são exibidos na saída.



- **Editar**: Use essa opção para alterar e salvar o gerador de tópicos. Essa opção é desativada enquanto você está gerando o conteúdo.
- **Excluir**: Use essa opção para excluir o gerador de tópicos selecionado. Essa opção é desativada enquanto você está gerando o conteúdo.
- **Duplicar**: Essa opção cria uma duplicata ou cópia do gerador de tópicos selecionado. A duplicata é criada com um sufixo (como `topic-sample_1`) por padrão.



## Usar ferramentas do Velocity nos modelos de fonte de dados {#use-velocity-tools}

Os modelos de Experience Manager também são compatíveis com as ferramentas do Velocity (versão 2.0). Essas ferramentas ajudam a aplicar várias funções aos dados obtidos nas fontes de dados. Saiba mais sobre o uso do [Ferramentas do Velocity](https://velocity.apache.org/tools/2.0/generic.html) e as funções que podem ser aplicadas.

Execute as seguintes etapas para usar uma ferramenta Velocity em um modelo:
1. Editar um modelo do Velocity no Editor da Web.
1. Adicione uma ferramenta e sua função na `<tool.function>` formato. Por exemplo:
   - Para gerar um número aleatório usando a ferramenta matemática, use `$mathTool.random`.
   - Para gerar a soma de números usando a ferramenta matemática, use `$mathTool.add(num1, num2)`.
1. Use o modelo para criar um trecho de conteúdo ou tópico.
1. Após aplicar o modelo aos dados, é possível exibi-los na visualização ou na exibição da fonte DITA.




Você pode usar as seguintes ferramentas nos modelos do Velocity para aplicar várias funções aos dados obtidos do conector: -`$alternatorTool`
- `$classTool`
- `$contextTool`
- `$conversionTool`
- `$dateTool`
- `$comparisonDateTool`
- `$displayTool`
- `$escapeTool`
- `$fieldTool`
- `$loopTool`
- `$linkTool`
- `$listTool`
- `$mathTool`
- `$numberTool`
- `$renderTool`
- `$resourceTool`
- `$sortTool`
