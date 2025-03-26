---
title: Exibir o status da tarefa de geração de saída
description: Visualize a fila de geração de saída de documentos do FrameMaker. Saiba como visualizar o status de uma tarefa de geração de saída.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Exibir o status da tarefa de geração de saída {#viewing_output_history}

Depois de iniciar a tarefa de geração de saída para um documento do FrameMaker, o AEM Guides envia essa tarefa para a fila de geração de saída. Essa fila é atualizada em tempo real, mostrando o status de cada tarefa de geração de saída na fila.

Execute as seguintes etapas para exibir a fila de geração de saída:

1. Na interface do usuário do Assets, navegue até o documento FrameMaker e clique nele para verificar o status de geração de saída.

1. Clique em Saídas.

   ![](images/output-queued-fm.png){align="left"}

1. A página Saídas é dividida em duas partes:

   - **Saídas na Fila:**

     Lista as saídas que estão aguardando para serem geradas ou que estão em processo de geração. Você também pode encontrar a configuração de geração de saída ou a predefinição usada para a tarefa na fila, o tipo, o usuário que iniciou a tarefa, o tempo desde quando a tarefa está na fila e o status atual.

   - **Saídas Geradas**

     Lista as tarefas de saída concluídas. Novamente, as informações mostradas aqui são semelhantes à seção Saídas em fila, com a única diferença do tempo de geração de saída.

     Nesta lista, você pode ter tarefas que foram executadas com sucesso ou tarefas que falharam. Para as tarefas concluídas com sucesso, o processo de publicação cria um arquivo de log \(logs.txt\) que pode ser acessado clicando no link da coluna Gerado em.


**Tópico pai:**[ Gerar saída de documentos do FrameMaker](fm-output-generatation.md)
