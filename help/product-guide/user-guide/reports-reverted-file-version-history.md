---
title: Relatório de histórico de versão de arquivos revertidos
description: Exibir relatórios de histórico de versão de arquivos revertidos no AEM Guides. Saiba como acessar logs de versão de reversão na interface do usuário do Assets, pré-visualização de tópico e seleção de ferramentas do AEM.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Relatório de histórico de versão de arquivos revertidos {#id205BBC00PRK}

Quando você está trabalhando em várias versões simultâneas com vários autores, seu conteúdo deve ter várias versões. Pode haver algumas informações comuns em várias versões, que diferentes autores poderiam usar em seus projetos. Para lidar com essas atribuições de trabalho, os autores podem acabar com várias versões dos arquivos. Essas versões podem ser simplesmente uma versão mais recente de um arquivo ou uma reversão para uma versão anterior. É uma tarefa complexa identificar quando e por que um arquivo foi revertido.

O Adobe Experience Manager Guides permite gerar um relatório de histórico de versão para um arquivo individual ou para todos os arquivos em uma pasta. Esse histórico de versões fornece uma visualização consolidada de todas as versões de um arquivo que foram revertidas e que criaram essas versões, além do motivo para criá-las.

Você pode acessar esse relatório nos seguintes locais:

- **Interface do usuário do Assets**: selecionando um arquivo e abrindo o **Histórico de Versões** no painel esquerdo. A exibição **Histórico de Versão** contém o link **Reverter Logs de Versão** na parte inferior do painel. Ao selecionar esse link, o histórico do arquivo selecionado das versões revertidas é exibido.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Visualização do tópico**: quando você estiver visualizando um tópico, também poderá exibir o painel **Histórico de Versões** no painel esquerdo. Você receberá um painel semelhante à interface do usuário do Assets, no qual poderá selecionar o link **Reverter logs de versão** para acessar o histórico de versões revertidas do documento ativo.

- **seção Ferramentas do Adobe Experience Manager**: você também pode acessar este relatório na seção Ferramentas do Experience Manager. O procedimento a seguir explica como acessar o histórico de versões revertidas na seção Ferramentas do Experience Manager.


Execute as seguintes etapas para acessar o relatório Reverter histórico:

1. Selecione o logotipo do Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecione **Guias** na lista de ferramentas.

1. Selecione o bloco **Histórico de Reversão da Versão**.

   Uma página em branco Reverter histórico de versão é exibida, na qual você precisa procurar e selecionar um arquivo ou pasta para gerar o relatório.

1. Selecione **Mostrar logs** para gerar o relatório do arquivo ou pasta selecionada.

   ![](images/revert-version-history-report.png){align="left"}

   O relatório contém os seguintes detalhes:

   - **Nome do Arquivo**: o título do tópico. Selecionar o link do título do tópico abre a visualização do tópico.

   - **Carimbo de Data/Hora**: A data e a hora em que o tópico foi revertido para uma versão anterior.

   - **Usuário**: nome do usuário que reverteu para uma versão anterior.

   - **Reverter de**: o número da versão original do arquivo de onde ele foi revertido.

   - **Reverter para**: a versão para a qual o arquivo foi revertido.

   - **Comentário**: qualquer comentário fornecido pelo usuário que reverteu o arquivo.


**Tópico pai:**&#x200B;[ Introdução aos relatórios](reports-intro.md)
