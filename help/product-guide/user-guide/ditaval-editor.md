---
title: Usar editor DITAVAL
description: Entenda como criar e editar arquivos DITAVAL usando o Editor DIVATAL no Adobe Experience Manager Guides. Saber como o editor DITAVAL oferece suporte a arquivos DITAVAL em visualizações de autor e origem.
exl-id: f3901a4f-1925-42aa-b773-0d6f18175ce8
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: a49234698e040c7441ea0f82265f4b7936a95dfc
workflow-type: tm+mt
source-wordcount: '1501'
ht-degree: 0%

---

# Editor DITAVAL {#ditaval-editor}

Os arquivos DITAVAL são usados para gerar saída condicional. Em um único tópico, você pode adicionar condições usando atributos de elemento para condicionar o conteúdo. Em seguida, crie um arquivo DITAVAL, no qual especifique as condições que devem ser selecionadas para gerar conteúdo e qual condição deve ser deixada de fora da saída final.

O Adobe Experience Manager Guides permite criar e editar facilmente arquivos DITAVAL usando o editor DITAVAL. O editor DITAVAL recupera os atributos (que podem ser usados como condições) definidos no sistema e você pode usá-los para criar ou editar arquivos DITAVAL. Para obter mais detalhes sobre como criar e gerenciar condições no Adobe Experience Manager, consulte a seção [Administração de tags](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) na documentação do Adobe Experience Manager.

As seções a seguir abordam as opções disponíveis para um arquivo DITAVAL no Experience Manager Guides.

- [Criar arquivo DITAVAL](#create-ditaval-file)
- [Editar arquivo DITAVAL](#edit-ditaval-file)
- [Visualizações do editor de arquivos DITAVAl](#ditaval-editor-views)
- [Trabalhar com o arquivo DITAVAL na interface do usuário do Assets](#working-with-ditaval-files-in-the-assets-ui)

## Criar arquivo DITAVAL

Execute as seguintes etapas para criar um arquivo DITAVAL:

1. No painel Repositório, selecione o ícone **Novo arquivo** e selecione **Tópico** no menu suspenso.

   ![](images/new-file-option.png){width="300" align="left"}

   Você também pode acessar esta opção a partir da [Página inicial do Experience Manager Guides](./intro-home-page.md) e do menu de opções de uma pasta na exibição Repositório.

2. A caixa de diálogo **Novo tópico** é exibida.

3. Na caixa de diálogo **Novo tópico**, forneça os seguintes detalhes:
   - Um Título para o tópico.
   - \(Opcional\)* O nome do arquivo do tópico. O nome do arquivo é sugerido automaticamente com base no tópico Título. Caso o administrador tenha ativado nomes de arquivo automáticos com base na configuração UUID, você não visualizará o campo Nome.
   - Um modelo no qual o tópico será baseado. Para um arquivo DITAVAL, selecione **Ditaval** na lista suspensa.
   - Caminho no qual você deseja salvar o arquivo de tópico. Por padrão, o caminho da pasta selecionada no momento no repositório é mostrado no campo Caminho.

   ![](images/new-topic-dialog-ditaval.png){width="300" align="left"}


4. Selecione **Criar**.

O tópico é criado no caminho especificado. Além disso, o tópico é aberto no Editor para edição.

![](images/ditaval-file-editor.png){align="left"}

## Editar arquivo DITAVAL

Quando você cria um tópico DITAVAL, ele é aberto no Editor para edição. Para editar um tópico DITAVAL existente, navegue até a pasta ou mapa onde o tópico DITAVAL está localizado e selecione **Editar** no menu **Opções**.

O editor DITAVAL permite executar várias tarefas, conforme listado abaixo, usando as opções na barra de ferramentas do Editor.

### Opções da barra de ferramentas do editor

#### Menu suspenso

A lista suspensa Menu fornece acesso às ações de edição, Localizar e substituir, Histórico de versão, Rótulo de versão, Mesclar, Criar tarefa de revisão, Rastrear alterações e Recurso de tags.
Para obter mais detalhes, consulte [Opções da lista suspensa de menus](./web-editor-toolbar.md#menu-dropdown)

#### Adicionar prop

Adicione uma única propriedade no arquivo DITAVAL.

![](images/ditaval-editor-props-new.png){width="650" align="left"}

A primeira lista suspensa lista os atributos DITA permitidos que você pode usar no arquivo DITAVAL.

A segunda lista suspensa mostra os valores configurados para o atributo selecionado. Em seguida, a lista suspensa seguinte mostra as ações que você pode configurar no atributo selecionado. Os valores permitidos no menu suspenso de ações são - `include`, `exclude`, `passthrough` e `flag`. Para obter mais informações sobre esses valores, exiba a definição do elemento [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) na documentação do OASIS DITA. Para obter detalhes sobre a ação das propriedades adicionadas nos atributos, exiba [Ações para a propriedade](#actions-for-property).

#### Adicionar prop rev

Para adicionar um número de revisão específico a uma tag em XML, use a opção Adicionar prop rev. Isso adiciona um atributo rev à tag, com o valor definido no campo Valor junto com a ação selecionada para a propriedade. Esse atributo de revisão pode ser usado posteriormente para filtrar o conteúdo XML relevante com base no número de revisão especificado ao gerar a saída.

![](images/ditaval-rev-props.png){width="650" align="left"}

#### Adicionar todas as props

Se você quiser adicionar todas as propriedades condicionais ou atributos definidos em seu sistema com um único clique, use o recurso Adicionar todas as props. Os valores permitidos no menu suspenso de ações são - `include`, `exclude`, `passthrough` e `flag`. Os detalhes dessas ações são mencionados abaixo.

>[!NOTE]
>
> Se todas as propriedades condicionais definidas já existirem no arquivo DITAVAL, não será possível adicionar mais propriedades. Você recebe uma mensagem de erro neste cenário.


![](images/ditaval-all-props-new.png){width="650" align="left"}



##### Ações para a propriedade

Há quatro ações disponíveis principais para uma determinada propriedade que podem ser usadas, listadas a seguir:

**Incluir:** Incluir o conteúdo na saída. Esse é o comportamento padrão, a menos que definido de outra forma.

**Excluir:** exclui o conteúdo da saída (se todos os valores no atributo específico forem excluídos).

**Passagem:** Inclua o conteúdo na saída e preserve o valor do atributo como parte do fluxo de saída para processamento adicional por um mecanismo de tempo de execução, por exemplo, filtragem de tempo de execução com base em configurações de usuário individuais.

**Adicionar Sinalizadores:** Para sinalizar o conteúdo na saída, você pode definir o sinalizador como a ação para o atributo desejado no arquivo. Você também pode aplicar diferentes estilos de sinalizador usando a lista suspensa **Estilo do sinalizador**, conforme mostrado no trecho abaixo.


![](images/ditaval-flag-style.png){width="650" align="left"}


- **Cor do Plano de Fundo**: selecione o matiz, a saturação e o contraste na cor do Plano de Fundo. O valor hexadecimal correspondente será atualizado automaticamente com base na sua seleção. Também é possível alternar o formato do espaço de cores usando a lista suspensa para escolher entre HEX, RGB e HSB.


![](images/ditaval-background-color.png){width="650" align="left"}



- **Cor do Texto**: selecione a matiz, a saturação e o contraste na cor do Texto. O valor hexadecimal correspondente será atualizado automaticamente com base na sua seleção. Também é possível alternar o formato do espaço de cores usando a lista suspensa para escolher entre HEX, RGB e HSB.


![](images/ditaval-text-color.png){width="650" align="left"}



- **Opções de estilo**: você pode adicionar algumas opções de estilo, como Negrito, Itálico, Sublinhado, Sobreposto, Sublinhado duplo.


![](images/ditaval-styling-option.png){width="650" align="left"}



- **Sinalizadores de Início e Término**: você pode inserir imagens como sinalizadores de início e término usando o botão **Adicionar Sinalizador**. Para escolher imagens, use o **Procurar Assets** para selecionar no repositório de Guias ou o **Adicionar Arquivo** para carregar do seu sistema local. Além disso, é possível especificar texto alternativo para as imagens.


![](images/ditaval-start-end-flags.png){width="650" align="left"}



- **Conflito de estilo**: resolve os conflitos que ocorrem quando um único elemento contém várias propriedades com estilos de Sinalizador diferentes. Nesses casos, o valor definido nas propriedades de conflito de estilo é selecionado, atuando efetivamente como um seletor de valor padrão para cores de fundo e texto.


![](images/ditaval-style-conflict.png){width="650" align="left"}


#### Informações de versão e Salvar como nova versão

O recurso Informações da versão e Salvar como nova versão combina o rastreamento de versão e a gravação de conteúdo em uma única funcionalidade.
Para obter mais detalhes, consulte [Salvar como nova versão](./web-editor-toolbar.md#version-information-and-save-as-new-version)


#### Bloquear/desbloquear

Bloqueia ou desbloqueia o arquivo atual. Bloquear um arquivo oferece acesso de gravação exclusivo ao arquivo.
Para obter mais detalhes, exiba [Bloquear e desbloquear o arquivo](./web-editor-toolbar.md#lockunlock)


### Salvar o conteúdo

Quando terminar de editar o arquivo DITAVAL, selecione **Salvar** na barra de guias.

>[!NOTE]
>
> Se você fechar o arquivo sem salvar, as alterações serão perdidas. Se você não deseja confirmar as alterações no repositório do Adobe Experience Manager, selecione **Fechar** e **Fechar sem salvar** na caixa de diálogo **Alterações não salvas**.

## Visualizações do editor DITAVAL

O editor DITAVAL do Adobe Experience Manager Guides é compatível com a visualização de arquivos DITAVAL em dois modos ou visualizações diferentes:

**Autor**:   Esta é uma exibição típica do What You See is What You Get \(WYSISYG\) do editor DITAVAL. Você pode adicionar ou remover propriedades usando a interface de usuário simples, que apresenta as propriedades, seus valores e ações na lista suspensa. Na visualização Autor, você tem as opções para inserir uma propriedade individual e inserir todas as propriedades com um único clique.

Você também pode encontrar a versão do arquivo DITAVAL que você está trabalhando no momento, passando o ponteiro sobre o nome do arquivo.

**Source**:   A visualização Source exibe o XML subjacente que compõe o arquivo DITAVAL. Além de fazer edições de texto regulares nessa visualização, um autor também pode adicionar ou editar propriedades usando o Catálogo inteligente.

Para chamar o Catálogo inteligente, coloque o cursor no final de qualquer definição de propriedade e digite &quot;&lt;&quot;. O editor mostrará uma lista de todos os elementos XML válidos que você pode inserir nesse local.

![](images/ditaval-source-view-new.png)


## Trabalhar com arquivos DITAVAL na interface do usuário do Assets

Você também pode criar um arquivo DITAVAL na interface do usuário do Assets. As etapas para criar um novo tópico DITAVAL são as seguintes:

1. Na interface do Assets, navegue até o local em que deseja criar o arquivo DITAVAL.

1. Selecione **Criar** \> **Tópico DITA**.

1. Na página Blueprint, selecione o modelo de arquivo DITAVAL e selecione **Próximo**.

1. Na página Propriedades, especifique o **Título** e o **Nome** para o arquivo DITAVAL.

   >[!NOTE]
   >
   > O nome é sugerido automaticamente com base no Título do arquivo. Se você quiser especificar manualmente o nome do arquivo, verifique se ele não contém espaços, apóstrofos ou chaves e termine com .ditaval.

1. Selecione **Criar**.

   A mensagem Topic Created (Tópico criado) é exibida.

Você pode optar por abrir o arquivo DITAVAL para edição no editor DITAVAL ou salvar o arquivo de tópico no repositório do Adobe Experience Manager.

Execute as seguintes etapas para editar um arquivo DITAVAL existente:

1. Na interface do Assets, navegue até o arquivo DITAVAL que deseja editar.

1. Para obter um bloqueio exclusivo sobre o arquivo, selecione o arquivo e **Check-out**.

1. Selecione o arquivo e selecione **Editar** para abri-lo no editor Adobe Experience Manager Guides DITAVAL.



