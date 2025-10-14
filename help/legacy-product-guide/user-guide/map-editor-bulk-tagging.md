---
title: Marcação em massa de conteúdo DITA
description: Use a marcação em massa de conteúdo no AEM Guides para melhorar a descoberta de conteúdo DITA. Saiba como aplicar, remover, mostrar ou ocultar tags em massa em um único ou vários tópicos.
feature: Metadata Management
role: User
hide: true
exl-id: b320e34f-ee0a-4cc3-b4f6-d322fbb29844
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 0%

---

# Marcação em massa de conteúdo DITA {#id179SG0TN05Z}

As tags permitem agrupar ou classificar o conteúdo no repositório de conteúdo e também na saída publicada. Se você tiver aplicado tags ao seu conteúdo, poderá encontrar facilmente tópicos relacionados em um mapa DITA que podem ajudá-lo a criar conteúdo. Com a saída publicada, os usuários finais poderão localizar o conteúdo correto mais rapidamente com as tags apropriadas em vigor.

O AEM Guides permite marcar o conteúdo DITA com apenas alguns cliques. Você pode usar o recurso de marcação em massa para aplicar várias tags a vários tópicos, um mapa DITA ou um submapa. Ou você também pode aplicar tags a um tópico individual. A marcação é o recurso nativo no AEM. Você pode encontrar mais detalhes sobre como criar e gerenciar tags na seção [Administração de tags](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=pt-BR) da documentação da AEM.

Por padrão, a AEM Guides não concede acesso de leitura a nenhum usuário na pasta em que todas as tags do repositório do AEM estão armazenadas. Para usar tags definidas no repositório do AEM, você deve solicitar que o administrador do sistema conceda acesso à pasta em que as tags estão armazenadas.

## Aplicar tags em massa

Use o recurso de marcação em massa para aplicar várias tags de uma só vez. Execute as seguintes etapas para aplicar tags aos seus tópicos em um mapa DITA:

1. Na interface do usuário do Assets, navegue e clique no arquivo de mapa DITA.

   O console do mapa DITA é exibido mostrando a lista de Predefinições de saída disponíveis para gerar saída.

1. Clique em **Tópicos**.

   Uma lista de tópicos disponíveis no mapa DITA é exibida. Os UUIDs dos tópicos são mostrados abaixo do título do tópico.

1. Selecione os tópicos ou submapas nos quais deseja aplicar tags.

   ![](images/apply-tags-uuid.png){width="650" align="left"}


   >[!NOTE]
   >
   > A captura de tela acima mostra um submapa selecionado e expandido. Ao selecionar o submapa, todos os tópicos sob o submapa também são selecionados.

1. Clique em **Aplicar marcas**.

   A caixa de diálogo Selecionar tags é exibida.

1. Selecione uma ou mais tags que deseja aplicar aos tópicos selecionados.

1. Confirme sua seleção.

   As tags selecionadas são aplicadas aos tópicos e mostradas ao lado do título do tópico.

   >[!NOTE]
   >
   > Depois de adicionar tags aos tópicos, se você mover ou excluir um tópico, as tags desses tópicos também serão removidas. No entanto, esse tópico permanece no mapa até que você o remova.


## Aplicar tags em um tópico individual

Execute as seguintes etapas para aplicar tags a um tópico individual:

1. Na interface do usuário do Assets, navegue até o arquivo de tópico no qual deseja aplicar tags e selecione-o.

1. Na barra de ferramentas, clique em **Propriedades**.

   A página de propriedades do tópico é exibida.

1. Na guia Básico, clique no ícone Procurar ao lado do campo **Tags**.

1. Selecione uma ou mais tags que deseja aplicar ao tópico selecionado.

1. Confirme sua seleção.

1. Clique em **Aplicar marcas**.

   As tags selecionadas são aplicadas ao tópico e mostradas no campo Tags.

1. Clique em **Salvar e fechar**.


## Remover tags

De acordo com suas necessidades comerciais, você pode alterar as informações de marcação de qualquer tópico DITA. Você pode remover facilmente todas as tags de uma só vez ou remover apenas as tags que não são válidas no tópico.

Execute as seguintes etapas para remover todas as tags de um ou mais tópicos:

1. Na interface do usuário do Assets, navegue e clique no arquivo de mapa DITA.

   O console do mapa DITA é exibido mostrando a lista de Predefinições de saída disponíveis para gerar saída.

1. Clique em **Tópicos**.

   Uma lista de tópicos disponíveis no mapa DITA é exibida.

1. Selecione os tópicos dos quais deseja remover tags.

1. Clique em **Remover Marcas**.

   >[!NOTE]
   >
   > Se o ícone Excluir tags não estiver visível, verifique se você não ativou o recurso Ocultar tags.

1. Na caixa de diálogo Confirmar Exclusão, clique em **OK** para remover marcas dos tópicos selecionados.


## Mostrar ou ocultar tags

Se você tiver uma longa lista de tags aplicadas em seus tópicos, talvez ache difícil navegar por ela. Você pode ocultar tags facilmente na exibição do console de mapa DITA clicando no ícone Ocultar tags. Da mesma forma, quando as tags não estão visíveis, clicar em Mostrar tags revela todas as tags.

**Tópico pai:**&#x200B;[&#x200B; Gerenciar metadados](manage-metadata.md)
