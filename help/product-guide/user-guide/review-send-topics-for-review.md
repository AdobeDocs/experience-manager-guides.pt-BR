---
title: Enviar tópicos para revisão
description: Saiba como criar uma tarefa de revisão e enviar tópicos para revisão no AEM Guides. Envie um ou mais tópicos em um mapa DITA para revisão.
exl-id: c486eb6a-7e1f-4faa-973d-b47252d3e7c5
feature: Reviewing
role: User
source-git-commit: cd536b9e27b3c422fc723e9f13b12ac432fa3fc9
workflow-type: tm+mt
source-wordcount: '3055'
ht-degree: 0%

---

# Enviar tópicos para revisão {#id199RD0S035Z}

O fluxo de trabalho de revisão cria um ambiente de vários revisores em que o iniciador especifica uma lista de tópicos para revisão, adiciona vários revisores e atribui uma linha do tempo para a tarefa de revisão. O Adobe Experience Manager Guides permite que os usuários pertencentes aos grupos Autores e Editores iniciem uma revisão.

Como o fluxo de trabalho de revisão é específico do projeto, o iniciador da revisão deve fazer parte da equipe do projeto ou ter direitos para criar um projeto. No momento da criação de um projeto, você define os membros da equipe para o projeto e atribui a eles várias funções ou grupos. Para obter mais informações sobre projetos, consulte [Criar um projeto DITA](authoring-create-dita-project.md#).

É possível criar uma tarefa de revisão a partir de:

- **Editor**: permite enviar um tópico individual ou mapa DITA para revisão. Observe que o fluxo de trabalho para criar uma tarefa de revisão é comum na interface do Editor e do Assets. Somente o método de início do fluxo de trabalho de revisão é diferente. Para obter informações sobre como iniciar o fluxo de trabalho de revisão a partir do Editor, exiba o recurso [Criar Tarefa de Revisão](web-editor-left-panel.md#review) no Editor.

- **Interface do usuário do Assets**: permite enviar um ou vários tópicos e mapa DITA para revisão. O compartilhamento de documentos para revisão do fluxo de trabalho da interface do usuário do Assets é abordado neste tópico.


Na interface do usuário do Assets, há duas maneiras pelas quais um Autor/Editor pode criar uma tarefa de revisão:

- Enviar um ou mais tópicos para revisão
- Envie vários tópicos de um mapa DITA para revisão

## Enviar um ou mais tópicos para revisão {#id1721E600FY4}

>[!IMPORTANT]
>
> Antes de criar uma tarefa de revisão, verifique se você criou um projeto e adicionou revisores a ele.

Para criar uma tarefa de revisão e enviar tópicos para revisão, execute as seguintes etapas:

>[!NOTE]
>
> Você só poderá criar uma tarefa de revisão se for um autor ou editor em um projeto DITA.

1. Navegue até a pasta desejada na interface do usuário do Assets.

1. Escolha o ícone **Selecionar** na ação rápida e selecione os tópicos que deseja enviar para revisão.

   ![](images/select-asset-62.png){width="300" align="left"}

1. Na barra de ferramentas, selecione **Criar Tarefa de Revisão**. A página de criação da tarefa de revisão é exibida.

   >[!NOTE]
   >
   > É possível criar uma tarefa de revisão somente para os tópicos que têm uma revisão. Caso o tópico selecionado não tenha uma revisão, você receberá um prompt.

   ![](images/create-review-task-023.png){width="650" align="left"}

1. Insira um **Título** para a tarefa e selecione um projeto DITA.

1. No campo suspenso **Projeto**, selecione um projeto DITA para esta tarefa de revisão. Você também pode digitar o nome do projeto para localizá-lo rapidamente na lista suspensa.

1. No campo suspenso **Atribuir a**, selecione os revisores para os quais deseja enviar os tópicos para revisão.

   É possível atribuir uma tarefa de revisão a usuários individuais do projeto ou a grupos de usuários. Observe que você pode atribuir uma tarefa de revisão a usuários individuais somente quando fizer parte do grupo de administradores do projeto; caso contrário, você só exibirá os grupos de usuários no campo Atribuir a.

   >[!NOTE]
   >
   > O fluxo de trabalho de revisão é específico do projeto. Ao criar projetos, você adiciona os membros da equipe ao projeto e os atribui a grupos. Então quando você seleciona o projeto aqui, você tem que escolher os membros que são parte daquele projeto. Para obter mais informações sobre projetos, consulte [Criar um projeto DITA](authoring-create-dita-project.md#).

1. Insira uma **Descrição** para a tarefa.

   Essa descrição é usada como o corpo do email de notificação enviado aos revisores.

1. Selecione a **Data de vencimento** e a hora para marcar o prazo final para a revisão.

   >[!NOTE]
   >
   > Ao atingir o prazo final, um email é enviado ao iniciador notificando que a tarefa de revisão foi concluída. O iniciador pode estender o prazo da tarefa de revisão no [Painel de Revisão](review-manage-tasks-review-dashboard.md#).

1. Selecione o mapa raiz no **Caminho do mapa de raiz**. Esse roteiro é usado para resolver todas as principais referências e termos do glossário usados no conteúdo da revisão. Se você não selecionar o roteiro, as referências principais ou os termos do glossário associados ao tópico DITA não serão resolvidos antes de enviar o tópico para revisão.

   Se você estiver criando a revisão para um mapa DITA, por padrão, o **Caminho do mapa de roteiros** será definido como o caminho desse mapa. Se você estiver criando a revisão para um único tópico ou vários tópicos, por padrão, o **Caminho do mapa de roteiros** será definido como o mapa definido nas Preferências do usuário.

   >[!NOTE]
   >
   > O mapa raiz selecionado tem a precedência mais alta para resolver referências principais. Para obter mais detalhes, consulte [Resolver referências de chave](map-editor-other-features.md#id176GD01H05Z).

1. Como é possível atribuir diferentes revisores a tópicos diferentes, a opção **Permitir que os Atribuídos revisem qualquer tópico** controla se os revisores podem revisar todos os tópicos em uma tarefa de revisão ou apenas aqueles tópicos aos quais estão atribuídos para revisão.

   Se você quiser permitir que todos os revisores revisem qualquer tópico na tarefa de revisão, selecione **Permitir que os atribuídos revisem qualquer tópico**.

   Se você não selecionar essa opção, os revisores adicionados ao campo **Atribuir a** terão acesso para revisar somente os tópicos atribuídos a eles.

1. Selecione **Próximo**.

   A página Content é exibida.

   ![](images/content_page_review.png){align="left"}

1. Na página Conteúdo, selecione uma versão do tópico que você deseja compartilhar para revisão.

   Você pode usar um dos seguintes métodos para selecionar uma versão:

   - *\(Padrão\)* Escolha a opção **Sua Versão Mais Recente** para selecionar a última revisão salva dos tópicos.
   - Escolha a opção **Versão em** e especifique a data e a hora para selecionar uma versão como na data e hora especificadas. Se não houver nenhuma versão do tópico disponível na data especificada, uma versão disponível imediatamente após a data e a hora especificadas será selecionada.
   - Escolha a opção **Selecionar um Rótulo** e selecione um rótulo na lista suspensa.
1. Depois de fazer sua seleção para escolher uma versão, selecione **Aplicar**.

   A versão baseada na opção selecionada é escolhida para os tópicos.

   >[!NOTE]
   >
   > Você também pode selecionar manualmente a versão desejada na lista suspensa **Versão** de cada tópico.

1. Selecione **Próximo**.

   A página Revisores é exibida, onde você pode adicionar ou remover revisores. Por padrão, os revisores adicionados ao campo Atribuir a são adicionados automaticamente a cada tópico selecionado para a revisão.

   ![](images/add-reviewers-topics.png){width="650" align="left"}

1. Na página Revisores, você pode adicionar ou remover revisores. As seguintes operações estão disponíveis na página Revisores:

   - **Selecionar Tudo**: seleciona todos os tópicos da lista de tópicos. Você pode executar facilmente uma operação em lote após selecionar todos os tópicos.
   - **Limpar seleção**: desmarca os tópicos selecionados na lista de tópicos.

     >[!NOTE]
     >
     > Você também pode marcar ou desmarcar um tópico individualmente marcando a caixa de seleção ao lado do tópico.

   - **Adicionar**: exibe a caixa de diálogo Adicionar Revisores. É possível digitar o nome de um revisor ou função de usuário \(ou grupo\) que você deseja adicionar como revisor aos tópicos selecionados.
   - **Remover**: exibe a caixa de diálogo Remover Revisores. Você pode digitar o nome de um revisor ou função de usuário \(ou grupo\) que deseja remover como revisor dos tópicos selecionados.

     >[!NOTE]
     >
     > Você também pode remover uma revisão de um tópico selecionando o sinal cruzado na caixa do revisor.

   - **Reatribuir**: exibe a caixa de diálogo Reatribuir Revisores. É possível digitar o nome de um revisor ou função de usuário \(ou grupo\) à qual você deseja atribuir a tarefa de revisão. Isso remove todos os revisores existentes dos tópicos selecionados e atribui os revisores recém-selecionados a esses tópicos.
   - **Exportar**: permite exportar os detalhes da tarefa de revisão em um arquivo CSV. O arquivo contém detalhes como caminho e título do tópico, nome do revisor e versão dos tópicos enviados para revisão.
   - **Editar Revisores**: selecionar o ícone ![](images/edit_pencil_icon.svg) na lista de tópicos exibe a caixa de diálogo Editar Revisores. Você pode adicionar ou remover revisores para o tópico selecionado nesta caixa de diálogo.
1. Selecione **Criar** para criar a tarefa de revisão.

   Uma mensagem de confirmação é exibida quando a tarefa de revisão é criada com sucesso. O [Estado do documento](web-editor-document-states.md#) para os tópicos enviados para revisão está definido como Em revisão.

   >[!NOTE]
   >
   > Você também pode selecionar a Campainha de notificações na parte superior direita da tela e confirmar se a tarefa de revisão foi criada com sucesso. No painel Notificações, você encontrará uma notificação para cada revisor que fez parte da tarefa de revisão e uma notificação para o iniciador da revisão.


Um email é enviado para todos os revisores, notificando que eles receberam um tópico ou vários tópicos para revisão. O e-mail contém um link direto que eles podem usar para acessar o tópico em uma janela do navegador.

Caso vários tópicos sejam atribuídos, os revisores podem visualizá-los e selecioná-los em uma lista suspensa de tópicos no navegador da Web.

## Enviar vários tópicos para revisão a partir de um mapa DITA

Um mapa DITA é uma organização lógica de tópicos dentro de um livro. Quando você envia um tópico individual para revisão, o revisor não obtém nenhuma informação sobre a localização desse tópico no livro. Se um revisor tiver informações sobre o local exato do tópico que está sendo revisado, ele obterá um contexto melhor do tópico que está sendo revisado.

O Experience Manager Guides permite enviar um ou mais tópicos em um mapa DITA para revisão ao mesmo tempo. O revisor visualiza o arquivo de mapa completo juntamente com os tópicos que foram compartilhados para revisão. Isso facilita para o revisor obter um contexto do tópico no mapa ou arquivo de livro.

É possível compartilhar o mesmo mapa DITA no para revisão em várias tarefas de revisão. Por exemplo, se em um mapa DITA houver os tópicos A, B, C, D e E. Em uma tarefa de revisão, é possível compartilhar A, B e C para revisão, e em outra tarefa de revisão você pode enviar os tópicos C, D e E para revisão. O processo de revisão permite compartilhar o mesmo tópico e arquivo de mapa em várias tarefas de revisão. Para o tópico comum em várias tarefas de revisão, os comentários fornecidos em uma tarefa de revisão não substituem nem se mesclam aos comentários nas outras tarefas de revisão.

>[!IMPORTANT]
>
> Caso um tópico de um arquivo de mapa tenha sido compartilhado em várias tarefas de revisão, seu status mostrará Em revisão até que todas as tarefas de revisão tenham sido concluídas.

Para enviar um ou vários tópicos juntamente com o arquivo de mapa para revisão, execute as seguintes etapas:

>[!IMPORTANT]
>
> Depois de iniciar uma revisão por meio de um arquivo de mapa, você não deve alterar a estrutura do arquivo de mapa adicionando novos tópicos ou removendo tópicos existentes.

1. Navegue até a pasta desejada na interface do usuário do Assets.

   >[!NOTE]
   >
   > Verifique se a exibição do console está definida como exibição de cartão ou exibição de lista.

1. Selecione o mapa de onde deseja enviar os tópicos para revisão.

1. Na barra de ferramentas, selecione **Criar Tarefa de Revisão**. A página de criação da tarefa de revisão é exibida.

1. Insira um **Título** para a tarefa.

1. No campo suspenso **Projeto**, selecione um projeto DITA para esta tarefa de revisão. Você também pode digitar o nome do projeto para localizá-lo rapidamente na lista suspensa.

   >[!NOTE]
   >
   > É possível criar uma tarefa de revisão somente para os tópicos que têm uma revisão. Caso seu mapa contenha tópicos que não têm uma revisão, você verá um prompt com uma lista desses arquivos. Os arquivos sem uma revisão são excluídos da tarefa de revisão.

1. No campo suspenso **Atribuir a**, selecione os revisores para os quais deseja enviar os tópicos para revisão.

   É possível atribuir uma tarefa de revisão a usuários individuais do projeto ou a grupos de usuários. Observe que você pode atribuir uma tarefa de revisão a usuários individuais somente quando fizer parte do grupo de administradores do projeto; caso contrário, você só exibirá os grupos de usuários no campo Atribuir a.

   >[!NOTE]
   >
   > O fluxo de trabalho de revisão é específico do projeto. Ao criar projetos, você adiciona os membros da equipe ao projeto e os atribui a grupos. Então quando você seleciona o projeto aqui, você tem que escolher os membros que são parte daquele projeto. Para obter mais informações sobre projetos, consulte [Criar um projeto DITA](authoring-create-dita-project.md#).

1. Insira uma **Descrição** para a tarefa.

   Essa descrição é usada como o corpo do email de notificação enviado aos revisores.

1. Selecione a **Data de vencimento** e a hora para marcar o prazo final para a revisão.

   >[!NOTE]
   >
   > Ao atingir o prazo final, um email é enviado ao iniciador notificando que a tarefa de revisão foi concluída. O iniciador pode estender o prazo da tarefa de revisão no [Painel de Revisão](review-manage-tasks-review-dashboard.md#).

1. Como é possível atribuir diferentes revisores a tópicos diferentes, a opção **Permitir que os Atribuídos revisem qualquer tópico** controla se os revisores podem revisar todos os tópicos em uma tarefa de revisão ou apenas aqueles tópicos aos quais estão atribuídos para revisão.

   Se você quiser permitir que todos os revisores revisem qualquer tópico na tarefa de revisão, selecione **Permitir que os atribuídos revisem qualquer tópico**.

   Se você não selecionar essa opção, os revisores adicionados ao campo **Atribuir a** terão acesso para revisar somente os tópicos atribuídos a eles.

1. Selecione **Próximo**.

   A página Conteúdo é exibida com todos os tópicos referenciados do arquivo de mapa. Se o mapa DITA contiver mapas aninhados, os tópicos desses mapas também serão listados aqui.

   ![](images/content-page-map-review.png){align="left"}

1. Na página Conteúdo, selecione uma versão do tópico que você deseja compartilhar para revisão.

   Você pode usar um dos seguintes métodos para selecionar uma versão:

   - *\(Padrão\)* Escolha a opção **Sua Versão Mais Recente** para selecionar a última revisão salva dos tópicos.
   - Escolha a opção **Versão em** e especifique a data e a hora para selecionar uma versão de acordo com a data e a hora. Se não houver nenhuma versão do tópico disponível na data especificada, uma versão disponível imediatamente após a data e a hora especificadas será selecionada.
   - Escolha a opção **Selecionar um Rótulo** e selecione um rótulo na lista suspensa. Todos os tópicos contendo o rótulo selecionado são selecionados na lista suspensa **Versão**.
   - Escolha a opção **Selecionar uma Linha de Base** e selecione uma linha de base na lista suspensa. Todas as versões de tópico que fazem parte da linha de base selecionada são selecionadas na lista suspensa **Versão**.
1. Depois de fazer sua seleção para escolher uma versão, selecione **Aplicar**.

   A versão baseada na opção selecionada é escolhida para os tópicos.

   >[!NOTE]
   >
   > Você também pode selecionar manualmente a versão desejada na lista suspensa **Versão** de cada tópico.

1. Selecione **Próximo**.

   A página Revisores é exibida, onde você pode adicionar ou remover revisores. Por padrão, os revisores adicionados ao campo Atribuir a são adicionados automaticamente a cada tópico selecionado para a revisão.

1. Na página Revisores, você pode adicionar ou remover revisores. As seguintes operações estão disponíveis na página Revisores:

   - **Selecionar Tudo**: seleciona todos os tópicos da lista de tópicos. Você pode executar facilmente uma operação em lote após selecionar todos os tópicos.
   - **Limpar seleção**: desmarca os tópicos selecionados na lista de tópicos.

     >[!NOTE]
     >
     > Você também pode marcar ou desmarcar um tópico individualmente marcando a caixa de seleção ao lado do tópico.

   - **Adicionar**: exibe a caixa de diálogo Adicionar Revisores. É possível digitar o nome de um revisor ou função de usuário \(ou grupo\) que você deseja adicionar como revisor aos tópicos selecionados.
   - **Remover**: exibe a caixa de diálogo Remover Revisores. Você pode digitar o nome de um revisor ou função de usuário \(ou grupo\) que deseja remover como revisor dos tópicos selecionados.
   - **Reatribuir**: exibe a caixa de diálogo Reatribuir Revisores. É possível digitar o nome de um revisor ou função de usuário \(ou grupo\) à qual você deseja atribuir a tarefa de revisão. Isso remove todos os revisores existentes dos tópicos selecionados e atribui os revisores recém-selecionados a esses tópicos.
   - **Exportar**: permite exportar os detalhes da tarefa de revisão em um arquivo CSV. O arquivo contém detalhes como caminho e título do tópico, nome do revisor e versão dos tópicos enviados para revisão.
   - **Editar Revisores**: selecionar o ícone ![](images/edit_pencil_icon.svg) na lista de tópicos exibe a caixa de diálogo Editar Revisores. Você pode adicionar ou remover revisores para o tópico selecionado nesta caixa de diálogo.
   >[!IMPORTANT]
   >
   > Você deve atribuir pelo menos um revisor para criar a tarefa de revisão.

1. Selecione **Criar** para criar a tarefa de revisão.

   Uma mensagem de confirmação é exibida quando a tarefa de revisão é criada com sucesso. O [Estado do documento](web-editor-document-states.md#) para os tópicos enviados para revisão está definido como Em revisão.

   >[!NOTE]
   >
   > Você também pode selecionar o painel Notificações na parte superior direita da interface e confirmar se a tarefa foi criada com sucesso. No painel Notificações, você encontrará uma notificação para cada revisão que fez parte da tarefa de revisão e uma notificação para o iniciador da revisão.

   >[!IMPORTANT]
   >
   > Depois de iniciar uma revisão, você não deve mover nem excluir o mapa DITA ou os tópicos para um local diferente. Isso resultará em uma interrupção no processo de revisão.


Um email é enviado para todos os revisores, notificando que eles receberam tópicos para revisão. O e-mail contém um link direto que eles podem usar para acessar o tópico em uma janela do navegador. Os tópicos, juntamente com o mapa DITA, são abertos no modo de revisão.

## Adicionar ou remover tópicos de uma tarefa de revisão em andamento

Como Autor ou iniciador de uma tarefa de revisão, você pode adicionar novos tópicos a uma tarefa de revisão em andamento (se eles não tiverem sido enviados anteriormente para revisão) ou remover tópicos de uma tarefa de revisão em andamento sem afetar o fluxo de trabalho de revisão.

Execute as seguintes etapas para adicionar ou remover tópicos de uma tarefa de revisão em andamento:

1. No painel Revisão, navegue até a tarefa de revisão que deseja modificar e selecione **Abrir detalhes da tarefa** no menu de contexto.

   A página **Detalhes da Tarefa** é exibida.

1. Selecione a guia **CONTEÚDO** para exibir os tópicos atualmente incluídos na tarefa de revisão.
1. Revise a lista de tópicos e modifique a seleção conforme necessário.

   - Selecione novos tópicos que não foram enviados anteriormente para revisão.
   - Desmarque os tópicos que deseja remover da tarefa de revisão.

   >[!NOTE]
   >
   > Pelo menos um tópico deve permanecer selecionado para atualizar uma tarefa de revisão em andamento.

   ![](images/modify-review-topics.png)

1. Depois de modificar a lista de tópicos, as atualizações correspondentes são propagadas automaticamente para a guia **REVISORES** da página Detalhes da Tarefa.

   ![](images/modify-reviewers.png)

   Revise a lista de tópicos atualizada na guia Revisores. Para qualquer tópico novo adicionado, é necessário atribuir revisores, a menos que a configuração **Permitir que os atribuídos revisem qualquer tópico** esteja habilitada para a tarefa de revisão.
1. Selecione **Atualizar**.

Quando a tarefa de revisão for atualizada, os revisores receberão notificações (AEM e Email) com base no status da revisão:

- **Em andamento**: os revisores que ainda estão trabalhando na tarefa são notificados de que a tarefa foi atualizada.
- **Concluído**: os revisores que concluírem sua revisão receberão uma notificação solicitando uma revisão.

Para obter mais detalhes, consulte [Noções básicas sobre notificações de revisão](./review-understanding-review-notifications.md).


**Tópico pai:**&#x200B;[&#x200B; Introdução à revisão](review.md)
