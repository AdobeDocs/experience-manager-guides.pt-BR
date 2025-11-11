---
title: Notas de versão | Novidades da versão 2025.10.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2025.10.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: bf08a48cd00170bdbe8cde312aac9776f871dbf9
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Novidades da versão 2025.10.0 (outubro de 2025)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2025.10.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2025.10.0](fixed-issues-2025-10-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.10.0](../release-info/upgrade-instructions-2025-10-0.md).


## As configurações do editor agora são renomeadas para configurações do Workspace e podem ser acessadas na Página inicial

Para melhorar a navegação e a usabilidade, foram introduzidos os seguintes aprimoramentos:

- As **configurações do editor** no Experience Manager Guides foram renomeadas para **configurações do Workspace**.
- O menu **Mais ações** (o menu de três pontos), anteriormente disponível apenas na interface do Editor e do console de Mapa, agora pode ser acessado na [Página inicial](../user-guide/intro-home-page.md).

  ![](assets/workspace-settings.png)

## Identifique e corrija facilmente IDs duplicadas em tópicos e mapas na exibição Autor

O Experience Manager Guides agora inclui um botão **IDs duplicadas** no Editor para ajudar você a identificar e corrigir rapidamente as IDs duplicadas presentes em um único tópico ou mapa. Quando IDs duplicadas são detectadas, este botão aparece no canto inferior esquerdo da interface do Editor na exibição **Autor**. Ao selecionar o botão, uma lista de todas as instâncias com IDs duplicadas é exibida em um popover. A seleção de uma ocorrência destaca o conteúdo correspondente no tópico ou mapa, permitindo que você localize e corrija as IDs duplicadas no painel direito.

Para obter mais detalhes, exiba [Recursos adicionais no Editor](../user-guide/web-editor-other-features.md).

![](assets/duplicate-element-IDs.png){width="350" align="left"}

## Melhorias nos filtros de Repositório e Relatórios

O filtro **Bloqueado por** nos filtros Avançado do Repositório e **Autor** nos Relatórios de mapa DITA agora carregam listas de usuários gradualmente conforme você rola a tela, em vez de carregar tudo de uma vez. Esse carregamento paginado melhora a velocidade e torna o trabalho com grandes conjuntos de dados de usuários mais eficiente e simples.

## Acessar o status de tarefas de revisão diretamente do painel Revisão

Como iniciador de uma tarefa de revisão, agora é possível verificar o status da tarefa de revisão diretamente do painel Revisão. Com os últimos aprimoramentos, a caixa de diálogo **Atualizar tarefa** no painel Revisão inclui uma nova opção **Verificar status da revisão**. A seleção dessa opção leva você diretamente ao painel de revisão, onde é possível visualizar o status da tarefa para cada revisor, permitindo um acesso mais rápido ao progresso da tarefa sem a necessidade de alternar contextos.

Para obter mais detalhes, exiba [Solicitar uma revisão ou feche uma tarefa de revisão como um Autor](../user-guide/review-close-review-task.md).

![](assets/check-review-status-icon.png){width="350" align="left"}



## API para rastrear o status pós-processamento de pastas ou ativos

Uma nova API agora está disponível para rastrear o status de pós-processamento de ativos e pastas individuais. Isso é especialmente útil para equipes que usam fluxos de trabalho automatizados, em que a publicação precisa ocorrer somente após o conteúdo ser totalmente processado. A API oferece uma maneira confiável de confirmar a prontidão, reduzindo o risco de falhas de publicação causadas por processamento incompleto.

Além disso, com a introdução dessa API, os eventos de pós-processamento de ativos não serão acionados automaticamente. Em vez disso, os administradores agora podem habilitar esse evento por meio de uma configuração no `fmdita config manager`.

Para obter detalhes, consulte:

- [API para rastrear o status de pós-processamento de ativos e pastas individuais](../api-reference/track-post-processing-status.md)
- [Configuração do manipulador de eventos pós-processamento no gerenciador de configurações da fmdita](../api-reference/post-process-event.md)

