---
title: Traduzir tópicos modificados
description: Saiba como traduzir novamente um tópico modificado no AEM Guides.
exl-id: b3228ea9-24a8-44aa-8ba4-e8f44754ffe4
feature: Translation
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Traduzir tópicos modificados {#id16A5A0B6072}

Se você fizer alterações em alguns dos tópicos, elas exigirão uma nova tradução. Você pode rastrear os tópicos modificados no mapa DITA. Na pasta de cópia do idioma de origem, clique no arquivo de mapa DITA e clique na guia Translation. Você pode ver o status de cada tópico, independentemente de exigir nova tradução ou não.

Execute as seguintes etapas para enviar um tópico modificado para nova tradução:

1. Clique no arquivo de mapa DITA na pasta de cópia do idioma de origem.

1. Clique na guia **Tradução**.

1. No painel **Filtro** à esquerda, selecione **Traduzir Idiomas** para verificar o status e clique em **Concluído**.

   Você pode ver o status da tradução de cada tópico. Os tópicos que têm outra revisão de tópico disponível diferente da que foi enviada para tradução mostram um status **Desatualizado**.

   >[!NOTE]
   >
   > O fluxo de trabalho de tradução compara a última revisão salva do arquivo de tópico na pasta de idioma de origem com a versão traduzida.

   Se você clicar na seta para ver mais detalhes. você pode ver a cópia de idioma específica que está desatualizada.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Clique na caixa de seleção para selecionar os tópicos que deseja enviar para nova tradução.

   Ao selecionar uma data fora de sincronia, a opção **Criar/Atualizar Cópias de Idioma** é exibida no painel Referências e no botão **Ignorar Status Fora de Sincronia** acima do ícone **Filtro**.

   Você pode usar o botão **Ignorar fora de sincronização** para substituir o status Desatualizado dos tópicos no mapa DITA. Por exemplo, se você tiver feito algumas alterações na versão em inglês do tópico que não precisa de tradução, poderá usar esse botão e alterar o status Desatualizado para o tópico selecionado.

   >[!NOTE]
   >
   > Se você clicar no botão **Ignorar status fora de sincronização**, ele definirá o status do tópico como Atualizado para os tópicos desatualizados selecionados.

1. Clique em **Atualizar cópias de idioma** e configure o trabalho de tradução.

1. Você pode optar por criar um novo projeto de tradução ou adicionar tópicos a um projeto de tradução existente. Forneça os detalhes necessários para configurar o projeto de tradução.

1. Clique em **Iniciar**.

   Uma mensagem de confirmação é exibida mostrando que o tópico foi enviado para tradução.

1. Navegue até o projeto de tradução no console Projeto. Um novo cartão de tarefa de tradução é criado na pasta. Clique nas reticências para ver os ativos da pasta.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Para iniciar a tradução, clique na seta no cartão de trabalho de tradução e selecione **Iniciar** na lista. Uma mensagem notifica que o trabalho foi iniciado.

   Você também pode visualizar o status do tópico que está sendo traduzido ao clicar nas reticências na parte inferior do cartão de tarefa de tradução.

   >[!NOTE]
   >
   > Se você estiver usando o serviço de tradução humana, será necessário exportar o conteúdo para tradução. Depois de ter o conteúdo traduzido, é necessário importá-lo de volta para o projeto de tradução.

1. Após a conclusão da tradução, o status muda para **Pronto para Revisão**. Clique nas reticências para ver os detalhes do tópico e siga um destes procedimentos na barra de ferramentas:

   - Clique em **Revelar no Assets** para ver e verificar a tradução.

   - Clique em **Aceitar tradução** se achar que as alterações foram traduzidas corretamente. Uma mensagem de confirmação é exibida.

   - Clique em **Rejeitar tradução** se achar que o trabalho precisa ser refeito. Uma mensagem de rejeição é exibida.

   >[!NOTE]
   >
   > É importante aceitar ou rejeitar o ativo traduzido, caso contrário, o arquivo permanecerá no local temporário e não será copiado para o DAM.

1. Volte para o arquivo de mapa DITA na pasta de idioma de origem na interface do Assets. Os tópicos retraduzidos agora estão em sincronia.


**Tópico pai:**[ Traduzir conteúdo](translation.md)
