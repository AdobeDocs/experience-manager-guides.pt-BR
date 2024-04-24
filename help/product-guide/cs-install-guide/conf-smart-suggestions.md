---
title: Configurar as sugestões inteligentes de criação
description: Saiba como configurar as sugestões inteligentes para criação
exl-id: a595ca1f-0123-40d3-a79c-a066bc6517b4
source-git-commit: b2042431e96f2cbd90eea9c8cfcdb3e7033e26bb
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 0%

---

# Configurar as sugestões inteligentes habilitadas por IA para criação

Como administrador, você pode configurar o recurso Sugestões inteligentes para os autores. O serviço de sugestão inteligente é protegido pela autenticação baseada em autenticação do Adobe IMS. Integre seu ambiente com os workflows de autenticação segura baseada em token do Adobe e comece a usar o novo recurso de sugestão inteligente. A configuração a seguir ajuda a adicionar o **Configuração de IA** guia para o perfil da pasta. Depois de adicionado, você pode usar o recurso de sugestões inteligentes no Editor da Web.

## Criar configurações do IMS no console do Adobe Developer

Execute as seguintes etapas para criar configurações do IMS no Console do Adobe Developer:

>[!NOTE]
>
>Se você já criou um projeto OAuth para configurar a publicação baseada em microsserviços, ignore as etapas a seguir para criar o projeto.

1. Launch [Console do Adobe Developer](https://developer.adobe.com/console).
1. Depois de fazer logon no Console do desenvolvedor, você visualizará a **Início** tela. A variável **Início** é onde você pode encontrar facilmente informações e links rápidos, incluindo links de navegação superior para Projetos e Downloads.
1. Para criar um novo projeto vazio, selecione  **Criar novo projeto** do  **Início rápido** links.
   ![Links de início rápido](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Crie um novo projeto.*

1. Selecionar  **Adicionar API**  do  **Projetos** tela.  A variável **Adicionar uma API** é exibida. Esta tela exibe todas as APIs, Eventos e serviços disponíveis para produtos e tecnologias Adobe com os quais você pode desenvolver aplicativos.

1. Selecione o **API de gerenciamento de E/S** para adicioná-lo ao seu projeto.
   ![API de gerenciamento de E/S](assets/confi-ss-io-management.png)
   *Adicione a API de gerenciamento de E/S ao projeto.*

1. Criar um novo **Credencial OAuth** e salve-o.
   ![Mosaico de credenciais OAuth na API de configuração](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Configure a credencial OAuth para sua API.*

1. No  **Projetos** escolha **Servidor OAuth para servidor** e selecione as credenciais recém-criadas.

1. Selecione o **Servidor OAuth para servidor** link para exibir os detalhes de credencial do seu projeto.

   ![credenciais conectadas](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Conecte-se ao projeto para visualizar os detalhes da credencial.*

1. Retorne para a **Projetos** e selecione **Visão geral do projeto** à esquerda.

   <img src="assets/project-overview.png" alt="visão geral do projeto" width="500">

   *Comece a usar o novo projeto.*

1. Clique em **Baixar** na parte superior para baixar o serviço JSON.

   <img src="assets/download-json.png" alt="baixar json" width="500">

   *Baixe os detalhes do serviço JSON.*

Você configurou os detalhes de autenticação do OAuth e baixou os detalhes do serviço JSON. Mantenha esse arquivo em mãos conforme necessário na próxima seção.

### Adicionar a configuração IMS ao ambiente

Execute as seguintes etapas para adicionar a configuração IMS ao ambiente:

1. Abra o Experience Manager e selecione seu programa que contenha o ambiente que você deseja configurar.
1. Alterne para a **Ambientes** guia.
1. Selecione o nome do ambiente que deseja configurar. Isso deve levar você ao **Informações do ambiente** página.
1. Alterne para a **Configuração** guia.
1. Atualize o campo JSON SERVICE_ACCOUNT_DETAILS. Certifique-se de usar o mesmo nome e configuração fornecidos na captura de tela a seguir.

![configuração da conta de serviço ims](assets/ims-service-account-config.png){width="800" align="left"}


*Adicione os detalhes de configuração do ambiente.*




Depois de adicionar a configuração IMS ao ambiente, execute as seguintes etapas para vincular essas propriedades aos Guias AEM usando OSGi:

1. No código do projeto Git do Cloud Manager, adicione os dois arquivos abaixo (para conteúdo de arquivo, exibir [Apêndice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Verifique se os arquivos recém-adicionados estão sendo cobertos pela `filter.xml`.
1. Confirme e envie suas alterações do Git.
1. Execute o pipeline para aplicar as alterações no ambiente.

Depois disso, você poderá usar o recurso de sugestões inteligentes.



## Apêndice {#appendix}

**Arquivo**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Conteúdo**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**Arquivo**: `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`

**Conteúdo**:

```
{
  "smart.suggestion.flag":true,
  "conref.inline.threshold":0.6,
  "conref.block.threshold":0.7,
  "emerald.url":"https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1",
  "instance.type":"prod"
}
```

## Detalhes de configuração das Sugestões inteligentes

| Chave | Descrição | Valores permitidos | Valor padrão |
|---|---|---|---|
| smart.suggestion.flag | Controla se as sugestões inteligentes estão habilitadas ou não | verdadeiro/falso | falso |
| conref.inline.threshold | Limite que controla a precisão/recuperação de sugestões buscadas para a tag que o usuário está digitando no momento. | Qualquer valor de -1,0 a 1,0. | 0,6 |
| conref.block.threshold | Limite que controla a precisão/recuperação de sugestões buscadas para tags em todo o arquivo. | Qualquer valor de -1,0 a 1,0. | 0,7 |
| emerald.url | Endpoint para o banco de dados de vetor Emerald | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | Tipo de instância do AEM. Verifique se isso é exclusivo para cada instância do AEM em que as sugestões inteligentes estão configuradas. Um caso de uso seria testar o recurso no ambiente de preparo com &quot;instance.type&quot; = &quot;stage&quot; enquanto, ao mesmo tempo, o recurso também é configurado em &quot;prod&quot;. | Qualquer chave exclusiva que identifique o ambiente. Somente *alfanumérico* valores são permitidos. &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; | &quot;prod&quot; |

Depois de configurar, o ícone de sugestões inteligentes é exibido no painel direito do Editor da Web. Você pode exibir a lista de sugestões inteligentes ao editar seus tópicos. Para obter mais detalhes, consulte [Sugestões inteligentes baseadas em IA para criação](../user-guide/authoring-ai-based-smart-suggestions.md) no Guia do usuário do Experience Manager.
