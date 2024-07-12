---
title: Configurar nova publicação baseada em microsserviços para o AEM Guides as a Cloud Service
description: Saiba como Configurar a nova publicação baseada em microsserviços para o AEM Guides.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
feature: Microservice in AEM Guides
role: User, Admin
source-git-commit: f929d4fd74e98e2025d80c14dbef6aeb464c0dd5
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 0%

---

# Configurar a publicação baseada em microsserviços com autenticação JWT

[!BADGE Cloud Service]{type=Informative}

>[!NOTE]
>
> As credenciais da Conta de serviço (JWT) foram substituídas pelas credenciais de servidor para servidor do OAuth. Seus aplicativos que usam as credenciais da Conta de serviço (JWT) deixarão de funcionar após 1º de janeiro de 2025. Você deve migrar para a nova credencial até 1º de janeiro de 2025 para garantir que seu aplicativo continue funcionando. Saiba mais sobre a [migração da credencial de conta de serviço (JWT) para a credencial de servidor para servidor OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/).



A publicação com base em microsserviços no para Adobe Experience Manager Guides as a Cloud Service suporta os tipos de predefinições de saída PDF (baseados em DITA e nativo), HTML5, JSON e CUSTOM.

Como as credenciais da Conta de serviço (JWT) foram substituídas, é recomendável usar a autenticação baseada em OAuth do Adobe IMS. Saiba como [configurar a publicação baseada em microsserviço com autenticação OAuth](configure-microservices-imt-config.md).

Para o serviço de publicação na nuvem protegido pela autenticação baseada em JWT do Adobe IMS, os clientes devem seguir as etapas fornecidas abaixo para integrar seus ambientes com fluxos de trabalho de autenticação baseados em token seguro do Adobe e começar a usar a nova solução de publicação escalável baseada em nuvem.


## Criar configurações do IMS no Adobe Developer Console

**Função necessária para criar as configurações**: Administrador do Sistema

Execute as seguintes etapas para criar configurações do IMS no Adobe Developer Console:

1. Abra o Developer Console: `https://developer.adobe.com/console`.

1. Mude para a guia **Projetos** a partir da parte superior.

   <img src="assets/projects-tab.png" alt="guia projetos" width="500">

1. Para criar um novo projeto vazio, selecione **Projeto vazio** na lista suspensa **Criar novo projeto**.

   <img src="assets/create-new-project.png" alt="criar novo projeto" width="500">

1. Selecione **API** na lista suspensa **Adicionar ao Projeto** para adicionar a API de Gerenciamento de E/S ao seu projeto.

   <img src="assets/add-project.png" alt="adicionar projeto" width="300">

   <img src="assets/io-management-api.png" alt="gerenciamento de e/s" width="500">

1. Crie um novo par de chaves privadas/públicas ao adicionar a API. Isso baixará automaticamente a chave privada no sistema.

   <img src="assets/generate-key-pair.png" alt="gerar par de chaves" width="500">

1. Salve a API configurada.

   <img src="assets/save-api.png" alt="salvar api" width="600">

1. Volte para a guia **Projetos** e clique em **Visão geral do projeto** à esquerda.

   <img src="assets/project-overview.png" alt="visão geral do projeto" width="500">

1. Clique no botão **Baixar** na parte superior para baixar o serviço JSON.

   <img src="assets/download-json.png" alt="baixar json" width="500">

Agora, você configurou os detalhes de autenticação JWT e também baixou a chave privada e os detalhes do serviço JSON. Mantenha esses dois arquivos à mão, pois eles são obrigatórios na próxima seção.

### Adicionar a configuração IMS ao ambiente

Execute as seguintes etapas para adicionar a configuração IMS ao ambiente:

1. Abra o Experience Manager e selecione seu programa que contenha o ambiente que você deseja configurar.
1. Mudar para a guia **Ambientes**.
1. Clique no nome do ambiente que deseja configurar. Você deve ir para a página Informações do ambiente.
1. Mudar para a guia **Configuração**.
1. Carregue a chave privada e o projeto JSON como mostrado na captura de tela abaixo. Verifique se você está usando os mesmos nomes e configuração destacados abaixo.

   <img src="assets/ims-config-environment.png" alt="configurações ims" width="500">

>[!NOTE]
>
> Você precisa abrir, copiar e colar o conteúdo do arquivo JSON de chaves privadas e detalhes do serviço na coluna de valor do painel Configuração, como mostrado na captura de tela acima.

Depois de adicionar a configuração IMS ao ambiente, execute as seguintes etapas para vincular essas propriedades ao Experience Manager Guides usando OSGi:

1. Em seu código de projeto Git do Cloud Manager, adicione os dois arquivos abaixo (Para obter o conteúdo do arquivo, consulte [Apêndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Certifique-se de que os arquivos recém-adicionados estejam sendo cobertos pelo seu `filter.xml`.
1. Confirme e envie suas alterações do Git.
1. Execute o pipeline para aplicar as alterações no ambiente.

Depois disso, você poderá usar a nova publicação na nuvem baseada em microsserviços.

## Perguntas frequentes

1. Uma única chave pode ser usada em vários ambientes de nuvem?
   * Sim, você pode gerar uma chave privada e usá-la para todos os ambientes, mas precisa configurar as variáveis de ambiente para todos os ambientes e usar a mesma chave.
1. Se as configurações de OSGi para usar o microsserviço estiverem ativadas, o processo de publicação funcionará no servidor AEM local com a mesma base de código?
   * Não, se o sinalizador `dxml.use.publish.microservice` estiver definido como `true`, ele sempre procurará configurações de microsserviço. Defina `dxml.use.publish.microservice` como `false` para que a publicação funcione no seu local.
1. Quanta memória é alocada para o processo DITA ao usar a publicação baseada em microsserviços? Isso é feito por meio de parâmetros de formigas de perfis DITA?
   * Com a publicação baseada em microsserviços, a alocação de memória não é orientada pelos parâmetros ant do perfil DITA. A memória total disponível no container de serviço é de 8 GB, dos quais 6 GB são alocados para o processo DITA-OT.


## Apêndice {#appendix}

**Arquivo**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Conteúdo**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
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
