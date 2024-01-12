---
title: Notas de versão | Guias do Adobe Experience Manager as a Cloud Service, versão de fevereiro de 2023
description: Lançamento do Adobe Experience Manager Guides as a Cloud Service em fevereiro
exl-id: 090eaf94-fe3a-47e9-9937-f84f8434550d
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 0%

---

# Novidades da versão de fevereiro de 2023 do Adobe Experience Manager Guides as a Cloud Service

Este artigo aborda os recursos novos e aprimorados da versão de fevereiro de 2023 do Adobe Experience Manager Guides (mais tarde conhecido como *Guias de AEM as a Cloud Service*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte [Notas de versão](release-notes-2023.2.0.md) artigo.


## Gerar relatórios pelo Editor da Web

O AEM Guides vem com um recurso no Editor da Web que permite verificar a integridade geral de seus documentos técnicos e gerar relatórios para eles.
Você pode visualizar a lista de tópicos, gerenciar os metadados e ver a multimídia usada em todas as referências para o mapa atual no
**Relatórios** no Editor da Web.

**Gerar a exibição da Lista de tópicos**

Você pode gerar a Lista de tópicos que fornece informações detalhadas sobre os tópicos, como tipo de referência, estado do documento e autor. Você também pode gerar o CSV para baixar o instantâneo atual dos tópicos no mapa DITA.

**Gerenciar metadados e alterar estado do documento**

Você pode aplicar tags a um tópico individual ou usar o recurso de marcação em massa para aplicar várias tags a vários tópicos, um mapa DITA ou um submapa. Você também pode alterar o estado do documento de todos os tópicos selecionados para o próximo estado de documento comum possível.

<img src="assets/web-editor-metadata-panel.png" alt="gerenciar metadados" width="600">

**Gerar o relatório Multimídia**

Você pode gerar o relatório multimídia que contém informações detalhadas sobre a multimídia usada em suas referências no mapa atual. Você tem a flexibilidade de filtrar e classificar os arquivos multimídia listados no relatório.
Você também pode gerar o CSV para baixar o instantâneo atual da multimídia usada no mapa DITA.

<img src="assets/web-editor-reports-multimedia.png" alt="relatório multimídia" width="600">

## UX renovado para a funcionalidade de revisão

Agora, os guias de AEM fornecem um UX aprimorado que ajuda a analisar os tópicos compartilhados para análise. Na experiência mais recente, a funcionalidade de revisão tem as seguintes melhorias:

* Interface do usuário atualizada
* Painel Condições, que permite realçar o conteúdo de acordo com as condições disponíveis no tópico
* Cada comentário no painel de comentários é vinculado ao texto correspondente no tópico atual. Isso ajuda a identificar o texto comentado.
* Os comentários são exibidos na ordem do texto comentado no documento.
* O nome da tarefa de revisão é exibido no workflow de revisão.
* Selecione o roteiro da tarefa de revisão que é usado para resolver todas as referências principais e termos de glossário usados no conteúdo da revisão.
* Barra de ferramentas contextual que ajuda a destacar ou tachar rapidamente o texto
* Menu Opções para editar ou excluir seus próprios comentários
* Para comentários desatualizados, você tem acesso à exibição lado a lado, o que ajuda a comparar a versão anterior do tópico com a versão de revisão atual.
* Ao usar os filtros, os comentários no painel direito são filtrados de acordo com a seleção e o número de comentários no painel esquerdo é atualizado adequadamente.


  <img alt="tarefa de revisão" src="assets/comment-pop-up-panel.png" width="600">



## Aprimoramentos de tradução

Agora você tem aprimoramentos mais fáceis de usar no painel Tradução que ajudam a traduzir facilmente seus documentos do Editor da Web.

**Passar o rótulo da versão para a versão de destino**

Guias do AEM permitem passar o rótulo do arquivo de origem para o arquivo de destino. Isso ajuda a identificar facilmente a versão de origem do arquivo traduzido.

<img alt="rótulos de tradução" src="assets/translation-pass-source-label.png" width="600">

Por exemplo, se você tiver alguns arquivos de origem com o rótulo da versão Release 1.0 aplicado a eles, também será possível passar o rótulo de origem (Release 1.0) para o arquivo traduzido.

**Forçar sincronização para ativos fora de sincronização**

Se você fizer alterações em alguns ativos, os Guias do AEM os marcará como Fora de sincronia. Você pode traduzir novamente os ativos modificados ou optar por descartar o status Fora de sincronização. Por exemplo, se você tiver feito algumas pequenas alterações que realmente não precisam de uma tradução, poderá marcar o status delas como Em sincronia.

<img src="assets/translation-version-diff.png" alt="quadro de tradução" width="600">

**Exibir projetos de tradução em andamento para um tópico ou mapa**

Algumas das referências no painel de tradução podem estar em andamento. Agora, o AEM Guides fornece um recurso para ajudar você a visualizar a lista de todos os projetos de tradução em andamento (juntamente com o idioma de destino) que contêm a referência selecionada.


## Gerar saída em vários formatos no Editor da Web

Agora é possível gerar facilmente a saída dos tópicos ou do mapa DITA no Editor da Web. Você pode configurar várias predefinições de saída, como AEM Site, PDF, HTML5, JSON (um formato de saída headless) e saída personalizada. Você pode usá-los para gerar as respectivas saídas.

Você pode definir atributos em seus tópicos DITA e, em seguida, usar a predefinição de condição para aplicar uma condição ao publicar a saída. Você também pode usar o recurso de publicação de linha de base para publicar seletivamente uma versão específica do mapa ou tópico DITA.


## Localizar e substituir o texto no nível do mapa

O Guia AEM permite procurar arquivos em um mapa que contenha texto específico. O texto pesquisado é destacado nos arquivos. Agora, você também pode substituir a palavra ou frase pesquisada por outra palavra ou frase em todos os arquivos. É possível selecionar **Substituir tudo** ícone na parte superior direita da lista para substituir todas as ocorrências do termo pesquisado em todos os arquivos.

<img src="assets/map-find-replace.png" alt="mapa localizar substituir" width="600">

## Excluir e duplicar arquivos no painel de repositório

Agora é possível criar facilmente uma duplicata ou uma cópia de um arquivo do **Opções** do arquivo selecionado no painel repositório. Por padrão, o arquivo é criado com um sufixo `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="menu de opções de arquivo " width="500">


## Outras melhorias no Editor da Web

* Nos Guias do AEM, você pode executar algumas operações comuns para imagens e arquivos de mídia usando o menu de contexto. Agora, também é possível localizar a imagem ou mídia selecionada no repositório ou visualizar o arquivo na interface do usuário do Assets.

* O nome do Perfil de pasta atual é exibido como um rótulo para o ícone Preferências do usuário na barra de ferramentas principal. Isso ajuda a identificar o perfil da pasta em que você está trabalhando.

* Quando você abre um mapa na exibição de mapa, o título do mapa atual é exibido no centro da barra de ferramentas principal. Isso é útil para informar aos usuários qual mapa está aberto no momento.


## Visualizar o título no lugar da UUID no editor de oxigênio

Agora o AEM Guides permite que você escolha **Usar Título no Editor e no Gerenciador de Mapas** em Configurações. Se você selecionar essa opção, o título do arquivo será exibido na guia do arquivo quando aberto no Editor ou no Gerenciador de mapas DITA. Se você não selecionar essa opção, a UUID do arquivo será exibida na guia do arquivo.

## Publicação baseada em microsserviços para guias do AEM as a Cloud Service

O novo microsserviço de publicação permite que você execute grandes cargas de trabalho de publicação simultaneamente no AEM Guides as a Cloud Service e aproveite a plataforma Adobe I/O Runtime sem servidor, líder do setor.

Para cada solicitação de publicação, o AEM Guides as a Cloud Service executa um contêiner separado que é dimensionado horizontalmente de acordo com as solicitações do usuário. Isso permite executar várias solicitações de publicação e obter um desempenho aprimorado.

Para obter mais detalhes, consulte [Configure a nova publicação baseada em microsserviços para os Guias do AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

## PDF nativo | Adicionar um marcador personalizado na saída do PDF

Agora é possível adicionar um marcador personalizado em um conteúdo específico na saída final do PDF para facilitar a navegação. Isso seria adicionado ao índice criado a partir dos títulos de tópico ou seção no mapa DITA.

## PDF nativo | Aplicar estilo personalizado em entradas de índice e conteúdo de tópico

Guias de AEM fornecem o recurso para aplicar um estilo personalizado nas entradas do índice ou em um tópico específico na saída do PDF. Por exemplo, é possível alterar a cor do texto no índice e no título do tópico. Também é possível aplicar estilos a todo o conteúdo do tópico.


## PDF nativo | Estilo do marcador de página no componente de nota de rodapé

Agora é possível estilizar o marcador de página nas notas de rodapé. Por exemplo, é possível adicionar colchetes ou alterar a cor. Esses estilos ajudam os usuários a identificar facilmente os marcadores de página no documento.

## PDF nativo | Alterar barra para indicar tópicos alterados no Sumário

Agora, os Guias do AEM permitem identificar rapidamente os tópicos alterados no índice da saída de PDF.  Ela mostra uma barra de alterações à esquerda dos tópicos alterados no índice. Você pode clicar no tópico no índice e exibir as alterações detalhadas.

<img src="assets/change-marker-toc.png" alt="Alterar marcador no sumário " width="500">
