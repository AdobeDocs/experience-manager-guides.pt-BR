---
title: Configurar um conector Git no AEM Guides
description: Saiba como configurar um Git no Experience Manager Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5f626c210e74c6d11e2441f719cfbfeb33bf55c5
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# Criar e configurar o Conector Git na interface do usuário

Use a ferramenta Fontes de dados no Experience Manager Guides para criar e configurar um conector Git a partir da interface do usuário. Após configurar o conector com sucesso, você pode usá-lo para importar conteúdo de um repositório Git para o Experience Manager Guides.


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

   * **Nome**: insira o nome da fonte de dados.
   * **Caminho raiz do AEM de destino**: insira o caminho no repositório do AEM onde o conteúdo importado do Git deve ser armazenado.
   * **Filtro de tipo de arquivo (inclusão)**: especifique os tipos de arquivo a serem incluídos durante a importação.
   * **Caminho excluído (regex)**: especifique os padrões de caminho a serem excluídos da importação.
   * **Tipo de autenticação**: selecione o tipo de autenticação na lista suspensa. Atualmente, o **PAT (Personal Access Token)** é o único método de autenticação com suporte. Insira o PAT durante a configuração do conector para autenticar e acessar o repositório Git.
   * **URL do repositório**: Insira a URL do repositório Git da qual o conteúdo deve ser importado.
   * **Ramificação**: insira a ramificação a ser usada para importação de conteúdo.

1. Teste a conexão. O botão **Testar conexão** só é habilitado depois que você insere os detalhes necessários. Se os detalhes da conexão estiverem corretos, uma mensagem de sucesso será exibida. Caso contrário, uma mensagem de erro será exibida.

   ![](assets/git-connector-test-connection.png){width="600"}

1. Selecione **Salvar** na parte superior para salvar o conector.

   O botão Salvar só é ativado depois que todos os detalhes necessários são inseridos e a conexão é bem-sucedida. Se o conector for salvo com êxito, você poderá exibir o conector Github configurado na página **Fontes de dados**.

   ![](assets/git-connector-connected.png){width="600"}

