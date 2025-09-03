---
title: Solicitar uma revisão ou fechar uma tarefa de revisão como um Autor
description: Saber sobre o fluxo de trabalho de fechamento de uma tarefa de revisão ou de solicitação de uma revisão como um Autor no Experience Manager Guides.
feature: Reviewing
role: User
exl-id: d2119bbe-3a0c-4da3-b4f8-7872496fa61f
source-git-commit: 439be49e8f4c8cfacb16679257352f4197574365
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# Solicitar uma revisão ou fechar uma tarefa de revisão como um Autor

>[!IMPORTANT]
>
> Os novos recursos descritos neste artigo são ativados por padrão com a versão 2508 do Experience Manager Guides as a Cloud Services. As revisões criadas antes da migração não são afetadas e continuarão a usar o fluxo de trabalho anterior. Se preferir continuar usando os recursos existentes sem essas atualizações, entre em contato com a equipe de Sucesso do cliente para desabilitar os novos recursos.

Quando uma tarefa de revisão é marcada como concluída por um Revisor, uma notificação é disparada para o iniciador da tarefa, permitindo que ele acesse e revise a tarefa e os comentários relacionados no nível da tarefa.

Como iniciador da tarefa de revisão, você pode decidir como proceder com base no feedback. As opções disponíveis são:

- Solicitar uma revisão
- Fechar a tarefa de revisão

## Solicitar uma revisão ou fechar uma tarefa de revisão

Execute as seguintes etapas para solicitar uma revisão ou fechar uma tarefa de revisão:

1. Abra a tarefa Revisar no Editor.
2. No painel Revisão, selecione a tarefa de revisão na lista **Tarefas ativas**.

   >[!NOTE]
   >
   > Também é possível abrir a tarefa no painel de tarefas para obter uma visualização mais abrangente. Para fazer isso, selecione **Abrir no painel de tarefas** no menu Opções de qualquer tarefa de revisão ativa. Isso abre os detalhes da tarefa no console Projetos.

   ![](images/task-dashboard-selection-author-view.png)
3. Selecione a caixa de diálogo **Comentários da tarefa** para acessar e revisar os comentários no nível da tarefa adicionados pelo Revisor.

   ![](images/task-comments-selection-author-view.png).

   A caixa de diálogo **Comentários da tarefa** é exibida à direita.

   ![](images/task-comments-dialog-editor.png){width="350" align="left"}.
4. Selecione **Atualizar tarefa** para executar mais ações na tarefa de revisão selecionada.
5. Na caixa de diálogo **Atualizar tarefa**, escolha uma das seguintes ações:

   - **Solicitar uma revisão**: inicia outra rodada de revisão. É possível selecionar uma versão diferente do tópico para revisão. Por padrão, a versão mais recente (ou a última edição) do tópico ou arquivo de mapa enviado para revisão é selecionada. Você também pode usar a opção **Editar versões** para definir a versão dos tópicos selecionados como **Versão mais recente**, **Versão em** e **Linha de Base** de acordo com a necessidade.  Os revisores que concluíram a revisão anterior receberão uma notificação para fornecer feedback sobre a versão atualizada. Outros Revisores, que não marcaram a tarefa de revisão como concluída, serão notificados sobre a atualização do tópico.

   - **Fechar revisão**: fecha a tarefa de revisão. O botão **Atualizar tarefa**, presente na parte inferior do painel Revisão, muda para **Fechado** e uma notificação é enviada a todos os usuários envolvidos na tarefa de revisão indicando seu encerramento.

   Para obter detalhes sobre como as notificações de revisão disparam, exiba [Noções básicas sobre notificações de revisão](./review-understanding-review-notifications.md).

   ![](images/update-task-dialog.png){width="350" align="left"}

   >[!NOTE]
   >
   > A caixa de diálogo **Atualizar tarefa** também incluirá uma coluna **Estado do documento** para indicar o estado atual dos tópicos de revisão listados ao usar o Experience Manager Guides como Cloud Services.


6. Selecione **Confirmar**.


Como Autor ou iniciador de uma tarefa de revisão, ao fechá-la, o botão **Atualizar tarefa**, presente na parte inferior do painel Revisão, é alterado para **Fechado**, indicando que a tarefa não está mais ativa.

![](images/review-task-status-closed-review-panel.png){width="350" align="left"}

Além disso, o botão **Atualizar tarefa** presente no painel Revisão permanece desabilitado para os outros usuários da tarefa de revisão. Por exemplo, como um dos revisores de uma tarefa de revisão, se você abrir a tarefa no Editor, o botão Atualizar tarefa será desabilitado com uma mensagem **Você não tem permissão para agir nessa tarefa**. Somente o iniciador de uma tarefa de revisão tem permissão para atualizar a tarefa do Editor.

![](images/update-task-button-disabled.png){width="350" align="left"}
