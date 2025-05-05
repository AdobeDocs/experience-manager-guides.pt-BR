---
title: Configurar a publicação baseada em microsserviço com a autenticação OAuth para o AEM Guides as a Cloud Service
description: Saiba como configurar a publicação baseada em microsserviços com autenticação OAuth para o AEM Guides.
feature: Microservice in AEM Guides
role: Admin
exl-id: db0c83c7-1ece-4010-b214-f8d806d26bc9
source-git-commit: c51a372dc44921a489219f5ac99e3ad180ccc91d
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 0%

---

# Configurar a publicação baseada em microsserviço com autenticação OAuth

O microsserviço de publicação permite executar grandes cargas de trabalho de publicação simultaneamente no Experience Manager Guides as a Cloud Service e aproveitar a plataforma Adobe I/O Runtime sem servidor, líder do setor.

Para cada solicitação de publicação, o Experience Manager Guides as a Cloud Service um contêiner separado que é dimensionado horizontalmente de acordo com as solicitações do usuário. Dessa forma, você pode executar várias solicitações de publicação e obter um desempenho melhor do que seus grandes servidores locais do Adobe Experience Manager.

>[!NOTE]
>
> A publicação com base em microsserviços no Experience Manager Guides é compatível com os tipos de predefinições de saída PDF (baseado em DITA e nativo), HTML5, JSON e CUSTOM.

Como o serviço de publicação na nuvem é protegido pela autenticação baseada em OAuth do Adobe IMS, execute as seguintes etapas para integrar seus ambientes com fluxos de trabalho de autenticação baseados em token seguro do Adobe e comece a usar a solução de publicação escalável baseada em nuvem.


## Criar configurações do IMS no Adobe Developer Console

**Função necessária para criar as configurações**: Administrador do Sistema

Execute as seguintes etapas para criar configurações de IMS no **Adobe Developer Console**:

>[!NOTE]
>
>Se você já criou um projeto OAuth para configurar as sugestões inteligentes habilitadas pela IA para criação, ignore as etapas a seguir para criar o projeto.

1. Abrir **Developer Console**: `https://developer.adobe.com/console`.

1. Alterne para a guia **Projetos** a partir da parte superior.

   <img src="assets/projects-tab.png" alt="guia projetos" width="500">

   *Selecione a guia **Projetos**&#x200B;no **Adobe Developer Console***

1. Para criar um novo projeto vazio, selecione **Projeto vazio** na lista suspensa **Criar novo projeto**.

   <img src="assets/create-new-project.png" alt="criar novo projeto" width="500">

   *Criar um novo projeto vazio.*

1. Selecione **API** na lista suspensa **Adicionar ao Projeto** para adicionar a API de Gerenciamento de E/S ao seu projeto.

   <img src="assets/add-project.png" alt="adicionar projeto" width="300">

   *Selecione um projeto de API na lista suspensa.*

   <img src="assets/io-management-api.png" alt="gerenciamento de e/s" width="500">

   *Adicionar a API de Gerenciamento de E/S ao seu projeto.*

1. Crie uma nova credencial OAuth e salve-a.

   <img src="assets/microservice-api-oauth.png" alt="gerar par de chaves" width="500">

   *Configure a credencial OAuth para sua API.*


1. Retorne à guia **Projetos** e selecione **Visão geral do projeto** à esquerda.

   <img src="assets/project-overview.png" alt="visão geral do projeto" width="500">

   *Introdução ao novo projeto.*

1. Clique no botão **Baixar** na parte superior para baixar o serviço JSON.

   <img src="assets/download-json.png" alt="baixar json" width="500">

   *Baixar detalhes do serviço JSON.*

Você configurou os detalhes de autenticação do OAuth e baixou os detalhes do serviço JSON. Mantenha esse arquivo em mãos conforme necessário na próxima seção.


## Adicionar a configuração IMS ao ambiente

>[!NOTE]
>
>Se você já tiver criado um projeto OAuth para sugestões inteligentes, poderá reutilizar o mesmo projeto para microsserviços e ignorar as etapas a seguir para adicionar a configuração do IMS ao ambiente.

### Atualizar configuração existente (JWT)   para OAuth shift )

Se você já estiver usando um microsserviço para publicar usando o JWT (obsoleto), execute as seguintes etapas para atualizar as configurações:



1. Abra **Experience Manager** e selecione o programa que contém o ambiente que você deseja configurar.
1. Alterne para a guia **Ambientes**.
1. Selecione o nome do ambiente que deseja configurar. Você deve ir para a página **Informações sobre o ambiente**.
1. Alterne para a guia **Configuração**.

1. Atualize o campo JSON SERVICE_ACCOUNT_DETAILS com o novo arquivo JSON do OAuth baixado.
1. Exclua o campo PRIVATE_KEY.



   <img src="assets/ims-service-account-config.png" alt="configuração da conta de serviço ims" width="500">

   *Atualizar as configurações existentes do ambiente JWT.*

### Primeira configuração

Para usar um microsserviço de publicação pela primeira vez, atualize as configurações de acordo com as seguintes etapas:
1. Abra **Experience Manager** e selecione o programa que contém o ambiente que você deseja configurar.
1. Alterne para a guia **Ambientes**.
1. Selecione o nome do ambiente que deseja configurar. Você deve ir para a página **Informações sobre o ambiente**.
1. Alterne para a guia **Configuração**.

1. Crie uma nova configuração chamada como SERVICE_ACCOUNT_DETAILS. Em valor, adicione o conteúdo do arquivo JSON OAuth que você baixou do console do desenvolvedor .


<img src="assets/jws-service-account-config.png" alt="configuração da conta de serviço ims" width="500">

*Configurar o ambiente pela primeira vez.*


### Alterações no código pela primeira vez para habilitação de publicação baseada em microsserviços

>[!NOTE]
>
> Ignore as seguintes etapas se já estiver usando a publicação com base em microsserviços:

Depois de adicionar a configuração IMS ao ambiente, execute as seguintes etapas para vincular essas propriedades ao Experience Manager Guides usando OSGi:

1. Em seu código de projeto Git do Cloud Manager, adicione os dois arquivos a seguir em `/apps/fmditaCustom/config` (para conteúdo de arquivo, exiba [Apêndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Certifique-se de que os arquivos recém-adicionados estejam sendo cobertos pelo seu `filter.xml`.
1. Confirme e envie suas alterações do Git.
1. Execute o pipeline para aplicar as alterações ao ambiente.

Depois disso, você poderá usar a publicação na nuvem com base em microsserviços.

## Perguntas frequentes


1. Se as configurações de OSGi para usar o microsserviço estiverem ativadas, o processo de publicação funcionará no servidor de Experience Manager local com a mesma base de código?
   * Não, se o sinalizador `dxml.use.publish.microservice` estiver definido como `true`, ele sempre procurará configurações de microsserviço. Defina `dxml.use.publish.microservice` como `false` para que a publicação funcione em seu servidor local.
1. Quanta memória é alocada para o processo DITA ao usar a publicação baseada em microsserviços? Isso é orientado pelo perfil e pelos parâmetros DITA?
   * Com a publicação baseada em microsserviços, a alocação de memória não é orientada pelo perfil e pelos parâmetros DITA. A memória total disponível no container de serviço é de 8 GB, dos quais 6 GB são alocados para o processo DITA-OT.


## Apêndice {#appendix}

**Arquivo**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Conteúdo**:

```
{
"service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**Arquivo**: `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Conteúdo**:
* `dxml.use.publish.microservice`: Alternar para habilitar a publicação baseada em microsserviço usando DITA-OT
* `dxml.use.publish.microservice.native.pdf`: Alternar para habilitar a publicação de PDF nativo baseado em microsserviços

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
