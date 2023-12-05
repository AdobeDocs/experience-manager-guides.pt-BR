---
title: Adicionar e gerenciar citações no seu conteúdo
description: Adicionar e gerenciar citações em Guias do AEM. Saiba como aplicar, importar, filtrar, pesquisar, alterar o estilo da citação, editar, visualizar, inserir, excluir e gerar saída de conteúdo com citações.
exl-id: 685d747d-e017-4350-a6bf-822fd55c76e8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Adicionar e gerenciar citações no seu conteúdo

Citações são referências à fonte de informações adicionada ao conteúdo. Usando citações, você pode creditar os autores das informações de origem e ajudar os leitores a acompanhar as informações de origem. Adicionar citações torna seu conteúdo mais confiável e evita plágios. Eles também permitem exibir conteúdo bem pesquisado.

Nos Guias do AEM, é possível adicionar e importar citações e aplicá-las ao conteúdo. É possível adicionar essas citações de qualquer fonte de livros, sites e diários.


O Guias do AEM ajuda você a editar, visualizar e classificar suas citações. Depois de adicionar suas citações ao conteúdo, você pode gerar a saída usando o PDF nativo. Você também pode adicionar a página de bibliografia ou referências na saída de PDF nativo.

O AEM Guides suporta vários estilos de citações, como Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electrical and Electronics Engineers (IEEE) e American Heart Association (AHA). A recomendação é usá-los de forma clara e consistente.


>[!NOTE]
>
>Atualmente, o AEM Guides suporta apenas o PDF nativo para citações.


## Adicionar citações

Para adicionar citações, siga estas etapas:

1. Selecione o **Citações** ![ícone de citações](images/citations-icon.svg) no painel esquerdo.
A variável **Citações** é aberto.

   ![](images/citation-panel.png){width="300" align="left"}

1. No **Citações** , selecione ![Ícone Adicionar](images/Add_icon.svg). Na lista suspensa, é possível optar por adicionar uma nova citação ou importar uma citação.

1. Selecionar **Nova Citação** para adicionar uma nova citação.
A variável **Adicionar Citação** é aberta.

   ![painel citação no editor da web](images/citation-add.png) {width="300" align="left"}


1. Preencha os campos no **Adicionar Citação** caixa de diálogo.

   >[!NOTE]
   >
   >Você também pode adicionar o ISBN ou DOI ou PubMed ID. Guias de AEM preenchem os outros campos automaticamente.

   | Livro | Site | Diário |
   | --- | ---|---|
   | **Origem** <br> No menu suspenso, selecione a origem da citação como um Livro. | **Origem**<br> No menu suspenso, selecione a origem da citação como um Site. | **Origem** <br> No menu suspenso, selecione a origem da citação como um Diário. |
   | **Pesquisar por** <br> Selecionar **ISBN** ou **DOI** no menu suspenso para pesquisar a ID digital vinculada à citação.  <br> DOI: Identificador de objeto digital <br> ISBN: Identificador de livro numérico exclusivo | **Pesquisar por** <br> Selecionar **DOI** no menu suspenso para pesquisar a ID digital vinculada à citação. | **Pesquisar por** <br> Selecionar **DOI** ou PubMed ID no menu suspenso para pesquisar a ID digital vinculada à citação. <br>  <br> |
   | **Autor** <br> Adicione o nome e o sobrenome do autor da citação. Selecionar ![](images/Add_icon.svg) para adicionar mais nomes. | **Autor** <br> Adicione o nome e o sobrenome do autor da citação. Selecionar ![](images/Add_icon.svg)  para adicionar mais nomes. | **Autor** <br> Adicione o nome e o sobrenome do autor da citação. Selecionar ![](images/Add_icon.svg)para adicionar mais nomes. |
   | **Título** <br> Adicione o título do livro. | **Título** <br> Adicione o título da página da Web. | **Título** <br> Adicione o título do artigo. |
   | **Editor** <br> Adicione o editor do livro. | **Nome do site** <br> Adicione o nome do site. | **Título do diário** <br> Adicione o título do trabalho no qual o artigo é encontrado. |
   | **Edição** <br> Adicione a edição do livro. | **URL** <br> Adicione o link da Web do site para navegar pelo conteúdo. | **Ano** <br> Adicione o ano em que o artigo é publicado. |
   | **Cidade** <br> Adicione a cidade da publicação. | **Data de acesso**<br> Adicione a data em que o conteúdo do site é acessado. | **Volume** <br> Adicione o volume do trabalho na série. |
   | **Editor** <br> Adicione o nome do editor do livro. | **Data de publicação** <br> Adicione a data em que o conteúdo do site é publicado. | **Número** <br> Adicione o número do volume dentro da série. |
   | **Ano** <br> Adicione o ano em que o livro é publicado. | **Data de atualização** <br> Adicione a data em que o conteúdo do site é atualizado. | **Páginas** <br> Adicione o número da página ou o intervalo de páginas em que o artigo é encontrado. |
   | **Versão** <br> Adicione a versão do livro. | **Identificador exclusivo** <br> Adicionar uma ID exclusiva para a citação. Um identificador exclusivo é um identificador exclusivo para essa citação. | **URL** <br>Adicionar o link da Web ao diário. |
   | **Série** <br>Adicione a série do livro. |  | **Identificador exclusivo** <br> Adicionar um identificador exclusivo para a citação. Um identificador exclusivo é um identificador exclusivo para essa citação. |
   | **URL**  <br>  Adicione o link da Web ao livro. |
   | **Identificador exclusivo** <br> Adicionar uma ID exclusiva para a citação. Um identificador exclusivo é um identificador exclusivo para essa citação. |





1. Selecionar **Concluído**.

   Uma nova citação é adicionada ao painel Citação.

>[!NOTE]
>
> É obrigatório adicionar um identificador exclusivo para o campo de citação.  Não é possível alterar o identificador exclusivo depois que a citação é adicionada.

## Importar citações

Para importar citações, siga estas etapas:

1. No painel esquerdo, selecione **Citações** ![ícone de citações](images/citations-icon.svg).

   A variável **Citações** é aberto.

1. No **Citações** , selecione ![Ícone Adicionar](images/Add_icon.svg)e selecione **Importar** na lista suspensa.
1. Procure um arquivo .bib em seu sistema e importe-o.

   >[!TIP]
   >
   > Uma extensão de arquivo .bib é um arquivo de banco de dados bibliográfico BibTeX. É um arquivo de texto especialmente formatado que lista referências sobre uma determinada fonte de informação.

   Depois que o arquivo for importado com êxito, você poderá exibir as referências no painel de citações.

   >[!NOTE]
   > <ol><li> O AEM Guides importa apenas as citações que são únicas e que ainda não estão presentes.
    &gt; <li> O AEM Guides pode importar citações de um Livro, Jornal ou site. Atualmente, não aceita citações de outras fontes.

## Gerenciar citações

As citações são classificadas alfabeticamente no painel esquerdo. Pesquise as citações de acordo com as fontes a serem usadas no tópico.

### Filtro

Selecione o **Filtro** ![](images/filter-search-icon.svg) ícone ao lado da barra de pesquisa e selecione as opções de origem no menu suspenso para filtrar a lista de citação. Permite seleções únicas e múltiplas.

* **Todas as fontes**: apresenta uma lista completa de citações, incluindo todas as fontes.

* **Livro**: mostra a lista de citações provenientes de livros.

* **Site**: ele mostra a lista de citações provenientes de sites.

* **Diário**: ele mostra a lista de citações originadas em jornais.

### Pesquisar

Pesquisar o conteúdo na citação.

1. No painel esquerdo, selecione Citações.
A variável **Citações** é aberto.

1. Use a barra de pesquisa para procurar a citação apropriada em uma lista longa.

### Alterar estilo de citação {#change-citation-style}

O administrador do sistema pode alterar o estilo das citações do **Citações**  na lista suspensa **Configurações gerais** na guia **Configurações do editor**.
Esses estilos determinam como as citações são exibidas no painel de visualização ou na saída de PDF nativo.

As seguintes opções estão disponíveis na lista suspensa:

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Estilo de Associação de Idioma Moderno <br> | American Psychological Association Estilo | Manual de estilo de Chicago | Estilo do Instituto de Engenheiros Elétricos e Eletrônicos | Estilo American Heart Association |
| Exemplo:<br> Crawford, Claire, et al. *Conteúdo emocional de memórias escuras* Editado por Memory, vol 16, 2010, Amsterdam. | Exemplo: <br> Crawford, C., J., &amp;, C. (2010). *Conteúdo emocional de memórias escuras* (505-16 ed.). 10.1080/ 09658210902067289 | Exemplo: <br> Crawford, Claire, et al. *Conteúdo emocional de memórias escuras*. 505-16, 2010. | Exemplo: <br> C. Crawford, J. e C. , *Conteúdo emocional de memórias escuras*. Amsterdam, 2010. | Exemplo: <br> C. Crawford, J. e C. , *Conteúdo emocional de memórias escuras*. Amsterdam, 2010. |


## Editar uma citação

Para editar a citação, siga estas etapas:

1. Passe o mouse sobre o nome da citação na lista. Selecionar  ![](images/options.svg) o **Opções** ícone.

1. Selecionar  **Editar**.

A variável **Editar Citação** é aberta.

1. Faça as alterações necessárias. Selecionar **Concluído**.
A citação selecionada é editada.

>[!NOTE]
>
>Não é possível alterar o identificador exclusivo depois que a citação é adicionada.

## Visualizar uma citação

Para visualizar uma citação, siga estas etapas:

Passe o mouse sobre o nome da citação na lista. Selecionar     ![](images/options.svg) **Opções** ícone.

1. Selecionar **Visualizar**.
Você pode visualizar o conteúdo e o formato da citação no painel de visualização.

   >[!NOTE]
   >
   >A visualização é baseada no estilo de citação selecionado pelo administrador na **Configurações do editor**.

1. Clique em qualquer lugar na tela para fechar a caixa de visualização.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> Você também pode visualizar uma citação inserida em um tópico da interface do usuário do Assets ou da guia Preview do Editor da Web.

## Inserir citações

Execute as seguintes etapas para inserir citações a um tópico:
1. Selecione o tópico no painel do repositório e clique duas vezes nele para abri-lo na janela de edição.
1. Coloque o cursor no local do tópico onde deseja adicionar a citação.



É possível inserir citações ao tópico a partir da barra de ferramentas principal ou do painel esquerdo.

### Na barra de ferramentas principal

1. Selecione o **Citações** ![ícone de citações ](images/citations-icon.svg) ícone na barra de ferramentas principal.
1. No **Citações** escolha a citação. Também é possível selecionar várias citações.
   ![caixa de diálogo de citação](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. Você pode filtrar citações digitando os primeiros alfabetos no painel de pesquisa do **Citação** caixa de diálogo.

1. Clique em **Concluído**.
A citação selecionada é adicionada no local do cursor em seu tópico.


### No painel esquerdo

>[!NOTE]
> 
>Para exibir as **Citações** no painel esquerdo, o administrador do sistema deverá selecionar o **Citações** opção no **Painéis** guia em **Configurações do editor**.

1. Selecionar **Citações** ![ícone de citações ](images/citations-icon.svg) no painel esquerdo.
1. Arraste a citação da caixa **Citações** e solte-o no local apropriado no tópico.

   Também é possível selecionar **Inserir** de  ![](images/options.svg) **Opções** para inserir uma citação.

   ![inserir citações](images/citation-panel-insert.png)
1. Para selecionar várias citações, clique com o botão direito do mouse em uma citação e selecione **Modificar Citação** no menu de atalho.
1. Selecione as citações que deseja inserir na **Citação** diálogo.
1. Selecionar **Concluído** para adicioná-los ao tópico.

Depois de inserir citações no tópico, você pode visualizá-las no Editor da Web. Você também pode publicar conteúdo com citações usando o PDF nativo.



## Excluir uma citação

É possível excluir citações do painel Citações ou de um tópico em que você inseriu citações.

### Excluir uma citação do painel Citações

Para excluir uma citação do painel Citações, siga estas etapas:

1. Passe o mouse sobre o nome da citação na lista.
1. Selecione o ![](images/options.svg) **Opções** ícone.
1. Selecione o   **Excluir** ![](images/Delete_icon.svg).
A caixa de diálogo de confirmação é aberta.
1. Selecionar **Sim**.
A citação selecionada é excluída do painel de citações.



### Excluir uma Citação de um Tópico

Para excluir uma citação já usada no tópico, siga estas etapas:

No tópico, coloque o cursor no final da citação.

1. Clique com o botão direito do mouse em uma citação no tópico e selecione **Modificar Citação** no menu de atalho. A caixa de diálogo Citação é aberta.
   ![menu de atalho de uma citação](./images/modify-citation.png)

1. Você pode escolher as citações que deseja inserir no documento.

   >[!NOTE]
   >
   >As citações já usadas no tópico são substituídas pelas citações selecionadas na caixa de diálogo.


1. Selecionar **Concluído**.

## Gerar saída de conteúdo com citações

Depois de inserir citações no tópico, você poderá publicar o conteúdo com citações usando o PDF nativo.

Na saída do PDF nativo, as citações aparecem no conteúdo em que você as inseriu. Você também pode criar uma página de Bibliografia. Ao clicar em qualquer citação, você é redirecionado para a página de bibliografia.

Criar um **Citações** layout de página nos modelos de PDF e inclua-o no documento. Todas as citações usadas no livro são listadas em uma página que aparece na saída de PDF. Para saber mais sobre como criar um layout de página, exiba [Criar um layout de página](../native-pdf/components-pdf-template.md#create-page-layout).


Para alterar a exibição e a aparência da página de citação, exiba [Personalizar modelos de PDF](../native-pdf/pdf-template.md).



### Aplicar estilo de conteúdo a uma citação

Aplicar formatação à citação quando adicionada ao tópico.

1. Selecionar **Folhas de estilos** no **Modelos** painel de uma predefinição de saída de PDF nativo.   Ele abre o **ESTILOS** painel que contém todas as opções de estilo.

1. No painel Pesquisar, procure por `<cite>`.

Para saber mais sobre estilos, veja [Trabalhar com os estilos de conteúdo comuns](../native-pdf/stylesheet.md).
