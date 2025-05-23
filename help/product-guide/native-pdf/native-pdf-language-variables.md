---
title: PDF nativo | Suporte para variáveis de idioma
description: Usar variáveis de linguagem nos templates de saída e saída do PDF
exl-id: 2335a7d5-251b-4266-8bba-9c9935e7bbf4
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6e9c998aa5c36b7e0dbb9d594dbf223017164698
workflow-type: tm+mt
source-wordcount: '1594'
ht-degree: 0%

---

# Suporte para variáveis de idioma

O Adobe Experience Manager Guides fornece o recurso para usar variáveis de idioma. Você pode usar variáveis de idioma para definir strings localizadas na saída do PDF ou para localizar qualquer texto estático nos templates de saída. Você pode usar estilos CSS para localizar as cadeias de caracteres provenientes de um CSS.

## Usar variáveis de idioma na saída do PDF

Você pode usar variáveis de idioma para definir uma versão localizada dos rótulos prontos para uso como Observação, Cuidado e Aviso ou texto estático na saída do PDF. O nome da variável é o mesmo para todos os idiomas, mas pode ter valores diferentes para os vários idiomas. Você pode atualizar o valor dessas variáveis em um ou mais idiomas e, em seguida, o valor localizado é selecionado automaticamente na saída do PDF.

Por exemplo, você pode ter as seguintes maneiras de apresentar o rótulo `Note` na saída do PDF:

- Inglês: Note

- Francês: Remarque

- Alemão: Hinweis

<img alt= "saída para o documento que contém variáveis de idioma" src="./assets/language-variable-output.png" width="550">

*Uma observação de exemplo em inglês, francês e alemão.*

>[!NOTE]
>
> Se o valor de qualquer variável não estiver definido em um idioma específico, o AEM Guides escolherá a string do idioma da interface do usuário (interface do usuário do aplicativo) como um mecanismo de fallback.
>
> Se você não tiver definido o valor no idioma da interface do usuário, ele procurará por inglês (`en_us`) ou então escolherá o valor em inglês (`en`) e exibirá o mesmo na saída do PDF.

## Tipos de variáveis de idioma

O AEM Guides oferece suporte a dois tipos de variáveis: Variáveis de aplicativo e de usuário.

### Variáveis de aplicativo

O AEM Guides fornece um conjunto de variáveis de aplicativo predefinidas ou prontas para uso. Você pode usar essas variáveis predefinidas para adicionar informações sobre um documento específico do AEM Guides. Por exemplo, a variável `chapter-number`, se incluída em uma página, exibe o número do capítulo ao qual a página pertence. A variável `author-label` exibe o nome do autor do documento.

>[!NOTE]
>
> É possível substituir o valor de uma variável do aplicativo.


### Variáveis do usuário

Você também pode criar novas variáveis de idioma. Por exemplo, você pode criar uma variável de usuário Editor para o rótulo do editor do documento.

>[!NOTE]
>
>  Você deve ter privilégios administrativos para criar variáveis de usuário e editar as variáveis do aplicativo.

<img alt="janela variáveis de idioma" src="./assets/add-language-variables.png" width="550">

*Adicione e exiba as variáveis de idioma para um idioma selecionado.*

## Adicionar uma nova variável de idioma

1. No Editor, navegue até o painel esquerdo e selecione **Variáveis de idioma**. Essa opção está disponível na seção Mais.
1. Selecione **Editar** para abrir a janela **Variáveis de idioma**. O aplicativo e as variáveis de usuário presentes no idioma selecionado são listados em ordem alfabética. Os valores são exibidos de acordo com o idioma selecionado. Por exemplo, se você selecionar o idioma francês, &quot;Dica&quot; será exibida como &quot;Conseil&quot;.
1. Na lista suspensa **Idioma**, selecione o idioma desejado no qual deseja editar uma variável.

   >[!NOTE]
   >
   > Se você não exibir os idiomas desejados, habilite o idioma desejado nas configurações de **Configurar idiomas**. Selecionar configurações <img src="./assets/settings-icon.svg" width="25"> para abrir a caixa de diálogo **Configurar idiomas**.

1. Insira o nome da variável na coluna **Nome** e seu valor na coluna **Valor**.

   >[!NOTE]
   >
   >Você pode usar qualquer conteúdo do HTML como um valor de variável para exibir o valor da variável em formatação específica. Por exemplo, você pode adicionar a tag `<b>` ao valor da variável para exibir o Editor em negrito.

1. Selecionar **Adicionar Variável de Idioma** <img src="./assets/add-language-variable.svg" width="25"> para adicionar uma nova variável de idioma ao idioma selecionado. Adicionar uma variável a um idioma a adiciona automaticamente a todos os idiomas. Não é possível criar uma variável com o mesmo nome de uma variável existente. Um erro é exibido.

>[!NOTE]
>
> Se você não selecionar **Adicionar variável de idioma**, a variável não será criada e adicionada à lista

## Exportar e importar variáveis de idioma

O Experience Manager Guides fornece suporte para exportar e importar as variáveis de idioma presentes no idioma selecionado. É possível exportar facilmente todas as variáveis de idioma juntamente com os valores definidos. Isso inclui as variáveis de aplicativo e usuário. Use o arquivo exportado para fazer as alterações desejadas nos valores ou localizá-las em outros idiomas.

Você também pode importar o arquivo XML, que contém as variáveis de idioma. O Experience Manager Guides importa somente as variáveis de idioma já definidas, incluindo as variáveis de aplicativo e usuário. Ela não importa nenhuma variável que ainda não esteja definida.

### Exportar variáveis de idioma

Para exportar as variáveis de idioma para um idioma, selecione o idioma na lista suspensa e selecione **Exportar** <img src="./assets/language-variable-export-icon.svg" alt="ícone exportar" width="25">.
Ele cria um arquivo XML com o formato `language_variable_<ln>`, onde `<ln>` é o código do idioma selecionado. Por exemplo, `language_variable_en.xml` para inglês e `language_variable_fr.xml` para francês.

>[!NOTE]
> 
>Se você tiver alterações não salvas nas variáveis de idioma, não poderá exportá-las. Salve as alterações para exibir a **Exportação** habilitada Ícone <img src="./assets/language-variable-export-icon.svg" alt="ícone de importação" width="25">.

### Importar variáveis de idioma

Para importar as variáveis de idioma:

1. Selecione um idioma na lista suspensa e selecione **Importar** <img src="./assets/language-variable-import-icon.svg" width="25">.
2. Procure e selecione o XML, que contém as variáveis de idioma. Por exemplo, language_variable_en.xml.
Você pode importar arquivos XML no seguinte formato:

```
<?xml version="1.0" encoding="UTF-8"?>
<variables>    
<variable id="note-important">Important: </variable>    
<variable id="note-caution">Avertir: </variable>    
<variable id="image-with-text">Text and image &lt;img src=&quot;/content/dam/assets/images/image_with_text.png&quot; /&gt; </variable> 
</variables> 
```

As variáveis com a mesma ID são importadas após a importação do arquivo. Os valores das variáveis no idioma selecionado são atualizados com aqueles no arquivo XML.  Uma mensagem sobre o número de variáveis atualizadas é exibida.

>[!NOTE]
> 
><ul><li>Se o arquivo não for um arquivo XML ou se contiver um formato incorreto que não mapeie com as variáveis de idioma, você verá um erro de que há um problema com o arquivo XML. 
>&gt;<li>Se o arquivo não contiver variáveis com a mesma ID, você verá um aviso de que nenhuma variável de idioma correspondente é encontrada no arquivo importado.

### Opções para uma variável de idioma

Passe o mouse sobre a variável para ver o menu **Opções** para ela.

<img width="550" alt="menu de opções para variáveis de idioma" src="./assets/language-variable-user-options.png">

*Use o menu **Opções**&#x200B;para excluir, visualizar ou duplicar uma variável de idioma.*

Você pode visualizar as variáveis do aplicativo e do usuário. Para exibir como o valor da variável é exibido na saída, selecione **Visualizar** no menu **Opções** da variável selecionada.
Você também pode optar por **Excluir** ou **Duplicar** as variáveis de usuário. A exclusão de uma variável de um idioma a exclui automaticamente de todos os idiomas.

### Editar ou reverter as variáveis do aplicativo

Também é possível editar os valores de uma variável de aplicativo. Posteriormente, é possível reverter uma variável do aplicativo para o valor original. **Redefinir** <img src="./assets/application-variable-revert.svg" width="25"> aparece para uma variável de aplicativo com um valor alterado.

## Usar variáveis de idioma nos modelos de saída

Você deve adicionar variáveis de idioma nos documentos localizados. Você pode inserir essas variáveis de idioma no layout de página que aparece em páginas diferentes nos documentos localizados. Por exemplo, você pode adicionar a variável de idioma para o `author-name` que aparece na área de cabeçalho do layout da página (ou qualquer outra parte, como o rodapé ou o corpo).



<img alt="page-layout de um pdf" src="./assets/language-variable-page-layout.png" width="550">


*O autor e o nome da marca localizados na saída do PDF gerada para o idioma francês.*

Para inserir uma variável de idioma como o `copyright-label` na área de cabeçalho, execute as seguintes etapas:

1. Abra o layout de página desejado para edição.

   >[!NOTE]
   >
   > Exibir [Personalizar uma seção de layout de página](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) para abrir um layout de página para personalização ou edição.

1. Selecione o cabeçalho para torná-lo ativo e inserir uma variável.
1. Selecionar **Inserir Variável**  <img src="./assets/insert-language-variable.svg" width="25"> na barra de ferramentas.
1. No pop-up **Inserir variável**, selecione o nome da variável de idioma a ser inserida e clique em **Inserir** para inseri-la na área de cabeçalho.

   >[!NOTE]
   >
   > Você também pode inserir a string de pesquisa na caixa de texto. Os nomes das variáveis que contêm a cadeia de caracteres fornecida são filtrados e exibidos na lista.
   > A variável de idioma selecionada é inserida na área de cabeçalho.



<img alt="inserir variável na área de cabeçalho" src="./assets/language-variable-header.png" width="550">

*O `copyright-label` foi adicionado à área do cabeçalho.*

### Aplicar estilo de conteúdo a variáveis de idioma

Além do valor atribuído a uma variável de idioma, também é possível usar tags HTML para exibir o valor da variável em formatação específica. Por exemplo, você pode exibir o valor de `publisher-label` em negrito.

- Também é possível formatar os estilos dos valores usando a tag <span>. Por exemplo, usando a variável de idioma page-number, é possível exibir o número da página no formato de número romano em inglês e especificar o formato para outros idiomas.

  Valor para inglês:
  `<span data-field="page-number" data-format="upper-roman">1</span>`

  Valor para tâmil:
  `<span data-field="page-number" data-format="tamil">1</span>`

Da mesma forma, é possível adicionar variáveis de idioma e formatar outros campos listados no recurso Inserir campos dos layouts de página. Para obter mais detalhes sobre como adicionar campos, exiba [Adicionar campos e metadados](../native-pdf/design-page-layout.md#add-fields-metadata).

- Também é possível adicionar imagens localizadas nos valores. Por exemplo, você pode adicionar um ícone de imagem no idioma do número do capítulo e obter imagens localizadas do ícone na saída do PDF.

  Para inglês, o valor da variável para uma imagem pode ser como `<img src="banner-en.jpg">`, e para a mesma variável em alemão, pode ser `<img src="banner-de.jpg">`. Então, ele pega as imagens dependendo da linguagem.

## Localizar as cadeias de caracteres usando estilos CSS

Usando estilos CSS, você também pode localizar as cadeias de caracteres usadas na Numeração automática, como Capítulo, Seção, Figura e Tabela. Como essas cadeias de caracteres vêm de arquivos CSS, não é possível localizá-las usando variáveis de idioma. Para traduzir essas cadeias de caracteres, você pode criar estilos de CSS para cada idioma em que deseja localizá-las.
Por exemplo, você pode usar o CSS a seguir para exibir o prefixo do capítulo e o formato de número correspondente em vários idiomas.
Por exemplo, você pode usar o CSS a seguir para exibir o Chapter como Hoofdstuk em alemão e o número do capítulo no formato decimal. No caso do japonês, é possível usar o formato de número japonês para mostrar os números de capítulo no índice.

```
// for English
h1:before {
  counter-increment: h11;
  content: "Chapter " counter(h11, decimal)".";
}

// for German
:root:lang(de) h1:before {
  content: "Hoofdstuk " counter(h11, decimal)".";
}

// for Japanese
:root:lang(ja) h1:before {
  content: "章 " counter(h11, japanese-formal)".";
}
```

As capturas de tela a seguir exibem as cadeias de caracteres localizadas na saída em alemão e japonês do PDF.

<img alt=" saída em japonês com variável de idioma" src="./assets/localize-chapter-german.png" width="550">



<img alt="Saída em alemão com variável de idioma" src="./assets/localize-chapter-japanese.png" width="550">



### Formatar os prefixos

Usando estilos CSS, você também pode formatar os prefixos. Por exemplo, você pode formatar o rótulo `Note` para aparecer na cor vermelha na saída PDF de vários idiomas.

```
.note .prefix-content 
{
color: red;
} 
```
