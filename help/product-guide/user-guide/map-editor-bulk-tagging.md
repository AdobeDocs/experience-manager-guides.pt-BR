---
title: Marcação em massa de conteúdo DITA
description: Use a marcação em massa de conteúdo no AEM Guides para melhorar a descoberta de conteúdo DITA. Saiba como aplicar, remover, mostrar ou ocultar tags em massa em um único ou vários tópicos.
exl-id: 4c6639a3-333b-44ad-9aec-735a327c3320
feature: Metadata Management
role: User
TQID: https://experienceleague.adobe.com/aIDAXlejB9zW12EYhH0cOwCJpGTKwU42gfvrbUmMqJ4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 722
ht-degree: 0%

---

# Marcação em massa de conteúdo DITA {#id179SG0TN05Z}

![](images/test-version-info-table.svg){width="650"}

As tags permitem agrupar ou classificar o conteúdo no repositório de conteúdo e também na saída publicada. Se você tiver aplicado tags ao seu conteúdo, poderá encontrar facilmente tópicos relacionados em um mapa DITA que podem ajudá-lo a criar conteúdo. Com a saída publicada, os usuários finais poderão localizar o conteúdo correto mais rapidamente com as tags apropriadas em vigor.

O Adobe Experience Manager Guides permite marcar conteúdo DITA em algumas etapas. Você pode usar o recurso de marcação em massa para aplicar várias tags a vários tópicos, um mapa DITA ou um submapa. Ou você também pode aplicar tags a um tópico individual. A marcação é o recurso nativo no Adobe Experience Manager. Você pode encontrar mais detalhes sobre como criar e gerenciar tags na seção [Administração de tags](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) da documentação da Adobe Experience Manager.

Por padrão, a Experience Manager Guides não concede acesso de leitura a nenhum usuário na pasta em que todas as tags do repositório do Adobe Experience Manager estão armazenadas. Para usar tags definidas no repositório do Adobe Experience Manager, você deve solicitar que o administrador do sistema conceda acesso à pasta em que as tags estão armazenadas.

## Aplicar tags em massa

Use o recurso de marcação em massa para aplicar várias tags de uma só vez. Execute as seguintes etapas para aplicar tags aos seus tópicos em um mapa DITA:

1. Na interface do Assets, navegue e selecione o arquivo de mapa DITA.

   O console do mapa DITA é exibido mostrando a lista de Predefinições de saída disponíveis para gerar saída.

1. Selecione **Tópicos**.

   Uma lista de tópicos disponíveis no mapa DITA é exibida. Os UUIDs dos tópicos são mostrados abaixo do título do tópico.

1. Selecione os tópicos ou submapas nos quais deseja aplicar tags.

   ![](images/apply-tags-uuid.png){width="650"}


   >[!NOTE]
   >
   > A captura de tela acima mostra um submapa selecionado e expandido. Ao selecionar o submapa, todos os tópicos sob o submapa também são selecionados.

1. Selecione **Aplicar Tags**.

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

1. Na barra de ferramentas, selecione **Propriedades**.

   A página de propriedades do tópico é exibida.

1. Na guia Básico, selecione o ícone Procurar ao lado do campo **Tags**.

1. Selecione uma ou mais tags que deseja aplicar ao tópico selecionado.

1. Confirme sua seleção.

1. Selecione **Aplicar Tags**.

   As tags selecionadas são aplicadas ao tópico e mostradas no campo Tags.

1. Selecione **Salvar e fechar**.


## Remover tags

De acordo com suas necessidades comerciais, você pode alterar as informações de marcação de qualquer tópico DITA. Você pode remover facilmente todas as tags de uma só vez ou remover apenas as tags que não são válidas no tópico.

Execute as seguintes etapas para remover todas as tags de um ou mais tópicos:

1. Na interface do usuário do Assets, navegue até o arquivo de mapa DITA e selecione-o.

   O console do mapa DITA é exibido mostrando a lista de Predefinições de saída disponíveis para gerar saída.

1. Selecione **Tópicos**.

   Uma lista de tópicos disponíveis no mapa DITA é exibida.

1. Selecione os tópicos dos quais deseja remover tags.

1. Selecione **Remover Marcas**.

   >[!NOTE]
   >
   > Se o ícone Excluir tags não estiver visível, verifique se você não ativou o recurso Ocultar tags.

1. Na caixa de diálogo Confirmar Exclusão, selecione **OK** para remover marcas dos tópicos selecionados.


## Mostrar ou ocultar tags

Se você tiver uma longa lista de tags aplicadas em seus tópicos, talvez ache difícil navegar por ela. Você pode ocultar tags facilmente na exibição de console do mapa DITA selecionando o ícone Ocultar tags. Da mesma forma, quando as tags não estão visíveis, selecionar Mostrar tags revela todas as tags.

**Tópico pai:**[ Gerenciar metadados](manage-metadata.md)
