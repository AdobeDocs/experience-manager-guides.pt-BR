---
title: Sugestões inteligentes alimentadas por IA para criar conteúdo
description: Saiba como visualizar e utilizar Sugestões inteligentes habilitadas por IA no Editor da Web.
exl-id: 23c5285e-0d4f-484a-a062-fe1ba1608b8d
source-git-commit: 75425d82ee55485503ea6678030c5e919e50a691
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---

# Sugestões inteligentes alimentadas por IA para criar conteúdo

Os Guias do Experience Manager fornecem o **Sugestões inteligentes** recurso que ajuda a criar conteúdo consistente e preciso.

Enquanto você cria conteúdo, a variável **Sugestões inteligentes** O recurso de pode pesquisar usando IA e mostrar o conteúdo existente que é semanticamente semelhante ao seu conteúdo. Você pode então escolher o melhor conteúdo correspondente que deseja incluir em seu tópico atual como referência.

Isso ajuda a reutilizar o conteúdo existente do repositório de documentação e criar conteúdo consistente. Por exemplo, você está criando um documento contendo informações sobre **Adobe Firefly**, incluindo um parágrafo sobre **Adobe**. Nesse caso, você pode visualizar e adicionar rapidamente a referência de conteúdo de outro tópico, como **Adobe Photoshop**, que inclui o mesmo parágrafo.





Quando você abre um tópico no Editor da Web, a variável **Sugestões inteligentes** é exibido à direita.

>[!NOTE]
>
> O administrador deve configurar o **Sugestões inteligentes** recurso. Para obter mais detalhes, consulte [Configurar as sugestões inteligentes habilitadas por IA para criação](../cs-install-guide/conf-smart-suggestions.md) no Guia de instalação e configuração do Cloud Service.

![Painel de sugestões inteligentes](images/smart-suggestions-panel.png){width="300" align="left"}

*Exibir o **Sugestões inteligentes**painel.*

Execute as seguintes etapas para exibir as sugestões inteligentes para adicionar referências de conteúdo apropriadas ao seu tópico:

1. Selecionar **Sugestões inteligentes** ![ícone de sugestões inteligentes](images/smart-suggestions-icon.svg) para abrir o painel.



   >[!NOTE]
   >
   > No [perfis globais ou de nível de pasta](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), o administrador precisa definir os arquivos ou pastas a serem indexados para sugestões inteligentes, o número mínimo de caracteres que você precisa inserir para exibir as sugestões e o número máximo de sugestões que você pode exibir na lista.

1. Digite o conteúdo do tópico para exibir as sugestões relacionadas. Verifique se o comprimento de caracteres do conteúdo excede o que o administrador definiu no perfil da pasta para que as sugestões de conteúdo sejam exibidas.

1. Selecionar **Sugestões para a tag atual** ![ícone de tag atual de sugestões inteligentes](images/smart-suggestions-current-tag-icon.svg) para exibir as sugestões de criação para a tag atual onde você coloca o ponteiro do mouse.  As sugestões para exibir e adicionar referências de conteúdo dos arquivos indexados são exibidas com base no conteúdo da tag atual.

   Atalho de teclado: **Windows** (*Ctrl* + *K*),  **macOS** (*Comando* + *K*)
1. Selecionar **Sugestões para o documento completo**  ![ícone de documento de conclusão das sugestões inteligentes](images/smart-suggestions-complete-document-icon.svg) para exibir as sugestões com base no conteúdo presente no documento completo.  As sugestões inteligentes![ícone de sugestões inteligentes](images/smart-suggestions-complete-document-icon.svg) O ícone é exibido ao lado do conteúdo, onde uma correspondência adequada é encontrada.

   Atalho de teclado: **Windows** ( *Ctrl* + *Shift* +  *K* ),  **macOS** (*Comando* + *Shift* + *K* )

   >[!NOTE]
   >
   > Você só pode exibir as sugestões para o visor atual (o conteúdo visível na tela). Para exibir sugestões para qualquer outro conteúdo no documento, role para cima ou para baixo para exibi-lo no visor e selecione a opção ![ícone de sugestões inteligentes](images/smart-suggestions-complete-document-icon.svg) ícone .

1. Selecione o **Sugestões inteligentes** ![ícone de sugestões inteligentes](images/smart-suggestions-complete-document-icon.svg) ícone próximo às tags adicionadas ao documento para exibir as sugestões inteligentes.
1. Você pode exibir as sugestões inteligentes no **Reutilização de conteúdo** sugestões.  Os Guias do Experience Manager fornecem sugestões para corresponder exatamente conteúdo e conteúdo com o mesmo significado. Por exemplo, você pode pesquisar pelo tópico que contém o número exato da versão, como &quot;versão 2023.03.12&quot;. Você também pode pesquisar por &quot;Adobe tem sede em San Jose, Califórnia&quot; e encontrar conteúdo semelhante como &quot;San Jose tem o quartel de muitas empresas de software como Adobe&quot;.
1. Selecionar **Informações de conteúdo** ![Informações de conteúdo](images/smart-suggestions-content-info-icon.svg) para exibir os detalhes.
   ![Painel de informações de conteúdo](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Exibir as informações detalhadas sobre a referência de conteúdo.*

   1. O título do tópico que contém a referência de conteúdo é exibido como um hiperlink.
   1. O caminho do arquivo que contém a referência de conteúdo.
   1. O tipo de referência para o qual o conteúdo é referenciado.
   1. Os nomes dos arquivos DITA para os quais o tópico é referido são exibidos como hiperlinks.
1. Selecionar **Visualização do conteúdo sugerido** ![ícone de visualização de sugestões inteligentes](images/smart-suggestions-preview-icon.svg) para comparar o conteúdo atual com o conteúdo sugerido. Isso o ajuda a comparar as diferenças e determinar se deseja adicionar a referência de conteúdo para o conteúdo sugerido e torná-lo consistente ou manter o conteúdo atual.

   ![Visualização do conteúdo sugerido](images/smart-suggestions-suggested-content-preview.png){width="800" align="left"}

   *Visualize a comparação entre o conteúdo atual e o conteúdo sugerido.*

1. Clique em **Aceitar** para adicionar a referência de conteúdo sugerida na **Visualização do conteúdo sugerido** caixa de diálogo.
1. Também é possível selecionar **Aceitar** ou **Recusar** no **Reutilização de conteúdo** sugestões para as recomendações apropriadas.


Esse recurso inteligente é útil e minimiza o esforço de pesquisa manual de conteúdo, permitindo que você se concentre mais na geração de novo conteúdo. Também facilita uma melhor colaboração em equipe e ajuda a manter a consistência no conteúdo criado por vários autores.

>[!NOTE]
>
>As sugestões inteligentes não retêm os dados além da sessão atual. Para respostas do, as sugestões inteligentes dependem apenas do índice criado no conteúdo que reside no banco de dados interno. As ferramentas de IA externa não são usadas, garantindo que os dados permaneçam no sistema.
