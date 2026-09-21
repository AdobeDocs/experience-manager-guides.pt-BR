---
title: Uso do MCP com o Adobe Experience Manager Guides
description: Saiba como usar o Protocolo de contexto de modelo (MCP) com o AEM Guides para trabalhar com tópicos, mapas, linhas de base e relatórios por meio de um assistente de IA
feature: Authoring
role: User
source-git-commit: 864884f26389d256b0e054e3c0b7400b89f6d6ce
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%
---

# Usando o servidor MCP do Adobe Experience Manager Guides

O Protocolo de contexto de modelo (MCP) é uma maneira padrão para os assistentes de IA se conectarem a ferramentas e dados externos, em vez de você alternar o contexto para operar essas ferramentas sozinho.

O servidor MCP do Adobe Experience Manager Guides traz isso para o Experience Manager Guides. Ele permite que um assistente de IA habilitado para MCP, como Anthropic Claude, se conecte ao seu ambiente do Experience Manager Guides e aja em seu nome, com suas próprias permissões do AEM. Depois de conectado, você pode trabalhar com seus mapas, tópicos, linhas de base e relatórios no Experience Manager Guides as a Cloud Service usando uma linguagem natural simples.

Este artigo explica por que o MCP é útil para o Experience Manager Guides, o que o servidor MCP cobre, com quais aplicativos ele funciona e como usá-lo.

## Por que o MCP para Experience Manager Guides é útil

As equipes de documentação geralmente gastam um tempo significativo em tarefas repetitivas e de navegação intensa, como encontrar tópicos em um mapa grande, verificar estados dos documentos, rastrear links desfeitos, criar linhas de base para uma versão ou exportar relatórios. Com o servidor MCP do Experience Manager Guides, você pode solicitar que um assistente de IA cuide deles diretamente, sem alternar para a interface do usuário do Experience Manager Guides.

Por exemplo:

- Em vez de abrir um mapa e verificar o estado de cada tópico, peça ao assistente para listar os tópicos e seus estados.
- Em vez de iniciar manualmente um relatório de links quebrados e aguardar na interface do usuário do Experience Manager Guides, peça ao assistente para executar o relatório e informá-lo quando ele for concluído.
- Em vez de navegar até a tela da linha de base, peça ao assistente para criar uma linha de base para um mapa específico.

## Servidor MCP fornecido pela Experience Manager Guides

O Experience Manager Guides expõe os recursos do MCP para trabalhar com conteúdo do Experience Manager Guides e workflows relacionados. Dependendo das permissões do AEM, o servidor MCP fornece acesso aos seguintes recursos:

* **Tópicos e mapas**: trabalhe com tópicos e mapas em todo o ciclo de vida do conteúdo, desde a criação e exibição até a atualização, controle de versão, bloqueio e exclusão do conteúdo.
* **Linhas de Base**: trabalhe com linhas de base criando, listando, exportando, duplicando, recompilando e rotulando-as.
  >[!NOTE]
  >
  > Para ambientes Cloud Service e locais, os recursos da linha de base estão disponíveis somente quando a [nova linha de base](../user-guide/web-editor-baseline-v2.md) está habilitada.
* **Relatórios**: obtenha informações sobre seu conteúdo acessando listas de tópicos e metadados, identificando links com falha e revisando o uso de multimídia.
* **Sistema**: compreenda o estado do seu sistema verificando as versões do pacote, a integridade do pacote e o diagnóstico do ambiente.

Se você não tiver permissão para executar uma ação no AEM, não poderá executar a mesma ação por meio do MCP.

As ferramentas exatas disponíveis podem mudar com o tempo. Em vez de depender de uma lista fixa, peça ao assistente para mostrar o que está disponível:

`List all Experience Manager Guides tools available and describe what they do.`


## Aplicativos compatíveis

O servidor MCP do Experience Manager Guides é um servidor MCP remoto que pode se conectar com clientes MCP compatíveis. Com base em seu ambiente, conecte seu cliente MCP e autentique-se no servidor MCP do Experience Manager Guides. Para obter detalhes, consulte [Configurar o servidor MCP do Experience Manager Guides](./configure-aem-guides-mcp.md).

## Usando o servidor MCP do Experience Manager Guides

Depois de conectado, descreva em linguagem simples o que você deseja. O assistente seleciona a ferramenta apropriada e preenche seus parâmetros, como o caminho do mapa ou o nome da linha de base.

>[!IMPORTANT]
>
> As solicitações que envolvem várias etapas ou levam tempo para serem concluídas, como exportações, builds de linha de base e atualizações em massa, funcionam melhor com um modelo de pensamento. Eles são executados em segundo plano: o assistente inicia o trabalho e verifica seu status até que o resultado, ou um link de download, esteja pronto.

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


