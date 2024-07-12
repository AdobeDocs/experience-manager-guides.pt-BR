---
title: PDF nativo | Usar variáveis na saída PDF
description: Use variáveis nos modelos de saída e saída em PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: 96e54aee-52df-4af1-97fd-34986f553be4
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---

# Variáveis na saída PDF

Um variável é um par de dados nome-valor que serve como uma informação reutilizável. Isso torna seus conteúdo portáteis e fáceis de atualizar. Quando você modifica uma variável ou seu valor, cada ocorrência dessa variável ou valor é atualizada.



## Criar uma nova variável

Execute as seguintes etapas para criar uma variável:

![Criar uma nova variável](assets/add-variable-default.png){width="800" align="left"}

*Crie variáveis e defina valores para elas.*


1. No Editor da Web, vá para a guia **Saída**.
1. Selecionar **Variáveis** <img alt= "ícone de variável" src="./assets/variables-icon.svg" width="25"> no painel esquerdo.
1. Selecionar **Editar** <img alt= "Ícone Editar lápis" src="./assets/edit_pencil_icon.svg" width="25"> para abrir o editor de **Variáveis**.
As variáveis estão listadas em ordem alfabética.
1. Insira o nome variável na **coluna Nome** e seu valor na **coluna Valor** .
   >[!TIP]
   >
   >Você pode usar qualquer conteúdo HTML como um valor de variável para exibir o valor da variável em formatação específica. Por exemplo, você pode adicionar uma tag `<b>` ao valor da variável para exibir o valor **Experience Manager Guides** em negrito. Você também pode adicionar imagens do repositório como valores.

1. Selecionar **Adicionar variável** <img alt= "Ícone Adicionar" src="./assets/add-icon.svg" width="25"> para adicionar uma nova variável. Não é possível criar uma variável com o mesmo nome de uma variável existente. Um erro é exibido.

   >[!NOTE]
   >
   >Se você não selecionar **Adicionar variável** <img alt= "Ícone Adicionar" src="./assets/add-icon.svg" width="25">, a variável não foi criada e adicionada à lista.

Dessa forma, você pode criar variáveis com valores padrão. Por exemplo:
* ProductName: Experience Manager Guides
* VersionNumber: 2300
* Data de lançamento: 01/01/2023


### Editar uma variável

É possível editar uma variável de duas maneiras:

**No painel Variáveis à esquerda**

1. Selecione uma variável no painel **Variáveis**.
1. Passe o mouse sobre a variável para ver o menu **Opções** e selecione a opção **Editar**.
1. Na caixa de diálogo **Editar Variável**, é possível editar o valor padrão da variável selecionada.
1. Clique em **Concluído**.

**No editor de Variáveis**

1. Selecionar **Variáveis** <img alt= "ícone de variável" src="./assets/variables-icon.svg" width="25"> no painel esquerdo.
1. Selecionar **Editar** <img alt= "Ícone Editar lápis" src="./assets/edit_pencil_icon.svg" width="25"> para abrir o **editor Variáveis** .

1. **Na editor Variáveis**, é possível editar o valor dos variável selecionados.

É necessário salvar as alterações feitas nas **Variáveis** editor para visualização-las no **painel Variáveis** no lado esquerdo.

>[!NOTE]
>
> Se você editar qualquer valor de variável, o Adobe Experience Manager Guias atualizará simultaneamente todas as referências sempre que aplicável.

### Search e pré-visualização uma variável

É possível pesquisar e pré-visualizar o valor de uma variável. Insira uma cadeia de caracteres na caixa de pesquisa do painel **Variáveis**. Ela faz a pesquisa com base no nome da variável e em seu valor.
É possível visualizar uma variável de duas maneiras:

A pré-visualização da variável exibe o valor padrão. Por exemplo, se você tiver definido o valor padrão da variável ProductName como &quot;Adobe Experience Manager Guides&quot;, ele exibirá esse valor na visualização.

**No painel Variáveis à esquerda**


1. Selecione uma variável no painel **Variáveis**.
1. Passe o mouse sobre a variável para ver o menu **Opções** e selecione a opção **Visualizar**.

![visualização de variável do painel de variáveis](assets/variables-panel-preview-default.png){width="550" align="left"}

*Visualize o valor padrão de uma variável.*

**No editor de Variáveis**

1. Passe o mouse sobre a variável na lista para ver o menu **Opções**.
1. Selecione **Visualizar**.




### Duplicação de uma variável

É possível duplicado um variável e modificar o valor de acordo com seus requisitos.


1. Passe o mouse sobre as variável no lista para visualização no **menu Opções** .
1. Selecione **Duplicar**.

O nome padrão da variável é `<selected variable name>` (como &quot;exemplo&quot;). Você pode alterar o nome de acordo com suas necessidades.

### Excluir uma variável

É possível excluir uma variável de duas maneiras:

**No painel Variáveis à esquerda**

1. Selecione uma variável no painel **Variáveis**.
1. Passe o mouse sobre a variável para ver o menu **Opções** e selecione a opção **Excluir**.

**No editor de Variáveis**

1. Passe o mouse sobre a variável na lista para ver o menu **Opções**.
1. Selecione a opção **Excluir**.

A variável é excluída de todos os conjuntos de variáveis.

## Conjuntos de variáveis para as predefinições de saída

Adobe Experience Manager Guias também suporta conjuntos de variável, que permitem atribuir valores alternativos às suas variáveis. Por exemplo, uma empresa pode vender dois produtos, A e B. Ela tem especificações diferentes para cada uma delas. Essas especificações podem incluir o nome do produto, o número da versão e a data de lançamento. Pode haver outras diferenças na identidade visual. Usando conjuntos de variáveis, você define um conjunto diferente de valores para as variáveis. Ao gerar a saída, você escolhe o conjunto de variáveis apropriado e produz a saída necessária.

### Configurar conjuntos de variáveis

É necessário configurar conjuntos de variáveis antes de adicionar variáveis a eles.



1. Selecionar **Configurações** <img alt= "Ícone Configurações" src="./assets/settings-icon.svg" width="25"> para abrir a caixa de diálogo **Configurar conjuntos de variáveis**.
   ![configurar conjunto de variáveis](assets/configure-variable-set.png){width="550" align="left"}
1. Insira o nome do conjunto de variáveis na coluna **Nome**.
1. Selecionar **Adicionar variável** <img alt= "Ícone Adicionar" src="./assets/add-icon.svg" width="25"> para adicionar um novo conjunto de variáveis. Os conjuntos de variáveis são listados em ordem alfabética.
1. Você pode selecionar **Excluir** para remover um conjunto de variáveis.

### Operações de conjunto de variáveis

Todos os conjuntos de variáveis têm as mesmas variáveis, mas podem ter valores diferentes.

É possível exibir, editar e visualizar os valores de um conjunto de variáveis específico. Selecione um conjunto de variáveis na lista suspensa **Conjuntos de variáveis**. Os valores são exibidos de acordo com o conjunto de variáveis escolhido.
Ao editar os valores das variáveis em conjuntos de variáveis específicos, os valores padrão são substituídos e os valores do conjunto de variáveis selecionado são alterados.
Por exemplo, você pode definir os seguintes valores para os conjuntos de variáveis, *Adobe-set1* e *Adobe-set2*.


**Conjunto de variáveis 1**: *Adobe-set1*

* Nome do produto: ProductA
* VersionNumber: 2311
* Data de lançamento: 02/11/2023


**Conjunto de variáveis 2**: *Adobe-set2*

* ProductName: ProductB
* VersionNumber: 2310
* Data de lançamento: 07/09/2023

Cada nova variável é adicionada a todos os conjuntos de variáveis. Quando você exclui ou duplica uma variável, ela é atualizada para todos os conjuntos de variáveis.

Também é possível visualizar os valores de um conjunto de variáveis.
Por exemplo, para o conjunto de variáveis *Adobe-Set1*, você definiu o valor da variável ProductName como &quot;ProductA&quot; e, em seguida, ele exibe esse valor na visualização no editor de Variáveis.

![visualização de variável do editor de variáveis](assets/variables-editor-preview.png){width="550" align="left"}

*Visualize o valor definido no conjunto de variáveis selecionado.*

### Redefinir o valor de uma variável

Se você editou o valor, também é possível redefinir uma variável para o valor padrão.
Redefinir <img alt= "ícone redefinir" src="./assets/application-variable-revert.svg" width="25"> aparece para uma variável com um valor alterado.
Por exemplo, é possível redefinir o valor da variável ProductName com o valor padrão Experience Manager Guides.

## Usar variáveis nos modelos de PDF nativo

Você pode adicionar variáveis enquanto gera a saída dos documentos do produto para torná-las portáteis e fáceis de atualizar. Você pode inserir essas variáveis no layout de página que aparece nas diferentes páginas dos documentos. Por exemplo, você pode adicionar a variável ProductName que aparece na área de cabeçalho do layout da página (ou qualquer outra parte, como o rodapé ou o corpo).



Para inserir uma variável como o Nome do produto na área de cabeçalho, execute as seguintes etapas:
1. Abra o layout de página desejado para edição.

   >[!NOTE]
   >
   > Exibir [Personalizar uma seção de layout de página](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) para abrir um layout de página para personalização ou edição.

1. Selecione o cabeçalho para torná-lo ativo e inserir uma variável.

1. É possível inserir o variável de duas maneiras:

   **No painel Variáveis, no lado esquerdo**

   * Arraste um variável do **painel Variáveis** e solte-o na área de cabeçalho.

   **Da barra de ferramentas**

   1. Selecionar **Inserir Variável/Campos** <img alt= "ícone de variável" src="./assets/variables-icon.svg" width="25">.
   1. Na caixa de diálogo **Variável**, selecione o nome da variável para inseri-la na área de cabeçalho.
   1. Você também pode inserir a string de pesquisa na caixa de texto. Os nomes das variáveis que contêm a cadeia de caracteres fornecida são filtrados e exibidos na lista. A variável selecionada é inserida na área de cabeçalho. É possível visualizar o valor padrão da variável.
   1. Para substituir uma variável, clique duas vezes no valor e selecione outra variável na caixa de diálogo **Variável**. A variável é substituída.


## Gerar saída de PDF com variáveis

Você pode gerar a saída de PDF com os valores de variáveis diferentes. Antes de gerar o layout, escolha um conjunto de variáveis na lista suspensa **Conjunto de variáveis** de uma predefinição de saída para escolher seus valores.

![lista suspensa do conjunto de variáveis](assets/output-preset-variable-dropdown.png){width="550" align="left"}

*Selecione uma variável definida na lista suspensa da predefinição de saída que deseja usar para gerar a saída PDF.*

>[!NOTE]
>
> Você também pode selecionar (Padrão) na lista suspensa para publicar os valores padrão de todas as variáveis.

Dependendo do conjunto de variáveis escolhido, você obterá uma saída correspondente aos valores de variáveis definidos no conjunto de variáveis. Por exemplo, se você selecionar o conjunto de variáveis *Adobe-set1*, sua saída exibirá os valores das variáveis conforme definido neste conjunto.


<img src="assets/variable-pdf-output.png" alt="saída de PDF com variáveis" width="500" border="2px">

*Gere a saída de PDF usando variáveis no layout da página.*

Você também pode atualizar rapidamente os valores de qualquer conjunto de variáveis sempre que necessário e gerar novamente a saída. Por exemplo, se você precisar atualizar os detalhes de uma versão, é possível atualizar o valor da versão na variável VersionNumber e gerar novamente a saída.
