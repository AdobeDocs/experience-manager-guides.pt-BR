---
title: Configurar um conector de fonte de dados usando ferramentas
description: Saiba como configurar um conector de fonte de dados usando as ferramentas.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 0%

---

# Configurar um conector de fonte de dados na interface do usuário

O Experience Manager Guides vem com a ferramenta **Fontes de Dados** que ajuda você a configurar conectores prontos para uso para fontes de dados. Você pode configurar os conectores JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch e Generic REST Client.


Além desses conectores prontos para uso, a Experience Manager Guides fornece os conectores para fontes de dados do Salsify, Akeneo e Microsoft Azure DevOps Boards (ADO). Você pode baixar e instalar esses conectores de código aberto do [repositório central Maven](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). Os usuários podem então configurar esses conectores.
Saiba como [instalar um conector de código aberto](#install-open-source-connector).



Você também pode se conectar a arquivos de dados JSON usando um conector de arquivos. Faça upload do arquivo JSON do seu computador ou navegue pelos ativos do Adobe Experience Manager. Em seguida, crie trechos de conteúdo ou tópicos usando os geradores.

Para configurar um conector, execute as seguintes etapas:

1. Selecione o link **Adobe Experience Manager** na parte superior e escolha Ferramentas.
1. Selecione **Guias** na lista de ferramentas.
1. Selecione o bloco **Fontes de Dados**. A página **Fontes de Dados** é exibida. Você pode exibir as fontes de dados conectadas.

   Você pode alternar entre a **Exibição de Lista** ou a **Exibição de Bloco** para exibir as várias fontes de dados conectadas como uma lista ou como blocos.

   <img src="./assets/data-sources-create-window.png" alt= "origens de dados listadas na página origens de dados" width="800">

   *Exibir ou criar um conector de fonte de dados.*

1. Clique em **Criar**.
1. Selecione o banco de dados para o qual deseja criar o conector. Por exemplo, o conector Elasticsearch.

   >[!NOTE]
   >
   >Todos os bancos de dados prontos para uso disponíveis são listados.

1. Clique em **Avançar**.
1. Insira os detalhes de configuração e conexão de acordo com o banco de dados.

   >[!TIP]
   >
   >* Focalizar <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo ao campo para ver mais detalhes sobre ele.
   >* Os campos com * são obrigatórios. Por exemplo, você pode inserir os detalhes a seguir para o conector do Elasticsearch.

   * **Nome**: insira o nome da fonte de dados.
   * **Tipo de autenticação**: selecione o tipo de autenticação no menu suspenso. Por exemplo, Autenticação básica de nome de usuário e senha
   * **Nome de usuário**: digite seu nome de usuário.
   * **Senha**: digite seu nome de usuário e senha.
   * **URL**: adicionar a URL da API.


1. Selecione a opção **Excluir modelos de fábrica** para impedir que os modelos de fábrica sejam usados para geração de tópico e trecho. Eles não aparecerão na lista suspensa **Modelo de mapeamento de dados** na caixa de diálogo **Adicionar gerador de trecho de conteúdo** ou **Adicionar gerador de tópico**.
1. Selecione **Testar conexão**. Você pode exibir o botão **Testar Conexão** habilitado somente após adicionar os detalhes necessários. Veja uma mensagem de sucesso se os detalhes da conexão estiverem corretos. Caso contrário, você poderá exibir uma mensagem de erro.
1. Selecione **Salvar** na parte superior para salvar o conector.     Exiba o botão **Salvar** habilitado depois que você preencher todos os detalhes e a conexão for bem-sucedida.


   Se o conector for salvo com sucesso, você poderá exibir a fonte de dados conectada na página.

**Conectar a vários recursos**

Você pode adicionar ou usar vários recursos com base em URLs diferentes para alguns conectores, como Cliente REST genérico, Salsify, Akeneo e placas DevOps (ADO) do Microsoft Azure. Em seguida, conecte-se com eles para criar trechos de conteúdo ou tópicos usando os geradores para eles.

Execute as seguintes etapas para criar um recurso:

1. Selecione ![ícone adicionar](assets/Add_icon.svg) na **seção de recurso de URL** para adicionar um recurso para cada URL.
1. Configure todos os detalhes na caixa de diálogo **Adicionar recurso**.
1. Clique em **Adicionar**.
1. Você pode editar o ![ícone de edição](assets/edit_pencil_icon.svg) ou excluir o recurso ![excluir](assets/Delete_icon.svg) da lista de recursos de URL.
1. Você também pode usar os recursos padrão disponíveis para fontes de dados como Salsify, Akeneo e Microsoft ADO. Ative as opções DESATIVADAS para o recurso que você não deseja configurar para uma fonte de dados.

Isso ajuda a buscar dados rapidamente de qualquer um dos recursos de uma fonte de dados específica em um único trecho de conteúdo ou tópico.



## Instalar um conector de código aberto{#install-open-source-connector}

Para publicar uma dependência presente no [repositório central Maven](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) nos Serviços de nuvem, você precisa incluir e incorporar a dependência de um conector de código aberto.

1. Adicione a dependência em `all/pom.xml` no código do projeto Git do Cloud Manager. Por exemplo, você pode adicionar a seguinte dependência para o conector de fonte de dados das placas DevOps do Microsoft Azure.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Incorpore a dependência adicionada.

   ```
   <embedded>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <type>jar</type>
       <target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install</target>
   </embedded> 
   ```

1. Execute o pipeline para aplicar as alterações nos Serviços em nuvem.
O conector é instalado em seu ambiente.


## Recursos disponíveis para um conector

* Alterne entre a **Exibição de Lista** ou a **Exibição de Bloco** para exibir as várias fontes de dados conectadas como uma lista ou como blocos.
* Marque a caixa de seleção de um único conector. Clique em **Selecionar tudo** para selecionar todos os conectores. Você pode clicar em **Desmarcar Tudo** quando todos os conectores estiverem selecionados.

<img src="./assets/data-sources-features.png" alt= "recursos das fontes de dados na página fontes de dados" width="800">

*Editar, reconectar, duplicar ou excluir um conector de fonte de dados.*

Você pode usar os seguintes recursos para o conector na página **Fontes de Dados**:

* **Editar**: edite os detalhes de configuração do conector selecionado.

* **Reconectar**: reconectar a um conector desconectado.

* **Duplicar**: crie um novo conector duplicado usando o conector atual como base. O conector duplicado é criado com um sufixo (como connectorname_1) por padrão. Por exemplo, sample-elastic-search_1.
Você verá um erro se existir um conector com o mesmo nome.

* **Excluir**: excluir o conector selecionado.


Após configurar a fonte de dados, o conector será listado no **painel Fontes de Dados** do Editor da Web. Em seguida, você pode se conectar à fonte de dados e inserir um trecho de conteúdo em seus tópicos. Para obter mais detalhes, exiba [Inserir um trecho de conteúdo da sua fonte de dados](../user-guide/web-editor-content-snippet.md).
