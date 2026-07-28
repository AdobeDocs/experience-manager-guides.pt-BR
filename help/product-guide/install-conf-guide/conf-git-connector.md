---
title: Configurar um conector Git no AEM Guides
description: Saiba como configurar um Git no Experience Manager Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: eb30be6342a50ba52e8afd8b4a31148b3ad9c340
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---

# Criar e configurar o Conector Git na interface do usuário

>[!NOTE]
>
> Esse recurso está desativado por padrão. Para ativar seu ambiente, entre em contato com a equipe de sucesso do cliente.

Use a ferramenta Fontes de dados no Experience Manager Guides para criar e configurar um conector Git a partir da interface do usuário. Após configurar o conector com sucesso, você pode usá-lo para importar conteúdo de um repositório Git para o Experience Manager Guides.

>[!NOTE]
>
> Antes de começar, verifique se o Conector Git está implantado em seu projeto do Cloud Manager. Para obter detalhes, consulte [Adicionar Conector Git ao seu projeto do Cloud Manager.](#add-git-connector-to-your-cloud-manager-project)


1. Selecione o link **Adobe Experience Manager** na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas.
1. Selecione o bloco **Fontes de Dados**. A página **Fontes de Dados** é exibida.
1. Selecione **Criar**.
1. Na lista de conectores de fonte de dados, selecione **GitHub**.

   ![](assets/github-connector-tile.png){width="600"}

1. Selecione **Próximo**.
1. Insira os detalhes de configuração e conexão.

   ![](assets/conf-git-connector.png){width="600"}

   >[!TIP]
   >
   >* Focalizar <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo ao campo para ver mais detalhes sobre ele.
   >* Os campos com * são obrigatórios. Por exemplo, você pode inserir os detalhes a seguir para o conector do Elasticsearch.

   &#x200B;- **Nome**: insira o nome da fonte de dados.
   &#x200B;- **Caminho raiz do AEM de destino**: insira o caminho no repositório do AEM onde o conteúdo importado do Git deve ser armazenado.
   &#x200B;- **Filtro de tipo de arquivo (inclusão)**: especifique os tipos de arquivo a serem incluídos durante a importação.
   &#x200B;- **Caminho excluído (regex)**: especifique os padrões de caminho a serem excluídos da importação.
   &#x200B;- **Tipo de autenticação**: selecione o tipo de autenticação na lista suspensa. Atualmente, o **PAT (Personal Access Token)** é o único método de autenticação com suporte. Insira o PAT durante a configuração do conector para autenticar e acessar o repositório Git.

     Saiba como [Gerar um token de acesso pessoal do GitHub](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic).

     Ao selecionar escopos durante a geração do PAT no GitHub, habilite os seguintes escopos:
     &#x200B;- **repositório**: marque a caixa de seleção de nível superior. Todos os subescopos são selecionados automaticamente, concedendo acesso ao conteúdo do repositório, status de confirmação e implantações.
     &#x200B;- **admin:org**: Selecione apenas **read:org**. Isso é necessário para resolver a organização e a associação à equipe.
   * **URL do repositório**: Insira a URL do repositório Git da qual o conteúdo deve ser importado.
   * **Ramificação**: insira a ramificação a ser usada para importação de conteúdo.

1. Teste a conexão. O botão **Testar conexão** só é habilitado depois que você insere os detalhes necessários. Se os detalhes da conexão estiverem corretos, uma mensagem de sucesso será exibida. Caso contrário, uma mensagem de erro será exibida.

   ![](assets/git-connector-test-connection.png){width="600"}

1. Selecione **Salvar** na parte superior para salvar o conector.

   O botão Salvar só é ativado depois que todos os detalhes necessários são inseridos e a conexão é bem-sucedida. Se o conector for salvo com êxito, você poderá exibir o conector Github configurado na página **Fontes de dados**.

   ![](assets/git-connector-connected.png){width="600"}

## Adicionar o Conector Git ao seu projeto do Cloud Manager

Antes de o Conector Git estar disponível para configuração na página **Fontes de dados**, ele deve ser incorporado como uma dependência no seu projeto do AEM. Execute as seguintes etapas para adicionar a dependência:

1. No `all/pom.xml` do seu projeto do AEM, adicione o Conector Git como uma dependência em `<dependencies>`:

   ```xml
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-github</artifactId>
       <version>1.0.0</version>
   </dependency>
   ```

1. No mesmo `pom.xml`, adicione a dependência à seção `<embeddeds>` da configuração `filevault-package-maven-plugin`:

   ```xml
   <embedded>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-github</artifactId>
       <type>jar</type>
       <target>/apps/YOUR-vendor-packages/content/install</target>
   </embedded>
   ```

   Substitua `YOUR-vendor-packages` pelo nome do pacote do fornecedor do projeto.

1. Confirme e envie as alterações para o repositório Git do Cloud Manager e execute o pipeline para implantá-las.

Depois que o pipeline for concluído, o Conector Git será instalado em seu ambiente e estará disponível para configuração na página **Fontes de dados**.





