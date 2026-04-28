---
title: Sugestões inteligentes alimentadas por IA para criar conteúdo
description: Saiba como visualizar e utilizar sugestões inteligentes habilitadas por IA no Editor da Web.
hide: true
exl-id: 30c85d46-61ba-486c-979c-1a2ed95f5a32
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 0%

---

# Sugestões inteligentes habilitadas por IA para criar conteúdo

O Experience Manager Guides fornece as sugestões inteligentes que ajudam a criar conteúdo consistente e preciso.

Enquanto você cria conteúdo, o recurso **Sugerir conteúdo reutilizável** na ferramenta Assistente de IA pode pesquisar usando a IA e mostrar o conteúdo existente semanticamente semelhante ao seu conteúdo. Você pode então escolher o melhor conteúdo correspondente que deseja incluir em seu tópico atual como referência.

Isso ajuda a reutilizar o conteúdo existente do repositório de documentação e criar conteúdo consistente. Por exemplo, você está criando um documento contendo informações sobre o **Adobe Firefly**, incluindo um parágrafo sobre o **Adobe**. Nesse caso, você pode visualizar e adicionar rapidamente a referência de conteúdo de outro tópico, como **Adobe Photoshop**, que inclui o mesmo parágrafo.
>[!NOTE]
>
> Nos [perfis globais ou de nível de pasta](/help/product-guide/cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), o administrador precisa definir os arquivos ou pastas a serem indexados para sugestões inteligentes, o número mínimo de caracteres que você precisa inserir para exibir as sugestões e o número máximo de sugestões que você pode exibir na lista.

Execute as seguintes etapas para exibir as sugestões inteligentes para adicionar referências de conteúdo apropriadas ao seu tópico:


1. Selecione o conteúdo do tópico para exibir as sugestões relacionadas. Verifique se o comprimento de caracteres do conteúdo excede o que o administrador definiu no perfil da pasta para que as sugestões de conteúdo sejam exibidas.
1. No painel Assistente de IA, selecione **Sugerir conteúdo reutilizável** ![ai sugerir conteúdo reutilizável ](./images/ai-suggest-reusable-content-icon.svg).

1. Selecione uma tag para exibir as sugestões de criação para a tag atual.  As sugestões para exibir e adicionar referências de conteúdo dos arquivos indexados são exibidas com base no conteúdo da tag atual. Também é possível selecionar várias tags.


1. Selecione todas as tags para exibir as sugestões com base no conteúdo presente no documento completo.  O ícone **Sugerir conteúdo reutilizável** ![ai sugerir conteúdo reutilizável ](./images/ai-suggest-reusable-content-icon.svg) é exibido ao lado do conteúdo, onde uma correspondência adequada é encontrada.



   >[!NOTE]
   >
   > Você só pode exibir as sugestões para o visor atual (o conteúdo visível na tela). Para exibir sugestões para qualquer outro conteúdo do documento, role para cima ou para baixo para exibi-lo no visor e selecione **Sugerir conteúdo reutilizável** ![ai sugerir ícone de conteúdo reutilizável ](./images/ai-suggest-reusable-content-icon.svg).


1. Você pode exibir as sugestões inteligentes no painel de sugestões.  O Experience Manager Guides fornece sugestões de conteúdo que é contextualmente semelhante ou tem o mesmo significado. Por exemplo, você pode pesquisar pelo tópico que contém o número exato da versão, como &quot;versão 2023.03.12&quot;. Você também pode pesquisar por &quot;Adobe tem sede em San Jose, Califórnia&quot; e encontrar conteúdo semelhante a &quot;San Jose tem o quartel de muitas empresas de software, como a Adobe&quot;.
1. Select **Content Information** ![Content Information](images/smart-suggestions-content-info-icon.svg) to view the details.

   ![Content information panel](images/smart-suggestions-content-information.png){width="300" align="left"}

   *View the detailed information about the content reference.*

   1. The title of the topic that contains the content reference is displayed as a hyperlink.
   1. The path of the file that contains the content reference.
   1. The type of reference where the content is referred.
   1. The names of DITA files where the topic is referred to are displayed as hyperlinks.
1. Select **Preview** ![preview icon](./images/expand-icon.svg) to compare the current content with the suggested content. This helps you compare the differences and determine if you want to add the content reference for the suggested content and make it consistent or retain your current content.

   ![Suggest reusable content preview](images/ai-assistant-suggest-reusable-content.png)

   *Preview the comparison between the current content and the suggested content.*

1. Click **Accept** to add the suggested content reference in the **Suggest reusable content** preview.
1. You can also select **Accept** or **Dismiss** in the suggestions panel for the appropriate recommendations.


This intelligent feature is handy and minimizes the effort of manual content searching, allowing you to concentrate more on generating new content. It also facilitates better team collaboration and helps maintain consistency in the content created by various authors.

>[!NOTE]
>
>Smart suggestions don&#39;t retain your data beyond the current session. For responses, smart suggestions rely solely upon the index created on the content residing within your internal database. External AI tools are not used, ensuring your data remains within the system.
