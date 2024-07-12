---
title: Configurar um conector de fonte de dados usando ferramentas
description: Saiba como configurar um conector de fonte de dados usando as ferramentas.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Configurar um conector de fonte de dados na interface do usuário

O Experience Manager Guides vem com a ferramenta **Fontes de Dados** que ajuda você a configurar conectores prontos para uso para fontes de dados. Você pode configurar conectores para bancos de dados JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce e Elasticsearch.

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
   >* Focalizar <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo ao campo para ver mais detalhes sobre ele.
   > * Os campos com * são obrigatórios. Por exemplo, você pode inserir os seguintes detalhes para o conector Elasticsearch.

   * **Nome**: insira o nome da fonte de dados.
   * Tipo de autenticação: selecione o tipo de autenticação no menu suspenso. Por exemplo, Autenticação básica de nome de usuário e senha
   * **Nome de usuário**: digite seu nome de usuário.
   * **Senha**: digite seu nome de usuário e senha.
   * **URL**: adicionar a URL da API.

1. Selecione **Testar conexão**. Você pode exibir o botão **Testar Conexão** habilitado somente após adicionar os detalhes necessários. Veja uma mensagem de sucesso se os detalhes da conexão estiverem corretos. Caso contrário, você poderá exibir uma mensagem de erro.



1. Selecione **Salvar** na parte superior para salvar o conector.     Exiba o botão **Salvar** habilitado depois que você preencher todos os detalhes e a conexão for bem-sucedida.


   Se o conector for salvo com sucesso, você poderá exibir a fonte de dados conectada na página.

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
