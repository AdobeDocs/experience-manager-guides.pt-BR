---
title: Notas de versão | Novidades da versão 4.2.1 do Adobe Experience Manager Guides
description: Conheça os recursos novos e aprimorados das versões 4.2.1 do Adobe Experience Manager Guides
exl-id: 441aa7ec-d88c-42cb-83f0-d0f6e58bfa41
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Novidades da versão 4.2.1 do Adobe Experience Manager Guides (maio de 2023)

Este artigo aborda os recursos novos e aprimorados da versão 4.2.1 do Adobe Experience Manager Guides (mais tarde conhecido como *AEM Guides*).

Para obter mais detalhes sobre as instruções de atualização, a matriz de compatibilidade e os problemas corrigidos nesta versão, consulte o artigo [Notas de versão](release-notes-4-2-1.md).

## Navegar do Editor da Web para a página inicial do AEM

Agora é possível navegar facilmente do Editor da Web para a página de Navegação do AEM.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Clique no ícone **Guias** (![](assets/aem-guides-icon.png) ) para voltar à página de Navegação por AEM.


Para obter mais detalhes, consulte [página de Navegação por AEM](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Suporte a metadados avançados na publicação do PDF

O AEM Guides agora fornece suporte avançado para os metadados que são mapeados para os metadados na saída do PDF. As opções de metadados incluem informações sobre o documento e seu conteúdo, como nome do autor, título do documento, palavras-chave, informações de direitos autorais e outros campos de dados.

<img src="assets/pdf-metadata.png" alt=" metadados pdf nativos">

Você pode importar um arquivo XMP e o AEM Guides pode selecionar as informações do arquivo. Também há a opção de fornecer os nomes e valores dos metadados usando a lista suspensa. Você também pode adicionar metadados personalizados digitando diretamente no campo de nome.

Para obter mais detalhes, consulte a descrição do recurso **Metadados** em [Criar uma predefinição de saída de PDF](../web-editor/native-pdf-web-editor.md).

### Painel Modo de Exibição de Estrutura de Tópicos Avançado

O AEM Guides fornece um painel Modo de Exibição de Estrutura de Tópicos aprimorado no qual você obtém a exibição hierárquica dos elementos usados no documento.

<img src="assets/select-element-content-outline-view_cs.png" alt=" metadados pdf nativos">

A Exibição de estrutura de tópicos fornece as seguintes melhorias:

* A lista suspensa Opções de exibição é exibida na parte superior do painel Exibição de estrutura de tópicos. Se um elemento tiver uma ID, um atributo e um texto, você poderá selecioná-los na lista suspensa para exibi-los junto com o elemento. Os atributos que podem ser exibidos no painel Modo de Exibição de Estrutura de Tópicos são determinados pelas configurações de Atributos de Exibição definidas pelo administrador nas **Configurações do Editor**.

* Usando o recurso de pesquisa, você pode pesquisar um elemento por seu nome, id, texto ou valor de atributo.

Para obter mais detalhes, consulte a descrição do recurso Modo de exibição de Estrutura de Tópicos na seção [Painel Esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Gerar o relatório Multimídia no Editor da Web

O AEM Guides fornece o recurso para gerar relatórios para seus documentos técnicos.  Você pode usar esse recurso para exibir a lista de tópicos e gerenciar os metadados de seus documentos. Você também pode ver a multimídia usada em todas as referências para o mapa atual na guia **Relatórios** no Editor da Web.

Você pode gerar o relatório multimídia que contém informações detalhadas sobre a multimídia usada em suas referências no mapa atual. Você tem a flexibilidade de filtrar e classificar os arquivos multimídia listados no relatório.
Você também pode gerar o CSV para baixar o instantâneo atual da multimídia usada no mapa DITA.

<img src="assets/web-editor-reports-multimedia.png" alt="relatório multimídia" width="600">

Para obter mais detalhes, consulte a descrição do recurso Gerar um relatório multimídia na seção [Relatório de mapa DITA do Editor da Web](../user-guide/reports-web-editor.md).

## PDF nativo | Alterar barra para indicar tópicos alterados no Sumário

O AEM Guides agora permite identificar rapidamente os tópicos alterados no índice da saída de PDF.  Ela mostra uma barra de alterações à esquerda dos tópicos alterados no índice. Você pode clicar no tópico no índice e exibir as alterações detalhadas.

<img src="assets/change-marker-toc.png" alt="Alterar marcador no sumário " width="500">

Para obter mais detalhes, consulte [Trabalhar com estilos de barras de alteração personalizados](../native-pdf/change-bar-style.md).



## PDF nativo | Estilo do marcador de página no componente de nota de rodapé

Agora é possível estilizar o marcador de página nas notas de rodapé. Por exemplo, é possível adicionar colchetes ou alterar a cor. Esses estilos ajudam os usuários a identificar facilmente os marcadores de página no documento.

Para obter mais detalhes, consulte [Usar estilos personalizados em notas de rodapé](../native-pdf/footnote-number-style.md).

## Abrir e reproduzir arquivos de vídeo ou áudio no Editor da Web

O AEM Guides agora fornece o recurso para abrir e reproduzir os arquivos de áudio ou vídeo no Editor da Web. Você pode alterar o volume ou a visualização do vídeo. No menu de atalho, você também tem opções para **Baixar**, alterar **Velocidade de Reprodução** ou exibir **Picture in Picture**.

<img src="assets/video-web-editor.png" alt="reproduzir vídeo" width="600">

Para obter mais detalhes, consulte a descrição do recurso Exibição do Repositório na seção [Painel Esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS).
