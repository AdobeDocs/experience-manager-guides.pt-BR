---
title: Geração de saída
description: Gerencie o processo de geração de saída no AEM Sites, PDF, HTML5, EPUB, personalizado e JSON por meio de plug-ins DITA-OT, publicação original do PDF e FMPS no AEM Guides.
feature: Publishing
role: User
exl-id: 11bb3604-f45c-4df7-be74-588dbf8594af
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# Gerenciar processo de geração de saída

O Adobe Experience Manager Guides permite executar as seguintes ações na saída gerada:

- [Exibir o status da tarefa de geração de saída](#view-the-status-of-the-output-generation-task)
- [Cancelar uma tarefa de geração de saída](#cancel-an-output-generation-task)
- [Excluir uma tarefa de saída](#delete-an-output-task)

## Exibir o status da tarefa de geração de saída

Depois de iniciar a tarefa de geração de saída para um mapa ou gerar novamente os tópicos selecionados, o Experience Manager Guides envia essa tarefa para a fila de geração de saída. Essa fila é atualizada em tempo real, mostrando o status de cada tarefa de geração de saída na fila.

1. Na interface do usuário do Assets, navegue e abra o arquivo de mapa para o qual deseja verificar o status de geração de saída.

1. Selecione **SAÍDAS**.

   ![](images/output-queued.png){align="left"}

   A página Saídas é dividida em duas partes:

   - **Saídas na Fila:**

     Lista as saídas que estão aguardando para serem geradas ou que estão em processo de geração. As tarefas em fila ou em andamento são mostradas com um ícone de cor azul antes do nome predefinido. Você também pode encontrar a configuração de geração de saída ou a predefinição usada para a tarefa na fila, o tipo, o usuário que iniciou a tarefa, o tempo desde quando a tarefa está na fila e o status atual.

     Selecione o link para acessar o **Painel de Publicação** e exibir o status atual de execução. Uma lista de todas as tarefas de publicação ativas está disponível no Painel de publicação. As **Saídas Enfileiradas** e o link **Painel de Publicação** são exibidos somente quando há saídas que estão aguardando geração ou que estão em processo de geração. Eles não aparecem quando as tarefas de saída são concluídas.Para obter mais detalhes sobre o Painel de Publicação, exiba [Gerenciar tarefas de publicação usando o Painel de Publicação](generate-output-publish-dashboard.md#).

   - **Saídas Geradas**

     Lista as tarefas de saída concluídas. Novamente, as informações mostradas aqui são semelhantes à seção Saídas em fila, com algumas diferenças. Você tem um novo conjunto de informações na forma de ícone de resultado de saída e o tempo de geração da saída.

     Nesta lista, você pode ter tarefas executadas com sucesso, tarefas executadas com mensagem ou tarefas com falha. As tarefas bem-sucedidas são mostradas com ícone de cor verde, as tarefas com uma mensagem têm um ícone de cor laranja e as tarefas com falha são mostradas com ícone de cor vermelha.

     Para todas as tarefas, o processo de publicação cria um arquivo de log \(logs.txt\) que pode ser acessado selecionando o link na coluna Gerado em. Para tarefas que falharam ou têm mensagens, você pode verificar o arquivo de log, o que é explicado na seção [Exibir e verificar o arquivo de log](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > Ao selecionar o link da saída gerada do PDF, você é solicitado a baixar a PDF.


## Cancelar uma tarefa de geração de saída

O Experience Manager Guides oferece aos editores uma maneira simples e fácil de cancelar qualquer tarefa de publicação em andamento. Como editor, você pode cancelar uma tarefa de publicação em andamento no console de mapas DITA ou no [Painel de Publicação](generate-output-publish-dashboard.md#).

Execute as seguintes etapas para cancelar uma tarefa de geração de saída no console do mapa DITA:

1. Na interface do usuário do Assets, navegue e abra o arquivo de mapa para o qual deseja cancelar uma tarefa de geração de saída em andamento.

1. Selecione **SAÍDAS**.

1. Na lista **Saídas em fila**, passe o ponteiro sobre uma tarefa que você deseja cancelar.

1. Selecione o ícone **Cancelar este trabalho**.

   ![](images/cancel-publish-task-map-console.png){align="left"}

1. Selecione **Sim** no prompt de mensagem **Confirmar cancelamento**.

   ![](images/confirm-cancel-output-map-console.png){align="left"}

   Se a tarefa ainda não tiver sido iniciada, o comando cancel será executado na tarefa. Para uma tarefa que está sendo cancelada, o Status é definido como Canceling.

   Quando a tarefa for cancelada com êxito, ela será movida para a lista **Saídas Geradas** com o status **Cancelada**. Quando você passa o mouse sobre a tarefa cancelada, ele mostra o nome do usuário que cancelou a tarefa. Na captura de tela a seguir, a tarefa *HTML5* foi cancelada.

   ![](images/cancelled-output-task.png){align="left"}


## Excluir uma tarefa de saída

Quando você gera várias saídas para um mapa DITA, durante um período de tempo, a lista Saídas geradas para esse mapa se torna muito longa. Como editor, você pode limpar o histórico de saída de qualquer arquivo de mapa removendo as tarefas desatualizadas da lista *Saídas Geradas*. Observe que a saída não é removida do sistema, apenas a entrada da saída gerada é removida da lista *Saídas Geradas*.

Execute as seguintes etapas para remover uma tarefa de saída da lista Saída Gerada:

1. Na interface do usuário do Assets, navegue até o arquivo de mapa do qual deseja excluir as tarefas, e abra-o.

1. Selecione **SAÍDAS**.

1. Na lista **Saídas geradas**, passe o ponteiro sobre uma tarefa que você deseja excluir.

1. Selecione o ícone de exclusão.

   ![](images/delete-output-task.png){align="left"}

1. Selecione **Sim** no prompt de mensagem **Confirmar Exclusão**.

   A tarefa é excluída da lista Saída gerada.
