---
title: Gerenciar tarefas de publicação usando o Painel de publicação
description: Gerencie tarefas de publicação usando o Painel de publicação no AEM Guides. Saber como acessar o painel de publicação e cancelar uma tarefa de publicação.
exl-id: d9e25e52-ba9d-4088-ac95-8df76b69f5d3
feature: Publishing
role: User
source-git-commit: ff75aca9ddd7b405501a62e055fb99bd5ea2291c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Gerenciar tarefas de publicação usando o Painel de publicação {#id205CC08305Z}

Quando um grande conjunto de tarefas de publicação está em execução no sistema, torna-se praticamente impossível verificar cada mapa DITA individualmente para monitorar sua tarefa de publicação. O Adobe Experience Manager Guides fornece aos administradores e editores uma visualização unificada de todas as tarefas de publicação em execução no sistema. Uma lista de todas as tarefas de publicação ativas está disponível no Painel de publicação.

O Painel de publicação fornece uma visão geral completa de todas as tarefas de publicação atualmente em execução no sistema.

![](images/publish-dashboard.png){width="800" align="left"}

O Painel de publicação contém os seguintes detalhes:

- **Título do Mapa** - O título de um arquivo de mapa que está sendo publicado no momento ou que está na fila de publicação.

- **Nome do arquivo** - O nome do arquivo do mapa DITA.

- **Predefinição de saída** - Nome da predefinição de saída usada para gerar a saída.

- **Iniciado por** - Nome de usuário do usuário que iniciou a tarefa de publicação.

- **Iniciado em** - Data e hora em que a tarefa de publicação foi iniciada.

- **Tempo Decorrido** - Tempo desde quando a tarefa de publicação está em execução no sistema.

- **Ícone Excluir** - Cancelar ou encerrar uma tarefa de publicação.

O painel esquerdo no Painel de publicação fornece as seguintes opções de filtro:

- **Predefinição de Saída** - Selecione uma ou mais predefinições de saída para as quais deseja exibir as tarefas de publicação ativas no momento. Na captura de tela a seguir, as tarefas de publicação são filtradas para mostrar somente as tarefas que usam a predefinição de saída do AEM Site:

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Iniciado por** - Selecione um nome de usuário na lista para mostrar as tarefas de publicação iniciadas pelo usuário selecionado.

- **Mapa** - Selecione um arquivo de mapa na lista para mostrar as tarefas de publicação em execução para o mapa selecionado.

## Acessar o painel de publicação

Você pode acessar o **Painel de Publicação** diretamente da [Home page do Experience Manager Guides](./intro-home-page.md). Abra a página inicial e selecione a opção **Publicar fila** no painel esquerdo.

>[!NOTE]
>
> Somente um Administrador ou Editor pode acessar o Painel de publicação.

Você também pode acessar o **Painel de Publicação** na página **Ferramentas** do Adobe Experience Manager. Para usar esse método, execute as seguintes etapas:

1. Selecione o logotipo do Adobe Experience Manager na parte superior e selecione **Ferramentas**.

1. Selecione **Guias** na lista de ferramentas.

1. Selecione o bloco **Publicar painel**.

   O Painel de publicação é aberto com uma lista de todas as tarefas de publicação ativas no sistema.

   Se você selecionar o link Nome do arquivo, o painel de mapa DITA do mapa selecionado será exibido.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> Você também pode acessar o Painel de Publicação na guia **Saídas** enquanto gera a saída do painel de mapa. Para obter mais detalhes, consulte [Exibir o status da tarefa de geração de saída](generate-output-for-a-dita-map.md#viewing_output_history).

## Cancelar uma tarefa de publicação

Execute as seguintes etapas para cancelar uma tarefa de geração de saída no Painel de publicação:

1. [Acessar o Painel de Publicação](#access-the-publish-dashboard).

1. Na lista de tarefas de publicação ativas, selecione o ícone excluir de uma tarefa que deseja cancelar.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Selecione **Sim** no prompt de mensagem **Confirmar cancelamento**.

   O comando cancel é aceito e o cancelamento é tentado enquanto a tarefa permanecer ativa. Quando a tarefa for finalizada com sucesso, ela será removida da lista de tarefas ativas no momento. O status da tarefa também é atualizado no painel de mapa DITA como Cancelado. Na captura de tela a seguir, a tarefa *HTML5* é cancelada no Painel de Publicação e seu status também é alterado no painel de mapa DITA.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Tópico pai:**[ Geração de saída](generate-output.md)
