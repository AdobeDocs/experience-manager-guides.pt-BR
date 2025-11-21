---
title: Recurso de publicação nativo do PDF | Trabalhar com os estilos de conteúdo comuns
description: Saiba como criar folhas de estilos de uso e criar estilos para o seu conteúdo.
exl-id: 42ba7347-d81d-45d9-9627-8d164e4f9539
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '3778'
ht-degree: 0%

---

# Trabalhar com os estilos de conteúdo comuns {#work-with-common-styles}

Uma folha de estilos contém as definições de estilos para os elementos usados na saída do PDF. Você pode optar por trabalhar com as folhas de estilos de amostra ou criar novas. Na maioria dos casos, criar uma cópia da folha de estilos de amostra do OOTB ajudará você a começar rapidamente.

O editor de estilos é um editor do WYSIWYG que oculta todas as complexidades de um código CSS por trás da interface do usuário. Usando o editor de estilos, é possível personalizar estilos fácil e rapidamente para os elementos de sua escolha. Os estilos são classificados nos seguintes cabeçalhos:

* Estilos de cabeçalho
* Estilos de parágrafo
* Estilos de caractere
* Estilos de Hiperlink
* Estilos de imagem
* Estilos de lista
* Estilos de Tabela
* Estilos Div
* Estilos de página
* Outros estilos

Ao trabalhar com conteúdo DITA estruturado, o mapeamento de estilos da maioria dos elementos DITA está em vigor na folha de estilos padrão. Se você estiver trabalhando com elementos DITA padrão, é possível alterar a aparência diretamente fazendo alterações na definição do estilo. Essas definições de estilo estão disponíveis na categoria Outro estilo. Para obter mais detalhes, consulte [Trabalhar com outros estilos](#other-styles) mais tarde neste tópico.

As seções a seguir abordam as configurações de estilo usadas com mais frequência na forma de exemplos.

>[!NOTE]
>
>Nos exemplos a seguir, presume-se que você esteja trabalhando com a folha de estilos de amostra enviada com o produto.

## Trabalhar com Estilos de Título {#heading-styles}

Os estilos de cabeçalho encapsulam todos os estilos de base para os cabeçalhos usados no conteúdo. OOTB você terá seis estilos de cabeçalho base e um estilo de cabeçalho para o tópico/capítulo e cabeçalho de título do apêndice. Em um documento estruturado, o H1 representa o título do tópico ou capítulo e H2 a H6 são usados para subtópicos ou seções dentro de um tópico/capítulo. Essa hierarquia de cabeçalhos é aplicada automaticamente ao seu conteúdo sempre que o cabeçalho correspondente é encontrado.

>[!NOTE]
>
>Você pode criar seus próprios estilos de cabeçalho personalizados e eles podem ser usados no conteúdo usando a classe de saída. Para obter mais detalhes, consulte a Etapa 4 em [Usar orientação de página e rotação de exibição](design-page-layout.md#page-orientation-rotation) exemplo.

### Criar cabeçalhos personalizados no nível do capítulo {#create-chapter-level-heading}

Em um livro (ou um mapa), você trabalha com Capítulos. Os estilos de cabeçalho básicos são projetados de forma a serem aplicados em seus cabeçalhos de nível de capítulo sem nenhuma personalização. No entanto, se você quiser criar cabeçalhos especializados para seu conteúdo, será necessário criar esses cabeçalhos. Por exemplo, o cabeçalho padrão `h1.chapter` é aplicado no título do capítulo. Se quiser que o título do capítulo apareça em um estilo diferente, será necessário personalizar o estilo `h1.chapter`. Da mesma forma, você pode criar estilos personalizados para subcabeçalhos no capítulo. Por exemplo, se você deseja criar um estilo personalizado para todos os cabeçalhos de nível 2<sup>nd</sup> e 3<sup>rd</sup> no capítulo, será necessário criar um novo estilo como `h2.chatper` e `h3.chatper`.

Como o recurso Publicação nativa no PDF contém as definições de estilo base para os estilos mais comuns, mesmo que você exclua um estilo acidentalmente, o estilo padrão será aplicado ao conteúdo. Por exemplo, se não houver uma definição de estilo para o estilo h2 na folha de estilos, o recurso Publicação nativa do PDF aplicará algum estilo base no conteúdo h2.

Neste exemplo, criaremos um estilo de cabeçalho de capítulo de segundo nível:

1. Abra a folha de estilos necessária para edição.
   >[!NOTE]
   >
   >Consulte a seção [Personalizar um estilo novo ou predefinido](components-pdf-template.md#customize-style) para abrir uma folha de estilos para personalização ou edição.

1. Na lista **Estilos**, expanda os **Estilos de Título**.
1. Clique com o botão direito do mouse no estilo **Estilos de Título** e escolha **Novo Estilo**.
1. Na caixa de diálogo *Adicionar Estilo*, mantenha o nome **Marca** como `h2` e digite `chapter` no campo de nome **Classe**.
1. Clique em **Concluído**.

Um novo estilo de cabeçalho chamado `h2.chapter` é criado e adicionado na lista de Estilos de Título.

Depois de criar um estilo, você pode personalizar as propriedades necessárias do estilo usando o editor de estilos.

### Criar cabeçalhos de numeração automática {#auto-number-heading}

Um dos estilos de saída mais usados é o cabeçalho com numeração automática. Esses cabeçalhos representam o número do capítulo, o tópico e os números do subtópico. Os cabeçalhos de numeração automática são diferentes dos estilos de lista em que uma lista de itens em um tópico recebe numeração automática.

Neste exemplo, vamos personalizar os cabeçalhos do nível 1 para o nível 3 para usar números automáticos em diferentes formatos.

1. Abra a folha de estilos necessária para edição.

   >[!NOTE]
   >
   >Consulte a seção [Personalizar um estilo novo ou predefinido](components-pdf-template.md#customize-style) para abrir uma folha de estilos para personalização ou edição.

1. Na lista **Estilos**, expanda os **Estilos de Título**.

1. Selecione o estilo **h1** na lista.
As propriedades do estilo h1 são mostradas no painel Propriedades junto com sua Visualização.

   >[!NOTE]
   >
   >O painel Visualizar fornece uma visualização em tempo real de qualquer atualização de estilo aplicada em qualquer elemento.

1. Selecione a propriedade **Autonumeração**.

   Os estilos que podem ser aplicados na lista de numeração automática são mostrados abaixo da propriedade Numeração automática.

1. Defina as seguintes propriedades:
   * **Estilo**: selecione entre uma grande variedade de estilos de numeração genéricos ou específicos de localidade. Você pode escolher estilos como Árabe-Índico, Devanágari, Georgiano, Decimal, Lower-Alpha e muito mais. Para o exemplo atual, selecione `upper-alpha`.

   * **Formato**: o formato padrão está definido como `<x>`, em que o valor `x` é substituído pelo Estilo de numeração selecionado na propriedade Style. Por exemplo, se você selecionou o estilo `decimal` (1), o valor de `x` é incrementado automaticamente para cada instância do estilo `h1`, vai para 2, 3 e assim por diante. Também é possível adicionar texto personalizado no campo para formatar o estilo do cabeçalho. Por exemplo, se você quiser que todos os cabeçalhos h1 tenham um prefixo `Chapter`, será necessário definir esse campo como `Chapter <x>`.

   * **Inserir Caractere**: Se você deseja adicionar qualquer caractere especial no Formato, clique no botão Inserir Caractere (<img src="./assets/insert-chars.png" width="25">) ícone. Selecione o caractere desejado que deseja adicionar no formato de estilo e clique em Inserir. Há diferentes tipos de caracteres especiais que você pode escolher na lista suspensa Selecionar categoria. Para o nosso exemplo, selecione a opção Aspas angulares à direita na categoria Pontuação.

     <img src="./assets/insert-special-chars.png" width="400">


   * **Iniciar numeração de**: se quiser que a numeração comece a partir de um número específico, forneça esse valor. Para o nosso exemplo, mantenha o valor padrão de 1.

   * **Recuo**: se você deseja recuar o cabeçalho, é necessário definir o valor de Recuo. Para o nosso exemplo, defina-o como 0 px.

     >[!NOTE]
     >
     >É possível inserir o valor em px (pixels), pt (pontos), rem, em, % (porcentagem) ou em unidades (polegadas).

   * **Largura do Prefixo**: esta é a área ocupada pelo formato de numeração automática. Ele é automaticamente definido para um tamanho que possa acomodar facilmente o formato de estilo selecionado. Se quiser aumentar o tamanho, você poderá substituir o valor padrão.

     Ao definir esse valor manualmente, tente alterar as outras propriedades que terão impacto na largura. Por exemplo, altere o tamanho da fonte, o formato com o prefixo (Capítulo) ou um sufixo (:), defina o valor máximo na propriedade *Iniciar numeração de* e as várias propriedades da fonte para obter o tamanho ideal.

     Para o nosso exemplo, mantenha o valor padrão.

   * **Espaçamento**: especifique o espaçamento horizontal e vertical. Para o nosso exemplo, mantenha os valores padrão.

     Com as personalizações acima, o estilo é personalizado conforme mostrado abaixo:

     <img src="./assets/h1-style-custmization.png" width="500">

   * **Aplicar formatação a**: as propriedades na categoria Autonumeração ajudarão você a definir o estilo de numeração. Para aplicar mais personalizações ao estilo de numeração ou ao conteúdo do formato de cabeçalho, você pode escolher Numeração ou Parágrafo nesse campo. Se você escolher &#39;Numeração&#39;, quaisquer alterações feitas em &#39;Fonte&#39;, &#39;Borda&#39;, &#39;Layout&#39; e outras categorias serão aplicadas somente ao estilo de numeração no cabeçalho. No entanto, se você escolher &#39;Parágrafo&#39;, as alterações serão aplicadas ao conteúdo do cabeçalho, não ao estilo de numeração.

   Use as configurações a seguir para gerar uma saída mostrada na seguinte captura de tela:

   | **Estilo do Título** | **Propriedade** | **Valor** | **Comentários Adicionais** |
   | :- | :- | :- | :- |
   | h1 | Estilo | Decimal | Essas propriedades estão na categoria Autonumeração |
   |  | Formato | `Capter <x>:` |  |
   |  | Largura do prefixo | 160px |  |
   |  | Fonte > Alinhamento de texto | Esquerda | Certifique-se de que &#39;Aplicar formatação a&#39; esteja definido como &#39;Numeração&#39; |
   | h2 | Estilo | Decimal | Essas propriedades estão na categoria Autonumeração |
   |  | Formato | `Section <x>:` |  |
   |  | Largura do prefixo | 125 px |  |
   |  | Fonte > Alinhamento de texto | Esquerda | Certifique-se de que &#39;Aplicar formatação a&#39; esteja definido como &#39;Numeração&#39; |
   | h3 | Estilo | Decimal | Essas propriedades estão na categoria Autonumeração |
   |  | Inserir Nível | 2 |  |
   |  | Formato | `Section <2>.<x>:` |  |
   |  | Largura do prefixo | 125 px |  |
   |  | Fonte > Alinhamento de texto | Esquerda | Certifique-se de que &#39;Aplicar formatação a&#39; esteja definido como &#39;Numeração&#39; |

   <img src="./assets/auto-number-output.png" width="500">

## Trabalhar com estilos de parágrafo {#paragraph-style}

Um estilo de parágrafo pode ser criado para aplicar formatação especial a um parágrafo inteiro. Entretanto, usando a pseudoclasse, você pode aplicar um estilo a apenas uma parte específica do texto. No exemplo a seguir, criaremos um estilo de parágrafo para usar o estilo de capitular.

### Criar o estilo de capitular {#drop-cap-style}

Um estilo capitular (ou capitular) é usado em revistas e documentos literários nos quais o primeiro caractere de um parágrafo ou seção recebe um estilo especial. Você pode obter o mesmo efeito usando o recurso Publicação nativa do PDF.

No exemplo a seguir, criaremos um estilo de capitular:

1. Abra a folha de estilos necessária para edição.

   >[!NOTE]
   >
   >Consulte a seção [Personalizar um estilo novo ou predefinido](components-pdf-template.md#customize-style) para abrir uma folha de estilos para personalização ou edição.

1. Na lista **Estilos**, expanda os **Estilos de parágrafo**.

1. Clique com o botão direito do mouse no **Estilo de parágrafo** e escolha **Novo estilo**.

1. Na caixa de diálogo *Adicionar estilo*, mantenha o nome da **Marca** como p e, no campo **Pseudo** **Classe**, selecione `::first-letter`.

1. Clique em **Concluído**.

   Um novo estilo de parágrafo chamado `::first-letter` foi criado e adicionado na lista **Estilos de parágrafo**.

1. Selecione `::first-letter` sob o estilo p e defina as seguintes propriedades:

   * **Fonte**: defina a fonte desejada para a primeira letra do parágrafo. Para o nosso exemplo, defina a Família da fonte como cursiva, espessura da fonte para 500, tamanho da fonte para 30 pt e escolha uma cor de fonte.

   * **Layout**: definir o alinhamento vertical do texto em torno do estilo de capitular. Para o nosso exemplo, definiremos o Alinhamento vertical como Inferior.

Como a marca `p` é mapeada com o elemento `<p>` em DITA, não é necessário adicionar explicitamente esse estilo usando o atributo outputclass. Sempre que um elemento `<p>` for usado no seu conteúdo, o estilo de capitular será aplicado automaticamente a ele. Na captura de tela a seguir, o título do capítulo, a descrição curta e os elementos da lista de definição não foram formatados com o estilo de capitular. Somente o estilo de parágrafo é formatado com o estilo de capitular:

<img src="./assets/char-style-drop-cap.png" width="500">

## Trabalhar com estilos de caractere {#char-style}

Com os estilos de caractere, é possível criar estilos para formatar caracteres ou palavras no conteúdo. Por exemplo, você pode criar um estilo de caractere para código incorporado ou nome de arquivo, ou pode criar um estilo que use vários formatos de estilo no conteúdo selecionado.

### Criar um estilo de caractere incorporado {#inline-char-style}

A formatação de caracteres ou palavras incorporadas em um parágrafo é um estilo muito comum. O processo de criação de um estilo em linha envolve duas tarefas: primeiro, crie um novo estilo na folha de estilos e, segundo, aplique o estilo no seu conteúdo usando o atributo `outputclass`.

No exemplo a seguir, criaremos um estilo de caractere em linha:

1. Abra a folha de estilos necessária para edição.

   >[!NOTE]
   >
   >Consulte a seção [Personalizar um estilo novo ou predefinido](components-pdf-template.md#customize-style) para abrir uma folha de estilos para personalização ou edição.

1. Na lista **Estilos**, expanda os **Estilos de Caractere**.

1. Clique com o botão direito do mouse no **Estilo de caractere** e escolha **Novo estilo**.

1. Na caixa de diálogo Adicionar estilo, mantenha o nome **Marca** como span e digite `BoldItalic` no campo de nome **Classe**.

   <img src="./assets/create-char-style.png" width="400">

1. Clique em **Concluído**.

   Um novo estilo de caractere chamado código é criado e adicionado na lista Estilos de caractere.

1. Selecione `span.BoldItalic` na lista **Estilo de caractere** e defina as seguintes propriedades:

   * **Fonte**: todas as propriedades relacionadas à fonte podem ser personalizadas a partir desta seção. Por padrão, há algumas fontes agrupadas com o produto. Você pode escolher a fonte desejada para o estilo de caractere. Para o nosso exemplo, defina a Família da Fonte como *Serif,* e selecione *Bold* e *Italic* na propriedade Estilo da Fonte. Você também pode personalizar outras propriedades de fonte, como Espessura da fonte (como negrito, mais claro), Decoração do texto (como sublinhado, linha sobreposta), Tamanho da fonte, Cor da fonte, Alinhamento do texto e muito mais.

     >[!NOTE]
     >
     >Também é possível adicionar fontes ao modelo, que são armazenadas na seção Resources do modelo. Para obter mais detalhes sobre como adicionar fontes e trabalhar com Recursos, consulte [Trabalhar com recursos](components-pdf-template.md#work-with-resources).

   * **Layout**: você pode definir as propriedades relacionadas ao layout, como Altura e Largura, Margem, Preenchimento, Alinhamento e muito mais.

   * **Plano de fundo**: as propriedades do Plano de fundo permitem formatar a cor do plano de fundo de um estilo específico. É possível definir a cor ou a imagem do plano de fundo para qualquer estilo.

Depois de criar o estilo de caractere incorporado, é necessário aplicá-lo ao conteúdo. Para aplicar o estilo de código incorporado, vá para a exibição de origem e adicione o atributo `outputclass` no conteúdo desejado:

`outputclass="BoldItalic"`

O exemplo a seguir mostra o formato Negrito Itálico sendo aplicado em locais diferentes no texto em execução:

<img src="./assets/char-format-applied.png" width="500">

## Personalizar estilo da lista {#custom-list-style}

Os Estilos de lista contêm as configurações de estilo padrão para as listas ordenadas e não ordenadas. É possível personalizar facilmente esses estilos de lista para atender aos requisitos de documentação.

No exemplo a seguir, vamos personalizar o estilo de lista numerada ou ordenada:

1. Abra a folha de estilos necessária para edição.

   >[!NOTE]
   >
   >Consulte a seção [Personalizar um estilo novo ou predefinido](components-pdf-template.md#customize-style) para abrir uma folha de estilos para personalização ou edição.

1. Na lista **Estilos**, expanda os **Estilos de Lista**.

1. Selecione o estilo **ol** na lista.

   As propriedades do estilo antigo são mostradas no painel Propriedades junto com a opção Visualizar.

   <img src="./assets/list-style-default.png" width="500">

1. Selecione a opção **Formatação Avançada**.

   Uma mensagem de confirmação é exibida.

1. Clique em **Sim** na mensagem *Confirmação* para abrir as propriedades de **Formatação Avançada**.

   As seguintes propriedades estão disponíveis por padrão:

   * **Nível**: por padrão, há 6 níveis de listas numeradas. O nível selecionado nesta lista suspensa controla as alterações de estilo no nível selecionado e em todos os níveis subsequentes. Por exemplo, se você selecionar nível 4, todas as alterações de estilo aplicadas serão definidas nos níveis 4, 5 e 6.

   * **Tipo de Estilo de Lista**: Há vários estilos de numeração de lista que você pode escolher. A lista contém estilos de numeração genéricos e específicos do local usados para criar uma lista numerada. Alguns dos tipos de estilo de lista são árabe, cambojano, devanágari, etíope, hangul, hebraico, japonês, coreano, chinês simples, urdu e muito mais.

   Além disso, você pode trabalhar com as seguintes propriedades de Formatação avançada:

   * **Formato de Número**: o formato padrão está definido como `<x>`, no qual o valor `x` é substituído pelo Estilo de numeração selecionado na propriedade Tipo de Estilo de Lista. Por exemplo, se você selecionou o estilo `decimal` (1), o valor de `x` é incrementado automaticamente para cada instância do elemento da lista, vai como 2, 3 e assim por diante. Você também pode adicionar texto personalizado no campo para formatar o estilo da lista. Por exemplo, se você quiser que todos os estilos de lista de primeiro nível tenham um sufixo &quot;`)`&quot;, defina esse campo para o estilo de lista de primeiro nível como &quot;`<x>)`&quot;.

   * **Inserir Caractere**: Se você deseja adicionar qualquer caractere especial no Formato de Número, clique no botão Inserir Caractere (<img src="./assets/insert-chars.png" width="25">) ícone. Selecione o caractere desejado que deseja adicionar no formato de estilo e clique em Inserir. Há diferentes tipos de caracteres especiais que você pode escolher na lista suspensa Selecionar categoria.

   * **Inserir Nível**: você pode incluir o número de qualquer um dos níveis anteriores no formato de número. Por exemplo, se você quiser incluir o formato de número do 5º nível no formato de número do 6º nível, escolha 5 na lista suspensa Inserir nível. Observe que a lista suspensa Inserir nível mostra apenas os números dos níveis anteriores e não o nível seguinte. Por exemplo, enquanto você estiver no Nível 3, a lista Inserir Nível mostrará apenas os níveis 1 e 2.

     <img src="./assets/list-insert-level.png" width="400">

     Você também pode alterar o Formato de número para apresentar os valores da lista conforme necessário. Por exemplo, quando estiver usando um estilo de numeração aninhado para o nível 3, você poderá formatá-lo como &quot;`<2>.<x>))`&quot;. Isso mostrará a lista número 2, seguida por um ponto, seguido pelo número de lista 3 e, então, dois colchetes, como `2.3))`.

   * **Recuo**: se você deseja recuar a lista, então você precisa definir o valor de Recuo. Quaisquer alterações no recuo podem ser revisadas no painel Visualização e ajustadas.

     >[!NOTE]
     >
     >É possível inserir o valor em px (pixels), pt (pontos), rem, em, % (porcentagem) ou em unidades (polegadas).

   * **Largura do Prefixo**: esta é a área ocupada pelo Formato de Número. Ele é automaticamente definido para um tamanho que possa acomodar facilmente o formato selecionado. Se quiser aumentar o tamanho, você poderá substituir o valor padrão.

     Ao definir esse valor manualmente, tente alterar as outras propriedades que terão impacto na largura. Por exemplo, altere o tamanho da fonte, o formato com prefixo ou um sufixo e as várias propriedades da fonte para obter o tamanho ideal.

   * **Espaçamento**: especifique o espaçamento horizontal entre o formato do número da lista e o conteúdo. O espaçamento vertical controla o intervalo entre os dois itens da lista.

     A captura de tela a seguir mostra a lista ordenada personalizada para cada nível:

     <img src="./assets/list-number-format-final.png" width="500">

## Trabalhar com estilo de tabela {#table-styles}

Usando as folhas de estilos, você pode criar *n* número de estilos de tabela. Com os estilos de tabela, é possível criar o modo como a tabela inteira, uma linha ou coluna específica será criada. Com o controle no estilo de nível de célula, é possível criar estilos de tabela muito apresentáveis.

No exemplo a seguir, vemos como criar um estilo de tabela e as várias opções de estilo de tabela que você pode personalizar:

1. Abra a folha de estilos necessária para edição.

   >[!NOTE]
   >
   >Consulte a seção [Personalizar um estilo novo ou predefinido](components-pdf-template.md#customize-style) para abrir uma folha de estilos para personalização ou edição.

1. Na lista **Estilos**, clique com o botão direito do mouse no **Estilo de Tabela** e escolha **Novo Estilo**.

1. Na caixa de diálogo *Adicionar Estilo*, mantenha o nome **Marca** como `table` e digite `double-border` no campo de nome **Classe**.

1. Clique em **Concluído**.

   Um novo estilo de tabela chamado `table.double-border` é criado e adicionado na lista de Estilos de Tabela.

1. Selecione `table.double-border` na lista **Estilos de Tabela** e defina as seguintes propriedades:

   * **Aplicar formatação a**: você pode optar por aplicar a formatação de estilo a toda a tabela, linhas ou colunas ímpares/pares ou primeira/última linha ou coluna.

     >[!NOTE]
     >
     >As configurações a seguir estão disponíveis na seção **Geral** quando **Aplicar Formatação a** está definido como **Tabela Inteira**.

   * **Quebra de texto**: selecione como quebrar texto em torno da tabela. Isso é útil quando a tabela está dentro de outro elemento de nível de bloco e a tabela deve ser renderizada juntamente com outro conteúdo no elemento de bloco. As opções de quebra automática estão *alinhadas à esquerda* ou *à direita* ou *nenhuma*.

   * **Recolhimento de Borda**: selecione a aparência da borda da tabela. Se você selecionar recolher, apenas uma única linha de borda será desenhada entre as células da tabela. No entanto, para estilos separados, a borda é visível ao redor de cada célula com preenchimento adicional.

     <img src="./assets/table-style-collapse-separate.png" width="500">

   * **Espaçamento entre Bordas**: esta configuração só estará disponível quando o Recolhimento de Borda estiver definido como Separado. Com essa configuração, você pode especificar o espaçamento vertical e horizontal entre as bordas da célula.

     <img src="./assets/table-border-spacing.png" width="500">

     >[!NOTE]
     >
     >As configurações a seguir estão disponíveis na seção **Célula** quando **Aplicar Formatação a** está definido como **Tabela Inteira**.

   * **Preenchimento**: especifique o preenchimento entre as células da tabela. Você pode especificar diferentes valores de preenchimento para os lados superior, inferior, esquerdo e direito.

   * **Alinhamento vertical**: especifique o alinhamento vertical para o conteúdo da célula. As opções disponíveis são: Superior, Meio e Inferior.

   * **Lado da Borda, Estilo, Cor, Largura, Raio:** Especifique as propriedades relacionadas à borda. Você pode optar por ter bordas somente em lados específicos, como Esquerda ou Direita. O Estilo da borda lista os estilos de borda disponíveis como Sólido, Tracejado, Linha dupla e muito mais. Especifique a cor da borda usando a paleta de cores. Você pode especificar a largura da borda em px, pt, rem, em, % e em unidades. O Raio define a curva para fazer cantos circulares.

   As outras propriedades em Fonte, Borda, Layout, Paginação e Plano de Fundo são explicadas em outros exemplos neste tópico. Dependendo da sua seleção na propriedade **Aplicar formatação a**, você poderá aplicar esses valores a toda a tabela ou às linhas ou colunas selecionadas.

   Uma visualização de uma tabela de amostra com linhas diferentes formatadas de forma diferente é mostrada abaixo:

   <img src="./assets/table-final-design.png" width="500">

## Trabalhar com outros estilos {#other-styles}

Se estiver trabalhando com conteúdo estruturado (DITA), você notará que quase todos os elementos DITA têm um mapeamento de estilos na folha de estilos padrão. Por exemplo, o estilo de um elemento `<shortdesc>` é definido na definição de estilo **Outro Estilo** > **.shortdesc**. É possível personalizar facilmente qualquer um desses estilos e eles serão aplicados automaticamente na saída do PDF gerada a partir do conteúdo estruturado. Isso significa que, diferente de outros estilos personalizados, você não precisa adicionar um atributo `outputclass` no conteúdo desses estilos.

Caso deseje criar uma definição de estilo para qualquer elemento que não esteja disponível por padrão ou tenha um elemento personalizado, é possível criá-lo facilmente na folha de estilos. O único ponto que você deve considerar é criar o estilo com o mesmo nome do nome do elemento estruturado.

No exemplo a seguir, criaremos um novo estilo de título (`wintitle`) da janela:

1. Abra a folha de estilos necessária para edição.

   >[!NOTE]
   >
   >Consulte a seção [Personalizar um estilo novo ou predefinido](components-pdf-template.md#customize-style) para abrir uma folha de estilos para personalização ou edição.

1. Na lista **Estilos**, expanda **Outros Estilos**.

1. Clique com o botão direito do mouse em **Outro estilo** e escolha **Novo estilo**.

1. Na caixa de diálogo *Adicionar Estilo*, mantenha o nome da **Marca** como *em branco* e digite `wintitle` no campo de nome da **Classe**.

   Como `wintitle` é um nome de elemento DITA reconhecido, sua definição de estilo é mapeada automaticamente para o elemento `<wintitle>` na sua origem.

1. Clique em **Concluído**.

   Um novo estilo chamado `.wintitle` foi criado e adicionado na lista **Outros Estilos**.

1. Selecione .wintitle na lista **Outros Estilos** e defina as propriedades conforme necessário.

A captura de tela a seguir exibe o estilo wintitle que está sendo aplicado ao texto &quot;Controle principal&quot;.

<img src="./assets/other-style-wintitle.png" width="500">


## Definir um estilo exclusivo para um layout de página única

Ao publicar a saída do PDF nativo, todos os estilos são mesclados no PDF final e é crucial atribuir um estilo exclusivo a cada modelo no CSS.
Use nomes de estilo CSS distintos para aplicar fontes e estilos específicos a diferentes seções de uma PDF. Por exemplo, você pode definir a fonte desejada para a página de capa usando o seguinte CSS.

```css
...
[data-page-layout="Front"] * { 
    font-size: 18pt; 
}  
...
```


O restante do documento usará a fonte padrão especificada para a marca de corpo em `content.css` ou `layout.css`. Isso garante que os estilos não sejam mesclados e que cada seção mantenha o design pretendido. Se quiser tamanhos de fonte diferentes, crie estilos específicos para eles.

Por exemplo, você pode definir os seguintes estilos para definir o tamanho de fonte 18 nos parágrafos da folha de rosto e o tamanho de fonte 11 pt para a página de capa traseira:

```css
[data-page-layout="Front"] p { //For all paragraphs inside Front page
  font-size: 18pt; 
} 
  
[data-page-layout="Back"] p { //For all paragraphs inside Back page
  font-size: 11pt; 
}
```

>[!NOTE]
>
> No exemplo anterior, &quot;Frente&quot; e &quot;Voltar&quot; são os nomes de exemplo dos arquivos de layout que podem ser usados nos modelos.


## Definir o estilo CSS personalizado para o conteúdo de prefixo e sufixo

Se você definir os estilos CSS personalizados, eles terão a primeira prioridade ao gerar a saída PDF nativa.
O estilo CSS padrão a seguir oculta o conteúdo do prefixo e do sufixo.

```css
...
.prefix-content, .suffix-content{
    display: none;
} 
...
```

Para permitir esses prefixos no elemento `<note>`, inclua o seguinte CSS no `content.css`:

```css
...
.prefix-content{
    display: inline !important;
}
...
```

O elemento `<note>` gera um `<span>` adicional com o prefixo de classe-conteúdo correspondente ao seu atributo de tipo. Esta regra CSS destina-se à classe `.prefix-content` em `<note>` elementos com um atributo de tipo, permitindo estilizar ou manipular o conteúdo do prefixo conforme necessário.

