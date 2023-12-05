---
title: Personalizar barra de ferramentas
description: Saiba como personalizar a barra de ferramentas
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# Personalizar barra de ferramentas {#id172FB00L0V6}

Por padrão, o Editor da Web é fornecido com os recursos editoriais mais comuns exigidos por qualquer editor DITA. Recursos como inserir elementos da lista de tipos \(numerada ou com marcadores\), referência cruzada, referência de conteúdo, tabela, parágrafo e formatação de caracteres estão disponíveis no editor. Além desses elementos básicos, você pode personalizar o Editor da Web para inserir elementos usados no seu ambiente de criação.

Há duas maneiras de personalizar a barra de ferramentas do Editor da Web:

- Adicionar uma nova funcionalidade à barra de ferramentas

- Remover qualquer funcionalidade existente da barra de ferramentas


## Adicionar um recurso na barra de ferramentas

Adicionar uma funcionalidade ao Editor da Web envolve duas tarefas principais - adicionar um ícone para o recurso no *ui\_config.json* e adicionando a funcionalidade em segundo plano no JavaScript.

**Adicionar um ícone na barra de ferramentas**

Execute as seguintes etapas para adicionar um recurso à barra de ferramentas do Editor da Web:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o arquivo de configuração padrão disponível no seguinte local:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Crie uma cópia do arquivo de configuração padrão no seguinte local:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navegue até e abra a `ui_config.json` arquivo no `apps` para edição.

1. No `ui_config.json` adicione a definição do novo recurso na seção barras de ferramentas. Normalmente, você pode criar um novo grupo de botões da barra de ferramentas e adicionar um ou mais botões da barra de ferramentas a ele. Ou você pode adicionar um novo botão de barra de ferramentas em um grupo existente. Os detalhes a seguir são necessários para criar um novo grupo de barras de ferramentas:

   - **tipo:**especificar `blockGroup` como o `type` valor. Esse valor indica que você está criando um grupo de blocos que conteria um ou mais grupos da barra de ferramentas.

   - **classe de extração:** Nome da classe ou classes separadas por espaço.

   - **itens:** Especifique a definição de todos os grupos na barra de ferramentas. Cada grupo pode conter um ou vários ícones da barra de ferramentas. Para definir ícones em um grupo de barras de ferramentas, é necessário definir novamente a variável `type` atributo dentro do `items`e defina seu valor como `buttonGroup`. Especifique um ou mais nomes de classe no `extraclass` propriedade. Especifique o nome do recurso no campo `label` propriedade. O trecho a seguir do `ui_config.json` arquivo mostra a definição do bloco da barra de ferramentas principal, seguida pelo `buttonGroup` definição:

     ```json
     "toolbar": {    
       "type": "blockGroup",    
       "extraclass": 
       "toolbar operations",    
         "items": [      
           {        
             "type": "buttonGroup",        
             "extraclass": "left-controls",        
             "label": "Left Controls",        
             "items": [
     ```

     No prazo de `items` é necessário especificar a definição de um ou mais ícones da barra de ferramentas.
É necessário definir as seguintes propriedades para adicionar um ícone da barra de ferramentas:

   - **tipo:** Especificar `button` como o `type` valor. Esse valor indica que você está adicionando um botão da barra de ferramentas.

   - **ícone:** Especifique o nome do ícone Coral que deseja usar na barra de ferramentas.

   - **variante:** Especificar `quiet` como o `variant` valor.

   - **título:** Especifique a dica de ferramenta do ícone.

   - **ao clicar:** Especifique o nome do comando definido para o recurso no arquivo JavaScript. Se o comando exigir parâmetros de entrada, especifique o nome do comando como:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **mostrar ou ocultar:** Se você estiver definindo a variável `show` e especifique os modos nos quais o ícone é exibido. Os valores possíveis são - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(exibir em todos os modos\), ou `false` \(ocultar em todos os modos\).

   Em vez de `show`, você também pode definir a variável `hide` propriedade. Os valores possíveis são os mesmos que em `show` com a única diferença de que o ícone não é exibido para o modo especificado.

1. Criar um *clientlib* e adicione o JavaScript a essa pasta.

1. Atualize a propriedade de categorias do *clientlib* atribuindo o valor de *apps.fmdita.xml\_editor.page\_overrides*.

1. Salve o *ui\_config.json* e recarregar o Editor da Web.


**Amostras de código JavaScript**

Esta seção fornece dois exemplos de código JavaScript que ajudariam você a começar a adicionar funcionalidade personalizada. O exemplo a seguir mostra o número da versão dos Guias do AEM quando um usuário clica no ícone Mostrar versão na barra de ferramentas.

Adicione o seguinte código a um arquivo JavaScript:

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Adicione o recurso no arquivo ui\_config.json como:

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

O exemplo a seguir mostra como alterar o estado de um documento de um arquivo ativo para &quot;Em revisão&quot;.

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Adicione o recurso no arquivo ui\_config.json como:

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Remover um recurso da barra de ferramentas

Às vezes, você pode não querer fornecer todos os recursos atualmente disponíveis no Editor da Web. Nesse caso, você pode remover o recurso indesejado da barra de ferramentas do Editor da Web.

Execute as seguintes etapas para remover qualquer recurso indesejado da barra de ferramentas:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o arquivo de configuração padrão disponível no seguinte local:.

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Crie uma cópia do arquivo de configuração padrão no seguinte local:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navegue até e abra a `ui_config.json` arquivo no `apps` para edição.
A variável `ui_config.json` O arquivo tem três seções:

- **barras de ferramentas:**   Esta seção contém a definição de todos os recursos disponíveis na barra de ferramentas do editor, como Inserir/Remover lista numerada, \(arquivo\) Fechar, Salvar, Comentários e muito mais.

- **atalhos:**   Esta seção contém a definição de atalhos de teclado atribuídos a um recurso específico no editor.

- **modelos:**   Esta seção contém a estrutura predefinida de elementos DITA que você pode usar no documento. Por padrão, a seção de modelos contém definições de modelo para um parágrafo, tabela simples, tabela e elementos de corpo. É possível criar uma definição de modelo para qualquer elemento adicionando uma estrutura XML válida para o elemento desejado. Por exemplo, se você deseja adicionar um `p` elemento a cada novo `li` em uma lista, é possível adicionar o seguinte código ao final da seção templates para fazer isso:

```HTML
"li": "<li><p></p></li>"
```

1. Na seção de barras de ferramentas, remova a entrada do recurso que você não deseja expor aos usuários.

1. Salve o *ui\_config.json* e recarregar o Editor da Web.


**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
