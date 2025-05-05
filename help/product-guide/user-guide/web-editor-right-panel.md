---
title: Painel direito no editor
description: Conheça o painel direito no Editor. Saiba mais sobre a interface e os recursos do editor no Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
exl-id: 6a0f4ed2-6eca-4b3c-bd3a-3f72f6919b36
source-git-commit: ffc9a9e15f11e7059822b7cf6d4707b83d15a4f4
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 0%

---

# Painel direito no Editor

O painel direito contém informações sobre o documento selecionado atualmente.

>[!NOTE]
>
> O painel direito é redimensionável. Para redimensionar o painel, coloque o cursor no limite do painel, o cursor se transformará em uma seta de duas pontas, selecione e arraste para redimensionar a largura do painel.

O painel direito fornece acesso aos seguintes recursos:

- [Propriedades de conteúdo](#content-properties)
- [Propriedades do arquivo](#file-properties)
- [Revisar](#review)
- [Rastrear alterações](#track-changes)
- [Schematron](#schematron)

## Propriedades de conteúdo

Você pode acessar o recurso **Propriedades de conteúdo** selecionando o ícone **Propriedades de conteúdo** no painel direito. O painel **Propriedades de conteúdo** contém informações sobre o tipo de elemento atualmente selecionado no documento e seus atributos.

**Tipo**: você pode exibir e selecionar as marcas da hierarquia completa para a marca atual na lista suspensa.

**Atributos**: o painel suspenso **Atributos** está disponível nos modos de exibição Layout, Autor e Source. É possível adicionar, editar ou excluir facilmente os atributos.

<details>
    <summary> Etapas para adicionar atributos </summary>


1. Selecione **Adicionar**.

   ![atributos em propriedades de conteúdo](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. No painel suspenso **Atributo**, selecione o atributo na lista suspensa e especifique o valor de um atributo.  Em seguida, selecione **Adicionar**.

   ![painel de atributos com vários atributos ](images/attributes-multiple-properties.png){width="300" align="left"}

1. Para editar o atributo, passe o mouse sobre ele e selecione **Editar** ![ícone de edição](images/edit_pencil_icon.svg).

1. Para excluir o atributo, passe o mouse sobre ele e selecione **Excluir** ![ícone de exclusão](images/Delete_icon.svg).

</details>


>[!NOTE]
>
> Mesmo que seu tópico tenha conteúdo referenciado, é possível adicionar atributos a ele usando o painel de propriedades.

Se o administrador tiver criado um perfil para atributos, você obterá esses atributos junto com seus valores configurados. Usando o painel de propriedades de conteúdo, você pode escolher esses atributos e atribuí-los ao conteúdo relevante em seu tópico. Dessa forma, você também pode criar conteúdo condicional, que pode ser usado para criar saída condicional. Para obter mais informações sobre como gerar saída usando predefinições condicionais, exiba [Usar predefinições de condição](generate-output-use-condition-presets.md#).



## Propriedades do arquivo

Visualize as propriedades do arquivo selecionado selecionando o ícone Propriedades do arquivo no painel direito. O recurso Propriedades do arquivo está disponível em todos os quatro modos ou exibições: Layout, Autor, Source e Visualização.

As propriedades do Arquivo têm as duas seções a seguir:

**Geral**

A seção Geral fornece acesso aos seguintes recursos:

![propriedades-arquivo](images/file-properties-general.png){width="300" align="left"}

- **Nome do arquivo**: exibe o nome do arquivo do tópico selecionado. O nome do arquivo tem um hiperlink para a página de propriedades do arquivo selecionado.
- **ID**: exibe a ID do tópico selecionado.
- **Marcas**: estas são as marcas de metadados do tópico. Eles são definidos no campo tags na página propriedades. Você pode digitá-los ou selecioná-los na lista suspensa.  As tags são exibidas na lista suspensa. Para excluir uma tag, selecione o ícone de cruz ao lado da tag.
- **Editar mais propriedades**: é possível editar mais propriedades na página de propriedades do arquivo.
- **Idioma**: mostra o idioma do tópico. Ele é definido no campo Language na página de propriedades.
- **Criado em**: exibe a data e a hora em que o tópico foi criado.
- **Modificado em**: exibe a data e a hora em que o tópico foi modificado.
- **Bloqueado por**: mostra o usuário que bloqueou o tópico.
- **Estado do documento**: você pode selecionar e atualizar o estado do documento do tópico aberto no momento. Para obter mais detalhes, exiba [Estado do Documento](web-editor-document-states.md#).

>[!NOTE]
>
> Você pode copiar os valores de atributo de vários campos nas propriedades do arquivo para a área de transferência.

**Referências**

A seção Referências fornece acesso aos seguintes recursos:

![](images/file-properties-references.png){width="300" align="left"}

- **Usado em**: as referências Usado em listam os documentos nos quais o arquivo atual está sendo referenciado ou usado.
- **Links de saída:** os Links de saída listam os documentos referenciados no documento atual.

Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um arquivo, é possível visualizar o título do arquivo e o caminho do arquivo como uma dica de ferramenta.

>[!NOTE]
>
> Como administrador, você também pode optar por visualizar a lista de arquivos por nomes de arquivo no Editor. Selecione a opção **Nome do arquivo** da seção **Configuração de exibição dos arquivos do editor** em **Preferências do usuário**.

>[!NOTE]
>
> Todas as referências Usadas no e de Saída têm hiperlinks para os documentos. É possível abrir e editar facilmente os documentos vinculados.

Além de abrir arquivos, você também pode executar muitas ações usando o menu **Opções** na seção Referências. Algumas das ações que você pode executar incluem Editar, Visualizar, Copiar UUID, Copiar caminho, Adicionar às coleções, Propriedades.

## Revisar

Selecionar o ícone Revisar abre o painel de revisão, no qual é possível selecionar uma tarefa de revisão para o documento aberto no momento e exibir comentários.

![](images/review-panel-before-opening.png){width="300" align="left"}

Se você tiver criado vários projetos de revisão, é possível selecionar um no menu suspenso e acessar os comentários da revisão.

Usando o painel de revisão, você pode exibir e postar respostas aos comentários fornecidos sobre o tópico. Você pode aceitar ou rejeitar os comentários um por um.

>[!NOTE]
>
> A caixa de comentário e a caixa de resposta são compatíveis com entradas de várias linhas e permitem que os usuários as expandam conforme necessário para fornecer comentários abrangentes, bem como respostas detalhadas aos comentários. Você pode usar **Shift** + **Enter** para ir para a próxima linha enquanto escreve os comentários ou as respostas.

Para obter mais informações, exiba [comentários de revisão de endereço](review-address-review-comments.md#).

## Rastrear alterações

Usando o recurso Alterações controladas do painel direito, você pode exibir as informações de todas as atualizações feitas em um documento. Você também pode procurar por atualizações específicas feitas no documento.

>[!NOTE]
>
> O recurso Alterações controladas mostra todas as atualizações que foram controladas usando o recurso Habilitar/Desabilitar Controlar Alterações da [Barra de guias](./web-editor-tab-bar.md).

## Schematron

&quot;Esquematron&quot; refere-se a uma linguagem de validação baseada em regras usada para definir testes para um arquivo XML. O Editor aceita arquivos do Schematron. É possível importar os arquivos do Schematron e editá-los no Editor. Usando um arquivo de Esquematron, você pode definir determinadas regras e depois validá-las para um tópico DITA ou um mapa.

Saiba como trabalhar com arquivos Schematron no Experience Manager Guides, consulte [Suporte para arquivos Schematron](./support-schematron-file.md).



**Tópico pai:**&#x200B;[ Introdução ao Editor](web-editor.md)
