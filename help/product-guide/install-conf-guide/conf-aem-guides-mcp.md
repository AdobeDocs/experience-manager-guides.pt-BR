---
title: Uso do MCP com o Adobe Experience Manager Guides
description: Saiba como usar o Protocolo de contexto de modelo (MCP) com o AEM Guides para trabalhar com tópicos, mapas, linhas de base e relatórios por meio de um assistente de IA
feature: Authoring, Publishing
role: User
source-git-commit: c724946a3426e28a1270ba01cdf2646bbf5f2a0d
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---


# Usando o servidor MCP do Adobe Experience Manager Guides

O Protocolo de contexto de modelo (MCP) é uma maneira padrão para os assistentes de IA se conectarem a ferramentas e dados externos, em vez de você alternar o contexto para operar essas ferramentas sozinho.

O servidor MCP do Adobe Experience Manager Guides traz isso para o Experience Manager Guides. Ele permite que um assistente de IA habilitado para MCP, como Anthropic Claude, se conecte ao seu ambiente do Experience Manager Guides e aja em seu nome, com suas próprias permissões do AEM. Depois de conectado, você pode trabalhar com seus mapas, tópicos, linhas de base e relatórios no Experience Manager Guides as a Cloud Service usando uma linguagem natural simples.

Este artigo explica por que o MCP é útil para o Experience Manager Guides, o que o servidor MCP cobre, com quais aplicativos ele funciona, como configurá-lo e como usá-lo.

## Por que o MCP para Experience Manager Guides é útil

As equipes de documentação geralmente gastam um tempo significativo em tarefas repetitivas e de navegação intensa, como encontrar tópicos em um mapa grande, verificar estados dos documentos, rastrear links desfeitos, criar linhas de base para uma versão ou exportar relatórios. Com o servidor MCP do Experience Manager Guides, você pode solicitar que um assistente de IA cuide deles diretamente, sem alternar para a interface do usuário do Experience Manager Guides.

Por exemplo:

- Em vez de abrir um mapa e verificar o estado de cada tópico, peça ao assistente para listar os tópicos e seus estados.
- Em vez de iniciar manualmente um relatório de links quebrados e aguardar na interface do usuário do Experience Manager Guides, peça ao assistente para executar o relatório e informá-lo quando ele for concluído.
- Em vez de navegar até a tela da linha de base, peça ao assistente para criar uma linha de base para um mapa específico.

## Servidor MCP fornecido pela Experience Manager Guides

O Experience Manager Guides expõe seus recursos de MCP por meio de um único endpoint HTTP.

| Servidor MCP | Terminal | Descrição |
| --- | --- | --- |
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Trabalhar com tópicos e mapas, linhas de base e relatórios no Experience Manager Guides. |

Este endpoint abrange quatro áreas:

- **Tópicos e mapas** - Criar, ler, atualizar, excluir, criar versão e bloquear tópicos e mapas.
- **Linhas de Base** - Criar, listar, exportar, duplicar, recompilar e rotular linhas de base.
- **Relatórios** - Listas de tópicos, metadados, links quebrados e uso de multimídia.
- **Sistema** - Versão do pacote, integridade do pacote e diagnóstico de ambiente.

As ferramentas exatas disponíveis podem mudar com o tempo. Em vez de depender de uma lista fixa, peça ao assistente para mostrar o que está disponível:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Solicitar acesso para sua organização

O acesso ao servidor MCP do Experience Manager Guides é de **aceitação por organização**. Antes que qualquer pessoa em sua organização possa se conectar:

- O Experience Manager Guides deve ser ativado no ambiente AEM as a Cloud Service.
- A IMS Organization ID (ID da organização) de sua organização deve estar na lista de permissões da equipe do Adobe Guides.

Para solicitar acesso, entre em contato com a equipe de Sucesso do cliente da Adobe.

## Aplicativos compatíveis

O servidor MCP do Experience Manager Guides é um servidor **remoto**. Funciona com qualquer cliente MCP que suporta servidores remotos, incluindo:

### Aplicativos de bate-papo

- Claude Antrópico (web e desktop)

### Ferramentas do desenvolvedor

- Cursor
- Código do Visual Studio
- Outros IDEs compatíveis com MCP

## Configurar

Você não instala nada localmente. Você aponta seu cliente para o URL do servidor e autentica por meio do fluxo de entrada do Adobe IMS.

### Claude Antrópico

Siga a apresentação oficial: [Configurar Claude para o AEM MCP](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/ai-in-aem/mcp-support/chat-applications/setup-claude). Ao adicionar o conector personalizado, use o endpoint do Experience Manager Guides:

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

## Autenticação

O servidor MCP do Experience Manager Guides usa o **Adobe IMS** para autenticação.

- Na primeira conexão, seu cliente abre uma janela de logon do navegador. Faça logon com sua Adobe ID para concluir a conexão.
- Depois de fazer logon, cada ação é executada com suas permissões existentes do AEM. Se você não tiver permissão para uma ação no AEM, a mesma ação falhará por meio do MCP.

## Usando o servidor MCP do Experience Manager Guides

Depois de conectado, descreva em linguagem simples o que você deseja. O assistente seleciona a ferramenta apropriada e preenche seus parâmetros, como o caminho do mapa ou o nome da linha de base.

>[!IMPORTANT]
>
>As solicitações que envolvem várias etapas ou levam tempo para serem concluídas, como exportações, builds de linha de base e atualizações em massa, funcionam melhor com um modelo de pensamento. Eles são executados em segundo plano: o assistente inicia o trabalho e verifica seu status até que o resultado, ou um link de download, esteja pronto.

### Exemplo de prompts

Os prompts a seguir ilustram as solicitações típicas, cada uma acionando uma ferramenta diferente:

1. **Verificar estados do tópico em um mapa**

   > Listar todos os tópicos no mapa em `/content/dam/docs/user-guide.ditamap` e mostrar seus títulos e estados do documento.

1. **Criar uma linha de base**

   > Crie uma linha de base estática de `/content/dam/docs/user-guide.ditamap` chamada &quot;Versão 3.2&quot;.

1. **Executar um relatório**

   > Execute o relatório de links quebrados no guia do usuário e forneça-me o link de download quando estiver pronto.

## Gerenciamento de expectativas

- **Validar o resultado** - O assistente pode cometer erros, como escolher o mapa ou tópico incorreto. Revise um relatório ou uma nova linha de base antes de usá-lo.
- **Melhora com o tempo** - À medida que o assistente melhora, as tarefas que recebem alguns prompts hoje podem receber um prompt mais tarde.
- **Você ainda faz a chamada** - O assistente pode informar o estado de um tópico ou listar links com falha, mas decidir se o conteúdo está pronto para ser publicado ainda depende do Revisor ou do Publicador.
- **Tenha cuidado com a aprovação automática** - Alguns clientes MCP, incluindo Claude, permitem que você aprove ações automaticamente em vez de confirmar cada um. Isso é aceitável para ações somente leitura, como executar um relatório. Para ações que criam, alteram ou bloqueiam conteúdo, confirme cada um deles para que você possa revisá-los antes que entrem em vigor.

Em caso de dúvidas sobre o Experience Manager Guides MCP, entre em contato com a equipe de Sucesso do cliente da Adobe.


