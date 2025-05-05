---
title: Baixar e instalar modelos do AEM Sites
description: Saiba como baixar e instalar modelos do AEM Sites
feature: Installation
role: Admin
level: Experienced
source-git-commit: 5a44836c75481256d9ae4e86952cbe1ec471e152
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 0%

---


# Baixar e instalar modelos do AEM Sites

Execute as seguintes etapas para baixar e instalar modelos do AEM Sites no Experience Manager Guides para Software no local:


## Instalação do pacote

1. Baixar os pacotes a seguir

   - Componentes: [guides-components-all.zip](https://github.com/adobe/aemg-sites-components/releases/tag/v1.0.0)

   - Sites para Software Local: [Documentação](https://github.com/adobe/aemg-docs/releases/tag/v1.0.0)

1. Faça logon na instância do AEM e navegue até o Gerenciador de pacotes da CRX. O URL padrão para acessar o gerenciador de pacotes é:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   O Gerenciador de pacotes gerencia os pacotes na sua instalação local do AEM. Para obter mais informações sobre como trabalhar com o Gerenciador de Pacotes, consulte [Como trabalhar com pacotes](https://helpx.adobe.com/br/experience-manager/6-5/sites/administering/using/package-manager.html) na documentação do AEM.

1. Para carregar o pacote, clique em **Carregar Pacote**.

1. Na caixa de diálogo **Carregar Pacote**, navegue até o arquivo que você baixou na Etapa 1 e clique em **OK**.

   O pacote é carregado para a instância do AEM.

1. Para instalar o pacote, clique em **Instalar**.

1. Na caixa de diálogo **Instalar Pacote**, clique em **Instalar** para instalar os pacotes.


## Configurar os modelos a serem usados com as predefinições do AEM Sites

Depois que os pacotes forem instalados, um site chamado **AEMG** será criado na interface do usuário do Sites. Este site de exemplo mostra como você pode configurar a estrutura do site para gerar a saída do AEM Sites. Isto é apenas uma amostra. Você pode criar sites personalizados de acordo com suas necessidades.

![páginas de exemplo do AEMG Sites](assets/aemg-sites-sample-pages.png)


**AEMG** contém os seguintes componentes.
- Uma pasta para o idioma inglês (EN) está presente na pasta **AEMG**. Você pode criar cópias de idioma semelhantes de acordo com seus requisitos. Por exemplo, um site multilíngue inclui cópias em inglês (EN), alemão (DE) e francês (FR).  Saiba mais sobre como criar uma cópia de idioma usando o [Assistente de Cópia de Idioma](https://experienceleague.adobe.com/pt-br/docs/experience-manager-65/content/sites/administering/introduction/tc-wizard).
- Na pasta do idioma inglês (en), a Experience Manager Guides fornece várias páginas de exemplo prontas para uso, como **Pesquisa**, **Entrar**, **Documentação** e **Suporte**.

- **Docs** é a página inicial de documentação de exemplo. Ele serve como um local central para toda a documentação relacionada ao produto
O e o exibem cada produto para o qual a documentação está disponível como blocos individuais.

- Junto com a Página inicial da documentação, há páginas de exemplo para **Pesquisa**, **Logon** e **Suporte**. Você pode personalizar essas amostras de acordo com seus requisitos.
- Você pode ter home pages para produtos individuais, como Product1. Uma página de exemplo **Product1** está presente em **Docs**, que é a Página Inicial de Documentação.

- O Experience Manager Guides também fornece os seguintes modelos predefinidos:

   - Modelo de **Página de conteúdo**: use este modelo para criar as páginas padrão que contêm a maior parte do conteúdo do site do produto. Eles podem incluir texto, imagens, vídeos e outros elementos de conteúdo. Este modelo contém somente o cabeçalho e o rodapé. Personalize e use-o para criar qualquer página de acordo com seus requisitos. Por exemplo, você pode criar a página de suporte ou a página de logon do seu produto.
   - Modelo **Página inicial**: a página de aterrissagem principal de um site, que inclui uma visão geral, seções principais como os elementos e recursos principais, e links de navegação. Por exemplo, a página principal de um produto ABC se conecta às outras páginas de conteúdo ou recursos.
   - Modelo de **Página de Tópico**: as páginas usadas para organizar e apresentar conteúdo baseado em tópico. Por exemplo, um guia do usuário contém páginas de tópicos diferentes, cada uma contendo um tópico específico relacionado aos recursos e à solução de problemas.

  ![Modelo de sites](assets/sites-ui-templates.png)

Use esses exemplos e modelos para gerar suas saídas do AEM Sites:
- Uma página inicial do produto corresponde a uma página inicial de mapa e é criada usando o modelo Página inicial. Selecione esse caminho na predefinição do AEM Sites para publicar o conteúdo do mapa sob ele. A página inicial do produto pode incluir outras páginas iniciais.
- Por exemplo, você tem um produto como o Experience Manager Guides e precisa de três manuais para usuários, administradores e desenvolvedores.  Crie uma página inicial para cada manual usando o modelo Página inicial e selecione a página inicial correspondente na predefinição de saída do AEM Sites.

Saiba mais sobre como criar e configurar as [predefinições do AEM Sites no Editor da Web](../user-guide/generate-output-aem-site-web-editor.md).

## Criar uma página inicial usando o modelo

Execute as seguintes etapas para criar a página inicial do seu produto:
1. Depois que o pacote for instalado, selecione **Sites** na Navegação Global.
1. Selecione o modelo &quot;AEMG Docs&quot; instalado na interface do usuário do Sites.
1. Na interface do usuário do Sites, clique no botão **Criar** no canto superior direito.
1. Selecione **Página** na lista suspensa **Criar**.
1. Selecione **Página Inicial** e clique em **Avançar**.
1. Insira o título do site e o nome do site e clique em **Criar** no canto superior direito. Um modelo de site AEM é criado usando o modelo de site **Página Inicial**. Por exemplo, você pode criar uma página inicial para o seu produto `Product ABC`.


>[!NOTE]
>
>Depois de criar a página inicial, você pode usar este caminho como o **Caminho do Publish** para gerar a saída de suas predefinições do AEM Sites. Por exemplo, `aemg-docs-en/docs/product-abc`.

## Editar modelos de tópico para o AEM Sites

Você também pode personalizar os modelos de tópico para sua AEM Sites. Você pode editar o conteúdo ou configurar as propriedades dos diferentes componentes do AEM em seu tópico. Por exemplo, você pode adicionar ou remover componentes de acordo com seus requisitos.\
Execute as seguintes etapas para editar os modelos de tópico:
1. Selecione o template que deseja editar.
1. Selecione o ícone **Editar** na parte superior.

O Editor de modelo AEM é aberto. Você pode editar seu modelo de tópico. Saiba mais sobre [Criação de Modelos de Página](https://experienceleague.adobe.com/pt-br/docs/experience-manager-65/content/sites/authoring/siteandpage/templates#editing-a-template-structure-template-author).


## Personalizar modelos existentes do AEM Sites

Além dos modelos predefinidos, você também pode usar seus modelos existentes com as predefinições do AEM Sites. Execute as seguintes etapas para personalizar modelos existentes do AEM Sites:

### Configuração do modelo

Você precisa dos dois tipos de modelos a seguir:

- Categoria ou modelo de aterrissagem: esse modelo é usado para a página de aterrissagem da documentação do produto e corresponde a um mapa DITA.  A página do site AEM para um mapa DITA é gerada usando esse modelo. Você pode usar esse template em qualquer nível.
- Adicione um componente de texto ao modelo existente. O componente de texto deve ter uma propriedade obrigatória, `text="$category.html$"`.
- Por exemplo, você pode escolher templates de we-retail e usar o template de página de seção como o template de página de aterrissagem do mapa DITA. Para fazer isso, faça as alterações conforme mostrado na seguinte captura de tela:
  ![modelo de página de seção](assets/customize-existing-aem-templates-section.png)
   - Página de detalhes ou Modelo de página de tópico: use este modelo para o conteúdo dos tópicos de um mapa. Todas as páginas de sites com conteúdo DITA/XML são criadas usando modelos de página de tópico. Para criar esses modelos, há dois pré-requisitos:
      - Adicione um componente de texto ao modelo, contido em um componente de contêiner, com uma propriedade obrigatória. `text="$topic.content$"`.

        ![modelo de página de contêiner](assets/customize-existing-aem-templates-container.png)
      - Reflita o mesmo contêiner e componente de texto na estrutura do mesmo modelo, como mostrado na seguinte captura de tela:

        ![estrutura do modelo de contêiner](assets/customize-existing-aem-templates-structure.png)

### Marcar página de categoria como contêiner da documentação

Supondo que uma hierarquia de site seja criada para as páginas de documentação usando o modelo anterior, escolha uma das páginas de categoria criadas nessa hierarquia de site. Adicione uma tag à página de categoria como um container de Documentação, fornecendo uma ID.
Para fazer isso, atribua um valor `category-page` à propriedade `id`. Consulte a seguinte captura de tela:

![página de categoria de marca](assets/customize-existing-aem-templates-tagging.png)