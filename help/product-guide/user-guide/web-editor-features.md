---
title: Conhecer os recursos do Editor da Web
description: Descubra os recursos do editor da Web em Guias do AEM. Conhecer a interface do editor da Web, incluindo a barra de ferramentas principal, a barra de ferramentas secundária, o painel esquerdo, a área de edição de conteúdo e o painel direito.
exl-id: 340cf72e-e44d-4df2-8312-50d00ac651b7
feature: Authoring, Features of Web Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '17364'
ht-degree: 0%

---

# Conhecer os recursos do Editor da Web {#id176NC500V5Z}

Esta seção aborda os vários recursos disponíveis no Editor da Web. Podemos dividir o Editor da Web nas seguintes seções ou áreas:

- [Barra de ferramentas principal](#id2051EA0G05Z)
- [Barra de ferramentas secundária](#id2051EA0J0Y4)
- [Painel esquerdo](#id2051EA0M0HS)
- [Área de edição de conteúdo](#id2051EB000UI)
- [Painel direito](#id2051EB003YK)

As subseções a seguir abordam em detalhes as várias seções do Editor da Web.

## Barra de ferramentas principal {#id2051EA0G05Z}

A barra de ferramentas principal está na parte superior da interface do Editor da Web e fornece recursos no nível do arquivo e vários modos de criação disponíveis no Editor da Web. Os recursos disponíveis na barra de ferramentas superior são explicados da seguinte maneira:

**Salvar tudo** - ![](images/SaveFloppy_icon.svg)

Salva as alterações feitas em todos os tópicos abertos. Se você tiver vários tópicos abertos no Editor da Web, clique em **Salvar tudo** ou usando o **Ctrl**+**S** as teclas de atalho salvam todos os documentos com um único clique. Não é necessário salvar cada documento individualmente.

>[!NOTE]
>
> A operação Salvar não cria uma nova versão dos tópicos. Para criar uma nova versão, escolha Salvar como nova versão.

**Salvar como nova versão** - ![](images/save-revision-icon.png)

Salva as alterações feitas no tópico e também cria uma nova versão do tópico. Se você estiver trabalhando em um tópico recém-criado, as informações da versão serão mostradas como **nenhum**.

![](images/save-all-first-version-none_cs.png){width="800" align="left"}

O número da versão é alterado com cada nova versão criada para o tópico ou arquivo de mapa.

Quando você opta por salvar um tópico ou mapa usando **Salvar como nova versão**, a seguinte caixa de diálogo será exibida:

![](images/save-as-new-version-dialog.PNG){width="300" align="left"}

Insira comentários e rótulos de versão para identificar as alterações e clique em **Salvar** para criar uma nova versão do arquivo.

Ao escolher a variável *Salvar como nova versão*, a primeira versão do tópico é criada no DAM, que também se torna a versão atualmente ativa do tópico. Posteriormente, se você reverter para uma versão mais antiga do tópico, essa será a versão ativa atual do tópico.

Se o administrador tiver rótulos de versão pré-configurados, você verá esses rótulos em uma lista suspensa. Você pode escolher um rótulo na lista de rótulos disponíveis e salvar seu documento.

![](images/web-editor-pre-defined-labels.PNG){width="300" align="left"}

Ao salvar um tópico, você pode adicionar um comentário especificando as alterações feitas no tópico. Este comentário é mostrado no Histórico de versão do tópico.

Se o tópico estiver sendo revisado, os revisores receberão uma notificação informando que uma versão mais recente do tópico está disponível. Eles podem acessar facilmente a última revisão do seu documento e continuar revisando a versão mais recente do seu tópico.

Ao passar o ponteiro sobre o título de um tópico, você verá o caminho do arquivo e o número da versão.

![](images/mouse-hover-on-title_cs.png){width="800" align="left"}

>[!NOTE]
>
> Quando uma versão do tópico estiver disponível, você também poderá adicionar rótulos a ele. Esses rótulos podem ser usados para criar uma linha de base para publicar uma versão específica do seu documento. Para obter mais informações sobre o uso de rótulos em seus tópicos, consulte [Usar rótulos](web-editor-use-label.md#).

**Desfazer e refazer** - ![](images/Undo_icon.svg) / ![](images/Redo_icon.svg)

Desfazer ou refazer a última ação.

**Excluir elemento** - ![](images/Delete_icon.svg)

Exclui o elemento atualmente selecionado ou o elemento no qual o cursor está posicionado.

**Localizar e substituir** - ![](images/FindAndReplace_icon.svg)

O recurso Localizar e substituir está disponível nos modos de exibição Autor e Fonte. A barra de texto Localizar e Substituir aparece na parte inferior da área de edição de tópico. Você pode usar as teclas de atalho **CTRL**+**F** para invocar a barra Localizar e Substituir.

![](images/find-replace-bar.png){width="800" align="left"}

Usando o ícone de configurações \(![](images/settings-find-replace-icon.svg)\), você poderá alternar a variável **Ignorar maiúsculas e minúsculas** e **Somente Palavra Inteira** opções de pesquisa. Para executar a pesquisa que não diferencia maiúsculas de minúsculas, ative \(ou selecione\) a **Ignorar maiúsculas e minúsculas** opção. Caso contrário, se você deseja executar a pesquisa que diferencia maiúsculas de minúsculas, desative \(ou desmarque\) a opção **Ignorar maiúsculas e minúsculas** opção. Você também pode optar por pesquisar uma palavra inteira.

A pesquisa é instantânea, o que significa que à medida que você digita a frase ou palavra de pesquisa na variável **Localizar** , o termo é imediatamente pesquisado e selecionado no tópico. Da mesma forma, para substituir um texto em seu tópico, insira o termo de pesquisa e sua substituição nos respectivos campos e clique no **Substituir** ou **Substituir tudo** botão.

Na visualização Código-fonte, Localizar e substituir é extremamente útil para procurar um elemento ou atributo específico. Por exemplo, se você deseja substituir o valor de `@product` atributo, isso pode ser feito facilmente na visualização Código-fonte. A visualização Autor não permite que você pesquise com base em um atributo ou elemento. No entanto, tenha cuidado ao usar o **Substituir tudo** recurso, pois pode substituir o código XML.

**Configurações do editor** - ![](images/editor_settings_icon.svg)

As Configurações do editor estão disponíveis somente para usuários administrativos. Usando as preferências, um administrador pode definir as seguintes configurações:

>[!NOTE]
>
> Se estiver atualizando qualquer configuração padrão, você deverá reabrir os documentos para que as alterações entrem em vigor.

- **Geral**: As configurações Gerais permitem configurar o dicionário a ser usado com o Editor da Web. Essa guia contém três seções: **Verificação ortográfica**, **Condição**, e **Criação**.

  ![](images/editor-setting-general.png){width="650" align="left"}

   - **Verificação ortográfica**: Há duas opções — **Verificação ortográfica do AEM** e **Verificação ortográfica do navegador**. Por padrão, o editor usa o recurso Verificação ortográfica do navegador, no qual a verificação ortográfica é executada usando o dicionário interno do navegador. Você pode alternar para Verificação ortográfica do AEM para usar o dicionário AEM, que também pode ser personalizado para adicionar sua lista de palavras personalizada. Para obter mais informações sobre a personalização do dicionário AEM, consulte *Personalizar dicionário padrão do AEM* na seção Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.


   - **Condição**

      - **Realçar Texto condicional na exibição Autor**: selecione essa opção para realçar o texto condicional na exibição do autor. O conteúdo condicional é realçado usando a cor definida para a condição.

      - **Validar com atributos de condição**: selecione essa opção para permitir a validação dos valores definidos para os atributos. Isso impede que você adicione qualquer valor incorreto.

      - **Mostrar a chave com o título no painel Assunto do esquema**: selecione esta opção para mostrar as chaves junto com os títulos no esquema de assunto. Se você não selecionar essa opção, somente os títulos serão exibidos. Por exemplo, aqui as chaves &quot;os&quot;, &quot;audience&quot; e &quot;other&quot; também são mostradas junto com títulos.

        ![](images/subject-scheme-title.png){width="550" align="left"}

      - **Mostrar esquema do assunto no painel Condições**: selecione esta opção para ver um esquema de assunto no painel condições. Se você desmarcar essa opção, as condições definidas serão mostradas no painel Condições.

   - **Criação**

      - **Ativar Substituir tudo**: Selecione essa opção para ver o ícone Substituir tudo no painel Localizar e Substituir.


   - **Citações**
Alterar o estilo das citações. Escolha o estilo da citação no menu suspenso que deseja usar em seu projeto. Para obter mais detalhes, consulte [Alterar estilos de citação](./web-editor-apply-citations.md#change-citation-style).


**Painéis**: essa configuração controla os painéis mostrados no painel esquerdo do editor. Você pode alternar o botão para mostrar ou ocultar o painel desejado.

![](images/editor-setting-panel.png){width="650" align="left"}

>[!NOTE]
>
> Se um painel personalizado tiver sido configurado, ele também aparecerá na lista de painéis. Você pode alternar o botão para mostrar ou ocultar o painel personalizado. Para obter mais detalhes sobre a configuração, consulte *Configurar um painel personalizado no painel esquerdo* na seção Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

- **Lista de elementos**: Como administrador, você pode controlar a lista de elementos que um autor pode inserir usando o [Inserir elemento](#id204SG30105Z) e também define o nome de exibição do elemento. A configuração Lista de elementos permite especificar o nome do elemento de acordo com as especificações DITA e um rótulo que você deseja usar em vez do nome do elemento definido por DITA:

  ![](images/editor-setting-element-list.png){width="650" align="left"}

Na captura de tela acima, a variável `b` elemento recebeu um rótulo de Negrito, `codeblock` O recebe um rótulo de Bloco de código junto com alguns outros elementos. Se você selecionar a variável **Usar somente os elementos acima** e, em seguida, somente os elementos válidos \(no ponto de inserção atual\) dessa lista serão exibidos na janela pop-up Inserir elemento.

Na captura de tela a seguir, apenas 3 dos 4 elementos configurados da captura de tela anterior são mostrados no contexto atual:

![](images/editor-setting-insert-element-list.PNG){width="300" align="left"}

- **Lista de atributos**: assim como a Lista de elementos, você pode controlar a lista de atributos e seus nomes de exibição a serem exibidos na lista de atributos de um elemento. Na captura de tela a seguir, apenas 3 atributos foram configurados para serem mostrados na lista de atributos de um elemento:

  ![](images/editor-setting-attributes-list.png){width="650" align="left"}

  Com essa configuração, ao tentar adicionar um atributo a um elemento, você verá apenas a lista de atributos configurados na lista.

  ![](images/editor-setting-add-attributes-list.png-to-element.PNG){width="300" align="left"}

- **Publicar perfil**: contém os Perfis de publicação que podem ser usados para publicar o **Knowledge base** saída. Você pode criar um novo perfil para uma base de dados de conhecimento de destino. Por exemplo, Salesforce ou ServiceNow.

   - **Criar um perfil de publicação do Salesforce**

     **Pré-requisitos**

      - Crie um aplicativo conectado para o Salesforce. Para obter mais detalhes, consulte [Habilitar configurações do OAuth para integração com a API](https://help.salesforce.com/s/articleView?id=sf.connected_app_create_api_integration.htm&amp;type=5).

      - Ao configurar o aplicativo conectado, verifique o seguinte:

         - Especifique o retorno de chamada.

           `URL: http://<server name>:<port>/bin/dxml/thirdparty/callback/salesforce`

         - Selecione os seguintes escopos do OAuth:
            - Acesso total (total)
            - Selecione Gerenciar dados do usuário por meio das APIs (api)

  Depois que o aplicativo é configurado, o Salesforce fornece uma **Chave do consumidor** e **Segredo do consumidor**.

  Eles podem ser usados para criar o Perfil de publicação do Salesforce.


   - Para criar um Perfil de publicação do Salesforce, selecione **Salesforce** Base de conhecimento da **Tipo de servidor** lista suspensa. Insira um Nome de perfil. No **URL do site**, insira o site do consumidor que você usaria para publicar a saída e adicionar o **Chave do consumidor** e **Segredo do consumidor** fornecido pelo site do consumidor do Salesforce. Em seguida, **Validar** e **Salvar** o perfil recém-criado.
     ![perfil de publicação do salesforce nas configurações do editor](./images/salesforce-publish-profile.png){width="550" align="left"}

     >[!NOTE]
     >
     >Para configurar um proxy para o Salesforce nos Guias do Experience Manager, use a Configuração de proxy dos componentes HTTP do Apache no AEM. Saiba como [configurar proxy para o Verificador de links AEM](https://helpx.adobe.com/experience-manager/kb/How-to-configure-proxy-for-the-AEM-Link-Checker-AEM.html).


   - **Criar um perfil de publicação do ServiceNow**

     **Pré-requisitos**

     Configure o servidor ServiceNow para fazer upload dos ativos.
      - Conecte-se à **ServiceNow** servidor.
      - Navegue até **Propriedades do sistema** > **Segurança**.
      - Desmarque a seguinte opção:

        **Essa propriedade deve ser definida para ativar a verificação de tipo MIME para uploads (Todas as versões Eureka e superior). Ativa (true) ou desativa (false) a validação do tipo MIME para os anexos de arquivo. Extensões de arquivo configuradas via glide.attachment.extensions serão verificadas em busca de tipo MIME durante o upload.**

      - Clique em **Salvar**.

     Depois de configurar o aplicativo, crie o **ServiceNow** Perfil de publicação.
   - Para criar um Perfil de publicação, selecione a Base de conhecimento ServiceNow na **Tipo de servidor** lista suspensa. Inserir um perfil **Nome**. No **URL do ServiceNow**, insira o site do consumidor que você usaria para publicar a saída e, em seguida, adicione o **Nome de usuário** e **Senha** fornecido pelo site do consumidor ServiceNow. Em seguida, **Validar** e **Salvar** o perfil recém-criado.

     ![Perfil de publicação do ServiceNow](./images/service-now-publish-profile.png){width="550" align="left"}

  Depois de validar, é possível selecionar o Perfil de publicação nas predefinições de saída de um Mapa DITA e usá-lo para gerar a saída para o  **Salesforce** ou **ServiceNow** servidor que você escolheu.

  Saiba mais sobre o [Knowledge base](../user-guide/generate-output-knowledge-base.md) de saída.


- **Validação**: esta guia contém opções para configurar as Validações de Schematron no editor da Web. Você pode ativar os seguintes recursos:

   - **Executar verificação de validação antes de salvar o arquivo**: selecione esta opção para executar validações do Schematron usando os arquivos do Schematron selecionados antes de qualquer operação de salvamento. Você pode adicionar um arquivo do Schematron clicando no ícone +. Os arquivos do Schematron selecionados são listados.

     >[!NOTE]
     >O(s) arquivo(s) de esquema selecionado(s) persistirá(ão) no perfil de pasta selecionado.

     ![Validação nas configurações do editor](./images/editor-setting-validation.png){width="550" align="left"}
Isso impede que os usuários salvem qualquer arquivo que quebre uma regra definida no(s) arquivo(s) selecionado(s) do Schematron. Se esta opção não estiver selecionada, o arquivo não será validado antes de salvar as alterações.

   - **Permitir que todos os usuários adicionem arquivos de esquemas no painel de validação**: selecione essa opção para permitir que os usuários adicionem qualquer arquivo do Schematron no painel Validação do Editor da Web. Isso permite que os usuários adicionem arquivos do Schematron e, em seguida, validem os tópicos em relação ao arquivo Schematron. Se essa opção não estiver selecionada, a variável **Adicionar arquivo de esquema** O botão não está disponível para os usuários na **Painel de validação** do Editor da Web.


- **Atributos de exibição**: Assim como a Lista de atributos, você pode controlar a lista de atributos a serem exibidos na lista de atributos de um elemento. Por padrão, quatro **Atributos de exibição** — o público-alvo, a plataforma, o produto e as props foram configurados para serem exibidos na lista de atributos de um elemento. Também é possível adicionar um atributo de exibição usando a variável **Adicionar** ícone na parte superior. Também é possível excluir qualquer um dos atributos de exibição usando o **Excluir** ícone.

  Os atributos definidos para um elemento são exibidos na exibição Layout e Estrutura de Tópicos.

  ![](images/editor-settings-display-attributes.png){width="550" align="left"}

- **Tradução**: Esta guia contém a opção para propagar os labels de origem para a versão de destino.

   - **Propagar rótulos de versão de origem para a versão de destino**: selecione essa opção para passar o rótulo da versão do arquivo de origem para o arquivo traduzido. Por padrão, está desativado.

  ![](images/editor-setting-translation.png){width="550" align="left"}


**Preferências do usuário** - ![](images/user_preference_editor_icon.svg)

As Preferências do usuário estão disponíveis para todos os autores. Usando as preferências, um autor pode definir as seguintes configurações:

![](images/user_preference_editor.PNG){width="550" align="left"}

- **Usar tema do dispositivo**: marque essa caixa de seleção para permitir que Guias do AEM alternem automaticamente entre temas claros e escuros com base no tema do seu dispositivo.

- **Exibir arquivos por**: selecione a maneira padrão de exibir os arquivos no Editor da Web. Você pode visualizar a lista de arquivos pelos títulos ou pelos nomes de arquivos dos vários painéis no **Autor** exibição.
  >[!NOTE]
  >
  > Por padrão, os arquivos são exibidos por título no Editor da Web.

- **Tema**: Você pode escolher entre os temas Claro, Mais claro, Escuro ou Mais escuro do editor. No caso do tema Mais claro, as barras de ferramentas e os painéis usam um plano de fundo de cor cinza mais claro. No caso do tema claro, as barras de ferramentas e os painéis usam o plano de fundo cinza-claro. No caso do tema Mais escuro, as barras de ferramentas e os painéis usam um plano de fundo de cor preta mais escuro. No caso do tema Escuro, as barras de ferramentas e os painéis usam o plano de fundo preto. Em todos os temas, a área de edição de conteúdo é mostrada em fundo branco.

- **Perfis de pasta**: o Perfil de pasta controla várias configurações relacionadas a atributos condicionais, modelos de criação, predefinições de saída e configurações do Editor da Web. O Perfil global é exibido por padrão. Além disso, se o administrador tiver configurado perfis de pastas no sistema, esses perfis de pastas também serão mostrados na lista Perfis de pastas.

  As configurações do Editor da Web que um administrador pode definir no perfil da pasta incluem: personalização da interface do usuário, incluindo ícones da barra de ferramentas, layout do Editor da Web, trechos e mapa raiz. Para obter mais detalhes, consulte *Configurar perfis globais ou de nível de pasta* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

  >[!NOTE]
  >
  > O nome do Perfil de pasta atual é exibido como um rótulo para o ícone Preferências do usuário na barra de ferramentas principal.

- **Caminho base**: por padrão, ao acessar o repositório AEM no Editor da Web, você verá os ativos no local /content/dam. Sua pasta de trabalho provavelmente seria algumas pastas dentro da pasta /content/dam/. Você levaria alguns cliques para acessar a pasta de trabalho todas as vezes. Você pode definir o Caminho base para sua pasta de trabalho e a Visualização do repositório, em seguida, mostra o conteúdo desse local antecipadamente. Isso reduz o tempo de acesso à pasta de trabalho. Além disso, quando você insere qualquer referência ou arquivo de mídia no tópico, o local de navegação do arquivo começa com a pasta definida no Caminho base.

- **Selecionar mapa raiz**: selecione um arquivo de mapa DITA para resolver referências principais ou entradas de glossário. O mapa raiz selecionado tem a precedência mais alta para resolver referências principais. Para obter mais detalhes, consulte [Resolver referências de chave](map-editor-other-features.md#id176GD01H05Z).

>[!NOTE]
> 
> Se não quiser usar nenhum mapa raiz, verifique se **Selecionar mapa raiz** está em branco.

**Modos Autor, Origem e Visualização**

Para obter detalhes sobre os vários modos de criação e exibição de documentos, consulte [Visualizações do Editor da Web](web-editor-views.md#).

## Barra de ferramentas secundária {#id2051EA0J0Y4}

A barra de ferramentas secundária é exibida quando você abre um tópico para edição no Editor da Web. Os recursos disponíveis na barra de ferramentas secundária são explicados da seguinte maneira:

**Inserir elemento** - ![](images/Add_icon.svg)

Insere um elemento válido no local válido atual ou próximo. Se você estiver trabalhando dentro de um elemento de bloco como um `note`, em seguida, use o ícone Inserir elemento para inserir um novo elemento após a variável `note` elemento. Na captura de tela a seguir, um elemento de nota foi inserido no elemento p \(parágrafo\):

![](images/note-in-para-insert-element_cs.png){width="800" align="left"}

Se você pressionar Enter no elemento de nota, um novo parágrafo será criado dentro do próprio elemento de nota. Para inserir um novo elemento fora da observação, clique no elemento p \(destacado na captura de tela\) na navegação estrutural dos elementos e clique no ícone Inserir elemento ou pressione ***Alt***+***Enter*** para abrir o pop-up Inserir elemento. Em seguida, selecione o elemento desejado e pressione Enter para inserir o elemento selecionado após o elemento de nota.

Você também pode adicionar um elemento entre dois elementos quando um cursor de bloco intermitente é exibido.

![](images/Block-cursor.png){width="300" align="left"}

Por exemplo, se você estiver trabalhando em um tópico DITA e o cursor de bloco estiver piscando entre a descrição curta e o corpo, é possível adicionar `prolog` elemento e, em seguida, adicione copyright, autor e outros detalhes.

Outra maneira de inserir o novo elemento é usando o menu de contexto. Clique com o botão direito do mouse em qualquer lugar do documento para chamar o menu de contexto. Nesse menu, escolha Inserir elemento para exibir a caixa de diálogo Inserir elemento e escolha o elemento que deseja inserir.

![](images/insert-element-before-after.png){width="300" align="left"}

**Inserir parágrafo** - ![](images/Paragraph_icon.svg)

Inserir elemento de parágrafo no local válido atual ou próximo.

**Inserir/Remover Lista Numerada** - ![](images/TextNumbered_icon.svg)

Cria uma lista numerada no local válido atual ou próximo. Se você estiver em uma lista numerada e clicar nesse ícone, o item será convertido em um parágrafo normal.

**Inserir/Remover Lista com Marcadores** - ![](images/BulletList_icon.svg)

Cria uma lista com marcadores no local válido atual ou próximo. Se você estiver em uma lista com marcadores e clicar nesse ícone, o item será convertido em um parágrafo normal.

**Inserir tabela** - ![](images/Table_icon.svg)

Insere uma tabela no local válido atual ou próximo. Clique no ícone Inserir tabela para abrir a caixa de diálogo Inserir tabela:

![](images/table-properties.png){width="550" align="left"}

Você pode especificar o número de linhas e colunas necessárias na tabela. Para manter a primeira linha como cabeçalho da tabela, selecione a opção Definir primeira linha como cabeçalho. Para adicionar um título à tabela, insira-o no campo Title.

Depois que uma tabela é inserida, você pode modificar a tabela usando o menu de contexto.

![](images/table-context-menu_cs.png){width="550" align="left"}

Usando o menu de contexto da tabela, você pode:

- Inserir células, linhas ou colunas

- Mesclar células nas direções direita e abaixo

- Dividir células horizontalmente ou verticalmente

- Excluir células, linhas ou colunas

- Criar um trecho da tabela

- Gerar IDs


Você também pode definir atributos em várias células, linha inteira ou coluna de uma tabela. Por exemplo, para alinhar a célula da tabela, arraste e selecione a célula necessária. No painel Propriedades de conteúdo (à direita), a propriedade **Tipo** alterações em **Múltiplas entradas**.

1. No **Atributos** clique em **+Adicionar**.
1. Selecione o `@valign` atributo do **Atributo** lista suspensa.
1. Na lista suspensa de valores, selecione o alinhamento de texto desejado que deseja aplicar às células selecionadas da tabela.
1. Clique em **Adicionar.**

![](images/align-table-cell_cs.png){width="800" align="left"}

**Inserir imagem** - ![](images/Image_icon.svg)

Insere uma imagem no local válido atual ou próximo. Clique no ícone Inserir imagem para abrir a caixa de diálogo Inserir imagem e, em seguida, pesquise e selecione a imagem que deseja inserir.

>[!NOTE]
>
> Você também pode adicionar uma imagem arrastando-a e soltando-a do seu sistema local no seu artigo. Nesse caso, o arquivo de imagem é adicionado usando o **Fazer upload de ativos** fluxo de trabalho.  Para obter mais detalhes, consulte **Fazer upload de ativos** fluxo de trabalho no [Painel esquerdo](web-editor-features.md#id2051EA0M0HS) seção.


![](images/insert-image.png){width="650" align="left"}

Você pode adicionar título de imagem/Figura e texto alternativo para a imagem na caixa de diálogo Inserir imagem.

Você pode pesquisar o arquivo de imagem desejado inserindo o nome do arquivo na barra Tipo a Pesquisar na parte superior e também filtrar os resultados da pesquisa por Caminho \(para pesquisar em\), Coleções, Tipo de arquivo e Tags. Depois de encontrar o arquivo de imagem necessário, selecione-o e clique em Selecionar para inserir a imagem no documento. É possível inserir vários formatos de arquivos de imagem, como `.png`, `.svg`, `.gif`, `.jpg`, `.eps`, `.ai`, `.psd`e muito mais.

Depois de inserir uma imagem, você pode alterar a altura, a largura, a disposição e os atributos no painel Propriedades de conteúdo. Clique em um arquivo de imagem e faça alterações no painel Propriedades de conteúdo no painel direito.

![](images/image-properties.png){width="800" align="left"}

O campo Origem exibe a UUID do arquivo de imagem inserido. Você pode encontrar o caminho completo do arquivo de imagem inserido passando o ponteiro do mouse sobre o campo Origem. O caminho é exibido na dica de ferramenta.

Você pode redimensionar uma imagem fornecendo o valor de Altura ou Largura para o arquivo de imagem. A proporção da imagem é mantida automaticamente. Se desejar, também é possível optar por não manter a proporção do arquivo de imagem clicando no ícone de cadeado \(de Manter proporção\) e fornecendo valores de Altura e Largura.

Você também pode especificar a configuração de Posicionamento para a imagem como Em linha ou Quebra. Caso opte por usar a opção Inserção de quebra, é possível escolher onde alinhar a imagem (esquerda, centro ou direita).

Você também pode adicionar outras propriedades para um arquivo de imagem selecionando as propriedades necessárias na **Atributos** campo.

>[!NOTE]
>
>Você também pode definir áreas clicáveis \(mapa de imagem\) na sua imagem. Para obter mais detalhes, consulte **Inserir/Editar mapa de imagem** descrição do recurso na [Painel esquerdo](web-editor-features.md#id2051EA0M0HS) seção.

**Menu de contexto para arquivos de imagem ou mídia**

Também é possível executar algumas operações comuns para imagens e arquivos de mídia usando o menu de contexto. Clique com o botão direito do mouse em qualquer lugar na imagem para chamar o menu de contexto.

O menu de contexto fornece opções para recortar, copiar ou colar a imagem ou mídia. Você pode inserir um elemento antes ou depois do elemento selecionado. Você também tem a opção de renomear ou decodificar um elemento. Você pode localizar a imagem ou mídia selecionada no repositório ou visualizar o arquivo na interface do usuário do Assets.

As outras opções no menu de contexto permitem copiar o caminho, editar um mapa de imagem, criar um trecho ou gerar IDs para o elemento selecionado.

**Inserir multimídia** - ![](images/insert-multimedia-icon.svg)

Insere diferentes tipos de arquivos multimídia. Clique no ícone Inserir multimídia e escolha o tipo de arquivo que deseja inserir. Os formatos de multimídia compatíveis são:

- Arquivo de áudio
- Arquivo de vídeo
- YouTube
- Vimeo

Ao selecionar a opção de arquivo de Áudio ou Vídeo, você verá a exibição de repositório para procurar e selecionar o arquivo desejado. Se você escolher YouTube ou Vimeo, você obterá a caixa de diálogo Inserir multimídia. Cole o link do arquivo de vídeo no campo Link da Web e clique em Inserir para adicionar o vídeo no local válido atual ou próximo no documento.

>[!NOTE]
>
> Ao adicionar um link de vídeo do YouTube, é necessário substituir a string `watch?v=` com `embed` no URL. Por exemplo, para adicionar um link de vídeo do YouTube: `https://www.youtube.com/**watch?v**=WlIKQOrmZcs`, é necessário adicioná-lo como: `https://www.youtube.com/**embed/**WlIKQOrmZcs`. Essa alteração garante que o vídeo seja incorporado na saída do site e PDF AEM.

Você poderá também adicionar o Arquivo de Áudio ou Vídeo a partir da janela Inserir Multimídia. Selecione a opção Arquivo de áudio/vídeo e clique no ícone de procura para iniciar a visualização de repositório. Selecione o arquivo de áudio ou vídeo do repositório e clique em Selecionar para adicionar o link do arquivo no campo Arquivo de áudio/vídeo. Caso escolha um arquivo de vídeo, uma pré-visualização do arquivo também é mostrada na área Pré-visualização. Você pode reproduzir o arquivo de vídeo para visualizá-lo.

![](images/insert-multimedia.png){width="650" align="left"}

**Inserir Referência Cruzada** - ![](images/Reference_icon.svg)

Inserir referências do tipo — Referência de conteúdo, Referência de chave de conteúdo, Referência de chave, Referência de arquivo, Link da Web ou Link de email.

Clique em **Selecionar arquivo** ícone \(para Referência de conteúdo e Referência de arquivo\) ou **Selecionar mapa** ícone \(para Referência de chave de conteúdo e Referência de chave\) e selecione o arquivo ou conteúdo desejado para vincular.

![](images/insert-references.png){width="650" align="left"}

Um link da referência selecionada é adicionado no documento. O menu de contexto no link fornece as opções para:

- **Inserir elemento**: mostra uma lista de elementos válidos que você pode inserir no contexto fornecido.
- **Copiar UUID**: copia a UUID da referência inserida.
- **Copiar caminho**: copia o caminho completo da referência inserida.
- **Criar trecho**: cria um trecho reutilizável da referência inserida.
- **Gerar IDs**: gera um identificador exclusivo para a referência inserida.

Também é possível pesquisar usando a UUID do arquivo que você deseja referenciar. Para links de Referência de Conteúdo e Chave, insira a UUID do arquivo ao qual deseja vincular e o arquivo é automaticamente pesquisado e exibido na seção Visualizar. Ao especificar a UUID do arquivo, você não precisa mencionar explicitamente a extensão de arquivo para arquivos .xml. A extensão .xml é anexada automaticamente ao UUID.

![](images/insert-content-using-uuid-search.png){width="650" align="left"}

Se o administrador tiver ativado a opção UUIDs no *XMLEditorConfig*, você verá a UUID do conteúdo referenciado na variável **Link** propriedade.

![](images/ref-link-uuid_cs.png){width="800" align="left"}

>[!NOTE]
>
> Se a variável **Habilitar UUIDs** não estiver ativada, o caminho relativo do conteúdo referenciado será mostrado.

>[!IMPORTANT]
>
> Mesmo que o caminho relativo do conteúdo referenciado seja mostrado na variável **Link** internamente, o link é criado usando a UUID do conteúdo referenciado.

>[!TIP]
>
> Consulte a seção Referências no guia de Práticas recomendadas para obter as práticas recomendadas sobre a referência de conteúdo.

**Filtrar pesquisa**

Você pode procurar algum texto nos arquivos presentes no caminho selecionado do repositório AEM. Por exemplo, é feita uma pesquisa de &quot;geral&quot; na captura de tela a seguir. Também é possível restringir sua pesquisa usando filtros aprimorados. Você pode procurar todos os arquivos DITA como Tópicos DITA e Mapas DITA presentes no caminho selecionado.

Você pode pesquisar arquivos não DITA como arquivos de imagem, multimídia e documentos no caminho selecionado. Também é possível pesquisar valores específicos nos atributos de elementos DITA. Você também pode procurar arquivos cujo check-out tenha sido feito pelo usuário especificado.

![](images/reference-search-filters.png){width="650" align="left"}

>[!NOTE]
>
> O administrador do sistema também pode configurar os filtros de texto e mostrar ou ocultar outros filtros. Para obter mais detalhes, consulte a seção Configurar filtros de texto em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

A lista de arquivos filtrados que contém o texto pesquisado é exibida. Por exemplo, na captura de tela acima, os arquivos que contêm o texto &quot;geral&quot; são listados. Você também pode visualizar o conteúdo do arquivo.

**Inserir conteúdo reutilizável** - ![](images/content-reuse-icon.svg)

Reutilize o conteúdo que existe em qualquer outro documento no seu projeto. É possível inserir conteúdo vinculando diretamente ao conteúdo em um arquivo ou usando uma referência de chave, consulte [Resolver referências de chave](map-editor-other-features.md#id176GD01H05Z). Ao clicar no ícone Inserir conteúdo reutilizável, você obtém a caixa de diálogo Reutilizar conteúdo:

![](images/reuse-content-dialog.png){width="650" align="left"}

Na caixa de diálogo Reutilizar conteúdo, selecione o arquivo DITA para referências de arquivo ou o arquivo de mapa DITA que contém as referências principais. Depois de selecionada, o tópico ou as referências de chave são mostrados na caixa de diálogo. Você pode selecionar a ID/chave do tópico que deseja inserir e clicar em Concluído para inserir o conteúdo no seu tópico.

Para inserir a Referência de conteúdo, você também pode inserir a UUID do arquivo e o conteúdo reutilizável desse arquivo é listado na seção Visualizar.

Com base na configuração para inserir links, você pode ver a UUID do conteúdo inserido ou o caminho relativo no painel Propriedades ou na visualização Código-fonte. O link é sempre criado usando a UUID do conteúdo referenciado. Consulte Configurar links baseados em UUID na seção Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

>[!NOTE]
>
> Para adicionar conteúdo antes ou depois do conteúdo referido, use *Alt*+*Esquerda* Seta ou Alt+*Direita* Teclas de seta para mover o cursor para o local desejado.

Também é possível incorporar o conteúdo referenciado no tópico clicando com o botão direito do mouse no conteúdo referido e escolhendo **Substituir referência pelo conteúdo** no menu de contexto.

**Inserir caracteres especiais** -  ![](images/insert-special-chars-icon.svg)

Insere caracteres especiais no tópico. Clique no ícone Inserir caractere especial para abrir a caixa de diálogo Inserir caractere especial.

>[!NOTE]
>
> As Guias do AEM fornecem caixas de diálogo móveis e redimensionáveis. As caixas de diálogo que têm duas linhas cruzadas no canto inferior direito podem ser redimensionadas. As linhas cruzadas na caixa de diálogo Caractere especial são mostradas abaixo.

![](images/insert-special-char.png){width="550" align="left"}

Na caixa de diálogo Inserir caractere especial, você pode procurar um caractere especial usando seu nome. Todos os caracteres especiais são armazenados em várias categorias. Use a lista suspensa Selecionar categoria e selecione uma categoria. Os caracteres especiais disponíveis na categoria selecionada são exibidos. Você pode navegar pela lista de caracteres especiais usando as teclas de seta ou clicar no caractere desejado que deseja inserir. O Nome e o Código hexadecimal do caractere especial selecionado são exibidos abaixo da lista. Clique em Inserir para inserir o caractere selecionado no documento.

**Inserir palavra-chave** - ![](images/Keyword_icon.svg)

Inserir palavra-chave definida no mapa DITA. Clique no ícone Inserir palavra-chave para abrir a caixa de diálogo Referência de chave.

![](images/insert-keyword.png){width="550" align="left"}

As palavras-chave são listadas em ordem alfabética e você também pode pesquisar palavras-chave\(s\) digitando uma string de pesquisa na caixa Pesquisar. O resultado da pesquisa retornará as palavras-chave que contêm a cadeia de caracteres em ID ou Valor. As palavras-chave definidas no mapa DITA são listadas nesta caixa de diálogo. Escolha a palavra-chave que deseja inserir e clique em **Inserir**.

Você também pode alterar os atributos da palavra-chave inserida clicando com o botão direito do mouse na palavra-chave e selecionando a opção Atributos. A caixa de diálogo Atributos para palavra-chave é aberta:

![](images/attributes-for-keyword.png){width="550" align="left"}

Você pode alterar os atributos da palavra-chave ou adicionar um novo atributo à palavra-chave.

**Inserir trecho** - ![](images/insert-snippet-icon.svg)

Insira um trecho no local válido atual ou seguinte. Para que esse recurso funcione, você deve ter os snippets definidos no sistema. Para obter mais informações sobre como adicionar um trecho, consulte a **Trecho** descrição do recurso na [Painel esquerdo](web-editor-features.md#id2051EA0M0HS) seção.

Ao clicar no ícone Inserir trecho, você verá o catálogo Inserir trecho. O catálogo é sensível ao contexto, o que indica que exibirá os trechos somente se forem permitidos no local atual.

O exemplo a seguir mostra dois trechos pré-configurados - Aviso e Erro que podem ser inseridos no local atual no documento.

![](images/insert-snippet.png){width="300" align="left"}

Quando você escolhe um trecho na lista, ele é inserido no local válido atual ou próximo no documento. A captura de tela a seguir mostra o trecho de erro inserido no documento:

![](images/error-snippet.png){width="400" align="left"}

**Inserir/Editar mapa de imagem** - ![](images/imagemap-rectangle.svg)

Insere um mapa de imagem na imagem selecionada. Uma imagem com áreas clicáveis que se vinculam a tópicos ou páginas da Web é chamada de mapa de imagem.

Selecione uma imagem no tópico atual e clique no ícone Inserir/Editar mapa de imagem para abrir a caixa de diálogo Inserir mapa de imagem.

![](images/insert-image-map.png){width="650" align="left"}

Escolher a forma preferida Retângulo ![](images/imagemap-rectangle-toolbar.png), Círculo ![](images/imagemap-circle-toolbar.png), ou Polígono ![](images/imagemap-polygon-toolbr.png) para definir uma área sobre uma imagem que você deseja usar como link. Depois de definir uma área, a caixa de diálogo Referência é exibida, onde é necessário especificar o link para conteúdo interno ou externo:

![](images/reference-dialog.png){width="650" align="left"}

Se houver sobreposição de áreas, você poderá trazer a forma para frente ou enviá-la para trás clicando no respectivo ícone na barra de ferramentas. Você também pode remover uma área selecionando-a e clicando no ícone Excluir. Clicar duas vezes em uma área abre a caixa de diálogo Referência, na qual é possível alterar o link de destino. Depois de marcar as áreas necessárias na imagem, salve as alterações clicando em Concluído.

**Check-out/Check-in** - ![](images/LockClosed_icon.svg)/ ![](images/LockOpen_icon.svg)

Faz check-out ou check-in do arquivo atual. Ao fazer check-out de um arquivo, o usuário obtém acesso exclusivo de gravação ao arquivo. Quando o check-in do arquivo é feito, as alterações são salvas na versão atual do arquivo.

Se você estiver na Exibição de mapa e expandir o mapa principal, poderá fazer check-out de todos os arquivos no mapa com um único clique. Basta expandir o arquivo de mapa principal e selecionar o arquivo principal, o que resulta na seleção de todos os arquivos no mapa. Em seguida, você pode selecionar **Confira**  ![](images/LockClosed_icon.svg) para bloquear todos os arquivos no mapa.

>[!NOTE]
>
> Ao fazer check-in de um arquivo que tenha alterações não salvas, ele solicita que você salve as alterações. Se você não salvar as alterações, ele só fará o check-in do arquivo.

A dica de ferramenta do Check-in/Check-out é determinada pela propriedade do título no campo `ui_config.json` arquivo.

Para obter mais detalhes, consulte [Configurar o título para os ícones Fazer check-in e Check-out](../install-guide/conf-checkin-checkout-title.md) no Guia de instalação e configuração no local.


**Alternar exibição de tags** - ![](images/Label_icon.svg)

Tags são dicas visuais que indicam os limites de um elemento. Um limite de elemento marca o início e o fim de um elemento. Em seguida, você pode usar esses limites como uma dica visual para colocar o ponto de inserção ou selecionar o texto dentro de um limite. Se quiser inserir outro elemento antes ou depois de um elemento no documento, você pode colocar o ponto de inserção antes ou depois do limite de abertura ou fechamento do elemento.

A captura de tela a seguir mostra um documento com a Exibição de tags em:

![](images/tags-view.png){width="650" align="left"}

As seguintes operações podem ser executadas em um documento com a Exibição de tags em:

- **Selecionar um elemento**: clique na tag de abertura ou fechamento de um elemento para selecionar seu conteúdo.

- **Expandir ou recolher tags**: Clique no sinal + ou - em uma tag para expandi-la ou recolhê-la.

- **Usar o menu de contexto**: o menu de contexto fornece opções para recortar, copiar ou colar o elemento selecionado. Também é possível inserir um elemento antes ou depois do elemento selecionado. As outras opções permitem Gerar ID ou abrir o painel Propriedades do elemento selecionado.

- **Arrastar e soltar elementos**: selecione a tag de um elemento e arraste-a e solte-a facilmente no documento. Se o local de destino for um local válido onde o elemento é permitido, o elemento será colocado no local de destino.


>[!NOTE]
>
> Se um usuário ativar a Exibição de tags no Editor da Web, ela permanecerá ativada mesmo nas sessões. Isso significa que não é necessário ativar a Exibição de tags novamente para acessá-la posteriormente. O valor padrão para a Exibição de tags para a sessão de um novo usuário é determinado pela propriedade tagsView no arquivo ui\_config.json. Para obter mais detalhes, consulte *Configurar valor padrão para a exibição de tags* seção em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

**Ativar/desativar o controle de alterações** ![](images/track-change-icon.svg)

Você pode controlar todas as atualizações feitas em um documento ativando o modo Controlar alterações. Depois de ativar o controle de alterações, todas as inserções e exclusões são capturadas no documento. Todo o conteúdo excluído é realçado usando Tachado e todas as inserções são realçadas em texto de cor verde. Além disso, você também obtém as barras de alteração na borda da página de tópico. Novamente, uma barra vermelha é exibida para o conteúdo excluído e uma barra verde é exibida para o conteúdo adicionado. Caso haja adição e exclusão na mesma linha, as barras verde e vermelha são exibidas.

A captura de tela a seguir destaca o conteúdo excluído e inserido junto com as barras de alteração:

![](images/track-changes-content.png){width="650" align="left"}

Um caso de uso típico para rastrear alterações em um documento pode ser para fazer revisão por pares. Você pode ativar o controle de alterações e compartilhar seu documento para revisão, o revisor faz as alterações com o controle de alterações ATIVADO. Ao receber o documento, você deve ter um mecanismo para visualizar as atualizações sugeridas, juntamente com uma maneira conveniente de aceitar ou rejeitar alterações.

O Guia do AEM fornece o recurso Alterações controladas, que contém informações sobre as atualizações feitas no documento. O recurso Alterações rastreadas fornece informações sobre quais atualizações foram feitas, quem as fez e em que momento. Usando o recurso Alterações controladas, você também pode aceitar ou rejeitar facilmente as atualizações sugeridas no documento.

Para acessar o recurso, clique no ícone Alterações controladas no painel direito.

![](images/changes-panel_cs.png){width="300" align="left"}

Clicar em uma alteração seleciona o conteúdo alterado no documento. Você pode aceitar uma alteração selecionando o ícone Aceitar alteração ou rejeitá-la selecionando Rejeitar alteração.

Se desejar aceitar ou rejeitar todas as alterações com um único clique, selecione **Aceitar tudo** ou **Rejeitar tudo**.

>[!NOTE]
>
> O modo Visualizar permite visualizar o documento com ou sem as marcações do conteúdo alterado. Para obter mais detalhes, consulte [Visualizar](web-editor-views.md#preview-mode-id19AAGL00163) modo.

**Mesclar** - ![](images/merge-icon.svg)

Quando você trabalha em um ambiente de vários autores, fica difícil rastrear as alterações que os outros autores fizeram em um tópico ou mapa. O recurso Mesclar oferece mais controle não apenas sobre a exibição das alterações, mas também sobre quais alterações são mantidas na versão mais recente do documento.

**Mesclar arquivos de tópico**

Para mesclar alterações em um tópico, execute as seguintes etapas:

1. Abra um tópico no Editor da Web.

1. Clique em **Mesclar**.

   A caixa de diálogo Mesclar é exibida.

   ![](images/merge-changes-in-topic.png){width="550" align="left"}

1. *\(Opcional\)* Você também pode procurar e selecionar um novo arquivo em algum outro local no repositório.

1. Selecione uma versão do arquivo com a qual deseja comparar a versão atual do arquivo.

1. Em Opções, escolha:

   - **Controlar alterações da versão selecionada**: essa opção mostra todas as atualizações de conteúdo na forma de alterações de rastreamento. Você pode optar por aceitar ou rejeitar as alterações no documento, uma de cada vez, ou todas de uma só vez.

   - **Reverter para a versão selecionada**: Esta opção reverte a versão atual do documento para a versão selecionada. Essa opção não oferece controle sobre qual conteúdo é aceito ou rejeitado.

1. Clique em **Concluído**.

1. Se você selecionou a variável **Rastrear alterações a partir da versão selecionada** e, em seguida, todas as alterações da versão selecionada serão mostradas no recurso Alterações controladas do painel direito.

   Você pode optar por aceitar ou rejeitar todos os comentários do painel Alterações controladas ou aceitar ou rejeitar comentários individuais.


**Mesclar arquivos de mapa**

Para mesclar alterações em um arquivo de mapa, execute as seguintes etapas:

1. Abra um mapa no Editor da Web.

1. Clique em **Mesclar**.

   A caixa de diálogo Mesclar é exibida.

   ![](images/merge-changes-in-map.png){width="550" align="left"}

1. *\(Opcional\)* Você também pode procurar e selecionar um novo arquivo em algum outro local no repositório.

1. Selecione uma versão do arquivo com a qual deseja comparar a versão atual do arquivo.

1. Em Opções, escolha:

   - **Controlar alterações da versão selecionada**: essa opção mostra todas as atualizações de conteúdo na forma de alterações de rastreamento. Você pode optar por aceitar ou rejeitar as alterações no documento, uma de cada vez, ou todas de uma só vez.

   - **Reverter para a versão selecionada**: Esta opção reverte a versão atual do documento para a versão selecionada. Essa opção não oferece controle sobre qual conteúdo é aceito ou rejeitado.

1. Clique em **Concluído**.

   1. Se você selecionou a variável **Rastrear alterações a partir da versão selecionada** e, em seguida, todas as alterações da versão selecionada serão mostradas no painel Alterações rastreadas \(à direita\).

      Você pode optar por aceitar ou rejeitar todas as alterações do painel Alterações controladas ou aceitar ou rejeitar alterações individuais no arquivo de mapa.


**Histórico da versão** - ![](images/version-history-web-editor-ico.svg)

Os Guias do AEM fornecem várias maneiras de exibir as versões criadas para seus arquivos de tópico e também maneiras de reverter para uma versão específica. No entanto, a maioria desses recursos está disponível fora do Editor da Web.

O recurso Histórico de versões no Editor da Web permite não apenas verificar as versões e rótulos disponíveis no tópico ativo, mas também oferece a flexibilidade de reverter para qualquer versão do próprio editor.

Para acessar o histórico de versões e reverter para uma versão específica do seu tópico, execute as seguintes etapas:

1. Abra um tópico no Editor da Web.

1. Clique em **Histórico da versão**.

   A caixa de diálogo Histórico de versão é exibida.

   ![](images/version-history-dialog-web-editor.png){width="550" align="left"}

1. Escolha uma versão do tópico para a qual você deseja reverter na **Selecionar versão** lista suspensa.

   >[!NOTE]
   >
   > Se uma versão tiver rótulos aplicados a ela, eles também serão mostrados \(entre colchetes\) junto com o número da versão.

   Depois de escolher uma versão na lista suspensa, a opção Reverter para a versão selecionada é disponibilizada. A janela de visualização exibe as diferenças entre a versão atual e a versão selecionada do tópico.

   ![](images/version-history-revert-diff-dialog-web-editor.png){width="550" align="left"}

1. Clique em **Reverter para a versão selecionada** para reverter sua cópia de trabalho com a versão selecionada do tópico.

   A caixa de diálogo Reverter versão é exibida.

   ![](images/version-history-revert-dialog-save-working-copy.png){width="550" align="left"}

1. \(*Opcional*\) Forneça um motivo para reverter para uma versão anterior. Você também pode criar uma nova versão da cópia de trabalho ativa do tópico.

1. Clique em **Confirme.**

   Sua cópia de trabalho do arquivo foi revertida para a versão selecionada. Se você optar por criar uma nova versão da cópia de trabalho ativa no momento, uma nova versão do arquivo também será criada com todas as alterações de trabalho.


Quando você reverte para uma versão anterior, uma dica visual é mostrada, indicando que a versão em que você está trabalhando no momento não é a versão mais recente.

![](images/older-version-visual-cue.png){width="800" align="left"}

**Gerenciamento de etiqueta de versão** -  ![](images/version-label-icon.svg)

Os rótulos ajudam a identificar o estágio em que um tópico específico está no DDLC \(Document Development Life Cycle\). Por exemplo, ao trabalhar em um tópico, você pode definir o rótulo como &quot;Aprovado&quot;. Depois que um tópico é publicado e disponibilizado aos clientes, é possível atribuir o rótulo &quot;Lançado&quot; a esse tópico.

Guias de AEM permitem especificar rótulos em um formato de texto livre ou usar um conjunto de rótulos predefinidos. O rótulo personalizado permitiria que qualquer autor no sistema especificasse um rótulo de acordo com sua escolha. Isso dá flexibilidade; no entanto, introduz rótulos inconsistentes no sistema. Para resolver esse problema, os administradores podem configurar um conjunto de rótulos predefinidos. Para obter mais informações sobre a configuração de rótulos predefinidos, consulte *Configurar e personalizar o editor da Web de XML* em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

Esses rótulos são mostrados na forma de uma lista suspensa para os autores sempre que eles precisarem especificar um rótulo. Isso garante que somente rótulos predefinidos e consistentes sejam usados no sistema.

Há diferentes métodos pelos quais você pode aplicar rótulos aos seus tópicos - [Histórico da versão](web-editor-use-label.md) painel na interface do usuário do Assets, [Linhas de Base](/help/product-guide/user-guide/generate-output-use-baseline-for-publishing.md) Interface do usuário do e Editor da Web. O recurso Rótulo de versão no Editor da Web fornece aos autores uma maneira rápida e fácil de atribuir rótulos a seus tópicos.

Para adicionar rótulos ao seu tópico a partir do Editor da Web, execute as seguintes etapas:

1. Abra um tópico no Editor da Web.

1. Clique em **Rótulo da versão**.

   A caixa de diálogo Gerenciamento de rótulo de versão é exibida.

   ![](images/version-label-management-dialog.png){width="650" align="left"}

   A caixa de diálogo Gerenciamento de rótulo de versão é dividida em duas partes: o painel esquerdo tem uma lista de versões disponíveis para o tópico, juntamente com a lista suspensa de rótulos \(ou uma caixa de texto para inserir um rótulo\) e o painel direito com uma visualização do tópico.

1. Selecione uma versão na qual você deseja aplicar rótulos.

   Quando você escolhe uma versão diferente do tópico na lista de versões, o painel de visualização exibe as alterações entre a versão atual e a versão selecionada do tópico

   >[!NOTE]
   >
   > Se um rótulo já estiver aplicado em uma versão, ele será exibido ao lado do número da versão na lista suspensa e abaixo da lista Selecionar versão. Você pode remover um rótulo existente clicando no sinal \(**x**\) ao lado do rótulo.

1. Caso o administrador tenha definido uma lista de rótulos, você verá uma lista suspensa dos rótulos de onde poderá escolher os rótulos que deseja aplicar. É possível selecionar vários rótulos na lista suspensa.

   Caso contrário, será exibida uma caixa de texto, na qual você poderá inserir os rótulos que deseja adicionar ao tópico.

   >[!NOTE]
   >
   > Não é possível aplicar o mesmo rótulo a várias versões de um tópico. Se tentar associar um rótulo existente, você terá a opção de removê-lo da versão existente e aplicá-lo na versão selecionada do tópico.

1. Clique em **Adicionar etiqueta**.

1. Na mensagem de confirmação Aplicar rótulo, selecione a variável **Mover rótulo** opção para mover rótulos de uma versão existente para a versão selecionada. Se você não selecionar essa opção e houver rótulos atribuídos a uma versão diferente do tópico, eles não serão movidos para a versão do tópico selecionado. Esses rótulos são ignorados no processo de aplicativo de rótulo.


**Criar tarefa de análise** -  ![](images/create-review-task-icon.svg)

Você pode criar uma tarefa de revisão do tópico atual ou mapear o arquivo diretamente do Editor da Web. Abra o arquivo para o qual deseja criar a tarefa de revisão e clique em Criar tarefa de revisão para iniciar o processo de criação da revisão.

>[!NOTE]
>
> Você também pode criar uma tarefa de revisão no painel Revisão \(à direita\).

Siga as instruções fornecidas no [Revisar tópicos ou mapas](review.md#) para obter mais detalhes.

## Painel esquerdo {#id2051EA0M0HS}

O painel esquerdo é persistente. Você pode expandi-la ou recolhê-la clicando no ícone Expandir Barra Lateral \(![](images/sidebar-expand-icon.svg)\). Na exibição expandida, ele mostra os nomes dos ícones que aparecem como dicas de ferramentas na exibição recolhida.

>[!NOTE]
>
> O painel esquerdo é redimensionável. Para redimensionar o painel, coloque o cursor no limite do painel, o cursor se transforma em uma seta de duas pontas, clique e arraste para redimensionar a largura do painel.

O painel esquerdo fornece acesso aos seguintes recursos:

**Favoritos** -  ![](images/favorite-collections.svg)

Se você trabalhar em um conjunto de arquivos ou pastas, poderá adicioná-los à sua lista de favoritos para acessá-los rapidamente. A lista Favoritos mostra a lista de documentos adicionados e outras listas de documentos favoritos acessíveis publicamente dos outros usuários.
Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um arquivo, é possível visualizar o título do arquivo e o caminho do arquivo como uma dica de ferramenta.
>[!NOTE]
>
> Como administrador, você também pode optar por exibir a lista de arquivos por nomes de arquivo no Editor da Web. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).

Para criar uma lista ou coleção de favoritos, clique no ícone + ao lado do painel Favoritos para mostrar o log de Nova coleção de dados:

![](images/favorite-new-collection.PNG){width="300" align="left"}

Insira um título e uma descrição para a coleção favorita que você deseja criar. Se você selecionar **Público**, esse favorito será mostrado aos outros usuários também.

Para adicionar um arquivo à sua coleção favorita, use um dos seguintes métodos:

- Navegue até o arquivo ou pasta desejado na Exibição do repositório, clique no *Opções* ícone para abrir o menu de contexto e escolher **Adicionar a Favoritos**. Na caixa de diálogo Adicionar a favoritos, você pode optar por adicionar o arquivo/pasta a um favorito existente ou criar um novo.

  ![](images/favorite-add-file-folder.png){width="300" align="left"}

- Clique com o botão direito do mouse na guia de um arquivo no editor para abrir o menu de contexto. Escolher **Adicionar a** > **Favoritos** para adicionar o arquivo à lista de favoritos.

  ![](images/favorite-add-from-file-context-menu_cs.png){width="400" align="left"}

>[!NOTE]
>
> - Para remover um item da lista de favoritos, selecione o ícone Opções ao lado do item em uma coleção Favoritos e escolha **Remover dos Favoritos**.
> - Para visualizar o arquivo sem abri-lo, selecione um arquivo e **Visualizar** no menu Opções.



**Menu Opções para a coleção Favoritos**\
Também é possível executar muitas ações usando o menu Opções disponível para uma coleção Favoritos:

![](images/favorites-options.png){width="400" align="left"}
- **Renomear**: renomeie a coleção selecionada.
- **Excluir**: exclui a coleção selecionada.
- **Atualizar**: obtenha uma nova lista de arquivos e pastas do repositório.
- **Exibir na interface do usuário do Assets**: mostrar o conteúdo do arquivo ou da pasta na interface do usuário do Assets.

>[!NOTE]
>
> Você também pode atualizar a lista usando o ícone Atualizar na parte superior.


**Visualização do repositório** - ![](images/Repository_icon.svg)

Ao clicar no ícone Exibição do repositório, você obtém uma lista de arquivos e pastas disponíveis no DAM. Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um arquivo, é possível exibir o título e o nome do arquivo como uma dica de ferramenta.

>[!NOTE]
>
> Como administrador, você também pode optar por exibir a lista de arquivos por nomes de arquivo no Editor da Web. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).


São carregados 75 arquivos de cada vez. Sempre que você clicar em **Carregar mais**... 75 arquivos são carregados e o botão para de ser exibido quando todos os arquivos forem listados. Esse carregamento em lote é eficiente, e você pode acessar os arquivos mais rapidamente em comparação ao carregamento de todos os arquivos existentes em uma pasta.

Você pode navegar facilmente para o arquivo necessário no DAM e abri-lo no Editor da Web. Se você tiver o acesso necessário para editar o arquivo, poderá fazê-lo.

Você também pode clicar e reproduzir um arquivo de áudio ou vídeo no Editor da Web. Você pode alterar o volume ou a visualização do vídeo. No menu de atalho, você também tem as opções para baixar, alterar a velocidade de reprodução ou visualizar uma imagem na imagem.



Selecione um mapa e pressione Enter ou clique duas vezes para abri-lo no **Exibição de mapa**. Para obter mais detalhes, consulte **Exibição de mapa** descrição do recurso na [Painel esquerdo](web-editor-features.md#id2051EA0M0HS) seção. Selecione um tópico e pressione Enter ou clique duas vezes para abri-lo no [Área de edição de conteúdo](#id2051EB000UI). Ser capaz de navegar e abrir um arquivo diretamente do Editor da Web economiza tempo e aumenta a produtividade.

**Filtrar pesquisa**

O Editor da Web fornece filtros aprimorados para pesquisar texto. Clique em Filtrar pesquisa \(![](images/filter-search-icon.svg)\) ícone para abrir o painel filtros. Você pode procurar um texto nos arquivos presentes no caminho selecionado do repositório AEM. Por exemplo, é feita uma pesquisa de &quot;finalidade geral&quot; na captura de tela a seguir.

![](images/repository-filter-search.png){width="400" align="left"}

Você também tem as seguintes opções para filtrar os arquivos e restringir sua pesquisa no repositório AEM:

- **Arquivos DITA**: você pode procurar todos **Tópicos DITA** e **Mapas DITA** presente no caminho selecionado.
- **Arquivos não-DITA**: Você pode pesquisar por **Arquivos de imagem**, **Multimídia**, e **Documentos** no caminho selecionado.
- **Elementos DITA**: também é possível pesquisar valores específicos nos atributos dos elementos DITA especificados.
- **Retirado por**: Você pode procurar arquivos nos quais o usuário especificado fez check-out.
- **Última modificação**: é possível procurar arquivos que foram modificados pela última vez após uma data selecionada, mas antes de uma data selecionada. Você também pode procurar arquivos que foram modificados pela última vez nas últimas 2 horas, na semana passada, no mês passado ou no ano passado.
- **Tags**: é possível procurar arquivos que tenham tags específicas aplicadas. Você pode digitar a tag ou selecioná-la na lista suspensa.

**Nota:** O administrador do sistema também pode configurar os filtros de texto e mostrar ou ocultar outros filtros. Para obter mais detalhes, consulte *Configurar filtros de texto* na seção Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

A lista de arquivos filtrados que contém o texto pesquisado é exibida. Por exemplo, na captura de tela acima, os arquivos que contêm o texto &quot;finalidade geral&quot; são listados. Você pode selecionar vários arquivos da lista filtrada para arrastá-los e soltá-los em um mapa aberto para edição.

**Menu Opções**

Além de abrir arquivos no painel esquerdo, também é possível executar muitas ações usando o menu Opções disponível na Exibição do repositório. Você verá opções diferentes, dependendo se você escolher uma pasta, um arquivo de tópico ou um arquivo de mídia.

**Opções de uma pasta**

Você pode executar as seguintes ações usando o menu Opções disponível para uma *pasta* na Exibição de repositório:

![](images/options-menu-folder_cs.PNG){width="550" align="left"}


- **Criar**: crie um novo tópico DITA, mapa DITA ou uma pasta. Para obter mais detalhes, consulte  **Criar tópicos na Exibição de repositório** procedimento no [Painel esquerdo](web-editor-features.md#id2051EA0M0HS) seção.



- **Fazer upload de ativos**: carregue um arquivo do sistema local para a pasta selecionada no repositório AEM. Você também pode arrastar e soltar arquivos do seu sistema local no tópico de trabalho atual. Isso é muito útil se você quiser inserir imagens do sistema local no tópico.

  ![](images/upload-assets.png){width="550" align="left"}

  É possível selecionar uma pasta na qual deseja fazer upload do arquivo, e uma visualização da imagem também é exibida. Se desejar renomear o arquivo, faça isso na caixa de texto nome do arquivo. Clique em fazer upload para concluir o processo de upload de arquivo. Se você tiver arrastado e soltado um arquivo de imagem em um tópico, o arquivo de imagem será adicionado ao artigo e também será carregado.

  Se o administrador tiver ativado a opção UUIDs no *XMLEditorConfig*, você verá a UUID da imagem carregada no **Origem** propriedade.

  ![](images/uuid-in-source-upload-image_cs.png){width="800" align="left"}

- **Localizar arquivos na pasta**: altera o foco para a pesquisa no repositório, na qual você pode inserir o termo de pesquisa. A pesquisa é realizada na pasta selecionada no repositório. Você também pode aplicar um filtro para retornar Arquivos DITA, Arquivos de imagem ou ambos.

  ![](images/find-files-in-folders-repo-view_cs.png){width="400" align="left"}

  Também é possível pesquisar usando a UUID de um arquivo. Nesse caso, os resultados da pesquisa exibem o título do arquivo DITA/XML e, caso o arquivo seja um arquivo de imagem, a UUID do arquivo é exibida. No exemplo de pesquisa a seguir, a UUID de um arquivo de imagem é pesquisada e os resultados da pesquisa exibem a UUID do arquivo de imagem original e o título do tópico do arquivo ao qual essa imagem é referenciada.

  ![](images/uuid-repo-search-image-topic-file_cs.png){width="300" align="left"}

- **Recolher Tudo**: Recolhe todas as pastas abertas no repositório e mostra apenas as pastas de nível raiz.

  >[!NOTE]
  >
  > Use o **\>** ícone ao lado de uma pasta para expandi-la.

- **Adicionar a Favoritos**: adiciona a pasta selecionada aos favoritos. Você pode optar por adicioná-lo a uma coleção de favoritos existente ou nova.

- **Atualizar**: obtenha uma nova lista de arquivos e pastas do repositório.
- **Exibir na interface do usuário do Assets**: mostrar o conteúdo da pasta na interface do usuário do Assets.

**Opções de um arquivo**

Você verá diferentes opções no menu Opções dependendo se você seleciona um arquivo de mídia ou um arquivo DITA. Algumas opções comuns disponíveis para arquivos de mídia e DITA são:

- Duplicar
- Check-out/Check-in
- Visualização
- Mover para
- Renomear
- Excluir
- Copiar
- Recolher Tudo
- Adicionar a Favoritos
- Propriedades
- Exibir na interface do usuário do Assets

![menu de opções de um arquivo na exibição repositório](images/options-menu-repo-view-file-level.png){width="550" align="left"}

As várias opções no menu Opções são explicadas abaixo:

- **Editar**: abra o arquivo para edição. No caso de um arquivo .ditamap/.bookmap, ele é aberto na [Editor de mapa avançado](map-editor-advanced-map-editor.md#) para edição.

- **Duplicar**: use essa opção para criar uma duplicata ou uma cópia do arquivo selecionado. Você também tem a opção de renomear o arquivo duplicado no prompt Duplicar ativo. Por padrão, o arquivo é criado com um sufixo \(como nomedoarquivo\_1.extensão\). O título do arquivo permanece o mesmo do arquivo de origem, e o novo arquivo começa com a versão 1.0. Todas as referências, tags e metadados são copiados, enquanto as linhas de base não são copiadas no arquivo duplicado.
- **Check-out**: obtenha um bloqueio no arquivo selecionado para edição. Para um arquivo bloqueado, essa opção muda para **Check-in**.

  >[!NOTE]
  >
  > - Se um arquivo for bloqueado ou submetido a check-out por um usuário, passar o ponteiro do mouse sobre o ícone de bloqueio mostrará o usuário \(name\) que bloqueou o arquivo.
  > - Ao fazer check-in de um arquivo que tenha alterações não salvas, ele solicita que você salve as alterações. Se você não salvar as alterações, ele só fará o check-in do arquivo.

- **Visualizar**: obtenha uma visualização rápida do arquivo (.dita, .xml, áudio, vídeo ou imagem) sem abri-lo. É possível redimensionar o painel de visualização. Se o conteúdo contiver qualquer `<xref>` ou `<conref>`, você pode selecioná-lo para abri-lo em uma nova guia. O título do arquivo aparece na janela. Se nenhum título estiver presente, o nome do arquivo será exibido. Para fechar o **Visualizar** você pode selecionar o ícone fechar ou clicar em qualquer lugar fora do painel.

  ![](images/quick-preview_cs.png){width="800" align="left"}

- **Renomear**: use essa opção para renomear o arquivo selecionado. Insira o nome do novo arquivo nas **Renomear ativo** diálogo.
   - É possível renomear arquivos de qualquer tipo.
   - Não é possível alterar a extensão de um arquivo.
   - Dois arquivos não podem ter o mesmo nome. Portanto, não é possível renomear um arquivo com um nome que já existe. Um erro é exibido.

- **Mover para**: use essa opção para mover o arquivo selecionado para outra pasta.
   - Você pode digitar o nome da pasta de destino ou escolher **Selecionar caminho** para selecionar a pasta de destino.
   - É possível mover um arquivo de qualquer tipo para qualquer destino na pasta Conteúdo.
   - Dois arquivos não podem ter o mesmo nome. Portanto, não é possível mover um arquivo para uma pasta na qual já exista um arquivo com o mesmo nome.

  Se você tentar mover um arquivo para uma pasta onde existe um arquivo com o mesmo nome mas com um título diferente, a caixa de diálogo Renomear e mover arquivo é exibida e você precisa renomear o arquivo antes de movê-lo. O arquivo movido na pasta de destino tem o novo nome de arquivo.

  ![](images/rename-move-asset.png){width="550" align="left"}

  >[!NOTE]
  > Você também pode arrastar e soltar um arquivo em outra pasta de destino.

  **Cenários de exclusão**

  O Guias do AEM não permite renomear ou mover um arquivo nos seguintes cenários:

   - Não é possível mover ou renomear um arquivo se ele fizer parte de um fluxo de trabalho de revisão ou tradução.

   - Se qualquer outro usuário fizer check-out do arquivo, você não poderá renomeá-lo ou movê-lo. Você não verá a opção Renomear ou Mover para do arquivo.

  >[!NOTE]
  > Se o administrador tiver concedido as permissões em uma pasta, somente a variável **Renomear** ou **Mover para** são exibidas.

  <details>
    <summary> Cloud Services </summary>

  Renomear ou mover qualquer arquivo não interrompe nenhuma referência existente do ou para o arquivo, pois cada arquivo tem uma UUID exclusiva.
  </details>



- **Excluir**: use essa opção para excluir o arquivo selecionado. Um prompt de confirmação é exibido antes de excluir o arquivo.

   - Um prompt de confirmação é exibido antes de excluir o arquivo.
   - Se o arquivo não for referenciado a partir de outro arquivo, ele será excluído e uma mensagem de sucesso será exibida.
   - Se o arquivo for submetido a check-out, não será possível excluí-lo e uma mensagem de erro será exibida.

     >[!NOTE]
     >
     > Se o administrador impediu a exclusão de arquivos com check-out, apenas a mensagem de erro será exibida. Para obter mais detalhes, consulte *Impedir exclusão de arquivos com check-out* na seção Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

   - Se o arquivo for adicionado a uma coleção de favoritos, **Forçar Exclusão** será exibida e você poderá excluí-la à força.
   - Se o arquivo for referenciado a partir de qualquer outro arquivo, **Forçar Exclusão** será exibida uma caixa de diálogo com a mensagem de confirmação, e você poderá excluir o arquivo à força:

     ![](images/options-menu-force-delete.png){width="550" align="left"}

     >[!NOTE]
     >
     > Se o administrador tiver dado permissão para excluir o arquivo, **Forçar Exclusão** está ativado. Senão, **Forçar Exclusão** O está desativado e é exibida uma mensagem informando que você não tem permissão para excluir os arquivos referenciados. Para obter mais detalhes, consulte *Impedir exclusão de arquivos referenciados* na seção Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.

   - Se você excluir um tópico referenciado e tiver aberto o arquivo contendo referências para edição, ele mostrará o link corrompido para o arquivo referenciado.

  >[!NOTE]
  >
  > Você também pode excluir o arquivo selecionado de forma semelhante usando a tecla Delete do teclado.

- **Copiar**: Você pode escolher entre as seguintes opções:

   - **Copiar UUID**: copie a UUID do arquivo selecionado para a Área de transferência.

   - **Copiar caminho**: copia o caminho completo do arquivo selecionado para a área de transferência.

- **Recolher Tudo**: Recolher todos os arquivos no repositório. Somente as pastas de nível superior no repositório são exibidas.
- **Adicionar a**: Você pode escolher entre as seguintes opções:
   - **Favoritos**: adiciona o arquivo selecionado aos favoritos. Você pode optar por adicioná-lo a uma coleção de favoritos existente ou nova.

   - **Conteúdos reutilizáveis**: adiciona o arquivo selecionado à lista Conteúdo reutilizável no painel esquerdo.

- **Propriedades**: use essa opção para abrir a página de propriedades do arquivo selecionado. Essa página de propriedades também pode ser acessada na interface do usuário do Assets selecionando um arquivo e clicando no ícone Propriedades na barra de ferramentas.

- **Abrir painel do mapa**: Caso o arquivo selecionado seja um mapa DITA, essa opção abre o painel de mapa.

- **Editar no Oxygen**: selecione esta opção para editar o arquivo selecionado no plug-in do conector Oxygen. O arquivo está aberto para edição.

  >[!NOTE]
  >
  >Entre em contato com a equipe de sucesso do cliente para habilitar esse recurso no ambiente. Isso não é ativado como parte do suporte pronto para uso. Para obter mais detalhes, consulte [Configurar a opção para editar no Oxygen](../cs-install-guide/conf-edit-in-oxygen.md) no Guia de instalação e configuração.


- **Exibir na interface do usuário do Assets**: use essa opção para mostrar uma pré-visualização de um arquivo .dita/.xml na interface do usuário do Assets. No caso de um arquivo .ditamap/.bookmap, todos os arquivos de tópico no mapa são mostrados em uma única exibição unificada página por página.

- **Baixar como PDF**: use a opção para gerar a saída do PDF e baixá-la.

- **Publicar como**: Use a opção para publicar um tópico ou os elementos dentro de um tópico em um fragmento de conteúdo.

- **Geração rápida**: gere a saída para o arquivo selecionado. A saída só pode ser gerada para arquivos que fazem parte de uma predefinição de saída. Para obter mais detalhes, consulte [Publicação baseada em artigos no Editor da Web](web-editor-article-publishing.md#id218CK0U019I).


**Criar tópicos na Exibição de repositório**

Você pode optar por criar um novo tópico, mapa ou pasta usando o ícone + ao lado do painel Repositório ou no menu de contexto de uma pasta na Exibição do Repositório.

***Criar um tópico***

Quando você optar por *criar um novo tópico* no menu, você verá a seguinte caixa de diálogo:

![](images/create-topic-dialog.png){width="300" align="left"}

No **Criar Novo Tópico** forneça os seguintes detalhes:

- Um modelo no qual o tópico será baseado. Por exemplo, para uma configuração pronta para uso, você pode escolher entre os modelos Em branco, Conceito, DITAVAL, Referência, Tarefa, Tópico e Solução de problemas.

  Se a pasta tiver um Perfil de pasta configurado, você verá apenas os modelos de tópico configurados no Perfil de pasta.

- Caminho no qual você deseja salvar o arquivo de tópico. Por padrão, o caminho da pasta selecionada no momento no repositório é mostrado no campo Caminho.
- Um Título para o tópico.

- *\(Opcional\)* O nome do arquivo do tópico. O nome do arquivo é sugerido automaticamente com base no tópico Título.

  Caso o administrador tenha ativado nomes de arquivo automáticos com base na configuração UUID, você não verá o campo Nome, como mostrado na seguinte captura de tela:

  ![](images/new-topic-without-filename.PNG){width="300" align="left"}


Ao clicar em **Criar**, o tópico é criado no caminho especificado. Além disso, o tópico é aberto no Editor da Web para edição.

***Criar um mapa DITA***

Quando você optar por *criar um novo mapa DITA*, você verá a seguinte caixa de diálogo:

![](images/create-map-dialog.png){width="300" align="left"}

No **Criar novo mapa** forneça os seguintes detalhes:

- Um modelo no qual o mapa será baseado. Por exemplo, para uma configuração pronta para uso, é possível escolher entre os modelos de mapa Bookmap ou DITA.

- Caminho no qual você deseja salvar o arquivo de mapa. Por padrão, o caminho da pasta selecionada no momento no repositório é mostrado no campo Caminho.
- A **Título** para o mapa.

- *\(Opcional\)* O nome de arquivo do mapa. O nome do arquivo é sugerido automaticamente com base no Título do mapa.

  Caso o administrador tenha ativado nomes de arquivo automáticos com base na configuração UUID, você não verá o campo Nome.


Ao clicar em **Criar**, o mapa é criado e adicionado à pasta especificada no campo Caminho. Além disso, o mapa é aberto na Exibição de mapa. Você pode abrir o arquivo de mapa no Editor de mapa e adicionar tópico a ele. Para obter mais informações sobre como adicionar tópicos a um arquivo de mapa, consulte [Criar um mapa](map-editor-create-map.md#).

***Criar uma pasta***

Quando você optar por *criar uma nova pasta*, você terá a **Criar nova pasta** diálogo:

![](images/new-folder-dialog_cs.png){width="300" align="left"}

Insira um **Título** para a pasta, que é convertida automaticamente no nome da pasta. O caminho é onde você deseja salvar o arquivo de mapa. Por padrão, o caminho da pasta selecionada no momento no repositório é mostrado no campo Caminho. Ao clicar em **Criar**, a pasta é criada e adicionada à pasta de onde a opção criar pasta foi executada.

**Exibição de mapa** -  ![](images/map-view-icon.svg)

Ao clicar no ícone Exibição de mapa, você obtém uma lista de tópicos dentro do arquivo de mapa. Se você não tiver aberto nenhum arquivo de mapa, a Exibição de mapa aparecerá em branco. Clicar duas vezes em qualquer arquivo de mapa abre o arquivo de mapa nesta exibição. Você pode clicar duas vezes em qualquer arquivo no mapa para abri-lo no Editor da Web.

Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um arquivo, é possível visualizar o título do arquivo e o caminho do arquivo como uma dica de ferramenta.
>[!NOTE]
>
>Como administrador, você também pode optar por exibir o nome do arquivo do mapa pai que está aberto na exibição de mapa. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).


Quando você abre um mapa na exibição de mapa, o título do mapa atual é exibido no centro da barra de ferramentas principal. Se o título for muito longo, uma reticências será exibida e você também poderá passar o mouse sobre o título para ver o título completo na dica de ferramenta.

Ao definir atributos principais para o tópico ou referências de mapa, é possível visualizar o título, o ícone correspondente e a chave no painel esquerdo. A chave é exibida como `keys=<key-name>`.

![chaves na exibição de mapa](images/view-key-title-map-view.png){width="300" align="left"}

Se você tiver direitos de edição nos arquivos de mapa, também poderá editar os arquivos. Para obter mais informações sobre como abrir e editar um tópico no mapa DITA, consulte [Editar tópicos por meio do mapa DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).


Você pode executar as seguintes ações usando o menu Opções do arquivo de mapa:

![](images/options-menu-map-view_cs.png){width="550" align="left"}

- **Editar**: Abra o arquivo de mapa para edição no Editor de mapa avançado.

- **Selecionar tudo**: selecione todos os arquivos no mapa.

- **Limpar seleção**: desmarque os arquivos selecionados no mapa.

- **Check-out e Bloqueio**: Faça o check-out e obtenha um bloqueio nos arquivos selecionados no mapa.

- **Cancelar check-out e desbloquear**: desbloqueia o arquivo de mapa e o disponibiliza para edição. Isso não reverte as alterações para a versão anterior.

- **Salvar como nova versão e desbloquear**: crie uma versão mais recente e libere o bloqueio nos arquivos selecionados no mapa.

- **Visualizar**: abra uma pré-visualização do arquivo de mapa. Nesta exibição, todos os arquivos de tópico no mapa são mostrados em uma única exibição unificada página por página.

- **Copiar**: Você pode escolher entre as seguintes opções:
   - **Copiar UUID**: copie a UUID do arquivo de mapa para a Área de transferência.
   - **Copiar caminho**: copie o caminho completo do arquivo de mapa para a Área de transferência.

- **Localizar no repositório**: mostra o local do arquivo de mapa no repositório \(ou DAM\).

- **Adicionar a**: Você pode escolher entre as seguintes opções:
   - **Favoritos**: adiciona o arquivo de mapa aos favoritos. Você pode optar por adicioná-lo a uma coleção de favoritos existente ou nova.

   - **Conteúdos reutilizáveis**: adiciona o arquivo de mapa à lista Conteúdo reutilizável no painel esquerdo.

- **Propriedades**: use esta opção para abrir a página de propriedades do arquivo de mapa. Essa página de propriedades também pode ser acessada na interface do usuário do Assets selecionando um arquivo e clicando no ícone Propriedades na barra de ferramentas.

- **Abrir painel do mapa**: abra o painel do mapa.

- **Exibir na interface do usuário do Assets**: use essa opção para mostrar uma pré-visualização do arquivo de mapa na interface do usuário do Assets. Nesta exibição, todos os arquivos de tópico no mapa são mostrados em uma única exibição unificada página por página.
- **Baixar mapa**: selecione esta opção para abrir a variável **Baixar mapa** diálogo.
No **Baixar mapa** você pode escolher as seguintes opções:
   - **Usar Linha de Base**: selecione esta opção para obter uma lista de Linhas de Base criadas para o mapa DITA. Para baixar o arquivo de mapa e seu conteúdo com base em uma Linha de Base específica, selecione a Linha de Base na lista suspensa. Para obter mais detalhes sobre como trabalhar com Linhas de Base, exiba [trabalhar com Linha de Base](./generate-output-use-baseline-for-publishing.md).
   - **Nivelar Hierarquia de Arquivo**: selecione esta opção para salvar todos os tópicos e arquivos de mídia referenciados em uma única pasta.

  Também é possível baixar o arquivo de mapa sem selecionar nenhuma opção. Nesse caso, as últimas versões persistentes dos tópicos e arquivos de mídia referenciados são baixadas.

  Depois de clicar no botão **Baixar** , a solicitação de download de mapa é enfileirada. Você recebe a notificação de que o mapa está pronto para download se estiver pronto para download. Caso o download falhe, você receberá a notificação de que o download do mapa falhou

  Você pode acessar o link de download na Caixa de entrada de notificação do AEM. Selecione a notificação de mapa gerada na Caixa de entrada para baixar o mapa no formato .zip.

  >[!NOTE]
  >
  >  Por padrão, os mapas baixados permanecem por cinco dias na Caixa de entrada de notificação do AEM.

- **Gerar saída**: gere a saída para o arquivo de mapa selecionado. A saída só pode ser gerada para arquivos que fazem parte de uma predefinição de saída. Para obter mais detalhes, consulte [Publicação baseada em artigos no Editor da Web](web-editor-article-publishing.md#id218CK0U019I).
- **Fechar**: fecha o arquivo de mapa.



A captura de tela a seguir mostra o menu Opções para um arquivo na Exibição do mapa DITA:

![](images/options-menu-file_cs.PNG){width="550" align="left"}

Você pode executar as seguintes ações usando o menu Opções:

- **Editar**: abra o arquivo para edição. No caso de um arquivo .ditamap/.bookmap, ele é aberto na [Editor de mapa avançado](map-editor-advanced-map-editor.md#) para edição.

- **Check-out**: Faça check-out do arquivo selecionado. Para um arquivo com check-out, essa opção muda para **Check-in**.



  >[!NOTE]
  >
  > - Se um arquivo for bloqueado ou submetido a check-out por um usuário, passar o ponteiro do mouse sobre o ícone de bloqueio mostrará o usuário \(name\) que bloqueou o arquivo.
  > - Ao fazer check-in de um arquivo, ele solicita que você salve as alterações. Se você não salvar as alterações, ele só fará o check-in do arquivo.

- **Visualizar**: obtenha uma visualização rápida do arquivo (.dita, .xml, áudio, vídeo ou imagem) sem abri-lo. É possível redimensionar o painel de visualização. Se o conteúdo contiver qualquer `<xref>` ou `<conref>`, você pode selecioná-lo para abri-lo em uma nova guia.  O título do arquivo aparece na janela. Se nenhum título estiver presente, o nome do arquivo será exibido. Para fechar o **Visualizar** você pode selecionar o ícone fechar ou clicar em qualquer lugar fora do painel.
- **Copiar**: Você pode escolher entre as seguintes opções:
   - **Copiar UUID**: copie a UUID do arquivo selecionado para a Área de transferência.
   - **Copiar caminho**: copia o caminho completo do arquivo selecionado para a área de transferência.


- **Localizar no repositório**: mostra o local do arquivo selecionado no repositório \(ou DAM\).
- **Expandir tudo**: expanda todos os tópicos nos arquivos de mapa.

- **Recolher Tudo**: Recolhe todos os tópicos que fazem parte do arquivo de mapa atual.

- **Adicionar a**: Você pode escolher entre as seguintes opções:
   - **Favoritos**: adiciona o arquivo selecionado aos favoritos. Você pode optar por adicioná-lo a uma coleção de favoritos existente ou nova.

   - **Conteúdos reutilizáveis**: adiciona o arquivo selecionado à lista Conteúdo reutilizável no painel esquerdo.

- **Propriedades**: use essa opção para abrir a página de propriedades do arquivo selecionado. Essa página de propriedades também pode ser acessada na interface do usuário do Assets selecionando um arquivo e clicando no ícone Propriedades na barra de ferramentas.

- **Exibir na interface do usuário do Assets**: use essa opção para mostrar uma pré-visualização de um arquivo .dita/.xml na interface do usuário do Assets. No caso de um arquivo .ditamap/.bookmap, todos os arquivos de tópico no mapa são mostrados em uma única exibição unificada página por página.

- **Geração rápida**: gere a saída para o arquivo selecionado. A saída só pode ser gerada para arquivos que fazem parte de uma predefinição de saída. Para obter mais detalhes, consulte [Publicação baseada em artigos no Editor da Web](web-editor-article-publishing.md#id218CK0U019I).

>[!NOTE]
>
> Também é possível abrir e editar as propriedades de tópicos selecionados em um mapa DITA na **Mais opções** na parte inferior da Exibição de Mapa.

**Modo de Estrutura de Tópicos** -  ![](images/outline-icon.svg)

Ao clicar no ícone Exibição de Estrutura de Tópicos, você obtém a exibição hierárquica dos elementos usados no documento.

![](images/outline-view_cs.png){width="300" align="left"}

A Exibição de Estrutura de Tópicos oferece os seguintes recursos:

- Uma exibição em árvore de todos os elementos usados no documento.

- Se um elemento tiver uma ID, um atributo e um texto, você poderá vê-los junto com o elemento.

- Acesse a Exibição da estrutura de tópicos nas exibições Autor e Fonte.

- Use a lista suspensa de filtro para mostrar todos os elementos ou somente as referências corrompidas:

- Clicar em um elemento no Modo de Exibição de Estrutura de Tópicos seleciona o conteúdo do elemento no modo de exibição Autor ou Fonte.O modo de exibição de Estrutura de Tópicos permanece sincronizado com o modo de exibição Autor e Fonte. Se você fizer alterações em qualquer exibição, poderá vê-las na exibição Estrutura de Tópicos. Por exemplo, se você adicionar um parágrafo ou atualizar um elemento na exibição Autor, ele será mostrado na exibição Estrutura de tópicos.

  ![](images/select-element-content-outline-view_cs.png){width="650" align="left"}

- Arraste e solte elementos. Você pode substituir facilmente um elemento soltando outro elemento nele. Se você arrastar e soltar um elemento sobre outro elemento e vir uma caixa quadrada ao redor dele, isso indica que o elemento será substituído. Ele substitui o elemento no qual o elemento é solto.

  ![](images/replace-element-outline-view_cs.png){width="300" align="left"}

  Se você arrastar e soltar um elemento, um retângulo tracejado indicará que o elemento pode ser colocado no local atual. Se arrastar e soltar for inválido, uma mensagem de erro será mostrada para indicar que a operação não é permitida.

  ![](images/drop-element-outline-view_cs.png){width="300" align="left"}

- A variável **Opções** no menu *Modo de Estrutura de Tópicos* O permite executar operações genéricas como Recortar, Copiar, Excluir, Gerar ID, Inserir elemento antes ou depois do elemento atual, Renomear ou substituir um elemento, Vincular um elemento, Desvincular um elemento e criar um trecho do elemento selecionado.

>[!NOTE]
>
>Para obter mais detalhes sobre Gerar ID, Inserir elemento antes ou depois do elemento atual e Decodificar um elemento, consulte [Outros recursos no Editor da Web](web-editor-other-features.md#).

**Opções de exibição para o painel Modo de Estrutura de Tópicos**

Usando a lista suspensa Opções de exibição, você pode optar por ver o seguinte, se o elemento tiver:

- **Mostrar ID**: mostra a ID do elemento.
- **Mostrar atributo**: mostra o atributo junto com seu valor.
- **Mostrar texto**: mostra o texto. Se o texto tiver mais de 20 caracteres, uma reticências será exibida.

Se um elemento de bloco tiver seu próprio texto, ele será exibido junto com esse elemento de bloco. Se não tiver seu próprio texto, o texto do primeiro elemento secundário será exibido junto com o elemento de bloco.

![](images/outline-view-block-element.png){width="550" align="left"}

Se o administrador tiver criado um perfil para atributos, você obterá esses atributos junto com seus valores configurados. Você também pode designar atributos de exibição configurados pelo administrador na **Atributos de exibição** nas configurações do editor. Os atributos definidos para um elemento são exibidos na exibição Layout e Estrutura de Tópicos.


Para obter mais detalhes, consulte *Atributos de exibição* no prazo de *Configurações do editor* descrição do recurso na [Painel esquerdo](web-editor-features.md#id2051EA0M0HS) seção.

**Recurso de pesquisa**
Usando o recurso de pesquisa, você pode pesquisar um elemento por seu nome, id, texto ou valor de atributo.

A pesquisa não diferencia maiúsculas de minúsculas e corresponde exatamente à sequência de caracteres. Os resultados da pesquisa são classificados de acordo com a posição do elemento no documento.

Você pode procurar por uma string no elemento se ela estiver mostrada no painel Modo de exibição de estrutura de tópicos. Por exemplo, se a sequência &quot;Adobe&quot; estiver presente no texto do elemento e for mostrada no painel Modo de exibição de estrutura de tópicos (como você selecionou **Mostrar texto** na lista suspensa Opções de exibição ), o elemento que o contém é filtrado. Mas se o texto não for mostrado no painel Modo de Exibição de Estrutura de Tópicos (já que você não selecionou **Mostrar texto** na lista suspensa Opções de exibição ), o elemento que o contém não é filtrado. Da mesma forma, você encontrará a cadeia de caracteres na ID ou nos atributos se os tiver selecionado.



**Conteúdos reutilizáveis** -  ![](images/content-reuse-icon.png)

Um dos principais recursos do DITA é a capacidade de reutilizar conteúdo. O painel Conteúdo reutilizável pode armazenar seus arquivos DITA de onde você geralmente insere conteúdo reutilizável. Depois de adicionados, os arquivos DITA permanecem no painel Conteúdo reutilizável nas sessões. Isso significa que não é necessário adicionar os arquivos DITA novamente para acessá-los posteriormente.

Você pode simplesmente arrastar e soltar o conteúdo reutilizável do painel no seu tópico atual e ele é inserido de forma fácil e rápida. Você também pode obter uma visualização do conteúdo antes de inseri-lo no documento.

Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um arquivo, é possível visualizar o título do arquivo e o caminho do arquivo como uma dica de ferramenta.
>[!NOTE]
>
> Como administrador, você também pode optar por exibir a lista de arquivos por nomes de arquivo no Editor da Web. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).

Para adicionar um arquivo DITA ao painel Conteúdo reutilizável, use um dos seguintes métodos:

- Clique no ícone + ao lado de Conteúdo reutilizável para abrir a caixa de diálogo Procurar arquivo. Selecione o arquivo que deseja adicionar e clique em **Adicionar** para concluir o processo.

  ![](images/reuse-content-add-dita-file_cs.png){width="650" align="left"}

- Na Exibição de repositório, clique no ícone Opções do arquivo desejado e escolha **Adicionar ao conteúdo reutilizável** no menu de contexto.

- Clique com o botão direito do mouse na guia de um arquivo no editor para abrir o menu de contexto e escolher **Adicionar ao conteúdo reutilizável**.


Depois que o arquivo for adicionado, você poderá ver todos os elementos de conteúdo reutilizáveis do arquivo no painel Conteúdo reutilizável. O conteúdo reutilizável é exibido com as IDs e os nomes de elemento.

Ao adicionar um arquivo à lista Conteúdo reutilizável, o título do arquivo é exibido em vez da UUID do arquivo. Para verificar a UUID do arquivo, passe o mouse sobre o título do arquivo e a UUID do arquivo será exibida na dica de ferramenta.

![](images/uuid-reusable-content-file-title_cs.png){width="300" align="left"}

>[!NOTE]
>
> É possível adicionar vários arquivos à lista de conteúdo reutilizável. Em seguida, você pode inserir o conteúdo desejado do painel Conteúdo reutilizável no documento.

**Atualizar**: verifica novamente todo o conteúdo reutilizável e exibe uma nova lista de conteúdos reutilizáveis.

Para inserir conteúdo do painel Conteúdo reutilizável, use um dos seguintes métodos:

- Passe o ponteiro do mouse sobre um elemento que você deseja inserir, clique no ícone Opções e escolha **Inserir conteúdo reutilizável**.

  ![](images/insert-reusable-content_cs.png){width="400" align="left"}

  >[!NOTE]
  >
  > Selecione um arquivo e **Visualizar** do **Opções** para visualizar o arquivo sem abri-lo. Você também pode visualizar as referências presentes em um tópico. A ID de referência aparece na janela.
  >
  > A variável **Visualizar** também está disponível na **Opções** menu de um elemento, que fornece uma visualização rápida do elemento antes de inseri-lo.

- Arraste e solte o item de conteúdo reutilizável do painel no local desejado no documento.



**Glossário** -  ![](images/glossary.svg)

O Guia do AEM permite criar e usar facilmente os documentos do tipo glossário. Você pode criar arquivos de tópico de glossário e incluí-los em um mapa de glossário comum. Depois que esse mapa é adicionado como mapa raiz, as entradas do glossário são mostradas no painel Glossário.

![](images/glossary-panel.png){width="650" align="left"}

Para inserir um termo do glossário, basta arrastar e soltar a entrada do painel para o local desejado no seu tópico. O menu Opções de um termo do glossário permite obter uma **Visualizar** do termo de entrada **Copiar caminho** do arquivo de termo de entrada ou localize o arquivo de termo de entrada no repositório.

Execute as seguintes etapas para pesquisar termos de texto e substituí-los por abreviações de glossário:

1. Abra o tópico DITA ou o mapa no qual deseja pesquisar e converter o texto ou os termos.
1. Selecione o painel de glossário para exibir os termos do glossário presentes no mapa-raiz. Você pode arrastar e soltar esses termos para adicioná-los ao tópico aberto.
1. Selecione o **Ponto de acesso** ferramenta \( ![](images/hotspot-icon.svg)\) no painel Glossário para pesquisar e converter termos de texto específicos em abreviações de glossário vinculadas. Além disso, vice-versa, você pode usá-lo para pesquisar abreviações de glossário e convertê-las em termos de texto.

![](images/glossary-hotspot-tool.png){width="300" align="left"}

Você pode definir as seguintes configurações da ferramenta Ponto de acesso:

![](images/Glossary-search-keys.png){width="300" align="left"}

- **Teclas de glossário**: Selecione as chaves do glossário no mapa DITA que deseja usar para a pesquisa no tópico selecionado. As teclas selecionadas serão exibidas abaixo. Você pode remover uma chave selecionada clicando no ícone **Remover** ícone.

- **Temas**: escolha uma das opções **Tópico atual** aberto no Editor da Web, tudo **Tópicos abertos** no mapa atual, ou na variável **Mapa atual** sendo editados no Editor de Mapas para pesquisar os termos.
- **Filtrar tópicos por status**: é possível optar por limitar a pesquisa aos tópicos que têm o status do documento selecionado. Os tópicos podem estar no status Rascunho, Editar, Em revisão, Aprovado, Revisado, Concluído ou em qualquer um dos estados configurados pela organização.
- **Ação**: você pode optar por pesquisar as chaves do glossário **Manualmente para cada tópico** ou **Automaticamente para todos os tópicos**. Se você escolher **Manualmente para cada tópico**, ele solicita que você confirme antes de converter cada termo em cada tópico. Se você escolher **Automaticamente para todos os tópicos**, ele converte automaticamente todos os termos em todos os tópicos.
- **Converter**: é possível converter um objeto pesquisado **Texto para termo do glossário** ou **Termo do glossário para texto.**
- **Opções**: É possível selecionar entre as seguintes opções:
   - **Correspondência que diferencia maiúsculas de minúsculas**: Pesquisa um termo para encontrar a correspondência que tem o mesmo uso de maiúsculas e minúsculas. Por exemplo, &quot;USB&quot; não corresponderá a &quot;usb&quot;.
   - **Converter apenas a primeira instância**: se várias instâncias do termo pesquisado estiverem presentes em um tópico, somente a primeira instância será convertida.
   - **Fazer Check-out do Arquivo Antes da Conversão**: o check-out do arquivo pesquisado é feito antes da conversão dos termos.
   - **Criar uma nova versão após a conversão**: uma nova versão do tópico é criada após a conclusão da conversão dos termos.
- **Próxima** será exibido se você selecionar **Manualmente para cada tópico** opção. Clique em **Próxima** para converter os termos de cada tópico com base nas configurações selecionadas. Ele solicita a conversão de termos em cada tópico e passa para o próximo arquivo. Você pode optar por converter um termo ou ignorá-lo e passar para o próximo termo.

  ![](images/manual-convert-skip.png){width="300" align="left"}

- **Converter** será exibido se você selecionar **Automaticamente para todos os tópicos** opção. Selecionar **Converter** para converter todos os termos encontrados no documento em abreviações de glossário vinculadas.

Uma lista dos **Tópicos atualizados** com os termos convertidos e **Tópicos com erro** é exibido. Passe o mouse sobre o \( ![](images/info-icon.svg)\) próximo a Tópicos com Erro para ver os detalhes do erro.

![](images/glossary-converted-terms-error.png){width="300" align="left"}

>[!NOTE]
>
> Atualize o tópico para exibir os termos convertidos.

**Condições** -  ![](images/conditions-icon.svg)

O painel Condições exibe os atributos condicionais definidos pelo administrador no perfil global ou de nível de pasta. Você pode adicionar condições ao seu conteúdo simplesmente arrastando e soltando a condição desejada no seu conteúdo. O conteúdo condicional é realçado usando a cor definida para a condição, para facilitar a identificação.

Você também pode aplicar várias condições a um elemento arrastando e soltando várias condições em um elemento. Quando você aplica várias condições em um elemento, o painel Propriedades exibe as condições aplicadas separadas por vírgula.

![](images/multiple-conditions-applied_cs.png){width="800" align="left"}

No entanto, na visualização Código, as condições são separadas usando um delimitador de espaço. Ao adicionar ou editar uma condição na Visualização de código, certifique-se de que várias condições sejam separadas usando um espaço.

>[!IMPORTANT]
>
> A captura de tela a seguir é de um usuário com privilégios administrativos. Como um usuário com privilégios administrativos, você pode adicionar, editar e excluir condições. Senão, como um autor normal, você só terá a opção de aplicar condições.

![](images/conditional-content-through-panel_cs.png){width="800" align="left"}

Para adicionar ou definir uma condição, clique no ícone + ao lado do painel Condições para abrir a caixa de diálogo Definir condição:

![](images/conditional-panel-create-cond.png){width="400" align="left"}

Na lista Atributo, selecione o atributo condicional que deseja definir, insira um valor para a condição e especifique o rótulo que é exibido no painel Condições. Você também pode definir uma cor para a condição. Essa cor é definida como a cor de fundo do conteúdo no qual a condição é aplicada

Para editar uma condição, escolha **Editar** no menu Opções. A caixa de diálogo Editar condição é exibida:

![](images/conditional-panel-edit-cond.png){width="400" align="left"}

Especifique os detalhes da mesma forma que foram configurados ao definir uma nova condição.

**Esquema do assunto** -  ![](images/subject_scheme_panel-icon.svg)

Mapas de esquema de assunto são uma forma especializada de mapas DITA que são usados para definir assuntos taxonômicos e valores controlados. Dependendo das suas necessidades, você pode criar um mapa de esquema de assunto e referenciá-lo no arquivo de mapa raiz. Guias de AEM permitem definir a hierarquia de nível aninhado das definições de assunto no esquema de assunto.

Você pode criar facilmente e usar o esquema de assunto em um mapa de esquema de assunto. Depois que esse mapa é adicionado como mapa raiz, o esquema de assunto é mostrado no painel Esquema de assunto. O painel Esquema do assunto exibe o esquema do assunto disponível de forma aninhada ou hierárquica.

As Guias do AEM também são compatíveis com mapas de esquema de assunto de nível aninhado, e você pode ter vários esquemas de assunto definidos no mapa de esquema de assunto raiz.

O exemplo a seguir mostra como usar o esquema do assunto nos Guias do AEM.

1. Crie um arquivo de esquema do assunto em uma ferramenta de sua escolha. O código XML a seguir cria um esquema de assunto que vincula valores para o `platform` atributo.

   ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "subjectScheme.dtd">
   <subjectScheme id="GUID-4f942f63-9a20-4355-999f-eab7c6273270">
       <title>rw</title>
       <!-- Define new OS values that are merged with those in the unixOS scheme -->
       <subjectdef keys="os">
           <subjectdef keys="linux">    </subjectdef>
           <subjectdef keys="mswin">    </subjectdef>
           <subjectdef keys="zos">    </subjectdef>
       </subjectdef>
       <!-- Define application values -->
       <subjectdef keys="app" navtitle="Applications">
           <subjectdef keys="apacheserv">    </subjectdef>
           <subjectdef keys="mysql">    </subjectdef>
       </subjectdef>
       <!-- Define an enumeration of the platform attribute, equal to       each value in the OS subject. This makes the following values       valid for the platform attribute: linux, mswin, zos -->
       <enumerationdef>
           <attributedef name="platform">    </attributedef>
           <subjectdef keyref="os">    </subjectdef>
       </enumerationdef>
       <!-- Define an enumeration of the otherprops attribute, equal to       each value in the application subjects.       This makes the following values valid for the otherprops attribute:       apacheserv, mysql -->
       <enumerationdef>
           <attributedef name="otherprops">    </attributedef>
           <subjectdef keyref="app">    </subjectdef>
       </enumerationdef>
   </subjectScheme>
   ```

   ![](images/subject-scheme-panel.png){width="300" align="left"}

1. Salve o arquivo com a extensão a.ditamap e faça upload dele para qualquer pasta no DAM.

   >[!NOTE]
   >
   > Você pode adicionar uma referência ao arquivo de esquema do assunto no mapa DITA principal.

   ![](images/subject-scheme-root-map.png){width="550" align="left"}

1. Defina o mapa principal como o mapa principal na **Preferências do usuário**. Depois que esse mapa é adicionado como mapa raiz, o esquema de assunto é mostrado no painel Esquema de assunto.

   ![](images/subject-scheme-user-preferences.png){width="400" align="left"}

1. No Editor da Web, abra o arquivo no qual deseja usar as definições do esquema de assunto.
1. Aplique o esquema de assunto ao seu conteúdo simplesmente arrastando e soltando o esquema de assunto desejado no seu conteúdo. O conteúdo é então realçado com a cor definida.

   ![](images/subject-scheme-apply.png){width="650" align="left"}

**Lidar com definições hierárquicas de definições e enumerações de assunto**

Além de lidar com as enumerações e as definições de assunto presentes no mesmo mapa, o AEM Guides também fornece o recurso para definir enumerações e definições de assunto em dois mapas separados. É possível definir uma ou mais definições de assunto em um mapa e as definições de enumeração em outro mapa e, em seguida, adicionar a referência do mapa. Por exemplo, o código XML a seguir cria definições de assunto e definições de enumeração em dois mapas separados.

As definições de assunto são definidas em `subject_scheme_map_1.ditamap`


```XML
  <?xml version="1.0" encoding="UTF-8"?> 
    <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
    <subjectScheme id="subject-scheme.ditamap_f0bfda58-377b-446f-bf49-e31bc87792b3"> 

    <title>subject_scheme_map_1</title> 
    
    <subjectdef keys="os" navtitle="Operating system">
        <subjectdef keys="linux" navtitle="Linux">
        <subjectdef keys="redhat" navtitle="RedHat Linux">
        </subjectdef>
        <subjectdef keys="suse" navtitle="SuSE Linux">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="windows" navtitle="Windows">
        </subjectdef>
        <subjectdef keys="zos" navtitle="z/OS">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="deliveryTargetValues">
        <subjectdef keys="print">
        </subjectdef>
        <subjectdef keys="online">
        </subjectdef>
    </subjectdef>
    <subjectdef keys="mobile" navtitle="Mobile">
        <subjectdef keys="android" navtitle="Android">
        </subjectdef>
        <subjectdef keys="ios" navtitle="iOS">
    </subjectdef>
    </subjectdef>
    <subjectdef keys="cloud" navtitle="Cloud">
        <subjectdef keys="aws" navtitle="Amazon Web Services">
        </subjectdef>
        <subjectdef keys="azure" navtitle="Microsoft Azure">
        </subjectdef>
        <subjectdef keys="gcp" navtitle="Google Cloud Platform">
        </subjectdef>
    </subjectdef>
    </subjectScheme>
```

A definição de enumeração está presente em subject_scheme_map_2.ditamap.

```XML
    ?xml version="1.0" encoding="UTF-8"?> 
        <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
        <subjectScheme id="subject-scheme.ditamap_17c433d9-0558-44d4-826e-3a3373a4c5ae"> 
        <title>subject_scheme_map_2</title> 
        <mapref format="ditamap" href="subject_scheme_map_1.ditamap" type="subjectScheme"> 
        </mapref> 
        <enumerationdef>
        <attributedef name="platform">
        </attributedef>
        <subjectdef keyref="mobile">
        </subjectdef>
        <subjectdef keyref="cloud">
        </subjectdef>
        </enumerationdef>
        </subjectScheme>
```

Aqui, as definições de assunto são definidas em `subject_scheme_map_1.ditamap`  enquanto o def de enumeração estiver presente em `subject_scheme_map_2.ditamap`. A referência a `subject_scheme_map_1.ditamap` também é adicionado em `subject_scheme_map_2.ditamap`.

>[!NOTE]
>
> Como a variável `subject_scheme_map_1.ditamap` e `subject_scheme_map_2.ditamap` são referenciados entre si, portanto, os esquemas de assunto estão sendo resolvidos.

As referências de enumeração do assunto são resolvidas na seguinte ordem de prioridade:

1. Mesmo mapa
1. Mapa referenciado


As referências não serão resolvidas se a enumeração não for encontrada no mesmo mapa e no mapa referenciado.




**Restringir os valores a um elemento específico**

Você também pode restringir as condições a alguns elementos dentro de um tópico. Use o `<elementdef>` para definir o elemento e a variável `<attributedef>` para definir a condição que pode ser aplicada ao elemento.  Se você não adicionar a variável `<elementdef>` você pode aplicar as condições a todos os elementos.
Por exemplo, use a seguinte enumeração para restringir o `@platform` atributo para o `<shortdesc>` elemento.  As outras condições são visíveis para todos os elementos.

```XML
<enumerationdef>
    <elementdef name="shortdesc">
    </elementdef>
    <attributedef name="platform">
    </attributedef>
    <subjectdef keyref="deliveryTargetValues">
    </subjectdef>
    <subjectdef keyref="os">
    </subjectdef>
  </enumerationdef>
```

</details>


**Menu suspenso Atributos**

Também é possível alterar o valor do esquema do assunto usando a variável **Atributos** lista suspensa no **Propriedades de conteúdo** no painel **Autor** exibição.
![](images/subject-scheme-attribute-dropdown.png){width="200" align="left"}
Execute as seguintes etapas para alterar o valor:

1. Selecione um atributo na **Atributo** lista suspensa.
1. Selecionar **Editar** ![ícone de edição](images/edit_pencil_icon.svg).
1. Selecione o valor obrigatório na caixa **Valor** lista suspensa.
1. Clique em **Atualizar**.



Você também pode aplicar valores a um atributo selecionando vários valores na lista suspensa.

**Exibição de origem**

Você também pode alterar os valores do menu suspenso do atributo na Exibição de origem. A Exibição de código-fonte também impede que você adicione qualquer valor incorreto.

![](images/subject-scheme-code-error.png){width="550" align="left"}

**Exibir e aplicar o esquema de assunto do painel Condições**

Você também pode exibir e aplicar o esquema de assunto do painel Condições.

Para exibir o esquema do assunto no painel Condições, o administrador do sistema deve selecionar a opção **Mostrar esquema do assunto no painel Condições** na guia Condição, em Configurações do editor. Para obter mais detalhes, consulte [Guia Condição](#id21BMNE0602V).

O painel Condições exibe a estrutura vertical plana das definições de assunto dentro do esquema de assunto.

![](images/subject-scheme-condtions-panel.png){width="300" align="left"}

Você pode adicionar condições ao seu conteúdo arrastando e soltando a condição desejada no seu conteúdo. O conteúdo condicional é realçado usando a cor definida para a condição.

**Trechos** -  ![](images/insert-snippet-icon.svg)

Os trechos são pequenos fragmentos de conteúdo que podem ser reutilizados em vários tópicos do projeto de documentação. O painel Snippets mostra uma coleção de trechos de conteúdo que você criou. Para inserir um trecho, arraste e solte o trecho do painel no local desejado no tópico. O painel Snippets permite adicionar, editar, excluir, visualizar e inserir um trecho.

>[!IMPORTANT]
>
> A captura de tela a seguir é de um usuário com privilégios administrativos. Como usuário com privilégios administrativos, você pode adicionar, editar e excluir trechos. Caso contrário, como autor normal, você só terá as opções para visualizar e inserir um trecho.

![](images/snippets-panel_cs.png){width="400" align="left"}

Para adicionar um trecho, use um dos seguintes métodos:

- Clique no ícone + ao lado de Trechos para abrir a caixa de diálogo Novo trecho.

  ![](images/snippet-new-dialog.png){width="550" align="left"}

  Na caixa de diálogo Novo trecho, forneça um título que apareça no painel Trechos, uma descrição e o código XML do conteúdo do trecho que você deseja criar. Clique em **Criar** para salvar e criar o trecho.

- Na área de edição de conteúdo, clique com o botão direito do mouse na navegação estrutural do elemento que deseja usar como snippet e escolha **Criar trecho** no menu de contexto. A caixa de diálogo Novo trecho é exibida com o código XML do elemento selecionado preenchido na **Conteúdo** campo. Insira o **Título** e **Descrição** para o trecho e clique em **Criar** para salvar o trecho.

- Na área de edição de conteúdo, clique com o botão direito do mouse em qualquer lugar do conteúdo que você deseja usar como um snippet e escolha **Criar trecho** no menu de contexto. A caixa de diálogo Novo trecho é exibida com o código XML do elemento selecionado preenchido na **Conteúdo** campo. Insira o **Título** e **Descrição** para o trecho e clique em **Criar** para salvar o trecho.

  A captura de tela a seguir destaca a navegação estrutural e a área de conteúdo da qual você pode chamar o menu de contexto.

  ![](images/snippet-create-from-breadcrumb-content.png){width="350" align="left"}


Para inserir um trecho, use um dos seguintes métodos:

- Selecione um trecho no painel Snippets e arraste-o e solte-o no local desejado no seu tópico.

- Posicione o ponto de inserção onde deseja inserir o trecho. No menu Opções do trecho necessário, escolha Inserir trecho.


>[!NOTE]
>
> No menu de contexto de uma entrada de trecho, você também pode optar por Editar, Excluir, obter uma Visualização ou Inserir um trecho.

**Modelos** -  ![](images/templates-icon.svg)

O painel Modelos está disponível somente para administradores. Com esse painel, o e o administrador do podem criar e gerenciar facilmente modelos que podem ser usados pelos autores. Por padrão, os modelos são categorizados em *Mapa* e *Tópico* modelos do tipo.

![](images/templates-panel_cs.png){width="550" align="left"}

Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um modelo, é possível exibir o título do arquivo e o nome do arquivo como uma dica de ferramenta.

>[!NOTE]
>
> Como administrador, você também pode optar por exibir a lista de arquivos no Editor da Web. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).

Para criar um modelo, clique no ícone + ao lado de Modelos e escolha um modelo que deseja criar. Se você selecionar **Modelo de Tópico**, a caixa de diálogo Criar novo modelo de tópico será exibida:

![](images/create-new-topic-template.PNG){width="400" align="left"}

Escolha o tipo de modelo que deseja criar na **Modelo** lista suspensa. Forneça o **Título**, que aparece no painel Modelos. A variável **Nome** do modelo é sugerido automaticamente com base no título. No entanto, você pode fornecer um nome de arquivo diferente.

>[!NOTE]
>
> Caso o administrador tenha ativado nomes de arquivo automáticos com base na configuração UUID, você não verá o campo Nome.

Depois que o modelo for criado, é necessário adicioná-lo ao perfil global ou de nível de pasta. Depois que o modelo for adicionado, os autores começarão a ver o novo modelo no processo de criação de tópico/mapa.

Usando o menu Opções em um modelo existente, você pode optar por **Editar** ou **Duplicar** o mesmo. No caso de duplicação, a estrutura e o tipo do modelo \(do documento\) são retidos e você pode reutilizá-los para criar outro modelo a partir dele.

**Revisão** -  ![](images/active-review-tasklist-icon.svg)

O Guias do AEM fornece o recurso para exibir todas as tarefas de revisão em seus projetos. Você pode exibir todos os projetos de revisão e as tarefas de revisão ativas nos projetos de revisão, dos quais você faz parte no **Revisão** painel.  É possível abrir as tarefas de revisão para exibir os comentários dos vários revisores.
O painel de revisão exibe as tarefas de revisão. Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um arquivo, é possível visualizar o título do arquivo e o caminho do arquivo como uma dica de ferramenta.
>[!NOTE]
>
> Como administrador, você também pode optar por exibir a lista de arquivos por nomes de arquivo no Editor da Web. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).

Como autor, você pode endereçar os comentários em um tópico usando o Editor da Web.


Para exibir os comentários de revisão nas tarefas de revisão ativas que estão presentes em seus projetos, execute as seguintes etapas:

1. Selecionar revisão ![](images/active-review-tasklist-icon.svg)   no painel esquerdo. A variável **Revisão** é aberto.  Todos os projetos de revisão e as tarefas de revisão ativas nos projetos de revisão, dos quais você faz parte, são exibidos.

   ![](images/web-editor-review-panel.png){width="300" align="left"}
1. Selecione um projeto de revisão e, em seguida, selecione uma tarefa de revisão na lista para abri-lo.
1. Você também pode filtrar seus projetos das seguintes maneiras:

   - Insira o termo ou texto de pesquisa que deseja localizar no título do projeto. Pressione Enter para realizar a pesquisa. Por exemplo, você pode pesquisar todos os projetos com o termo &quot;espaço&quot; no título.

   - Selecionar ![](images/filter-search-icon.svg)  para abrir o **Filtro** diálogo. Você pode selecionar todos ou somente projetos específicos. Os projetos selecionados são listados na **Revisão** painel.
     ![](images/active-review-select-project.png){width="300" align="left"}

     A variável **Tarefas iniciadas por mim** está ativada por padrão. Permite exibir somente as tarefas que você iniciou.

1. Por padrão, no projeto de revisão, você exibirá uma lista simples de tópicos que têm comentários associados a eles. Aplique os filtros necessários no painel esquerdo para filtrar os tópicos com base nos comentários de revisão presentes neles:

   - **Exibir todos os tópicos**: lista todos os tópicos presentes nos projetos.
   - **Exibir tópicos com comentários**: lista somente os tópicos que contêm comentários de revisão.
1. Você também pode inserir o termo de pesquisa ou o texto que deseja localizar no título do tópico ou no caminho do arquivo. Os tópicos que contêm o termo no título ou no caminho do arquivo são listados.
1. Clique duas vezes em qualquer tópico para abri-lo na exibição do autor. É possível exibir os comentários nas **Comentários** painel.
   ![](images/active-review-task-comments.png){width="800" align="left"}


   >[!NOTE]
   > 
   > A variável **Revisão** e o painel **Comentários** Os painéis do estão sincronizados o tempo todo. No painel Comentários, os comentários são carregados com base na tarefa de revisão carregada no painel Revisão.
   > Para obter mais informações sobre como tratar os comentários, consulte [Comentários de revisão de endereço](review-address-review-comments.md#).

**Localizar e substituir** -  ![](images/FindAndReplace_icon.svg)

O ícone Localizar e substituir é encontrado na parte inferior do painel esquerdo. O painel Localizar e substituir permite procurar e substituir texto entre arquivos em um mapa ou uma pasta no repositório. É possível localizar e substituir em todos os tópicos de um mapa, bem como nos tópicos presentes nos submapas dentro do mapa.

![](images/map-find-replace.png){width="800" align="left"}

Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um arquivo, é possível visualizar o título do arquivo e o caminho do arquivo como uma dica de ferramenta.
>[!NOTE]
>
> Como administrador, você também pode optar por exibir a lista de nomes de arquivo no Editor da Web. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).

Para executar a pesquisa global e substituir, execute as seguintes etapas:

1. Abrir o global **Localizar e substituir** painel.
1. Clique em **Examinar** selecione uma das seguintes opções para realizar a pesquisa.
   - **Mapa atual**: Para pesquisar no mapa aberto no momento

     >[!NOTE]
     >
     > Essa opção será exibida se você já tiver aberto um mapa para edição.

   - **Caminho**: Para pesquisar no caminho selecionado
   - **Selecionar mapa**: Para pesquisar no mapa selecionado

1. Você pode clicar no link **Opções** e escolha entre as seguintes opções:

   - **Fazer check-out do arquivo antes de substituir**: selecione essa opção se desejar fazer check-out de um arquivo automaticamente antes de substituir o termo de pesquisa. Essa configuração é mais relevante caso o administrador tenha ativado a configuração para fazer check-out de um arquivo antes de editar. Com a configuração de backend ativada, você deve selecionar essa opção. Isso impedirá que a caixa de diálogo de check-out de arquivo solicite que você faça check-out de cada arquivo antes de fazer qualquer alteração. Se você não selecionar essa opção, um prompt será exibido antes que um arquivo seja aberto para edição.
   - **Somente Palavra Inteira**: selecione essa opção se desejar pesquisar a cadeia de caracteres de pesquisa inteira. Por exemplo, se você inserir sobre na cadeia de caracteres de pesquisa, o resultado da pesquisa retornará todos os arquivos contendo palavras como sobre e visão geral. Se quiser restringir a pesquisa para retornar o termo exato inserido, selecione essa opção.
   - **Criar nova versão após substituição**: selecione esta opção se quiser criar uma nova versão do tópico no qual você escolher substituir o texto. Você também pode fornecer comentários de versão que serão adicionados com cada arquivo atualizado.

     Se você não selecionar essa opção, as alterações serão salvas na versão atual do tópico e nenhuma nova versão será criada.

   - **Incluir referência indireta**: selecione essa opção se desejar pesquisar a cadeia de caracteres nas referências indiretas também no mapa DITA. Por padrão, isso fica desativado para que a pesquisa seja executada somente nas referências diretas.

1. Informe o termo ou texto de pesquisa que deseja localizar.
1. Insira o texto pelo qual deseja substituir o termo de pesquisa.
1. Pressione Enter ou selecione **Pesquisar** ícone \( ![](images/search-icon.svg)\) para realizar a pesquisa.
1. Selecione um arquivo na lista de resultados da pesquisa. O arquivo é aberto na área de edição de conteúdo com o termo pesquisado realçado no conteúdo.
1. Abrir o global **Localizar e substituir** painel.
1. Clique em **Examinar** selecione uma das seguintes opções para realizar a pesquisa.

   - **Mapa atual**: Para pesquisar no mapa aberto no momento

     >[!NOTE]
     >
     > Essa opção será exibida se você já tiver aberto um mapa para edição.

   - **Caminho**: Para pesquisar no caminho selecionado
   - **Selecionar mapa**: Para pesquisar no mapa selecionado

1. Você pode clicar no link **Opções** e escolha entre as seguintes opções:

   - **Fazer check-out do arquivo antes de substituir**: selecione essa opção se desejar fazer check-out de um arquivo automaticamente antes de substituir o termo de pesquisa. Essa configuração é mais relevante caso o administrador tenha ativado a configuração para fazer check-out de um arquivo antes de editar. Com a configuração de backend ativada, você deve selecionar essa opção. Isso impedirá que a caixa de diálogo de check-out de arquivo solicite que você faça check-out de cada arquivo antes de fazer qualquer alteração. Se você não selecionar essa opção, um prompt será exibido antes que um arquivo seja aberto para edição.

   - **Somente Palavra Inteira**: selecione essa opção se desejar pesquisar a cadeia de caracteres de pesquisa inteira. Por exemplo, se você inserir sobre na cadeia de caracteres de pesquisa, o resultado da pesquisa retornará todos os arquivos contendo palavras como sobre e visão geral. Se quiser restringir a pesquisa para retornar o termo exato inserido, selecione essa opção.

   - **Criar nova versão após substituição**: selecione esta opção se quiser criar uma nova versão do tópico no qual você escolher substituir o texto. Você também pode fornecer comentários de versão que serão adicionados com cada arquivo atualizado.

     Se você não selecionar essa opção, as alterações serão salvas na versão atual do tópico e nenhuma nova versão será criada.

   - **Incluir referência indireta**: selecione essa opção se desejar pesquisar a cadeia de caracteres nas referências indiretas também no mapa DITA. Por padrão, isso fica desativado para que a pesquisa seja executada somente nas referências diretas.

1. Informe o termo ou texto de pesquisa que deseja localizar.

1. Insira o texto pelo qual deseja substituir o termo de pesquisa.

1. Pressione Enter ou selecione **Pesquisar** ícone \( ![](images/search-icon.svg)\) para realizar a pesquisa.
1. Selecione um arquivo na lista de resultados da pesquisa. O arquivo é aberto na área de edição de conteúdo com o termo pesquisado realçado no conteúdo.

1. Clique em **Substituir ocorrência única** \( ![](images/replace-icon.svg)\) para substituir o termo de pesquisa destacado no tópico ou clique em Próxima correspondência ![](images/next-match-in-search.png) ou ![](images/previous-match-in-search.png) Anterior Corresponder para mover para a próxima ocorrência ou ocorrência anterior do texto.

1. Clique em **Substituir tudo no arquivo** \( ![](images/replace-all-in-file-icon.svg)\) para substituir todas as ocorrências do termo pesquisado em um único arquivo pelo termo de substituição em um único clique. Você verá uma notificação depois de substituir todas as ocorrências no arquivo selecionado.

   >[!NOTE]
   >
   > Passe o mouse sobre um arquivo da lista de resultados da pesquisa para ver o ícone Substituir tudo no arquivo à direita. Você também obtém o ícone Ignorar arquivo para remover o arquivo do resultado da pesquisa. Os arquivos que você ignora são removidos da lista e o termo pesquisado não é substituído neles.

1. Clique em **Substituir tudo** \( ![](images/replace-all-in-file-icon.svg)\) à direita na parte superior da lista para substituir todas as ocorrências do termo pesquisado em todos os arquivos pelo termo de substituição em um único clique.

   >[!NOTE]
   >
   > Para ativar o **Substituir tudo** , o administrador do sistema deverá selecionar a opção **Ativar Substituir tudo** no **Geral** guia em **Configurações do editor**.


Somente uma operação de substituição total pode ser executada de cada vez em todo o sistema. Até que a operação esteja sendo executada, você verá o status &quot;Substituir tudo em andamento&quot;. Você também pode abortar a operação replace all no meio ou ver o relatório de log. Se você suspender a operação, receberá uma notificação sobre ela na sua Caixa de entrada. Você receberá uma notificação de sucesso depois de substituir todas as ocorrências no arquivo selecionado.

![](images/replace-all-in-progress.png){width="400" align="left"}

Você também pode usar a variável **Localizar no mapa** opção no **Opções** menu de um mapa para localizar e substituir texto em um mapa. Essa opção aparece para um mapa aberto no painel de repositório ou na exibição de mapa.

![](images/map-options-menu.png){width="550" align="left"}

## Área de edição de conteúdo {#id2051EB000UI}

A área de edição de conteúdo é onde o conteúdo do tópico ou mapa é exibido. Você faz todas as edições de conteúdo nesta área. Ele fornece uma visualização WYSIWYG do conteúdo que você está editando. É possível abrir vários tópicos ao mesmo tempo, que são exibidos em suas respectivas guias.

Por padrão, é possível exibir os títulos dos arquivos nas guias. Ao passar o mouse sobre um arquivo, é possível visualizar o título do arquivo e o caminho do arquivo como uma dica de ferramenta.
>[!NOTE]
>
> Como administrador, você também pode optar por exibir a lista de arquivos por nomes de arquivo nas guias. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).

Abaixo da guia do arquivo, você tem a navegação estrutural do elemento na localização atual do cursor. No canto superior direito da área de edição de conteúdo, o número da versão do tópico atual é exibido.

![](images/content-editing-area.png){width="650" align="left"}

## Painel direito {#id2051EB003YK}

O painel direito é um painel persistente que contém informações sobre o documento selecionado no momento.

>[!NOTE]
>
> O painel direito é redimensionável. Para redimensionar o painel, coloque o cursor no limite do painel, o cursor se transforma em uma seta de duas pontas, clique e arraste para redimensionar a largura do painel.

O painel direito fornece acesso aos seguintes recursos:

**Propriedades de conteúdo** -  ![](images/content-properties-icon.svg)

Você pode acessar o recurso Propriedades de conteúdo clicando no ícone Propriedades de conteúdo no painel direito. O painel Propriedades de conteúdo contém informações sobre o tipo de elemento atualmente selecionado no documento e seus atributos.
É possível adicionar, editar ou excluir facilmente os atributos.

1. Clique em **+ Adicionar**.

   ![atributos em propriedades de conteúdo](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. No **Atributo** selecione o atributo na lista suspensa e especifique o valor de um atributo.  Clique em **Adicionar**.

   ![painel atributos com vários atributos ](images/attributes-multiple-properties.png){width="300" align="left"}

1. Para editar o atributo, passe o mouse sobre ele e selecione **Editar** ![ícone de edição](images/edit_pencil_icon.svg).
   ![editar atributos](images/edit-attributes-content-properties.png){width="300" align="left"}

1. Para excluir o atributo, passe o mouse sobre ele e selecione **Excluir** ![ícone de exclusão](images/Delete_icon.svg).


>[!NOTE]
>
> Mesmo que seu tópico tenha conteúdo referenciado, é possível adicionar atributos a ele usando o painel de propriedades.

Se o administrador tiver criado um perfil para atributos, você obterá esses atributos junto com seus valores configurados. Usando o painel de propriedades de conteúdo, você pode escolher esses atributos e atribuí-los ao conteúdo relevante em seu tópico. Dessa forma, você também pode criar conteúdo condicional, que pode ser usado para criar saída condicional. Para obter mais informações sobre a geração de saída usando predefinições condicionais, consulte [Usar predefinições de condição](generate-output-use-condition-presets.md#).



**Propriedades do arquivo** -  ![](images/topic-properties-icon.svg)

Visualize as propriedades do arquivo selecionado clicando no ícone Propriedades do arquivo no painel direito. As Propriedades do arquivo têm as duas seções a seguir:

**Geral**

A seção Geral fornece acesso aos seguintes recursos:

![file-properties](images/file-properties-general.png){width="300" align="left"}

- **Nome**: exibe o nome de arquivo do tópico selecionado. O nome do arquivo tem um hiperlink para a página de propriedades do arquivo selecionado.
- **ID**: exibe a ID do tópico selecionado.
- **Tags**: Essas são as tags de metadados do tópico. Eles são definidos no campo tags na página propriedades. Você pode digitá-los ou selecioná-los na lista suspensa.  As tags são exibidas na lista suspensa. Para excluir uma tag, selecione o ícone de cruz ao lado da tag.
- **Editar mais propriedades**: é possível editar mais propriedades na página de propriedades do arquivo.
- **Idioma**: mostra o idioma do tópico. Ele é definido no campo Language na página de propriedades.
- **Criado em**: exibe a data e a hora em que o tópico foi criado.
- **Retirado por**: mostra o usuário que fez check-out do tópico.
- **Estado do documento**: Você pode selecionar e atualizar o estado do documento do tópico aberto no momento. Para obter mais detalhes, consulte [Estado do documento ](web-editor-document-states.md#)*.*

**Nota:** Você pode copiar os valores de atributo de vários campos nas propriedades do arquivo para a área de transferência.

**Referências**

A seção Referências fornece acesso aos seguintes recursos:

![](images/file-properties-references.png){width="300" align="left"}

- **Usado em**: as referências Usadas em listam os documentos nos quais o arquivo atual está sendo referenciado ou usado.
- **Links de saída:** Os Links de Saída listam os documentos referenciados no documento atual.

Por padrão, é possível visualizar os arquivos por títulos. Ao passar o mouse sobre um arquivo, é possível visualizar o título do arquivo e o caminho do arquivo como uma dica de ferramenta.
>[!NOTE]
>
> Como administrador, você também pode optar por exibir a lista de arquivos por nomes de arquivo no Editor da Web. Selecione o **Nome do arquivo** opção do **Exibir arquivos por** seção em **Preferências do usuário** ![](images/user_preference_editor_icon.svg).

**Nota:** Todas as referências Usadas em e de Saída têm hiperlinks para os documentos. É possível abrir e editar facilmente os documentos vinculados.

Além de abrir arquivos, você também pode executar muitas ações usando o **Opções** na seção Referências. Algumas das ações que você pode executar incluem Editar, Visualizar, Copiar UUID, Copiar caminho, Adicionar a favoritos, Propriedades e Abrir painel de mapa.

**Revisão** -  ![](images/review-icon.svg)

Clicar no ícone Revisar abre o painel de revisão, no qual é possível criar uma tarefa de revisão para o documento aberto no momento.

![](images/review-panel-before-opening.png){width="300" align="left"}

Se você tiver criado vários projetos de revisão, é possível selecionar um no menu suspenso e acessar os comentários da revisão.

Usando o painel de revisão, você pode exibir e postar respostas aos comentários fornecidos sobre o tópico. Você pode aceitar ou rejeitar os comentários um por um.

Para obter mais informações, consulte [Comentários de revisão de endereço](review-address-review-comments.md#).

**Alterações controladas** -  ![](images/track-change-icon.svg)

Usando o recurso Alterações controladas do painel direito, você pode exibir as informações de todas as atualizações feitas em um documento. Você também pode procurar por atualizações específicas feitas no documento.

>[!NOTE]
>
> O recurso Alterações controladas mostra todas as atualizações que foram controladas usando o recurso Habilitar/Desabilitar Controlar alterações da barra de ferramentas principal. Para obter mais detalhes, consulte [Ativar/desativar o controle de alterações](#id205DF0203Y4).

**Tópico pai:**[ Trabalhar com o editor da Web](web-editor.md)
