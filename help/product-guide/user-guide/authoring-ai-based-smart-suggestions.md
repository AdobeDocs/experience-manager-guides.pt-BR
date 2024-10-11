---
title: Sugestões inteligentes alimentadas por IA para criar conteúdo
description: Saiba como visualizar e utilizar sugestões inteligentes habilitadas por IA no Editor da Web.
exl-id: 23c5285e-0d4f-484a-a062-fe1ba1608b8d
source-git-commit: 6cf65f70252e133cf8977ce925f0a103dc79c0ec
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# Sugestões inteligentes habilitadas por IA para criar conteúdo

O Experience Manager Guides fornece as sugestões inteligentes que ajudam a criar conteúdo consistente e preciso.

Enquanto você cria conteúdo, o recurso **Sugerir conteúdo reutilizável** na ferramenta Assistente de IA pode pesquisar usando a IA e mostrar o conteúdo existente semanticamente semelhante ao seu conteúdo. Você pode então escolher o melhor conteúdo correspondente que deseja incluir em seu tópico atual como referência.

Isso ajuda a reutilizar o conteúdo existente do repositório de documentação e criar conteúdo consistente. Por exemplo, você está criando um documento contendo informações sobre **Adobe Firefly**, incluindo um parágrafo sobre **Adobe**. Nesse caso, você pode visualizar e adicionar rapidamente a referência de conteúdo de outro tópico, como **Adobe Photoshop**, que inclui o mesmo parágrafo.
>[!NOTE]
>
> Nos [perfis globais ou de nível de pasta](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), o administrador precisa definir os arquivos ou pastas a serem indexados para sugestões inteligentes, o número mínimo de caracteres que você precisa inserir para exibir as sugestões e o número máximo de sugestões que você pode exibir na lista.

Execute as seguintes etapas para exibir as sugestões inteligentes para adicionar referências de conteúdo apropriadas ao seu tópico:


1. Selecione o conteúdo do tópico para exibir as sugestões relacionadas. Verifique se o comprimento de caracteres do conteúdo excede o que o administrador definiu no perfil da pasta para que as sugestões de conteúdo sejam exibidas.
1. No painel Assistente de IA, selecione **Sugerir conteúdo reutilizável** ![ai sugerir conteúdo reutilizável ](./images/ai-suggest-reusable-content-icon.svg).

1. Selecione uma tag para exibir as sugestões de criação para a tag atual.  As sugestões para exibir e adicionar referências de conteúdo dos arquivos indexados são exibidas com base no conteúdo da tag atual. Também é possível selecionar várias tags.


1. Selecione todas as tags para exibir as sugestões com base no conteúdo presente no documento completo.  O ícone **Sugerir conteúdo reutilizável** ![ai sugerir conteúdo reutilizável ](./images/ai-suggest-reusable-content-icon.svg) é exibido ao lado do conteúdo, onde uma correspondência adequada é encontrada.



   >[!NOTE]
   >
   > Você só pode exibir as sugestões para o visor atual (o conteúdo visível na tela). Para exibir sugestões para qualquer outro conteúdo do documento, role para cima ou para baixo para exibi-lo no visor e selecione **Sugerir conteúdo reutilizável** ![ai sugerir ícone de conteúdo reutilizável ](./images/ai-suggest-reusable-content-icon.svg).


1. Você pode exibir as sugestões inteligentes no painel de sugestões.  O Experience Manager Guides fornece sugestões de conteúdo que é contextualmente semelhante ou tem o mesmo significado. Por exemplo, você pode pesquisar pelo tópico que contém o número exato da versão, como &quot;versão 2023.03.12&quot;. Você também pode pesquisar por &quot;Adobe tem sede em San Jose, Califórnia&quot; e encontrar conteúdo semelhante como &quot;San Jose tem o quartel de muitas empresas de software como Adobe&quot;.
1. Selecione **Informações de Conteúdo** ![Informações de Conteúdo](images/smart-suggestions-content-info-icon.svg) para exibir os detalhes.

   ![Painel de informações de conteúdo](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Exibir as informações detalhadas sobre a referência de conteúdo.*

   1. O título do tópico que contém a referência de conteúdo é exibido como um hiperlink.
   1. O caminho do arquivo que contém a referência de conteúdo.
   1. O tipo de referência para o qual o conteúdo é referenciado.
   1. Os nomes dos arquivos DITA para os quais o tópico é referido são exibidos como hiperlinks.
1. Selecione o **ícone de visualização** ![para comparar o conteúdo atual com o conteúdo sugerido. ](./images/expand-icon.svg) Isso o ajuda a comparar as diferenças e determinar se deseja adicionar a referência de conteúdo para o conteúdo sugerido e torná-lo consistente ou manter o conteúdo atual.

   ![Sugerir visualização de conteúdo reutilizável](images/ai-assistant-suggest-reusable-content.png)

   *Visualize a comparação entre o conteúdo atual e o conteúdo sugerido.*

1. Clique em **Aceitar** para adicionar a referência de conteúdo sugerida na visualização de **Sugerir conteúdo reutilizável**.
1. Você também pode selecionar **Aceitar** ou **Dispensar** no painel de sugestões para as recomendações apropriadas.


Esse recurso inteligente é útil e minimiza o esforço de pesquisa manual de conteúdo, permitindo que você se concentre mais na geração de novo conteúdo. Também facilita uma melhor colaboração em equipe e ajuda a manter a consistência no conteúdo criado por vários autores.

>[!NOTE]
>
>As sugestões inteligentes não retêm os dados além da sessão atual. Para respostas do, as sugestões inteligentes dependem apenas do índice criado no conteúdo que reside no banco de dados interno. As ferramentas de IA externa não são usadas, garantindo que os dados permaneçam no sistema.
