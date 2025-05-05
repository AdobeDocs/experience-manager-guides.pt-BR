---
title: Recursos do Editor de Mapa
description: Conhecer os recursos do Editor de mapas no Adobe Experience Manager Guides. Edite tópicos por meio de um mapa DITA e use o modo de exibição de layout, de criação e de visualização.
exl-id: e58e3705-2c3b-48cc-b2c8-2596e9751c85
feature: Authoring, Map Editor
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '2570'
ht-degree: 0%

---

# Recursos do Editor de Mapa {#id1942D0S0IHS}

A barra de ferramentas no Editor de Mapa é semelhante ao Editor de tópico. As operações básicas, como alternar o painel esquerdo, salvar o mapa, criar uma nova versão do mapa, desfazer/refazer a última operação e excluir os elementos selecionados, são comuns em ambos os editores. Para obter detalhes sobre como essas operações funcionam, consulte a seção [Conhecer os recursos do Editor](web-editor-features.md#).

As opções exibidas na barra de ferramentas do editor se baseiam na visualização Editor de mapa. Há quatro exibições disponíveis no Editor de mapa:

- [Layout](#layout-view)
- [Autor](#author-view)
- [Origem](#source-view)
- [Visualização](#preview)

As seções a seguir abordam as opções da barra de ferramentas disponíveis nas diferentes visualizações do Editor de mapas:

## Exibição de layout

Quando você abre um mapa para edição, ele abre a exibição de layout do Editor de mapas. A exibição de layout mostra a hierarquia de mapa em uma exibição em árvore e permite organizar os tópicos em um mapa.

>[!NOTE]
>
> A exibição de layout exibe apenas as referências presentes em um mapa. Se alguma referência for quebrada, um pequeno símbolo de cruz será exibido à esquerda da referência

As seguintes opções estão disponíveis na barra de ferramentas da exibição de layout:

**Referência de tópico** - ![](images/topic-reference.svg)

Exibe a caixa de diálogo de pesquisa de tópico. Navegue até o arquivo de tópico/mapa que você deseja inserir e escolha **Selecionar** para adicioná-lo ao mapa.

![](images/insert-topic-reference-dialog.png){align="left"}


**Grupo de tópicos** - ![](images/topic-group.svg)

Insira o elemento `topicgroup`. Para obter mais informações sobre tópicos de agrupamento, consulte a documentação do [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) na Especificação de Linguagem OASIS DITA.

**Definição de chave** - ![](images/key-definition.svg)

Exibe a caixa de diálogo Inserir Keydef. Use esta caixa de diálogo para definir qualquer definição de chave que você deseja usar no mapa.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Inserir Antes/Inserir Depois** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Exibe a caixa de diálogo Inserir elemento. Selecione o elemento que deseja inserir no mapa. Dependendo da operação, o novo elemento é inserido antes ou depois do elemento atual no mapa.

**Inserir assunto principal** - ![](images/frontmatter.svg)

Esse ícone é exibido quando você abre um bookmap para edição. Você pode inserir componentes no início do livro como um índice, um índice e uma lista de tabelas.

**Inserir pendência** - ![](images/backmatter.svg)

Esse ícone é exibido quando você abre um bookmap para edição. Você pode inserir componentes para no final do livro, como um índice, um glossário e uma lista de figuras.

**Mover o item selecionado para a esquerda/direita** - ![](images/move-left.svg) / ![](images/move-right.svg)

Selecione a seta para a esquerda para mover o tópico para o lado esquerdo na hierarquia. Isso basicamente promove o respectivo tópico um nível acima na hierarquia. Por exemplo, ao selecionar a seta para a esquerda enquanto um tópico filho é selecionado, torne-o irmão do tópico acima dele. Da mesma forma, se você selecionar a seta para a direita, o tópico será empurrado para o lado direito, tornando-se o filho do tópico acima dele.

**Mover o item selecionado para cima/para baixo** ![](images/move-up.svg) - / ![](images/move-down.svg)

Selecione os ícones de seta para cima ou para baixo para mover o tópico para cima ou para baixo na hierarquia.

>[!NOTE]
>
> Você também pode arrastar e soltar as referências para movê-las em um mapa.

**Bloquear/Desbloquear**

Obtém um bloqueio no arquivo de mapa e libera o bloqueio. Se houver alterações não salvas no arquivo de mapa, no momento do lançamento do bloqueio, será solicitado que você salve o arquivo de mapa. As alterações são salvas na versão atual do arquivo de mapa.

**Mesclar** - ![](images/merge.svg)

Para obter mais detalhes sobre como mesclar o conteúdo de uma versão diferente do mesmo arquivo ou de um arquivo diferente, consulte [Mesclar](web-editor-features.md#menu-dropdown) no Editor.

**Histórico de versões** - ![](images/version-history-web-editor-ico.svg)

Verifique as versões e rótulos disponíveis no tópico ativo e reverta para qualquer versão do próprio editor.

**Rótulo da versão** - ![](images/version-label.svg)

Exibe a caixa de diálogo de gerenciamento de rótulo da versão. Selecione uma versão na lista suspensa. Escolha o rótulo que deseja aplicar à versão selecionada e selecione **Adicionar rótulo** para adicioná-lo.

**Mostrar nome do arquivo**

Mostra o nome do arquivo dos títulos dos tópicos.

>[!NOTE]
>
> Ao passar o ponteiro sobre o título de um tópico, é mostrado o caminho do arquivo.

**Mostrar números de linha**

Mostra ou oculta o número da linha de cada tópico. Os números de linha são mostrados dependendo do nível na hierarquia.

**Mostrar caixa de seleção**

Mostra ou oculta uma caixa de seleção para cada tópico. Você pode usar a caixa de seleção para selecionar o tópico\(s\) e executar várias tarefas usando o menu Opções.

**Menu de opções no modo de exibição de layout**

Além de organizar tópicos no arquivo de mapa, você também pode executar as seguintes ações usando o menu Opções que aparece ao passar o mouse sobre um arquivo ou clicar com o botão direito do mouse no editor na exibição de layout:

![](images/map-editor-options-menu.png){width="650" align="left"}

- **Adicionar**: você pode optar por adicionar um novo tópico ou uma referência vazia do Editor de Mapa:
   - **Referência vazia**: essa opção permite adicionar uma referência vazia ao mapa DITA. Você pode clicar duas vezes na referência vazia inserida posteriormente e adicionar os detalhes do tópico.
   - **Novo tópico**: quando você opta por criar um novo tópico do menu, a caixa de diálogo **Novo tópico** é exibida. Na caixa de diálogo **Novo tópico**, forneça os detalhes necessários e selecione **Criar**.
- **Mover**: você pode optar por mover um tópico para cima/baixo/direita/esquerda na hierarquia. Você também pode arrastar e soltar um tópico ou um mapa do painel do repositório no mapa aberto no Editor de Mapas.
- **Desfazer**: desfaz a última operação no modo de exibição de layout.
- **Refazer**: refaz a última operação no modo de exibição de layout.
- **Copiar**: copie a referência selecionada do arquivo de mapa.

  >[!NOTE]
  >
  > Você pode exibir e marcar as caixas de seleção para copiar várias referências.

- **Colar**: Cola as referências copiadas no local atual na hierarquia.
- **Excluir**: excluir as referências selecionadas do arquivo de mapa.

  >[!NOTE]
  >
  > Você pode exibir e marcar as caixas de seleção para excluir várias referências.

**Exibir tópicos com base em filtros condicionais**

Se você tiver aplicado condições em um tópico, um ícone de filtro será exibido à direita do tópico. Ao passar o ponteiro sobre um ícone de filtro, é exibida a condição aplicada e seu valor de atributo.

## Visualização do autor

A exibição **Author** permite editar o mapa DITA no Editor. Isso mostra a visualização WYSIWYG do Editor de mapas e alguns dos ícones exibidos na visualização Autor são iguais à visualização Layout.

![](images/map-editor-author-view.png){align="left"}

Além disso, você pode exibir os seguintes ícones e executar as tarefas relacionadas na exibição Autor:

**Inserir antes/Inserir depois de** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Exibe a caixa de diálogo **Inserir elemento antes ou &#x200B;** Inserir elemento após. Selecione o elemento que deseja inserir no mapa. Dependendo da operação, o novo elemento é inserido antes ou depois do elemento atual no mapa.

**Elemento** - ![](images/Add_icon.svg)

Exibe a caixa de diálogo **Inserir elemento**. Selecione o elemento que deseja inserir. Você pode usar o teclado para rolar pela lista de elementos e pressionar Enter para inserir o elemento necessário. Como alternativa, você pode selecionar o elemento para inseri-lo no mapa.




<!-----------------------------------------------------------

**Relationship table** - ![](images/relationship_table_icon.svg)

Inserts a relationship table in the map.

Perform the following steps to work with relationship tables in the Basic Map Editor:

1.  In the Assets UI, navigate to the DITA map in which you want to create the relationship table.

1.  Select the DITA map to open it in DITA map console.

1.  Select the **Topics** tab to view a list of topics available in the DITA map.

    >[!TIP]
    >
    > The Topics tab gives you an option to download the map file with its dependents. For more details, view [Export a DITA map file](authoring-download-assets.md#id218UBA00IXA).

1.  In the main toolbar, select **Edit**.

    The map file is opened in the Advanced Map Editor.

1.  Select **Reltable** from the toolbar.

    ![](images/reltable.png){width="650" align="left"}

1.  Drag-and-drop topics from the topic list to the Reltable editor.

    >[!NOTE]
    >
    > You can add topics from any folder in the References rail.

    ![](images/create-reltable.png){width="550" align="left"}

1.  To add a header to your relationship table, click **Add Relheader**.

1.  To add a column to your relationship table, click **Add a Column**.

    ![](images/complete-reltable.png){width="550" align="left"}

1.  Click **Save**.


You can also perform the following actions from the relationship table editor:

**Delete rows or columns**

If you want to delete a column from your table, select the checkbox in the column header and click Delete. If you want to remove a row from table, select the checkbox in the first column of the respective row and click Delete.

**Delete a topic**

If you want to delete a topic from your table, click the cross icon next to the topic.

**Delete the relationship table**

If you want to delete the relationship table, click anywhere outside the relationship table and click Delete. For details, view [Work with relationship tables in the Map Editor](map-editor-basic-map-editor.md).
----->

**Conteúdo reutilizável** - ![](images/reusable-content.svg)

Exibe a caixa de diálogo **Reutilizar conteúdo**. Use esta caixa de diálogo para inserir o conteúdo que você deseja reutilizar no mapa.

**Atualizar atributo de título de navegação** - ![](images/refresh.svg)

Sincroniza o elemento `title` de um arquivo referenciado em um mapa com o valor especificado em seu atributo `@navtitle`. É possível adicionar diferentes tipos de arquivos de referência em um mapa, por exemplo, tópico, referência, tarefa, mapas \(sub\) e assim por diante. A maioria desses arquivos oferece suporte ao atributo `@navtitle`. Se um arquivo contiver o atributo `@navtitle`, o atributo `@navtitle` para o mesmo arquivo no mapa será atualizado. Caso o atributo `@navtitle` não esteja presente, o atributo `@navtitle` é adicionado a esse arquivo de referência e seu `title` também é atualizado para exibir o `@navtitle`.

>[!NOTE]
>
> O administrador pode configurar a adição automática do atributo `@navtitle` a cada arquivo de referência adicionado a um mapa. Para obter mais detalhes sobre como configurar a adição automática do atributo `@navtitle`, exiba *Incluir atributo @navtitle por padrão* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

Selecione o ícone Atualizar atributo de título de navegação para sincronizar os valores do elemento `title` e do atributo `@navtitle`.

**Tags**

Mostra ou oculta as marcas de formatação XML. As tags servem como dicas visuais que indicam o limite de um elemento. Nesse modo, se você quiser inserir uma referência de tópico/mapa, arraste e solte o arquivo desejado antes ou depois da tag. A barra horizontal não é mostrada no modo de Exibição de tags.

**Controlar alterações** - ![](images/track-changes.svg)

Você pode acompanhar todas as atualizações feitas no arquivo de mapa habilitando o modo Controlar Alterações. Depois de ativar o controle de alterações, todas as inserções e exclusões são capturadas no documento. Para obter mais detalhes, consulte [Controlar alterações](web-editor-features.md#track-changes) no Editor.

**Criar tarefa de revisão** - ![](images/create-review-task.svg)

Você pode criar uma tarefa de revisão do tópico atual ou mapear o arquivo diretamente do Editor. Abra o arquivo para o qual deseja criar a tarefa de revisão e selecione **Criar tarefa de revisão** para iniciar o processo de criação da revisão. Siga as instruções fornecidas na [Introdução à revisão](review.md#) para obter mais detalhes.

## Visualização do Source

Essa visualização permite editar o conteúdo em seu formato bruto, fornecendo controle total sobre a estrutura e a formatação.

![](images/map-editor-source-view.png){align="left"}


Nesta exibição, a barra de ferramentas fornece opções básicas de edição de conteúdo e inserção disponíveis no menu suspenso **Menu**, incluindo Recortar, Copiar, Desfazer, Refazer, Excluir, Localizar e substituir, Rótulo de versão, Mesclar, Salvar como nova versão, Bloquear e Desbloquear.

## Visualização

O modo de Visualização renderiza o conteúdo como ele aparecerá na saída final, permitindo que você revise o layout e a formatação antes de publicá-lo.

Além de poder exibir a posição de cada arquivo de tópico em um mapa, é desejável exibir o conteúdo do mapa em um fluxo consecutivo. O recurso Visualizar mapa permite visualizar todo o conteúdo do arquivo de mapa em um único clique. Não é necessário gerar uma saída do arquivo de mapa para visualizar como o mapa inteiro será exibido depois de publicado. Você pode simplesmente acessar a visualização do mapa e todos os tópicos e submapas são renderizados na forma de um livro.

![](images/map-editor-preview.png){align="left"}

>[!NOTE]
>
> Nenhuma opção de edição ou inserção de conteúdo está disponível na barra de ferramentas no modo de Visualização. Não é possível editar o conteúdo nesta exibição. Entretanto, você pode usar os recursos **Salvar como nova versão** e **Bloquear** ou **Desbloquear**.

Você pode executar as seguintes tarefas adicionais no modo de visualização:

- Clique com o botão direito em um tópico e selecione **Editar** para abrir o tópico para edição em uma nova guia.

  >[!NOTE]
  >
  > Se você não tiver direitos de edição, o tópico será aberto no modo somente leitura.

- Pule para o tópico desejado selecionando o título do tópico na árvore de mapa \(no painel esquerdo\).

- O tópico atual na visualização do mapa também é destacado na árvore do mapa.

**Outras maneiras de visualizar um arquivo de mapa**

Você pode acessar a visualização de um mapa em:

- **Interface do usuário do Assets**: na interface do usuário do Assets, navegue até o local do mapa, selecione o arquivo de mapa e escolha **Visualizar Mapa** na Barra de Ferramentas. A visualização do mapa é mostrada em uma nova guia. É possível exibir o conteúdo de todos os tópicos no modo de visualização. Nesta exibição, não é possível editar nenhum tópico.

  >[!NOTE]
  >
  > Se a opção *Visualizar Mapa* não estiver visível na barra de ferramentas principal, ela pode ter sido movida para o menu da barra de ferramentas **Mais**.

- **Editor de Mapas**: no Editor de Mapas, selecione **Visualizar** no menu de opções para exibir a visualização do mapa atual.

  ![](images/map-preview-icon.png){width="650" align="left"}

  A visualização do mapa é exibida em uma caixa pop-up.

  ![](images/map-editor-preview-pop-up.png){width="500" align="left"}

**Mapear propriedades**

Exibe a caixa de diálogo Propriedades do Mapa, na qual você pode definir os atributos e as informações de metadados do mapa.


## Editar tópicos por meio do mapa DITA {#id17ACJ0F0FHS}

A edição de um tópico individual não fornece o contexto completo ao autor. Um autor não teria informações sobre onde um tópico é colocado em um mapa DITA. Sem essas informações contextuais, fica um pouco difícil para os autores criar conteúdo.

O Experience Manager Guides permite que os autores abram um mapa DITA no Editor e visualizem a disposição dos tópicos no mapa. Isso ajuda os autores a saber exatamente onde o tópico é colocado no mapa e criar conteúdo mais relevante. Além disso, se houver vários autores trabalhando em um projeto, eles poderão saber quais tópicos estão disponíveis no mapa e reutilizar o conteúdo, onde for necessário.

Para editar tópicos por meio de um mapa DITA, execute as seguintes etapas:

1. No painel Repositório, navegue e abra o arquivo de mapa DITA que deseja editar.

   O arquivo de mapa é aberto na visualização Mapa.

>[!NOTE]
>
> Também é possível usar a interface do usuário do Assets para abrir um arquivo de mapa DITA. Navegue até o arquivo de mapa DITA que contém os tópicos que você deseja editar e selecione **Editar tópicos** na barra de ferramentas principal para iniciar o Editor.

1. Selecione qualquer link de tópico para abri-lo no Editor para edição.

   É possível abrir vários tópicos no editor e cada tópico é aberto em uma nova guia no editor. Mesmo que o mapa DITA contenha submapas, os tópicos desses submapas também serão abertos em uma nova guia para edição. Se quiser exibir os tópicos em um submapa, selecione e expanda o submapa.

   ![](images/web-editor-multiple-topics.png){align="left"}

   Se você selecionar um arquivo de mapa, o mapa será aberto em uma nova guia do Editor.

1. Quando terminar de editar os tópicos, você poderá fazer o seguinte:

   - Você pode salvá-los individualmente. Se fechar sem salvar os tópicos, você verá uma caixa de diálogo solicitando que salve os tópicos não salvos:

     ![](images/save-multiple-topics-new.png){width="300" align="left"}

     Você pode optar por salvar todos os tópicos selecionados ou desmarcar os tópicos que não deseja salvar.

   - Você pode desbloquear o tópico usando a opção **Salvar como nova versão**. Quando você salva uma versão do tópico, uma nova versão é criada e o bloqueio também é lançado.

     É recomendável salvar as alterações antes de desbloquear os arquivos.  Quando você salva as alterações, o arquivo XML é validado.

   - Você também pode exibir o progresso dos tópicos da caixa de diálogo **Salvar como nova versão**. Uma mensagem de sucesso é exibida quando os arquivos são desbloqueados.

   - Se o administrador tiver ativado a opção de desbloquear arquivos ao fechar, você receberá um prompt para salvar os arquivos sempre que os arquivos bloqueados forem fechados. Com essa opção ativada, ao fechar o editor com arquivos alterados, você verá a lista de arquivos bloqueados que precisam ser salvos. Os arquivos bloqueados são mostrados com um ícone de bloqueio:

     ![](images/save-on-close-new.png){width="350" align="left"}

## Painel direito no Editor de mapa

O painel direito exibe as Propriedades do Conteúdo e as Propriedades do Mapa na exibição de Layout do Editor de Mapas.

**Propriedades do conteúdo**

O painel Propriedades de conteúdo contém informações sobre o tipo de tópico atualmente selecionado no mapa, o URL do link e os atributos. Para obter mais detalhes, consulte [Propriedades do conteúdo](web-editor-features.md#right-panel) no Editor.

- **Outros atributos** Se o administrador tiver criado um perfil para atributos, você obterá esses atributos junto com seus valores configurados. Usando o painel de propriedades de conteúdo, você pode escolher esses atributos e atribuí-los ao conteúdo relevante em seu tópico. Você também pode atribuir atributos configurados pelo administrador na guia **Exibir atributos** das configurações do editor. Os atributos definidos para um elemento são exibidos na exibição Layout e Estrutura de Tópicos. Isso ajuda você a ter uma olhada rápida em todos os tópicos em um mapa para o qual um determinado atributo é definido. Por exemplo, todos os tópicos que têm o atributo `audience` são definidos como `US`.

  ![exibição de layout](images/layout-inline-attributes.png){width="650" align="left"}


  Para obter mais detalhes, exiba os *Atributos de exibição* na descrição do recurso *Configurações* no [Editor](web-editor-features.md#main-toolbar).

- **Metadados** Usando os metadados, você pode definir as informações de metadados. Você pode definir o Título de navegação, Texto do link, Descrição curta e Palavras-chave.

Para obter mais informações sobre atributos e metadados de tópico padrão, consulte a documentação [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) na Especificação de Linguagem OASIS DITA.




**Tópico pai:** [Introdução ao Editor de Mapa](map-editor.md)
