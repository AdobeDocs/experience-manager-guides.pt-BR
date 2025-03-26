---
title: Console de mapas no Adobe Experience Manager Guides
description: Saiba mais sobre o Console de mapas e os vários recursos disponíveis que permitem publicar e gerenciar mapas no Adobe Experience Manager Guides.
feature: Publishing
role: User
exl-id: b273b1ae-fbb2-4b35-abce-0df78eeb2e11
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 0%

---

# Visão geral do console de mapa

O Adobe Experience Manager Guides oferece um console dedicado, conhecido como **Console de mapas**, para simplificar todas as tarefas de publicação e gerenciamento de mapas. Essa interface centralizada aumenta a produtividade e a precisão de suas atividades relacionadas a mapas, oferecendo opções para gerar saídas, traduzir conteúdo, acessar relatórios e muito mais, tudo em um só lugar.

![guia de opções de propriedades do arquivo](./images/map-console-screen.png){align="left"}

A interface do console do Mapa está dividida principalmente em duas seções: **Barra de navegação** e **Painel esquerdo**.

![Novo](images/map-console-sections.png){align="left"}

- (**A**) **Barra de navegação**: a barra de navegação apresenta ferramentas para alternar a navegação, ajustar a exibição de página e exibir o nome do arquivo de mapa selecionado.

  Os recursos disponíveis na barra de navegação são explicados da seguinte maneira:

   - **Alternador de navegação**: permite a navegação contínua para outras páginas - Editor ou Página inicial:
   - **Arquivo de mapa selecionado**: exibe o nome do arquivo de mapa selecionado no momento. Você pode abri-lo no Editor ou escolher um arquivo de mapa diferente para o console Mapa.
   - **Mais ações**: fornece opções para navegar até a **Interface do usuário do Assets** e as **Configurações**. Para obter detalhes, consulte a seção **Mais ações** do documento [Conhecer os recursos do Editor](./web-editor-features.md#tab-bar).
   - **Expandir exibição**: permite expandir a exibição de página usando o ícone **Expandir**. Nesta visualização, a barra do cabeçalho fica oculta, maximizando o espaço de conteúdo. Para retornar ao modo de exibição padrão, use o ícone **Sair do modo de exibição expandido**.

  >[!NOTE]
  >
  > Se você estiver usando o Adobe Experience Manager Guides as a Cloud Service, um recurso adicional [Assistente de IA](./ai-assistant.md) será exibido na barra de navegação.

- (**B**) **Painel esquerdo**: o painel esquerdo fornece acesso rápido aos recursos de Geração de saída, Criação e gerenciamento de relatórios, Linha de base, Predefinições de condição, Tradução de conteúdo e Workfront (somente se configurado).

  Para obter mais detalhes, consulte a seção [Mapear recursos do console](#map-console-features) abaixo.

## Mapear recursos do console

Os seguintes recursos estão disponíveis no painel Esquerdo quando você [abre um arquivo de mapa DITA no Console de mapa](./open-files-map-console.md).

**Geração de saída**

Com o console de Mapa, você pode gerar saídas com eficiência em vários formatos, incluindo AEM Sites, PDF, HTML5, EPUB, JSON e saída personalizada por meio de DITA-OT, publicação PDF nativa e FMPS. Você pode gerar saída para um mapa DITA inteiro ou publicar seletivamente apenas alguns tópicos atualizados. Você também pode usar o recurso de publicação de linha de base para publicar seletivamente uma versão específica do mapa ou tópico DITA.

Para obter mais detalhes, consulte [Geração de saída](./generate-output.md).

**Criação e gerenciamento de relatórios**

Em uma configuração organizacional, você deseja verificar a integridade geral da documentação técnica antes de começar a trabalhar nela ou enviar os documentos para o ar. Essa necessidade torna-se ainda mais essencial em ambientes de vários usuários e de grande escala. Com o console de Mapa, você obtém acesso aos relatórios do Experience Manager Guides que fornecem um insight útil sobre a integridade geral do conteúdo no repositório e como o conteúdo está sendo usado no processo de documentação.

Para obter mais detalhes, consulte [Relatórios no Experience Manager Guides](./reports-intro.md).

**Linha de base**

O Experience Manager Guides fornece o recurso Linha de base que permite criar uma versão dos tópicos e ativos que podem ser usados para publicação ou tradução. Também é possível publicar várias predefinições de saída do mesmo mapa DITA em paralelo.

Saiba como [criar e gerenciar linhas de base no Experience Manager Guides](./web-editor-baseline.md).

**Predefinições de condição**

O Experience Manager Guides permite definir atributos em seus tópicos DITA e usar a predefinição de condição para especificar o que acontece com o atributo na saída final. Por exemplo, você pode adicionar atributos como versão 1.0 e versão 2.0 no conteúdo e usar uma predefinição de condição para incluir a versão 1.0 para a versão 1.0 e excluir a versão 2.0. Da mesma forma, você pode adicionar atributos como SO Windows e OS Linux ao seu conteúdo e, em seguida, incluir ou excluir o conteúdo relevante para sua saída final de acordo com o sistema operacional.

Saiba mais sobre [Predefinições de condição](./generate-output-use-condition-presets.md).

**Conversão de conteúdo**

O Experience Manager Guides vem com recursos avançados que permitem traduzir o conteúdo para vários idiomas. Os fluxos de trabalho de tradução humana e tradução automática são compatíveis com o Experience Manager Guides.

No console de Mapa, você tem acesso a todas as opções necessárias para começar a usar fluxos de trabalho de tradução. Para obter mais detalhes, consulte [Traduzir conteúdo](./translation.md).


**Workfront**

O recurso Workfront também está presente no console Mapa, que permite trabalhar com tarefas do Adobe Workfront diretamente do Experience Manager Guides.

Saiba mais sobre a [integração do Adobe Workfront no Experience Manager Guides](./workfront-integration.md).

Você só poderá acessar este recurso se o administrador tiver configurado a integração do **Adobe Workfront** na sua instância do Experience Manager Guides.
