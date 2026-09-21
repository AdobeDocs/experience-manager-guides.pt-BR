---
title: Configuração do MCP para o Adobe Experience Manager Guides
description: Saiba como conectar um assistente de IA ao servidor MCP do Experience Manager Guides para implantações do Cloud Service e locais
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: User
meta-type: Documentation
source-git-commit: e234425f1e277990de25057971f3e2453c93360f
workflow-type: tm+mt
source-wordcount: '1539'
ht-degree: 1%
---

# Configurar o servidor MCP do Experience Manager Guides

Este artigo aborda os detalhes específicos do ambiente para conexão com o servidor MCP do Experience Manager Guides. A configuração é diferente dependendo se a instância do Experience Manager Guides executa o as a Cloud Service ou no local. Selecione a guia que corresponde ao seu ambiente.

>[!BEGINTABS]

>[!TAB Cloud Service]

## Ponto de acesso do servidor MCP

O Experience Manager Guides expõe seus recursos de MCP por meio de um único endpoint HTTP.

| Servidor MCP | Terminal | Descrição |
|---|---|---|
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Trabalhe com tópicos e mapas, [novas linhas de base](../user-guide/web-editor-baseline-v2.md) e relatórios no Experience Manager Guides. |

Para descobrir a lista de ferramentas atual para seu ambiente, pergunte ao assistente:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Solicitar acesso para sua organização

O acesso ao servidor MCP do Experience Manager Guides é de **aceitação por organização**. Antes que qualquer pessoa em sua organização possa se conectar:

- O Experience Manager Guides deve ser ativado no ambiente AEM as a Cloud Service.
- A IMS Organization ID (ID da organização) de sua organização deve estar na lista de permissões da equipe do Adobe Guides.

Para solicitar acesso, entre em contato com a equipe de Sucesso do cliente da Adobe.

## Configurar

Você não instala nada localmente. Você aponta seu cliente para o URL do servidor e autentica por meio do fluxo de entrada do Adobe IMS.

### Claude Antrópico

Siga a apresentação oficial: [Configurar Claude para o AEM MCP](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-service/content/ai-in-aem/mcp-support/chat-applications/setup-claude). Ao adicionar o conector personalizado, use o endpoint do Experience Manager Guides:

```
https://mcp.adobeaemcloud.com/adobe/mcp/guides
```

### Cursor/Código do Visual Studio

Adicione o servidor à configuração MCP. Para Cursor, adicione-o a `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "aem-guides": {
      "url": "https://mcp.adobeaemcloud.com/adobe/mcp/guides"
    }
  }
}
```

Para clientes que oferecem suporte apenas a servidores locais (stdio), conecte-se ao ponto de extremidade remoto com [`mcp-remote`](https://www.npmjs.com/package/mcp-remote):

```json
{
  "mcpServers": {
    "aem-guides": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.adobeaemcloud.com/adobe/mcp/guides"]
    }
  }
}
```

>[!TAB No local]

Você pode conectar clientes de IA compatíveis a uma instância local do Experience Manager Guides usando o Protocolo de Contexto de Modelo (MCP). Após estabelecer a conexão, o cliente poderá acessar as operações do Experience Manager Guides disponíveis para sua conta de usuário do AEM.

Todas as operações são executadas usando **sua identidade e permissões do AEM**. O cliente conectado pode visualizar ou modificar somente o conteúdo e os recursos que sua conta do AEM está autorizada a acessar.

A autenticação usa o fluxo de código de autorização OAuth 2.0 com a chave de prova para troca de código (PKCE). Você se autentica com o AEM quando se conecta a um cliente pela primeira vez. Após a autenticação bem-sucedida, a conexão atualiza os tokens de acesso automaticamente.

Você pode conectar os seguintes clientes:

| Cliente | Método de conexão | Requisitos da instância do AEM |
| ------------------ | ----------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Claude Desktop** | Extensão da Área de Trabalho (`.mcpb`) | Suporta endpoints HTTP e HTTPS, incluindo hosts internos acessíveis a partir de sua rede corporativa. |
| **ChatGPT (Web e área de trabalho)** | Conector personalizado | Exige um terminal HTTPS acessível publicamente com um certificado TLS válido e confiável publicamente. |
| **Cursor** | Configuração de MCP em `~/.cursor/mcp.json` | Suporta endpoints HTTP e HTTPS, incluindo hosts internos acessíveis a partir de sua rede corporativa. |

## Pré-requisitos

Antes de conectar um cliente, entre em contato com o administrador do AEM para verificar a seguinte configuração:

1. **Verifique se o recurso MCP está implantado.**: certifique-se de que o recurso MCP esteja implantado e em execução em sua instância do Experience Manager Guides.

2. **Configurar a URL de base do Granite.**: no Gerenciador de configuração do console da Web do AEM (`/system/console/configMgr`), localize a configuração do **Experience Manager Guides OAuth PKCE Token Wrapper** e verifique se a URL de base do Granite está configurada. Se o URL de base do Granite não estiver configurado corretamente, o cliente não poderá estabelecer a conexão.

3. **Configure o Day CQ Link Externalizer.**: no Gerenciador de Configuração do Console da Web do AEM, localize a configuração do **Day CQ Link Externalizer** e verifique se a URL do autor externo aponta para a instância correta do autor do AEM. O URL do autor externo é usado durante a descoberta do OAuth. Um URL incorreto pode impedir que o cliente conclua a conexão.

   Para obter mais detalhes, consulte [Definir configurações de conexão MCP para o AEM Guides no Local](./configure-aem-guides-mcp-on-prem.md)

4. **Obter a URL do servidor MCP.**: a URL do servidor MCP usa o seguinte formato:

   ```
   http(s)://<AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   >[!NOTE]
   >
   > Use o endpoint SSE completo ao configurar um cliente. Não adicione uma barra à direita ao URL.

   Por exemplo:

   **Instância interna do autor do AEM:**

   ```
   http://10.42.42.20:4502/bin/guides/v1/mcp/sse
   ```

   **Instância de autor de AEM público:**

   ```
   https://author.example.com/bin/guides/v1/mcp/sse
   ```



5. **Verifique suas credenciais e permissões do AEM.**: você deve ter uma conta válida para a instância do AEM. Use as mesmas credenciais usadas para fazer logon na interface do usuário do AEM. As operações disponíveis por meio do MCP são determinadas pelas permissões atribuídas a essa conta.

## Conectar o Claude Desktop

O Claude Desktop oferece suporte às Extensões de Desktop (`.mcpb`). A extensão MCP do Experience Manager Guides empacota a configuração da conexão para que você não precise editar manualmente uma configuração JSON de MCP.

1. Extraia o [arquivo zip .mcpb do AEM Guides](./mcpbfile.zip) e obtenha o arquivo de extensão `aem-guides-mcp.mcpb`.

2. Abra o **Claude Desktop** e navegue até **Configurações > Extensões**.

3. Instale o `aem-guides-mcp.mcpb` clicando duas vezes no arquivo ou arrastando-o para a janela Extensões.

   O **Adobe Experience Manager Guides MCP** é exibido na caixa de diálogo Instalação.

4. Selecione **Instalar**.

5. No campo **URL do Servidor MCP do Experience Manager Guides**, digite o ponto de extremidade SSE completo para sua instância do AEM.

   Por exemplo:

   ```
   http://<AEM-HOST>:4502/bin/guides/v1/mcp/sse
   ```

6. Selecione **Salvar** e verifique se a extensão está habilitada.

## Conectar o ChatGPT

Você pode configurar o servidor MCP do Experience Manager Guides como um conector personalizado no ChatGPT.

>[!IMPORTANT]
>
> O ChatGPT requer que o servidor MCP esteja disponível por meio de um **ponto de extremidade HTTPS acessível publicamente com um certificado TLS válido e confiável publicamente**.
>
> Não há suporte para pontos de extremidade HTTP, `localhost`, endereços IP privados e certificados autoassinados. A instância do AEM deve ser exposta por meio de um host HTTPS, como um balanceador de carga, proxy reverso ou Dispatcher configurado com TLS.
>
> A URL do autor externo configurada no **Day CQ Link Externalizer** também deve apontar para o endereço HTTPS público. Caso contrário, os metadados de descoberta do OAuth podem anunciar pontos de extremidade de autenticação incorretos e impedir o logon.

1. Verifique se o servidor MCP está disponível em um URL HTTPS público no seguinte formato:

   ```
   https://<PUBLIC-AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   Abra o endpoint em um navegador e verifique se você pode acessar o host sem um aviso de certificado ou erro de conexão.

2. No ChatGPT, abra **Configurações > Plug-ins**.

   >[!NOTE]
   >
   > A disponibilidade do conector depende do plano do ChatGPT e da configuração do espaço de trabalho. Talvez o administrador do espaço de trabalho precise habilitar conectores personalizados ou de desenvolvedor.

3. Selecione a opção para adicionar ou criar um plugin.

4. Especifique os detalhes do conector:

   * **Nome:** Insira `Experience Manager Guides` ou outro nome descritivo.
   * **URL do Servidor MCP:** Insira o ponto de extremidade HTTPS SSE público.
   * **Autenticação:** Selecione **OAuth**.

   Não é necessário fornecer uma ID de cliente OAuth ou um segredo de cliente. O servidor MCP suporta registro automático de cliente.

5. Crie o conector.

## Conectar cursor

Configure o servidor Experience Manager Guides MCP no Cursor, adicionando os detalhes do servidor à configuração do MCP.

1. No Cursor, navegue até **Personalizar > MCPs > Novo**.

   O cursor abre o arquivo de configuração `~/.cursor/mcp.json`.

2. Adicione a configuração do servidor Experience Manager Guides MCP.

   Por exemplo:

   ```json
   {
     "mcpServers": {
       "aem-guides": {
         "url": "http://10.42.34.176:4502/bin/guides/v1/mcp/sse",
         "type": "http"
       }
     }
   }
   ```

3. Substitua o URL de exemplo pelo endpoint MCP SSE da sua instância do AEM.

4. Salve a configuração.

5. Ative o servidor MCP configurado.

>[!ENDTABS]

## Autenticar e usar o Experience Manager Guides

Após configurar a conexão MCP em seu cliente, autentique com sua conta do AEM.

1. Inicie o processo de autenticação do cliente.

   * **Claude Desktop:** o fluxo de autenticação começa quando Claude tenta usar a conexão do Experience Manager Guides pela primeira vez.
   * **ChatGPT:** A autenticação é iniciada após a criação e conexão do conector do Experience Manager Guides.
   * **Cursor:** Habilite o servidor MCP configurado e selecione **Autenticar**.

2. Quando a página de logon do AEM for aberta no navegador, faça logon usando as credenciais da AEM.

3. Aprove a solicitação de acesso quando solicitado.

4. Após a conclusão da autenticação, volte para o cliente.

Agora você pode usar as operações do Experience Manager Guides disponíveis para sua conta. Por exemplo, tente prompts como:

```
List the available Experience Manager Guides operations.
```

```
Get the topic list for my map in Experience Manager Guides.
```

```
Show me the broken-link report for my map.
```

>[!NOTE]
>
> As operações e o conteúdo disponíveis por meio do MCP são determinados pelas permissões da conta do AEM usada para autenticação. A conexão MCP não fornece privilégios AEM adicionais.

Após a autenticação bem-sucedida, o cliente atualiza os tokens de autenticação automaticamente. Normalmente, você não precisa fazer logon novamente, a menos que a sessão expire ou o acesso seja revogado.

## Solução de problemas de conexão

Use as informações a seguir para solucionar problemas comuns de conexão e autenticação.

| Cliente | Problema | Possível causa e resolução |
| -------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Claude Desktop | A extensão não pode ser instalada ou está desabilitada. | Sua versão do Claude Desktop pode não ser compatível com a extensão. Atualize o Claude Desktop e tente novamente. |
| Claude Desktop | O navegador não abre para autenticação ou a conexão não foi concluída. | Verifique o URL do servidor MCP. Deve terminar com `/bin/guides/v1/mcp/sse` e não deve conter uma barra à direita. Verifique também se a instância do AEM pode ser acessada no seu computador. |
| ChatGPT | O ChatGPT não pode acessar o servidor MCP ou não permite adicionar o conector. | Verifique se o endpoint está acessível publicamente via HTTPS. Não há suporte para pontos de extremidade HTTP, `localhost`, endereços IP privados e pontos de extremidade de rede privada. |
| ChatGPT | Um certificado ou erro de segurança é exibido. | Verifique se o servidor usa um certificado válido não expirado emitido por uma autoridade de certificação confiável publicamente. Certificados autoassinados não têm suporte. |
| ChatGPT | A autenticação redireciona para um host incorreto ou falha durante a descoberta. | Verifique se a URL do autor externo no **Day CQ Link Externalizer** aponta para o endereço público do autor do AEM HTTPS. |
| Todos os clientes | Falha de registro durante a autenticação. | Verifique a configuração de registro OAuth do lado do servidor com o administrador do AEM. |
| Todos os clientes | A autenticação falha ou não é concluída. | Verifique o URL básico do Granite, a configuração do Day CQ Link Externalizer, o URL do servidor MCP e a conectividade com a instância do AEM. |
| Todos os clientes | A conexão foi bem-sucedida, mas as operações ou os resultados do Experience Manager Guides não estão disponíveis. | Verifique se a conta autenticada do AEM tem as permissões necessárias do Experience Manager Guides e se a operação solicitada está disponível para a conta. |
| Todos os clientes | O cliente solicita autenticação após a conexão ter funcionado. | A sessão de autenticação pode ter expirado ou o acesso pode ter sido revogado. Autentique com o AEM novamente. |



