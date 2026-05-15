---
title: Relatório de histórico de versão de arquivos revertidos
description: Exibir relatórios de histórico de versão de arquivos revertidos no AEM Guides. Saiba como acessar logs de versão de reversão na interface do usuário do Assets, pré-visualização de tópico e seleção de ferramentas do AEM.
feature: Report Generation
role: User
hide: true
exl-id: c787947a-b235-4c12-a9cc-eac5136d31db
TQID: https://experienceleague.adobe.com/lRZe-xPwSSlgWvk5-YLMZkqLRHwe-lTO8jUsgYQn1dM
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 468
ht-degree: 0%

---

# Relatório de histórico de versão de arquivos revertidos {#id205BBC00PRK}

Quando você está trabalhando em várias versões simultâneas com vários autores, seu conteúdo deve ter várias versões. Pode haver algumas informações comuns em várias versões, que diferentes autores poderiam usar em seus projetos. Para lidar com essas atribuições de trabalho, os autores podem acabar com várias versões dos arquivos. Essas versões podem ser simplesmente uma versão mais recente de um arquivo ou uma reversão para uma versão anterior. É uma tarefa complexa identificar quando e por que um arquivo foi revertido.

O AEM Guides permite gerar um relatório de histórico de versão para um arquivo individual ou para todos os arquivos em uma pasta. Esse histórico de versões fornece uma visualização consolidada de todas as versões de um arquivo que foram revertidas e que criaram essas versões, além do motivo para criá-las.

Você pode acessar esse relatório nos seguintes locais:

- **Interface do usuário do Assets**: selecionando um arquivo e abrindo o **Histórico de Versões** no painel esquerdo. A exibição **Histórico de Versão** contém o link **Reverter Logs de Versão** na parte inferior do painel. Ao clicar nesse link, o histórico do arquivo selecionado das versões revertidas é exibido.

  ![](images/revert-log-from-assets-ui.png){width="300"}

- **Visualização do tópico**: quando você estiver visualizando um tópico, também poderá exibir o painel **Histórico de Versões** no painel esquerdo. Você obterá um painel semelhante à interface do Assets de onde pode clicar no link **Reverter logs de versão** para acessar o histórico de versões revertidas do documento ativo.

- **Seção Ferramentas do AEM**: você também pode acessar este relatório na seção Ferramentas do AEM. O procedimento a seguir explica como acessar o histórico de versões revertidas na seção Ferramentas do AEM.


Execute as seguintes etapas para acessar o relatório Reverter histórico:

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecione **Guias** na lista de ferramentas.

1. Clique no bloco **Histórico de Reversão da Versão**.

   Uma página em branco Reverter histórico de versão é exibida, na qual você precisa procurar e selecionar um arquivo ou pasta para gerar o relatório.

1. Clique em **Mostrar Logs** para gerar o relatório para o arquivo ou pasta selecionada.

   ![](images/revert-version-history-report.png){width="800"}

   O relatório contém os seguintes detalhes:

   - **Nome do Arquivo**: o título do tópico. Clicar no link do título do tópico abre a visualização do tópico.

   - **Carimbo de Data/Hora**: A data e a hora em que o tópico foi revertido para uma versão anterior.

   - **Usuário**: nome do usuário que reverteu para uma versão anterior.

   - **Reverter de**: o número da versão original do arquivo de onde ele foi revertido.

   - **Reverter para**: a versão para a qual o arquivo foi revertido.

   - **Comentário**: qualquer comentário fornecido pelo usuário que reverteu o arquivo.



**Tópico pai:**[ Relatórios](reports-intro.md)
