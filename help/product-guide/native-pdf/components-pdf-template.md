---
title: Recurso de publicação nativo do PDF | Componentes de um modelo do PDF
description: Saiba mais sobre os vários componentes de um modelo do PDF e como personalizá-los e configurá-los.
exl-id: 0ddb3b81-42ca-4a66-be7d-051a5175d53a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '4702'
ht-degree: 0%

---

# Componentes de um modelo do PDF {#components-pdf-template}

Um modelo do PDF tem quatro componentes: Layouts de página, Folhas de estilos, Recursos e Configurações. É possível criar um modelo personalizando esses componentes individuais e associando o modelo a uma predefinição de saída ao gerar uma saída do PDF. As seções a seguir abordam esses componentes e seu processo de personalização em detalhes.


## Criar e personalizar layouts de página {#create-customize-page-layout}

As configurações no componente Layouts de página permitem que você crie a estrutura de uma página definindo o cabeçalho, o rodapé e a área de conteúdo em uma página. Usando o editor de layout de página do WYSIWYG, você pode criar um layout de página para diferentes seções em uma PDF, como as páginas de capa frontal e traseira, capítulo, Tabela de
Conteúdo (índice), índice, página em branco, Páginas de primeiro plano, Páginas de segundo plano, Lista de figuras (LOF), Lista de tabelas (LOT), glossário ou criar um layout para uma página personalizada. Nas Configurações do modelo do PDF, é possível atribuir um layout de página com diferentes seções em um PDF, que são usadas para gerar a saída do PDF.

### Criar um novo layout de página {#create-page-layout}

>[!NOTE]
>
>Há exemplos de layouts de página que foram enviados imediatamente. É possível personalizar esses layouts ou criar novos layouts de página.

1. No Editor da Web, vá para a guia **Saída**.
1. Expanda a barra lateral esquerda e clique em **Modelos**.
1. Abra o modelo com o qual deseja trabalhar.

   >[!NOTE]
   >
   >É possível abrir um modelo clicando duas vezes no nome ou clicando no ícone > ao lado do nome.

1. Para criar um novo layout de página, siga um destes procedimentos:

   * Passe o mouse sobre **Layouts de Página** e clique no ícone (*Opções*) **...** e escolha **Novo Layout de Página**.


   * No painel **Modelos**, clique no ícone **+** ao lado de **Modelos** e escolha **Layout da Página** no menu de contexto.


     Isso abre a caixa de diálogo **Adicionar Layout**.

     <img src="assets/add-layout-2.png" alt="Caixa de diálogo Adicionar layout" width="250">

1. Especifique um nome para o novo layout de página.
   >[!NOTE]
   >
   >Evite usar caracteres especiais ao nomear um layout de página. Um espaço no nome é substituído por um sublinhado &quot;_&quot;.

1. Clique em **Concluído**.

   O novo layout é criado e adicionado em Layouts de página.


### Duplicação de um layout de página {#duplicate-page-layout}

1. Na seção **Modelos** do modelo que você deseja duplicar, clique duas vezes em **Layouts de Página** ou no ícone **>** antes de **Layouts de Página**.

   Isso exibe a lista de layouts de página no modelo.

1. Passe o mouse sobre o layout de página que você deseja duplicar e clique no ícone (*Opções*) **...** e selecione **Duplicar** no menu de contexto.

1. Na caixa de diálogo _Duplicar Layout_, digite um nome para o layout da página.

1. Clique em **Concluído**.
Uma cópia do layout de página selecionado é criada e adicionada em Layouts de página.

### Personalizar um layout de página {#customize-page-layout}

1. Na seção **Modelos** do modelo que você deseja editar, clique duas vezes em **Layouts de Página** ou no ícone **>** antes de **Layouts de Página**.

   Isso exibe a lista de layouts de página no modelo.
1. Para personalizar qualquer layout de página, siga um destes procedimentos:
   * Clique duas vezes em qualquer layout de página.
   * Passe o mouse sobre qualquer layout de página e clique no ícone (*Opções*) **...** e selecione **Editar** no menu de contexto.

   Isso abre o editor de layout de página para personalização.
1. Depois de fazer as alterações desejadas, clique em *Salvar tudo* (ou `Crl+S`).

   Para obter mais informações sobre como definir elementos de layout individuais, como cabeçalho, rodapé, número de página, título e muito mais, consulte [Criar um layout de página](design-page-layout.md).

## Usar folhas de estilos para personalizar o PDF {#stylesheet-customization}

As configurações no componente Folha de estilos permitem estilizar os componentes do layout da página e o conteúdo DITA usando o editor de WYSIWYG ou trabalhar diretamente com o arquivo CSS. Você pode criar seus próprios estilos ou personalizar as propriedades de estilo padrão. O editor do WYSIWYG fornece acesso à maioria das propriedades que seriam necessárias para criar o estilo do layout da página ou do conteúdo DITA. Para personalizações avançadas, você pode trabalhar diretamente na visualização do Source.

### Criar uma nova folha de estilos {#create-stylesheet}

Embora os arquivos CSS sejam fornecidos para conteúdo e layout, você pode criar uma nova folha de estilos para aplicar várias personalizações a um tipo de estilo específico que pode ser aplicado a um componente de destino. Por padrão, os arquivos CSS de amostra são agrupados no produto. Esses arquivos CSS destinam-se a ajudar você a organizar suas informações de estilo em todo o conteúdo e layouts. Você pode optar por mesclar esses estilos em um único arquivo CSS ou em vários arquivos.

Por padrão, sempre que você cria um novo layout de página, o arquivo `layout.css` é incluído no novo layout de página. Se quiser que o layout de página contenha estilos de um arquivo CSS diferente, basta arrastar e soltar o arquivo CSS desejado na área de edição de conteúdo do novo layout de página. Para validar se o arquivo CSS foi incorporado no layout de página, alterne para o modo de exibição do Source e você encontrará um link para o arquivo CSS no elemento `<head>`.

Para criar uma folha de estilos, siga as etapas abaixo:
1. No painel **Modelos**, siga um destes procedimentos:
   * Passe o mouse sobre a guia **Folhas de Estilos** e clique no ícone (*Opções*) **...** e escolha **Nova Folha de Estilos**.
   * Clique no ícone **+** ao lado de **Modelos** e escolha **Folha de Estilos** no menu de contexto.

   Isso abre a caixa de diálogo Adicionar folha de estilos.

   <img src="assets/add-stylesheet.png" alt="Adicionar folha de estilos" width="250">
1. Especifique um nome para a nova folha de estilos.
1. Clique em **Concluído**.

   Uma nova folha de estilos é criada e adicionada na seção Folhas de estilos.

### Criar um novo estilo {#create-style}

Por padrão, os arquivos CSS fornecidos com o modelo contêm estilos para cabeçalho, parágrafo, caractere, hiperlink, imagem, tabela, div, página e outros estilos. É possível substituir o formato de estilo padrão ou criar um novo estilo.


Você pode criar um novo estilo para usá-lo no layout de página do modelo ou aplicar um estilo personalizado a qualquer elemento DITA. Para aplicar esses estilos personalizados ao elemento DITA, você deve garantir que o nome da classe do estilo seja igual ao nome do elemento DITA ou ao atributo `outputclass`.  Por exemplo, `<div>` no DITA é regido pelo `.div {}` no CSS ou seu atributo `outputclass`. Se você aplicar `<div outputclass="my-div">` no DITA, ele será regido pelo `.div {}` ou `.my-div {}` no CSS.



Para criar um novo estilo, siga as etapas abaixo:
1. Expanda a barra lateral esquerda e clique duas vezes no template no qual deseja criar o estilo.
1. Expanda a seção **Folhas de estilos**. Ele abre o painel **Estilos**, que contém todas as opções de estilo.
1. Selecione o ícone + para adicionar um novo estilo.

   A caixa de diálogo **Adicionar Estilo** é aberta.


   <img src="assets/add-style.png" alt="Adicionar novo estilo" width="500"/>

1. Especifique um nome de **Classe**. Para aplicar um estilo ao elemento DITA, verifique se o nome da classe do estilo é igual ao nome do elemento DITA ou ao atributo `outputclass`.
1. No campo **Marca** (opcional), escolha uma marca para a qual deseja criar um novo estilo.


1. Selecione uma **Pseudo-Classe** para estilizar um elemento. Uma pseudoclasse ajuda a definir um estado especial do elemento. Por exemplo, use a pseudoclasse para estilizar um elemento ao passar o mouse sobre ele ou ao focalizar sobre ele. Também é possível selecionar várias pseudoclasses. Por exemplo, você pode usar a pseudoclasse `a::visited {color: blue;}` para estilizar os links visitados.

1. Adicione o seletor para o novo estilo. O campo **Seletor** ajuda você a adicionar seletores personalizados além da combinação Classe, Marca e Pseudo Classe. Por exemplo, você pode criar o estilo `table a.link` para todos os hiperlinks dentro de uma tabela.

   Para obter mais informações sobre marcas CSS, exiba [Consulte a gramática de estilo CSS](https://www.w3.org/TR/CSS21/syndata.html#characters).

1. Clique em **Concluído**.

   Um novo estilo é criado e adicionado à lista de estilos.

### Personalizar um estilo predefinido ou novo {#customize-style}

Depois de criar um novo arquivo CSS com estilos padrão ou personalizar estilos em um arquivo CSS existente, você pode usar o editor de estilos para fazer isso.

Para personalizar um estilo, siga as etapas abaixo:
1. Clique duas vezes em **Folhas de estilos** ou clique no ícone **>** antes de **Folhas de estilos**.

   Isso exibe os arquivos CSS padrão (Conteúdo e Layout) e personalizados.
1. Abra uma folha de estilos para edição.

   Para abrir a folha de estilos para edição, siga um destes procedimentos:
   * Clique duas vezes no nome da folha de estilos.
   * Passe o mouse sobre o nome da folha de estilos, clique em (ícone Options ) ... e escolha Edit.

   Essa ação abre a folha de estilos para edição e exibe a lista de estilos no painel Estilos.

   <img src="assets/customize-style.png" alt="Personalizar estilo" width="800">

1. Para personalizar um estilo, selecione-o e personalize-o usando o editor de Estilos.


### Propriedades de estilos

No painel central, você pode editar as propriedades, mas pode ser difícil obter um instantâneo do que todos os valores estão presentes.  O painel **Propriedades** fornece uma exibição rápida de todos os atributos e valores do estilo.

No painel central, você pode editar as propriedades comumente usadas, mas não todas as propriedades compatíveis com o CSS. No painel **Propriedades**, você pode editar e visualizar todas as propriedades compatíveis com CSS. Você não precisa alternar para a exibição de origem para editar propriedades.


Saiba mais sobre como usar o editor de estilos para [trabalhar com os estilos de conteúdo comuns](stylesheet.md).

## Trabalhar com recursos {#work-with-resources}

Este é um contêiner de todos os ativos usados para criar um modelo. Pense nisso como uma pasta, que contém ativos como imagens de fundo, fontes personalizadas, logotipos e muito mais. Sempre que você adiciona um ativo no modelo, ele é carregado ou registrado na pasta de ativos. Em seguida, você pode usar esses ativos para personalizar ou projetar seus modelos do PDF.

Para adicionar um arquivo de ativo à pasta Recursos, siga as etapas abaixo:

1. Passe o mouse sobre a guia Resources folder, clique em (Options icon) ... e escolha Import.

   Isso abre a caixa de diálogo Fazer upload do Assets.

   <img src="assets/resources-import-assets.png" alt="Upload de ativos" width="300">

   O caminho para onde o arquivo de ativo será carregado é mostrado no campo **Selecionar pasta de ativos**.
   >[!NOTE]
   >
   >Não é possível alterar o caminho para fazer upload de ativos. Por padrão, todos os ativos são armazenados na pasta `/content/dam/dita-templates/pdf/<PDF-template-name>`.

1. Clique em **Escolher arquivos** para procurar o arquivo de ativo de seu computador local

1. Clique em **Carregar**.
O arquivo selecionado é importado e listado na pasta Recursos.

## Configurações avançadas do PDF {#advanced-pdf-settings}

Use a seção Configurações para definir as configurações avançadas para o layout de página do PDF, iniciando o PDF a partir de página ímpar ou par, formatos para as referências cruzadas e habilitando marcas de impressão no PDF final gerado
usando o template.

>[!NOTE]
>
> A partir da versão Experience Manager Guides 5.0/2025.02.0, a seção **Imprimir** das configurações avançadas do PDF foi movida para o painel **Predefinições de saída**. Para definir as configurações de Impressão, exiba [Publicar saída do PDF](../web-editor/native-pdf-web-editor.md#print).

Para configurar, clique em **Configurações** no painel **Modelos** para exibir as seguintes opções:

### Geral

Defina as configurações básicas para iniciar um capítulo a partir de uma página ímpar ou par, a estrutura do sumário e defina o formato da linha de chamada para as entradas do sumário. Você pode definir a seguinte configuração:

* **Iniciar qualquer novo capítulo de**: permite definir como cada capítulo é publicado no PDF final. Você pode escolher entre uma **Nova Página**, **Página Ímpar**, **Página par** ou **Página atual** opções. Se você optar por iniciar um novo capítulo a partir de uma página ímpar, uma página em branco será inserida depois de um capítulo que termina em uma página ímpar. Por exemplo, se o capítulo terminar na página número 15, o processo de publicação inserirá uma página 16<sup>th</sup> em branco para que o novo capítulo possa começar na página 17<sup>th</sup>.  Se você escolher a opção **Página atual**, todos os capítulos serão publicados na continuação sem nenhuma quebra de página. Por exemplo, se um capítulo terminar no meio da página 15, o próximo capítulo também será iniciado a partir da própria 15 página.

* **Iniciar cada tópico a partir de uma nova página**: se quiser que cada tópico do capítulo comece a partir de uma nova página, selecione a opção **Iniciar cada tópico a partir de uma nova página**. Se quiser manter os tópicos em continuação sem qualquer intervalo de página, desmarque essa opção.

* **Estrutura do Sumário**: permite personalizar a hierarquia do Sumário. Ele usa as seguintes configurações adicionais:

   * **Usar títulos até o nível**: permite ajustar o número de níveis de cabeçalho a serem exibidos na estrutura de índice do seu PDF.
   * **Não mostrar número de página para o primeiro nível no índice**: selecione esta opção para ocultar os números de página correspondentes para todos os capítulos que contenham tópicos aninhados ou filhos. Considere o exemplo a seguir em que uma saída é criada sem selecionar essa opção.

  <img src="assets/page-number-in-toc.png" alt="Upload de ativos" width="250">

  No exemplo acima, Configurações avançadas do PDF, Apêndice e Ofício são os títulos de tópico de primeiro nível ou títulos de capítulo. Um número de página é atribuído a todos esses cabeçalhos.

  Agora, se você selecionar essa opção e gerar a saída, você obterá o seguinte índice:

  <img src="assets/page-number-missing-in-toc.png" alt="Upload de ativos" width="250">

  Aqui você pode notar que o primeiro capítulo sobre configurações avançadas do PDF não recebe nenhum número de página, pois tem tópicos aninhados ou secundários. Ao passo que um número de página se atribuído ao Apêndice e Legal porque são tópicos independentes sem nenhum tópico secundário.

* **Não mostrar o número do capítulo no sumário**: selecione esta opção para exibir os nomes dos capítulos sem os números de capítulo no sumário.   Por padrão, os números de capítulo são exibidos no índice da saída do PDF.
* **Formato de guia**: use o menu suspenso para selecionar linhas pontilhadas, sólidas ou linhas de guia de espaço para conectar níveis de cabeçalho aos números de página correspondentes.
Para aplicar a estrutura de índice e os níveis de cabeçalho de estilo, consulte [Adicionar um índice de capítulo](design-page-layout.md#add-chapter-toc).

  >[!NOTE]
  >
  >Se você for um desenvolvedor de CSS, também poderá definir o formato de líder diretamente no arquivo CSS.

* **Usar marcador de continuação de tabela**: selecione essa opção para definir marcadores para tabelas longas que se espalham por várias páginas.
Você pode definir o texto a ser exibido antes e depois da quebra. Por exemplo, uma tabela é quebrada na página 5 e você define `<Continued on page %page-num%>` para **Texto antes da quebra**.  O texto exibe &quot;Continuado na página 6&quot; na parte inferior da página 5.

  Use variáveis de idioma para definir o texto do marcador de continuação antes e depois da interrupção. Dependendo do idioma escolhido, o valor localizado é escolhido automaticamente na saída do PDF. Por exemplo, você pode publicar `Continued on page %page-num%` como texto em inglês e `Fortsetzung auf Seite %page-num%` em alemão.

  Focalizar <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo à opção para ver mais detalhes sobre ele.
* **Vincular termos do glossário à página do glossário**: selecione esta opção para mostrar os termos do glossário como hiperlinks no conteúdo e vinculá-los aos termos na página do glossário. Isso ajuda os leitores a visualizar rapidamente a definição de um termo definido no glossário.

  Para converter os termos do glossário em hiperlinks, é necessário:
   * Habilite o **Glossário** na guia **Ordem de Layout da Página** para obter um mapa DITA.
   * Adicione o Glossário nas Páginas do Back Matter para um mapa de Livros.

  Se você não ativar a página Glossário, os termos do Glossário no conteúdo não serão convertidos em hiperlinks na saída do PDF.
  <!--For more information on using table continuation markers, see Use table continuation markers.-->

### Layouts de página {#page-layouts}

As configurações de Layouts de página oferecem controle total sobre a especificação de qual layout de página deve ser usado para uma seção específica do documento. Por exemplo, para selecionar um layout para o Sumário, clique no menu suspenso sob o campo Sumário e selecione o layout criado para gerar o Sumário.

É importante observar que as configurações do mapa de favoritos têm prioridade sobre as configurações do layout da página.

As seguintes configurações estão disponíveis na seção Layout da página:

<img src="assets/template-page-layout.png" alt="Layouts de página" width="550">


**Layout de página padrão**: selecione um layout de página que atue como o layout padrão para todas as páginas do PDF. Esse é o layout de página base aplicado às seções ou aos tópicos em que você não criou um layout de página dedicado.

**Layout de página para diferentes seções**: você pode mapear um layout de página com as seguintes seções da saída do PDF. Se você tiver criado um layout de página para a seção relacionada, selecione-o na lista suspensa. Se nenhum layout de página tiver sido criado para seções específicas, o layout de página padrão será aplicado.

* **Capítulos e tópicos**: você pode especificar o layout da página para o Capítulo e Tópicos. O layout selecionado será aplicado a todos os capítulos e tópicos.

* **TOC**: se você tiver criado o layout de página do TOC, selecione **TOC** na lista suspensa e todas as páginas do TOC no documento terão o layout de página do TOC.

* **Lista de Figuras e Lista de Tabelas**: você também pode especificar o layout da página para figuras e tabelas. O layout selecionado será aplicado a todas as figuras e tabelas.

* **Índice**: se você tiver criado um layout de página de Índice, mapeie-o para a opção Índice. Usando as folhas de estilos, é possível estilizar diferentes elementos de índice na saída do PDF. Use os estilos de índice `.idx-header`, `.idx-footer`, `.idx-body`, `.idx-title`, `.idx-keyword-group`, `.idx-unit`, `.idx-keyword`, `.idx-name`, `.idx-link` e `.idx-child` para personalizar os estilos dos elementos do índice.

* **Glossário**: se você tiver um layout de página do Glossário, mapeie-o para a opção Glossário.

  Os termos no glossário da sua saída do PDF são sempre classificados em ordem alfabética.

  Você também pode adicionar a tag `sort-as` para definir uma chave de classificação para os termos do glossário. O Experience Manager Guides usa a chave de classificação para classificar os termos do glossário no lugar dos termos do glossário. Se você não tiver definido a chave de classificação, ela usará os termos do glossário para classificação. Por exemplo, você pode adicionar a marca `sort-as` a `glossterm` e definir seu valor como `A` para o termo &quot;USB&quot; (por exemplo, `<glossterm>USB<sort-as>A</sort-as></glossterm>`). Da mesma forma, você pode adicionar a tag `sort-as` e definir seu valor como `B` para o termo &quot;Pen Drive&quot;. Ao classificar esses termos do glossário, a chave de classificação `A` para o termo do glossário &quot;USB&quot; aparece antes da chave de classificação `B` para o termo do glossário &quot;Pen Drive&quot;. Portanto, na saída do PDF, &quot;USB&quot; vem antes de &quot;Pen Drive&quot; na página do glossário.

  Usando as folhas de estilos, é possível estilizar diferentes elementos de glossário na saída do PDF. Use os estilos de glossário `.glo-header`, `.glo-footer`, `.glo-body`, `.glo-title`, `.glo-unit`, `.glo-link` e `.glo-term` para personalizar os estilos dos elementos do glossário.

  Saiba mais sobre como usar o editor de estilos para [trabalhar com os estilos de conteúdo comuns](stylesheet.md).

* **Páginas da frente e do verso**: esses layouts de página definem o estilo das páginas da frente e do verso do seu livro. Se você tiver criado o layout de front matter, mapeie-o para a opção **Front Matter Pages**. Quando você seleciona o layout da frente na lista suspensa, o layout da frente é aplicado a todos os tópicos presentes na frente.

  Se você tiver criado o layout de fundo, mapeie-o para a opção **Páginas de Fundo**. Quando você seleciona o layout de material de fundo na lista suspensa, o layout de material de fundo é aplicado a todos os tópicos presentes no material de fundo.

  As **Front Matter Pages** também são usadas como layout de fallback para o **TOC**, **Lista de Figuras** e Lista de Tabelas.  Da mesma forma, as **Páginas de Retorno** também são usadas como layout de fallback para os layouts do **Índice** e do **Glossário**. Se você não tiver selecionado o layout dessas páginas, o layout selecionado de Páginas da frente ou do verso será aplicado.  Se você não tiver selecionado o layout Páginas da frente ou do verso, o layout padrão da página será aplicado a elas.

* **Layout da página para páginas vazias**:    Você também pode especificar o layout das páginas vazias. O layout selecionado será aplicado a todas as páginas vazias. Por exemplo, se você tiver criado um layout de página em branco para todas as páginas vazias, selecione **Em branco** na lista suspensa e todas as páginas vazias no documento terão o layout de página em branco.

* **Página de capa e página traseira**: se você criou um layout de página de capa, mapeie-o para a opção **Página de capa**. Da mesma forma, se você tiver um layout de página de trás, mapeie-o para a opção **Página de trás**. Se nenhum layout de folha de rosto ou de página posterior tiver sido criado, o layout de página padrão será aplicado.



Para obter mais informações sobre layouts de página, consulte [Criar um layout de página](design-page-layout.md).

### Ordem do layout da página {#page-order}

Você pode mostrar ou ocultar as seguintes seções no PDF e também organizar a ordem em que elas devem aparecer na saída final do PDF:



* TOC
* Capítulos e tópicos
* Lista de figuras
* Lista de tabelas
* Índice
* Glossário
* Citação

  <img src="assets/page-order-advance-settings.png" alt="Ordem do layout da página" width="550">

  Se você não quiser mostrar uma seção específica na saída do PDF, oculte isso desativando o botão de alternância.

  Você também pode definir a ordem em que essas diferentes seções são geradas no PDF. Para alterar a ordem padrão dessas seções, selecione as barras pontilhadas para arrastar e soltar as seções no local desejado.

  >[!NOTE]
  >
  > As configurações de ordem e inclusão se aplicam somente a um mapa DITA. Para um mapa, essas configurações não se aplicam. As páginas em um mapa são exibidas de acordo com a ordem das seções no mapa.


.
O layout **Capítulo e Tópicos** é sempre habilitado por padrão. Não é possível alterná-lo.

**Mesclar páginas**

Por padrão, todas as seções começam em uma nova página. Selecione a opção **Página anterior** ou **Próxima página** na lista suspensa **Mesclar com** para mesclar uma seção com uma página anterior ou seguinte. Isso publicará a seção em continuação com a página selecionada na saída do PDF. Com isso, não haverá quebra de página entre eles.

>[!NOTE]
>
> Essa configuração se aplica somente à seção e não a seus componentes.  Por exemplo, se você selecionar a opção **Página anterior** para **Capítulos e tópicos**, a seção **Capítulos e tópicos** será mesclada com a página anterior. Os vários capítulos e tópicos são publicados de acordo com as configurações de **Geral**.Por exemplo, se em **Iniciar qualquer novo capítulo da configuração**, você selecionar **Página ímpar**, uma página em branco será inserida após um capítulo que terminar em uma página ímpar.

Ao mesclar uma seção com sua página anterior ou próxima página, o conteúdo é mesclado e o estilo da seção de destino na qual o conteúdo é mesclado é aplicado.

Por exemplo, se você habilitar o **TOC** e o **Capítulo e Tópicos** e selecionar a **Próxima Página** para o **TOC**, o **TOC** será mesclado com a próxima seção, que é o **Capítulo e Tópicos**. O estilo da seção **Capítulo e Tópicos** é aplicado ao conteúdo mesclado de ambas as seções.

A opção de mesclagem funciona sucessivamente, portanto, se você tiver selecionado **Próxima página** para várias seções contínuas, todas elas serão mescladas com a primeira seção (na próxima direção), que não tem essa propriedade definida. Por exemplo, você habilita o **TOC**, **Capítulo e Tópicos**, **Lista de Figuras** e **Índice**. Se você definir **Próxima Página** para **Índice**, **Capítulo e Tópicos**, **Lista de Figuras** e **Nenhum** para **Índice**, todos serão mesclados com **Índice**.


**Páginas estáticas**

Os vários layouts de página ajudam a projetar a saída das várias seções. Essas seções são geradas pelo mapa DITA enquanto você publica a saída.
Você também pode criar layouts de página personalizados e publicá-los como páginas estáticas na saída do PDF. Isso ajuda a adicionar qualquer conteúdo estático, como Notas ou páginas em branco.

Execute as seguintes etapas para adicionar um layout de página personalizado:

1. Selecione **Adicionar** ![](assets/add-icon.svg) para adicionar um novo layout de página. O painel Adicionar layout de página é aberto.
2. Selecione o layout de página na lista e clique em Adicionar. O novo layout da página é adicionado à lista de layouts de página.


Você também pode executar as seguintes ações:

* Selecione as barras pontilhadas para arrastar e soltar o layout da página no local desejado.

* Selecione **Remover layout** ![](assets/delete-icon.svg) para remover um layout.

* Também é possível mesclar uma página estática com a página anterior ou a próxima página.

* Você também pode adicionar um layout personalizado várias vezes e organizá-los. Isso ajuda a publicar o conteúdo estático adequadamente.

  Por exemplo, você pode usar um layout personalizado para publicar um aviso estático várias vezes na saída do PDF.



### Organização da página

As páginas em um documento do PDF normalmente são publicadas de acordo com o conteúdo organizado no mapa DITA ou no arquivo de mapa. No entanto, também é possível alterar a ordem das páginas no documento do PDF. Por exemplo, você pode imprimir um documento de várias páginas como um livreto. Ao agrupar, dobrar e grampear as folhas, o resultado é um único livro com a ordem de página correta.  Você pode então ler o livreto publicado como um livro.

<img src="assets/template-page-organization.png" alt="Organização da página" width="550">


As seguintes configurações estão disponíveis na seção **Organização da página**:

#### Ordem da página

Selecione uma ordem de página que determine a sequência das páginas no documento do PDF. Você pode escolher as seguintes opções na lista suspensa:

* **Padrão**: a ordem padrão das páginas de acordo com o arquivo de origem.
* **Páginas ímpares primeiro**: todas as páginas ímpares são movidas antes de todas as páginas pares.
* **Páginas pares primeiro**: todas as páginas pares são movidas antes de todas as páginas ímpares.
* **Reverter**: a ordem da página é revertida.
* **Livreto**: todas as páginas são ordenadas como em um livreto.
* **Livreto da Direita para a Esquerda**: todas as páginas estão na ordem do livreto da direita para a esquerda.
* **Personalizado**: defina uma ordem personalizada das páginas em vez de uma ordem predefinida.
   * &quot;a..b&quot; — Todas as páginas consecutivas de a a b.
   * &quot;a,b,c&quot; — Ordem das novas páginas a, b, c.
   * &quot;a*b&quot; — A página a é repetida b vezes.
   * &quot;-a&quot; — Números de página negativos são contados retroativamente a partir da última página e podem ser combinados com outros pedidos personalizados.
   * &quot;X&quot; — Todas as páginas do documento. Mesmo resultado que &quot;1..-1&quot;.

Assim, por exemplo, você pode fornecer um pedido personalizado como &quot;2,3,5*2,7.10,-1,-2.
A ordem de páginas fornecida resulta em um PDF com os seguintes números de página do documento original, supondo que ele tenha um total de 25 páginas: 2, 3, 5, 5,7, 8, 9, 10, 25, 24.

#### Configurar mais de uma página por folha

Escolha essa opção para publicar várias páginas em uma única folha de papel.  Em seguida, selecione o número de linhas e colunas e publique as páginas como uma grade em uma única planilha. Por exemplo, você pode publicar as páginas como uma grade de 2 linhas e 4 colunas.

Defina o tamanho da planilha de destino e a orientação na qual deseja publicar a planilha. Você também pode especificar a margem e as propriedades de preenchimento da planilha.

### Referências cruzadas {#cross-references}

Use a guia **Referência cruzada** para definir como as referências cruzadas são publicadas no PDF. É possível formatar as referências cruzadas para título de tópico, tabelas, figuras e muito mais.

>[!NOTE]
>
> Se você tiver definido o texto do link ao inserir a referência cruzada, ele terá precedência sobre o formato de referência cruzada definido no modelo PDF nativo.

Você também pode usar variáveis para definir uma referência cruzada.  Quando você usa uma variável, seu valor é extraído das propriedades. Você pode usar uma única variável ou uma combinação de variáveis para definir uma referência cruzada. Também é possível usar uma combinação de uma string e uma variável.

Por exemplo, você pode usar `View details on {chapter}`. Se o nome do capítulo for &quot;Configurações gerais&quot;, a referência cruzada na saída será &quot;Consulte detalhes em Configurações gerais&quot;.

O AEM Guides fornece as seguintes variáveis prontas para uso:

* {title}: Cria uma referência cruzada ao título do tópico. Por exemplo, consulte Links úteis na página 2.
* {page} Adiciona uma referência cruzada aos números de página. Por exemplo, consulte na página 1.
* {description}: adiciona uma referência cruzada ao texto da descrição. Por exemplo, consulte os detalhes do AEM Guides.
* {chapter}: adiciona uma referência cruzada aos números de capítulo. Por exemplo, consulte no Capítulo 1.
* {bookmarkText}: Cria uma referência cruzada para o texto marcado. Por exemplo, consulte stop_words na página 5.
* {captionText}: cria uma referência cruzada para a legenda da figura ou tabela no seu tópico. Por exemplo, consulte Fluxo de ar na página 2.
* {figure}: Adiciona uma referência cruzada ao número de figura. Seleciona o número de figura a partir dos estilos de numeração automática que você definiu para a legenda digital.  Por exemplo, você pode usar &quot;Ver {figure} na página {page}&quot;. A referência cruzada na saída contém o número de figura gerado automaticamente e seu número de página, &quot;Consulte a Figura 1 na página 5&quot;.
* {table}: Adiciona uma referência cruzada ao número da tabela. Seleciona o número da tabela a partir dos estilos de numeração automática definidos para a legenda. Por exemplo, você pode usar &quot;Ver {table} na página {page}&quot;. A referência cruzada na saída contém o número de tabela gerado automaticamente e seu número de página, &quot;Consulte a Tabela 1 na página 5&quot;.



  >[!NOTE]
  >
  >É possível criar estilos de numeração automática para tags de legenda e legenda.

#### Formato de referência cruzada padrão

Se você deixar o campo de texto em branco e não tiver definido o texto do link ao inserir uma referência cruzada, o Experience Manager Guides adicionará as seguintes variáveis às respectivas referências cruzadas:

* **Título**: `{title}`
* **Descrição**: `{description}`
* **Parágrafo**: `{bookmarkText}`
* **Indicador**: `{bookmarkText}`
* **Figura**: `{captionText}`
* **Tabela**: `{captionText}`

A ordem de precedência das referências cruzadas é:
* Texto do link adicionado nas referências cruzadas
* Formato de referência cruzada definido no template PDF nativo
* Formato de referência cruzada padrão


#### Variáveis de idioma em referências cruzadas

Você também pode usar variáveis de idioma para definir referências cruzadas localizadas. Dependendo do idioma escolhido, o valor localizado é escolhido automaticamente na saída do PDF.

Por exemplo, é possível adicionar uma variável de idioma &quot;reference-label&quot; e definir os valores em inglês e alemão.

* Inglês - &quot;View on page {page}&quot;
* Alemão - &quot;Einzelheiten finden Sie auf der Seite {page}&quot;


Ao adicionar `${lng:<variable name>}` à seção Parágrafo, as referências cruzadas nos parágrafos da saída contêm o texto localizado e o número da página.\
Por exemplo, as capturas de tela a seguir mostram as referências cruzadas &quot;View on page 1 &quot; em inglês e &quot;Einzelheiten finden Sie auf der Seite 1&quot; em alemão.

<img src="./assets/english-output-corss-reference.png" alt="Inglês output of a cross-reference in a pragrah" width ="800" border="2px">

*Uma referência cruzada dentro de um parágrafo quando publicado em inglês.*

<img src="./assets/german-output-corss-reference.png" alt="Saída alemã de uma referência cruzada em um pragrah" width ="800" border="2px">


*Uma referência cruzada dentro de um parágrafo quando publicado em alemão.*

<!--For more information, see *Format cross-references*.-->
