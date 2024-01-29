---
title: Configurar as sugestões inteligentes de criação
description: Saiba como configurar as sugestões inteligentes para criação
source-git-commit: f0bb8e29748ab6820d772225d1689bd5ce6f4c09
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 0%

---

# Configurar as sugestões inteligentes de criação

Como administrador, você pode configurar o recurso Sugestões inteligentes para os autores. Como o serviço de sugestão inteligente é protegido pela autenticação baseada em autenticação do Adobe IMS, integre seus ambientes aos fluxos de trabalho de autenticação baseados em token seguro do Adobe e comece a usar a nova solução de sugestão inteligente. A configuração a seguir ajuda a adicionar a guia Configuração de IA ao perfil da pasta. Depois de adicionado, você pode usar o recurso de sugestões inteligentes no Editor da Web.

## Criar configurações do IMS no console do Adobe Developer

Execute as seguintes etapas para criar configurações do IMS no Console do Adobe Developer:
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

1. No  **Projetos** selecione as credenciais recém-criadas.

1. Selecione o **Servidor OAuth para servidor** link para exibir os detalhes de credencial do seu projeto.

![credenciais conectadas](assets/conf-ss-connected-credentials.png) {width="800" align="left"}
*Conecte-se ao projeto para visualizar os detalhes da credencial.*
1. Copie as chaves CLIENT_ID e CLIENT_SECRET.

Agora você configurou os detalhes de autenticação do OAuth. Mantenha essas duas chaves à mão, pois elas são necessárias na próxima seção.

### Adicionar a configuração IMS ao ambiente

Execute as seguintes etapas para adicionar a configuração IMS ao ambiente:

1. Abra o Experience Manager e selecione seu programa que contenha o ambiente que você deseja configurar.
1. Alternar para **Ambientes** guia.
1. Selecione o nome do ambiente que deseja configurar. Você deve ir para a página Informações do ambiente.
1. Alternar para **Configuração** guia.
1. Adicione as chaves CLIENT_ID e CLIENT_SECRET conforme mostrado na captura de tela a seguir. Verifique se você está usando os mesmos nomes e configuração destacados abaixo.
   ![Configuração do ambiente](assets/conf-ss-environment.png) {width="800" align="left"}
   *Adicione os detalhes de configuração do ambiente.*




Depois de adicionar a configuração IMS ao ambiente, execute as seguintes etapas para vincular essas propriedades aos Guias AEM usando OSGi:

1. No código do projeto Git do Cloud Manager, adicione os dois arquivos abaixo (Para conteúdo de arquivo, consulte [Apêndice](#appendix).

   * `com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Verifique se os arquivos recém-adicionados estão sendo cobertos pela `filter.xml`.
1. Confirme e envie suas alterações do Git.
1. Execute o pipeline para aplicar as alterações no ambiente.

Depois disso, você poderá usar a nova publicação na nuvem baseada em microsserviços.



## Apêndice {#appendix}

**Arquivo**:
`com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`

**Conteúdo**:

```
{
  "client.id": "$[secret:CLIENT_ID]",
  "client.secret": "$[secret:CLIENT_SECRET]",
  "ims.url": "https://ims-na1.adobelogin.com"
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

## Detalhes de Configuração de Sugestão Inteligente

| Chave | Descrição | Valores permitidos |
|---|---|---|
| smart.suggestion.flag | Controla se as sugestões inteligentes estão habilitadas ou não | verdadeiro/falso |
| conref.inline.threshold | Limite que controla a precisão/recuperação de sugestões buscadas para a tag que o usuário está digitando no momento. | -1,0 &lt;= x &lt;= 1,0 |
| conref.block.threshold | Limite que controla a precisão/recuperação de sugestões buscadas para tags em todo o arquivo. | -1,0 &lt;= x &lt;= 1,0 |
| emerald.url | Endpoint para o banco de dados de vetor Emerald | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | Tipo de instância do AEM. Verifique se isso é exclusivo para cada sugestão inteligente de instância do AEM configurada em. Um caso de uso seria testar o recurso no ambiente de preparo com &quot;instance.type&quot; = &quot;stage&quot; enquanto, ao mesmo tempo, o recurso também é configurado em &quot;prod&quot;. | Qualquer chave exclusiva que identifique o ambiente &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; |

Após configurar, o ícone de sugestões inteligentes é exibido no painel direito do Editor da Web. Você pode exibir a lista de sugestões inteligentes ao editar seus tópicos. Para obter mais detalhes, consulte [Sugestões inteligentes baseadas em IA para criação](../user-guide/web-editor-content-snippet.md).
