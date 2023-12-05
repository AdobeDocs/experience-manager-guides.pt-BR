---
title: Configure a nova publicação baseada em microsserviços para os Guias do AEM as a Cloud Service
description: Saiba como Configurar a nova publicação baseada em microsserviços para Guias do AEM.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Configure a nova publicação baseada em microsserviços para os Guias do AEM as a Cloud Service

O novo microsserviço de publicação permite que os usuários executem grandes cargas de trabalho de publicação simultaneamente no AEM Guides as a Cloud Service e aproveitem a plataforma Adobe I/O Runtime sem servidor, líder do setor.

Para cada solicitação de publicação, o AEM Guides as a Cloud Service executa um contêiner separado que é dimensionado horizontalmente de acordo com as solicitações do usuário. Isso fornece aos usuários os recursos para executar várias solicitações de publicação e obter um desempenho melhor do que seus grandes servidores AEM no local.

>[!NOTE]
>
> A publicação com base em microsserviços nos Guias AEM oferece suporte aos tipos de predefinições de saída PDF (baseado em DITA e nativo), HTML5, JSON e CUSTOM.

Como o novo serviço de publicação na nuvem é protegido pela autenticação baseada em JWT do Adobe IMS, os clientes devem seguir as etapas fornecidas abaixo para integrar seus ambientes com fluxos de trabalho de autenticação baseados em token seguro do Adobe e começar a usar a nova solução de publicação escalável baseada em nuvem.


## Criar configurações do IMS no console do Adobe Developer

**Função necessária para criar as configurações**: Administrador do sistema

Execute as seguintes etapas para criar configurações do IMS no Console do Adobe Developer:

1. Abra o Console do desenvolvedor: `https://developer.adobe.com/console`.

1. Alternar para **Projetos** da parte superior.

   <img src="assets/projects-tab.png" alt="guia projetos" width="500">

1. Para criar um novo projeto vazio, selecione **Projeto vazio** do **Criar novo projeto** lista suspensa.

   <img src="assets/create-new-project.png" alt="criar novo projeto" width="500">

1. Selecionar **API** do **Adicionar ao projeto** lista suspensa para adicionar a API de gerenciamento de E/S ao projeto.

   <img src="assets/add-project.png" alt="adicionar projeto" width="300">

   <img src="assets/io-management-api.png" alt="gerenciamento de e/s" width="500">

1. Crie um novo par de chaves privadas/públicas ao adicionar a API. Isso baixará automaticamente a chave privada no sistema.

   <img src="assets/generate-key-pair.png" alt="gerar par de chaves" width="500">

1. Salve a API configurada.

   <img src="assets/save-api.png" alt="salvar api" width="600">

1. Volte para **Projetos** e clique em **Visão geral do projeto** à esquerda.

   <img src="assets/project-overview.png" alt="visão geral do projeto" width="500">

1. Clique em **Baixar** na parte superior para baixar o serviço JSON.

   <img src="assets/download-json.png" alt="baixar json" width="500">

Agora, você configurou os detalhes de autenticação JWT e também baixou a chave privada e os detalhes do serviço JSON. Mantenha esses dois arquivos à mão, pois eles são obrigatórios na próxima seção.

### Adicionar a configuração IMS ao ambiente

Execute as seguintes etapas para adicionar a configuração IMS ao ambiente:

1. Abra o Experience Manager e selecione seu programa que contenha o ambiente que você deseja configurar.
1. Alternar para **Ambientes** guia.
1. Clique no nome do ambiente que deseja configurar. Você deve ir para a página Informações do ambiente.
1. Alternar para **Configuração** guia.
1. Carregue a chave privada e o projeto JSON como mostrado na captura de tela abaixo. Verifique se você está usando os mesmos nomes e configuração destacados abaixo.

   <img src="assets/ims-config-environment.png" alt="configurações ims" width="500">

>[!NOTE]
>
> Você precisa abrir, copiar e colar o conteúdo do arquivo JSON de chaves privadas e detalhes do serviço na coluna de valor do painel Configuração, como mostrado na captura de tela acima.

Depois de adicionar a configuração IMS ao ambiente, execute as seguintes etapas para vincular essas propriedades aos Guias AEM usando OSGi:

1. No código do projeto Git do Cloud Manager, adicione os dois arquivos abaixo (Para obter o conteúdo do arquivo, consulte [Apêndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Verifique se os arquivos recém-adicionados estão sendo cobertos pela `filter.xml`.
1. Confirme e envie suas alterações do Git.
1. Execute o pipeline para aplicar as alterações no ambiente.

Depois disso, você poderá usar a nova publicação na nuvem baseada em microsserviços.

## Perguntas frequentes

1. Uma única chave pode ser usada em vários ambientes de nuvem?
   * Sim, você pode gerar uma chave privada e usá-la para todos os ambientes, mas precisa configurar as variáveis de ambiente para todos os ambientes e usar a mesma chave.
1. Se as configurações de OSGi para usar o microsserviço estiverem ativadas, o processo de publicação funcionará no servidor AEM local com a mesma base de código?
   * Não, se o sinalizador `dxml.use.publish.microservice` está definida como `true` então, ele sempre procura por configurações de microsserviços. Definir `dxml.use.publish.microservice` para `false` para que a publicação funcione no local.
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
* `dxml.use.publish.microservice`: alterne para habilitar a publicação baseada em microsserviço usando o DITA-OT
* `dxml.use.publish.microservice.native.pdf`: Alternar para habilitar a publicação de PDF nativo com base em microsserviços

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
