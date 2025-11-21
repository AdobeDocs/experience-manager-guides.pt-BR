---
title: Personalizar barra de ferramentas
description: Saiba como personalizar a barra de ferramentas
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 0%

---

# Personalizar barra de ferramentas {#id172FB00L0V6}

Por padrão, o Editor da Web é fornecido com os recursos editoriais mais comuns exigidos por qualquer editor DITA. Recursos como inserir elementos da lista de tipos \(numerada ou com marcadores\), referência cruzada, referência de conteúdo, tabela, parágrafo e formatação de caracteres estão disponíveis no editor. Além desses elementos básicos, você pode personalizar o Editor da Web para inserir elementos usados no seu ambiente de criação.

>[!NOTE]
>
> Ao migrar da interface antiga para a nova interface do AEM Guides (aplicável a partir das versões 2502 e 5.0 do AEM Guides), as atualizações do `ui_config` devem ser convertidas em configurações de interface mais flexíveis e modulares. Essa estrutura ajuda a adotar alterações facilmente na editor_toolbar e em outro widget do target, conforme aplicável. Para obter detalhes, consulte [Visão geral da configuração da interface de conversão](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

Há duas maneiras de personalizar a barra de ferramentas do Editor da Web:

- Adicionar uma nova funcionalidade à barra de ferramentas
- Remover qualquer funcionalidade existente da barra de ferramentas


## Adicionar um recurso na barra de ferramentas

Adicionar uma funcionalidade ao Editor da Web envolve duas tarefas principais: adicionar um ícone para o recurso no arquivo *ui\_config.json* e adicionar a funcionalidade em segundo plano no JavaScript.

Execute as seguintes etapas para adicionar um recurso à barra de ferramentas do Editor da Web:

1. Para baixar o arquivo de configuração da interface do usuário, faça logon no Adobe Experience Manager como administrador.

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior
1. Clique no ícone **Baixar** para baixar o arquivo ui\_config.json em seu sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.
1. No arquivo `ui_config.json`, adicione a definição do novo recurso na seção de barras de ferramentas. Salve o arquivo e faça upload dele.

   Normalmente, você pode criar um novo grupo de botões da barra de ferramentas e adicionar um ou mais botões da barra de ferramentas a ele. Ou você pode adicionar um novo botão de barra de ferramentas em um grupo existente. Os detalhes a seguir são necessários para criar um novo grupo de barras de ferramentas:

   **tipo**:   Especifique `blockGroup` como o valor `type`. Esse valor indica que você está criando um grupo de blocos que conteria um ou mais grupos da barra de ferramentas.

   **classe_de_extração**:   Nome da classe ou classes separadas por espaço.

   **itens**:   Especifique a definição de todos os grupos na barra de ferramentas. Cada grupo pode conter um ou vários ícones da barra de ferramentas. Para definir ícones em um grupo de barras de ferramentas, você precisa definir novamente o atributo `type` em `items` e definir seu valor como `buttonGroup`. Especifique um ou mais nomes de classe na propriedade `extraclass`. Especifique o nome do recurso na propriedade `label`. O trecho a seguir do arquivo `ui_config.json` mostra a definição do bloco da barra de ferramentas principal, seguida pela definição `buttonGroup`:

   ```
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

   Na coleção `items`, é necessário especificar a definição de um ou mais ícones da barra de ferramentas.

   É necessário definir as seguintes propriedades para adicionar um ícone da barra de ferramentas:

   **tipo**:   Especifique `button` como o valor `type`. Esse valor indica que você está adicionando um botão da barra de ferramentas.

   **ícone**:   Especifique o nome do ícone Coral que deseja usar na barra de ferramentas.

   **variante**:   Especifique `quiet` como o valor `variant`.

   **título**:   Especifique a dica de ferramenta do ícone.

   **ao clicar**:   Especifique o nome do comando definido para o recurso no arquivo JavaScript. Se o comando exigir parâmetros de entrada, especifique o nome do comando como:

   ```Javascript
   "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
   ```

   **mostrar ou ocultar**:   Se você estiver definindo a propriedade `show`, especifique os modos nos quais o ícone será exibido. Os valores possíveis são - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(exibir em todos os modos\), ou `false` \(ocultar em todos os modos\).

   No lugar de `show`, você também pode definir a propriedade `hide`. Os valores possíveis são os mesmos da propriedade `show` com a única diferença de que o ícone não é exibido para o modo especificado.

   O exemplo a seguir mostra o número da versão do AEM Guides quando o usuário clica no ícone Mostrar versão na barra de ferramentas.

   Adicione o seguinte código a um arquivo do JavaScript:

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

   Adicione o recurso no arquivo *ui\_config.json* como:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Crie uma pasta *clientlib* e adicione seu JavaScript a essa pasta.

1. Atualize a propriedade categories da pasta *clientlib* atribuindo o valor de *apps.fmdita.xml\_editor.page\_overrides*.

1. Salve o arquivo *ui\_config.json* e recarregue o Editor da Web.


## Remover um recurso da barra de ferramentas

Às vezes, você pode não querer fornecer todos os recursos atualmente disponíveis no Editor da Web. Nesse caso, você pode remover o recurso indesejado da barra de ferramentas do Editor da Web.

Execute as seguintes etapas para remover qualquer recurso indesejado da barra de ferramentas:

1. Para baixar o arquivo de configuração da interface do usuário, faça logon no Adobe Experience Manager como administrador.

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior
1. Clique no ícone **Baixar** para baixar o arquivo ui\_config.json em seu sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.

   O arquivo `ui_config.json` tem três seções:

   1. **barras de ferramentas**:   Esta seção contém a definição de todos os recursos disponíveis na barra de ferramentas do editor, como Inserir/Remover lista numerada, \(arquivo\) Fechar, Salvar, Comentários e muito mais.

   1. **atalhos**:   Esta seção contém a definição de atalhos de teclado atribuídos a um recurso específico no editor.

   1. **modelos**:   Esta seção contém a estrutura predefinida de elementos DITA que você pode usar no documento. Por padrão, a seção de modelos contém definições de modelo para um parágrafo, tabela simples, tabela e elementos de corpo. É possível criar uma definição de modelo para qualquer elemento adicionando uma estrutura XML válida para o elemento desejado. Por exemplo, se você deseja adicionar um elemento `p` a cada novo elemento `li` em uma lista, é possível adicionar o seguinte código no final da seção de modelos para fazer isso:

   ```css
   "li": "<li><p></p></li>"
   ```

1. Na seção de barras de ferramentas, remova a entrada do recurso que você não deseja expor aos usuários.

1. Salve o arquivo *ui\_config.json* e recarregue o Editor da Web.


**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
