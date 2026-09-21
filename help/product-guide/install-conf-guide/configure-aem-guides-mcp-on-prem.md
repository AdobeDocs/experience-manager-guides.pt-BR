---
title: Definir configurações de conexão MCP para o AEM Guides no local
description: Saiba como definir configurações de conexão MCP para o AEM Guides no local.
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: Admin
meta-type: Documentation
source-git-commit: e234425f1e277990de25057971f3e2453c93360f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%
---

# Definir configurações de conexão MCP para o Experience Manager Guides (no local)

Ferramentas de IA, como Claude, Cursor e Codex, podem se conectar ao Experience Manager Guides usando o Protocolo de contexto de modelo (MCP). Você pode definir a conexão MCP e as definições de autenticação a partir da página Configuração do Console da Web do Adobe Experience Manager.

As configurações disponíveis controlam o manuseio de token, solicitações sem informações de referenciador e o URL externo para a instância de autor do AEM.

## Configurar manipulação de token de entrada

Para configurar o tratamento do token de entrada, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Procure por e selecione **AEM Guides OAuth PKCE Token Wrapper**.

3. Configure as seguintes propriedades:

   | Propriedade | Padrão | Descrição |
   |---|---|---|
   | URL base do Granite | `http://localhost:4502` | Especifica a URL que o AEM usa para se comunicar com a instância do autor durante a autenticação. Altere a porta padrão 4502 somente se a instância do autor usar uma porta diferente. |
   | Tempo limite do Granite (ms) | `5000` | Especifica o tempo máximo, em milissegundos, para aguardar a conclusão da solicitação de autenticação. |

4. Selecione **Salvar**.

## Configurar solicitações sem informações do referenciador

>[!NOTE]
>
> Esta configuração só precisa ser definida se você estiver usando o Cursor.

Alguns clientes MCP, incluindo o Cursor, podem enviar solicitações sem informações do referenciador. Para permitir essas solicitações, configure o Filtro referenciador do Apache Sling da seguinte maneira:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Procure e selecione **Filtro do referenciador Apache Sling**.

3. Na propriedade **Permitir vazio**, defina o valor como `true`.

   Essa configuração permite solicitações que não contêm informações de referenciador durante a autenticação.

4. Selecione **Salvar**.

## Configurar o URL externo para a instância do autor

O serviço **Day CQ Link Externalizer** permite definir centralmente as URLs externas usadas para prefixar caminhos de recursos, incluindo a URL da instância de autor do AEM.

Para configurar o URL externo, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Procure e selecione **Day CQ Link Externalizer**.

3. Em **Domínios**, adicione ou atualize o mapeamento `author` usando o seguinte formato:

   ```
   author [scheme://]server[:port][/contextpath]
   ```

   Por exemplo:

   ```
   author https://author.mycompany.com
   ```

4. Selecione **Salvar**.