---
title: Configurar o assistente do Guides para pesquisar conteúdo
description: Saiba como configurar o Assistente de guias para pesquisar conteúdo
source-git-commit: 8ac0ed6b867a3efdef750cb19ed4955a67def9ee
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---


# Configure o Assistente de guias alimentado por IA para pesquisar conteúdo

Como administrador, você pode configurar o recurso Assistente de guias para os autores. O serviço do Assistente de guias é protegido pela autenticação baseada em autenticação do Adobe IMS. Integre seu ambiente com os workflows de autenticação segura baseada em token do Adobe e comece a usar o novo recurso Assistente de guias. As configurações a seguir ajudam a adicionar a guia **Configuração de IA** a um perfil de pasta. Depois de adicionado, você pode usar o recurso Assistente de guias no Editor da Web.

## Criar configurações do IMS no Adobe Developer Console

Execute as seguintes etapas para criar configurações do IMS no Adobe Developer Console:

>[!NOTE]
>
>Se você já tiver criado um projeto OAuth para configurar o recurso Sugestões inteligentes ou a publicação baseada em microsserviços, ignore as etapas a seguir para criar o projeto.

1. Iniciar [Adobe Developer Console](https://developer.adobe.com/console).
1. Depois de fazer logon no Developer Console, você verá a tela **Página inicial**. A tela **Página Inicial** é onde você pode encontrar facilmente informações e links rápidos, incluindo links de navegação superior para Projetos e Downloads.
1. Para criar um novo projeto vazio, selecione **Criar novo projeto** nos links **Início rápido**.
   ![Links de início rápido](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Criar um novo projeto.*

1. Selecione **Adicionar API** na tela **Projetos**.  A tela **Adicionar uma API** é exibida. Esta tela exibe todas as APIs, Eventos e serviços disponíveis para produtos e tecnologias Adobe com os quais você pode desenvolver aplicativos.

1. Selecione a **API de Gerenciamento de E/S** para adicioná-la ao seu projeto.
   ![API de gerenciamento de E/S](assets/confi-ss-io-management.png)
   *Adicionar a API de Gerenciamento de E/S ao seu projeto.*

1. Crie uma nova **credencial OAuth** e salve-a.
   ![Bloco de credenciais do OAuth na API de configuração](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Configure a credencial OAuth para sua API.*

1. Na guia **Projetos**, escolha a opção **Servidor OAuth para Servidor** e selecione as credenciais recém-criadas.

1. Selecione o link **Servidor a Servidor OAuth** para exibir os detalhes de credencial do seu projeto.

   ![credenciais conectadas](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Conecte-se ao projeto para exibir os detalhes da credencial.*

1. Retorne à guia **Projetos** e selecione **Visão geral do projeto** à esquerda.

   <img src="assets/project-overview.png" alt="visão geral do projeto" width="500">

   *Introdução ao novo projeto.*

1. Clique no botão **Baixar** na parte superior para baixar o serviço JSON.

   <img src="assets/download-json.png" alt="baixar json" width="500">

   *Baixar detalhes do serviço JSON.*

Você configurou os detalhes de autenticação do OAuth e baixou os detalhes do serviço JSON. Mantenha esse arquivo em mãos conforme necessário na próxima seção.

### Adicionar a configuração IMS ao ambiente

Execute as seguintes etapas para adicionar a configuração IMS ao ambiente:

1. Abra o Experience Manager e selecione seu programa, que contém o ambiente que você deseja configurar.
1. Alterne para a guia **Ambientes**.
1. Selecione o nome do ambiente que deseja configurar. Você deve ir para a página **Informações sobre o ambiente**.
1. Alterne para a guia **Configuração**.
1. Atualize o campo JSON SERVICE_ACCOUNT_DETAILS. Certifique-se de usar o mesmo nome e configuração fornecidos na captura de tela a seguir.

![configuração da conta de serviço ims](assets/ims-service-account-config.png){width="800" align="left"}


*Adicionar os detalhes de configuração do ambiente.*




Depois de adicionar a configuração IMS ao ambiente, execute as seguintes etapas para vincular essas propriedades ao AEM Guides usando OSGi:

1. Em seu código de projeto Git do Cloud Manager, adicione os dois arquivos abaixo (para conteúdo de arquivo, exibir [Apêndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Certifique-se de que os arquivos recém-adicionados estejam sendo cobertos pelo seu `filter.xml`.
1. Confirme e envie suas alterações do Git.
1. Execute o pipeline para aplicar as alterações ao ambiente.

Depois disso, você poderá usar o recurso **Assistente de Guias**.



## Apêndice {#appendix}

**Arquivo**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Conteúdo**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


Depois de configurado, o ícone do **Assistente de Guias** ![Assistente de Guias](assets/guides-assistant-icon.svg) é exibido no painel direito do Editor da Web. Selecione o ícone para exibir o painel do **Assistente de Guias**.
Para obter mais detalhes, consulte a seção [Assistente de guias alimentados por IA para pesquisar conteúdo](../user-guide/ai-based-guides-assistant.md) no Guia do Usuário do Experience Manager.
