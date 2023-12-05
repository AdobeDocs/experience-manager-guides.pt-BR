---
title: Relatório de histórico de versão de arquivos revertidos
description: Visualize relatórios de histórico de versão de arquivos revertidos nos Guias AEM. Saiba como acessar logs de versão de reversão na interface do usuário do Assets, na pré-visualização de tópicos e na seleção de ferramentas do AEM.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Relatório de histórico de versão de arquivos revertidos {#id205BBC00PRK}

Quando você está trabalhando em várias versões simultâneas com vários autores, seu conteúdo deve ter várias versões. Pode haver algumas informações comuns em várias versões, que diferentes autores poderiam usar em seus projetos. Para lidar com essas atribuições de trabalho, os autores podem acabar com várias versões dos arquivos. Essas versões podem ser simplesmente uma versão mais recente de um arquivo ou uma reversão para uma versão anterior. É uma tarefa complexa identificar quando e por que um arquivo foi revertido.

Guias do AEM permitem gerar um relatório de histórico de versões para um arquivo individual ou para todos os arquivos em uma pasta. Esse histórico de versões fornece uma visualização consolidada de todas as versões de um arquivo que foram revertidas e que criaram essas versões, além do motivo para criá-las.

Você pode acessar esse relatório nos seguintes locais:

- **Interface do usuário do Assets**: selecionando um arquivo e abrindo o **Histórico da versão** do painel esquerdo. A variável **Histórico da versão** a exibição contém o **Reverter logs da versão** na parte inferior do painel. Ao clicar nesse link, o histórico do arquivo selecionado das versões revertidas é exibido.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Visualização do tópico**: quando você estiver visualizando um tópico, também poderá exibir a **Histórico da versão** painel à esquerda. Você obterá um painel semelhante à interface do usuário do Assets, onde é possível clicar no link **Reverter logs da versão** link para acessar o histórico de versões revertidas do documento ativo.

- **Seção Ferramentas do AEM**: também é possível acessar esse relatório na seção Ferramentas de AEM. O procedimento a seguir explica como acessar o histórico de versões revertidas na seção Ferramentas AEM.


Execute as seguintes etapas para acessar o relatório Reverter histórico:

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecionar **Guias** na lista de ferramentas.

1. Clique no link **Histórico de reversão da versão** bloco.

   Uma página em branco Reverter histórico de versão é exibida, na qual você precisa procurar e selecionar um arquivo ou pasta para gerar o relatório.

1. Clique em **Mostrar logs** para gerar o relatório do arquivo ou pasta selecionada.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   O relatório contém os seguintes detalhes:

   - **Nome do arquivo**: O título do tópico. Clicar no link do título do tópico abre a visualização do tópico.

   - **Carimbo de data e hora**: A data e a hora em que o tópico foi revertido para uma versão anterior.

   - **Usuário**: nome do usuário que reverteu para uma versão anterior.

   - **Reverter de**: o número da versão original do arquivo de onde ele foi revertido.

   - **Reverter para**: A versão para a qual o arquivo foi revertido.

   - **Comentário**: qualquer comentário fornecido pelo usuário que reverteu o arquivo.


**Tópico pai:**[ Relatórios](reports-intro.md)
