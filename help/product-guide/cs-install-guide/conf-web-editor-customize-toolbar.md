---
title: Personalizar barra de ferramentas
description: Saiba como personalizar a barra de ferramentas
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Personalizar barra de ferramentas {#id172FB00L0V6}

Por padrão, o Editor da Web é fornecido com os recursos editoriais mais comuns exigidos por qualquer editor DITA. Recursos como inserir elementos da lista de tipos \(numerada ou com marcadores\), referência cruzada, referência de conteúdo, tabela, parágrafo e formatação de caracteres estão disponíveis no editor. Além desses elementos básicos, você pode personalizar o Editor da Web para inserir elementos usados no seu ambiente de criação.

Há duas maneiras de personalizar a barra de ferramentas do Editor da Web:

- Adicionar uma nova funcionalidade à barra de ferramentas

- Remover qualquer funcionalidade existente da barra de ferramentas


## Adicionar um recurso na barra de ferramentas

Adicionar uma funcionalidade ao Editor da Web envolve duas tarefas principais - adicionar um ícone para o recurso no *ui\_config.json* e adicionando a funcionalidade em segundo plano no JavaScript.

Execute as seguintes etapas para adicionar um recurso à barra de ferramentas do Editor da Web:

1. Para baixar o arquivo de configuração da interface do usuário, faça logon no Adobe Experience Manager como administrador.

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecionar **Guias** na lista de ferramentas e clique no botão **Perfis de pasta**.
1. Clique no link **Perfil global** bloco.
1. Selecione o **Configuração do editor XML** e clique em **Editar** ícone na parte superior
1. Clique em **Baixar** ícone para baixar o arquivo ui\_config.json no sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.
1. No `ui_config.json` adicione a definição do novo recurso na seção barras de ferramentas. Salve o arquivo e faça upload dele.

   Normalmente, você pode criar um novo grupo de botões da barra de ferramentas e adicionar um ou mais botões da barra de ferramentas a ele. Ou você pode adicionar um novo botão de barra de ferramentas em um grupo existente. Os detalhes a seguir são necessários para criar um novo grupo de barras de ferramentas:

   **type**: especificar `blockGroup` como o `type` valor. Esse valor indica que você está criando um grupo de blocos que conteria um ou mais grupos da barra de ferramentas.

   **extraclass**: Nome da classe ou classes separadas por espaço.

   **itens**: especifique a definição de todos os grupos na barra de ferramentas. Cada grupo pode conter um ou vários ícones da barra de ferramentas. Para definir ícones em um grupo de barras de ferramentas, é necessário definir novamente a variável `type` atributo dentro do `items`e defina seu valor como `buttonGroup`. Especifique um ou mais nomes de classe no `extraclass` propriedade. Especifique o nome do recurso no campo `label` propriedade. O trecho a seguir do `ui_config.json` arquivo mostra a definição do bloco da barra de ferramentas principal, seguida pelo `buttonGroup` definição:

       &quot;
       &quot;barra de ferramentas&quot;: {
       &quot;type&quot;: &quot;blockGroup&quot;,
       &quot;extraclass&quot;:
       &quot;operações da barra de ferramentas&quot;,
       &quot;items&quot;: [
       {
       &quot;type&quot;: &quot;buttonGroup&quot;,
       &quot;extraclass&quot;: &quot;left-controls&quot;,
       &quot;label&quot;: &quot;Left Controls&quot;,
       &quot;items&quot;: [
       &quot;
   
   No prazo de `items` é necessário especificar a definição de um ou mais ícones da barra de ferramentas.

   É necessário definir as seguintes propriedades para adicionar um ícone da barra de ferramentas:

   **type**: especificar `button` como o `type` valor. Esse valor indica que você está adicionando um botão da barra de ferramentas.

   **ícone**: especifique o nome do ícone Coral que deseja usar na barra de ferramentas.

   **variante**: especificar `quiet` como o `variant` valor.

   **título**: Especifique a dica de ferramenta do ícone.

   **ao clicar**: especifique o nome do comando definido para o recurso no arquivo JavaScript. Se o comando exigir parâmetros de entrada, especifique o nome do comando como:

       &quot;Javascript
       &quot;ao clicar&quot;: {&quot;name&quot;: &quot;AUTHOR_INSERT_ELEMENT&quot;, &quot;args&quot;: &quot;simpletable&quot;}
       &quot;
   
   **mostrar ou ocultar**: Se estiver definindo o parâmetro `show` e especifique os modos nos quais o ícone é exibido. Os valores possíveis são - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(exibir em todos os modos\), ou `false` \(ocultar em todos os modos\).

   Em vez de `show`, você também pode definir a variável `hide` propriedade. Os valores possíveis são os mesmos que em `show` com a única diferença de que o ícone não é exibido para o modo especificado.

   O exemplo a seguir mostra o número da versão dos Guias do AEM quando o usuário clica no ícone Mostrar versão na barra de ferramentas.

   Adicione o seguinte código a um arquivo JavaScript:

   ```Javascript
   $(document).ready(setTimeout(function() {
                           fmxml.commandHandler.subscribe({
                           key: 'user.alert',
                           next: function() {
                           alert("AEM Guides version x.x")
                           }
                           })
                           }, 1000))
   ```

   Adicione o recurso na *ui\_config.json* arquivar como:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Criar um *clientlib* e adicione o JavaScript a essa pasta.

1. Atualize a propriedade de categorias do *clientlib* atribuindo o valor de *apps.fmdita.xml\_editor.page\_overrides*.

1. Salve o *ui\_config.json* e recarregar o Editor da Web.


## Remover um recurso da barra de ferramentas

Às vezes, você pode não querer fornecer todos os recursos atualmente disponíveis no Editor da Web. Nesse caso, você pode remover o recurso indesejado da barra de ferramentas do Editor da Web.

Execute as seguintes etapas para remover qualquer recurso indesejado da barra de ferramentas:

1. Para baixar o arquivo de configuração da interface do usuário, faça logon no Adobe Experience Manager como administrador.

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecionar **Guias** na lista de ferramentas e clique no botão **Perfis de pasta**.
1. Clique no link **Perfil global** bloco.
1. Selecione o **Configuração do editor XML** e clique em **Editar** ícone na parte superior
1. Clique em **Baixar** ícone para baixar o arquivo ui\_config.json no sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.

   A variável `ui_config.json` O arquivo tem três seções:

   1. **barras de ferramentas**: esta seção contém a definição de todos os recursos disponíveis na barra de ferramentas do editor, como Inserir/Remover lista numerada, \(arquivo\) Fechar, Salvar, Comentários e muito mais.

   1. **atalhos**: esta seção contém a definição de atalhos de teclado atribuídos a um recurso específico no editor.

   1. **modelos**: esta seção contém a estrutura predefinida de elementos DITA que podem ser usados no documento. Por padrão, a seção de modelos contém definições de modelo para um parágrafo, tabela simples, tabela e elementos de corpo. É possível criar uma definição de modelo para qualquer elemento adicionando uma estrutura XML válida para o elemento desejado. Por exemplo, se você deseja adicionar um `p` elemento a cada novo `li` em uma lista, é possível adicionar o seguinte código ao final da seção templates para fazer isso:

   ```css
   "li": "<li><p></p></li>"
   ```

1. Na seção de barras de ferramentas, remova a entrada do recurso que você não deseja expor aos usuários.

1. Salve o *ui\_config.json* e recarregar o Editor da Web.


**Tópico pai:**[ Personalizar editor da Web](conf-web-editor.md)
