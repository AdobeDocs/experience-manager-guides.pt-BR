---
title: Configurar um conector de fonte de dados usando ferramentas
description: Saiba como configurar um conector de fonte de dados usando as ferramentas.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 873542cb2e8e1b7e80e0ecc113cae4f603b18592
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 0%

---

# Configurar um conector de fonte de dados na interface do usuário

Os Guias do Experience Manager vêm com a tag **Fontes de dados** ferramenta que ajuda a configurar conectores prontos para uso para fontes de dados. Você pode configurar os conectores JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch e Generic REST Client.


Além desses conectores prontos para uso, o Experience Manager Guides fornece os conectores para fontes de dados do Salsify, Akeneo e Microsoft Azure DevOps Boards (ADO). Você pode baixar e instalar esses conectores de código aberto na [Repositório central Maven](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). Os usuários podem então configurar esses conectores.
Saiba como [instalar um conector de código aberto](#install-open-source-connector).



Você também pode se conectar a arquivos de dados JSON usando um conector de arquivos. Faça upload do arquivo JSON do seu computador ou navegue pelos ativos do Adobe Experience Manager. Em seguida, crie trechos de conteúdo ou tópicos usando os geradores.

Para configurar um conector, execute as seguintes etapas:

1. Selecione o **Adobe Experience Manager** na parte superior e escolha Ferramentas.
1. Selecionar **Guias** na lista de ferramentas.
1. Selecione o **Fontes de dados** bloco. A variável **Fontes de dados** é exibida. Você pode exibir as fontes de dados conectadas.

   Você pode alternar entre as **Exibição de lista** ou **Exibição lado a lado** para exibir as várias fontes de dados conectadas como uma lista ou como blocos.

   <img src="./assets/data-sources-create-window.png" alt= "origens de dados listadas na página origens de dados" width="800">

   *Exibir ou Criar um conector de origem de dados.*
1. Clique em **Criar**.
1. Selecione o banco de dados para o qual deseja criar o conector. Por exemplo, o conector Elasticsearch.
   >[!NOTE]
   >
   >Todos os bancos de dados prontos para uso disponíveis são listados.

1. Clique em **Avançar**.
1. Insira os detalhes de configuração e conexão de acordo com o banco de dados.

   >[!TIP]
   >
   >* Focalizar <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo ao campo para exibir mais detalhes sobre ele.
   > * Os campos com * são obrigatórios. Por exemplo, você pode inserir os seguintes detalhes para o conector Elasticsearch.

   * **Nome**: digite o nome da fonte de dados.
   * **Tipo de autenticação**: selecione o tipo de autenticação no menu suspenso. Por exemplo, Autenticação básica de nome de usuário e senha
   * **Nome de usuário**: digite seu nome de usuário.
   * **Senha**: digite seu nome de usuário e senha.
   * **URL**: adicione o URL da API.


1. Selecione o **Excluir modelos de fábrica** opção para excluir os modelos de fábrica de serem usados para geração de tópico e snippet. Eles não aparecerão sob o **Modelo de mapeamento de dados** na lista suspensa  **Adicionar gerador de trecho de conteúdo** ou o **Adicionar gerador de tópico** caixa de diálogo.


1. Selecionar **Testar conexão**. É possível exibir a **Testar conexão** botão ativado somente após adicionar os detalhes necessários. Veja uma mensagem de sucesso se os detalhes da conexão estiverem corretos. Caso contrário, você poderá exibir uma mensagem de erro.



1. Selecionar **Salvar** na parte superior para salvar o conector.     Exibir o **Salvar** botão ativado depois de preencher todos os detalhes e a conexão for bem-sucedida.


   Se o conector for salvo com sucesso, você poderá exibir a fonte de dados conectada na página.

**Conectar a vários recursos**

Você pode adicionar ou usar vários recursos com base em URLs diferentes para alguns conectores, como Cliente REST genérico, Salsify, Akeneo e placas DevOps (ADO) do Microsoft Azure. Em seguida, conecte-se com eles para criar trechos de conteúdo ou tópicos usando os geradores para eles.

Execute as seguintes etapas para criar um recurso:

1. Selecionar ![ícone adicionar](assets/Add_icon.svg) no **Seção de recurso de URL** para adicionar um recurso para cada URL.
1. Configure todos os detalhes no **Adicionar recurso** caixa de diálogo.
1. Clique em **Adicionar**.
1. É possível editar ![ícone editar](assets/edit_pencil_icon.svg) ou excluir ![excluir](assets/Delete_icon.svg) o recurso na lista de recursos de URL.

1. Você também pode usar os recursos padrão disponíveis para fontes de dados como Salsify, Akeneo e Microsoft ADO. Ative as opções DESATIVADAS para o recurso que você não deseja configurar para uma fonte de dados.

Isso ajuda a buscar dados rapidamente de qualquer um dos recursos de uma fonte de dados específica em um único trecho de conteúdo ou tópico.



## Instalar um conector de código aberto{#install-open-source-connector}

Para publicar uma dependência presente na [Repositório central Maven](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) para os Cloud Service, é necessário incluir e incorporar a dependência de um conector de código aberto.

1. Adicionar a dependência no `all/pom.xml`  no código do projeto Git do Cloud Manager. Por exemplo, você pode adicionar a seguinte dependência para o conector de fonte de dados das placas DevOps do Microsoft Azure.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Incorpore a dependência adicionada.

       &quot;
       &lt;embedded>
       &lt;groupid>com.adobe.aem.addon.guides&lt;/groupid>
       &lt;artifactid>konnect-azure-devops&lt;/artifactid>
       &lt;type>jar&lt;/type>
       &lt;target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install&lt;/target>
       &lt;/embedded>
       &quot;
   
1. Execute o pipeline para aplicar as alterações nos Cloud Service.
O conector é instalado em seu ambiente.


## Recursos disponíveis para um conector

* Alternar entre as opções **Exibição de lista** ou **Exibição lado a lado**  para exibir as várias fontes de dados conectadas como uma lista ou como blocos.
* Marque a caixa de seleção de um único conector. Clique em **Selecionar tudo** para selecionar todos os conectores. Você pode clicar em **Desmarcar tudo** quando todos os conectores estiverem selecionados.

<img src="./assets/data-sources-features.png" alt= "recursos das fontes de dados na página fontes de dados" width="800">

*Editar, reconectar, duplicar ou excluir um conector de origem de dados.*

Você pode usar os seguintes recursos para o conector no **Fontes de dados** página:

* **Editar**: edite os detalhes de configuração do conector selecionado.

* **Reconectar**: reconecte a um conector desconectado.

* **Duplicar**: crie um novo conector duplicado usando o conector atual como base. O conector duplicado é criado com um sufixo (como connectorname_1) por padrão. Por exemplo, sample-elastic-search_1.
Você verá um erro se existir um conector com o mesmo nome.

* **Excluir**: exclua o conector selecionado.


Após configurar a fonte de dados, o conector será listado no **Painel Fontes de dados** no Editor da Web. Em seguida, você pode se conectar à fonte de dados e inserir um trecho de conteúdo em seus tópicos. Para obter mais detalhes, consulte [Inserir um trecho de conteúdo da sua fonte de dados](../user-guide/web-editor-content-snippet.md).
