---
title: Baixar arquivos
description: Saiba como baixar arquivos do console de mapa DITA no AEM Guides e exportar um arquivo de mapa DITA no repositório do AEM.
exl-id: ae9eb355-d3ac-446a-958b-5f2da43f5533
feature: Content Management
role: User
source-git-commit: 632b253a36822b4b5b93766153f0fc3a1116b616
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Baixar arquivos {#id216MC0H0BE8}

Você pode baixar ativos, incluindo arquivos DITA e não DITA. Há várias maneiras de baixar ativos, alguns métodos são nativos do Adobe Experience Manager e outros são compatíveis com o Adobe Experience Manager Guides. Para obter informações sobre o download de ativos nativos do Adobe Experience Manager, consulte [Baixar ativos do Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) na documentação do Adobe Experience Manager. A seção a seguir explica o mecanismo de download de arquivos por meio do console de mapa DITA no Experience Manager Guides.

## Exportar um arquivo de mapa DITA

Depois de ter o arquivo de mapa DITA no repositório do Adobe Experience Manager, você pode baixar o arquivo de mapa junto com seus dependentes. Isso proporciona a flexibilidade de compartilhar o arquivo de mapa completo para edição, validação, revisão ou simplesmente criação de um backup offline.

Execute as seguintes etapas para baixar um arquivo de mapa DITA junto com seus arquivos dependentes:

1. Na interface do usuário do Assets, navegue até o mapa DITA que deseja baixar.

1. Selecione o mapa DITA para abri-lo no console do mapa DITA.

1. Selecione a guia **Tópicos** para exibir a lista de tópicos disponíveis no mapa DITA.

1. Na barra de ferramentas principal, selecione **Baixar mapa**.

   A caixa de diálogo Baixar mapa é exibida.

   ![](images/download-map.png){width="300" align="left"}

1. Selecione **Baixar**. Na caixa de diálogo Baixar mapa, escolha as seguintes opções:

   - **Usar Linha de Base**: selecione esta opção para obter uma lista de Linhas de Base criadas para o mapa DITA. Para baixar o arquivo de mapa e seu conteúdo com base em uma Linha de Base específica, selecione a Linha de Base na lista suspensa. Para obter mais detalhes sobre como trabalhar com Linhas de Base, exiba [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#).

   - **Nivelar Hierarquia de Arquivos**: selecione esta opção para salvar todos os tópicos e arquivos de mídia referenciados em uma única pasta.


   >[!NOTE]
   >
   > Também é possível baixar o arquivo de mapa sem selecionar nenhuma opção. Nesse caso, a última versão persistente dos tópicos e arquivos de mídia referenciados é baixada.

1. Após selecionar o botão **Baixar**, a solicitação de download de mapa é enfileirada. Você receberá a seguinte notificação assim que o mapa estiver pronto para download.

   ![](images/download-map-prompt.png){width="550" align="left"}

   - Selecione **Baixar** para baixar o arquivo de mapa no formato .zip.

   - Selecione **Baixar Mais Tarde** para baixar o arquivo de mapa mais tarde. O link de download pode ser acessado na Caixa de entrada de notificação do Adobe Experience Manager. Selecione a notificação de mapa gerada na Caixa de entrada para baixar o mapa no formato .zip.

   >[!NOTE]
   >
   > Por padrão, os mapas baixados permanecem por cinco dias na Caixa de entrada de notificação do Adobe Experience Manager.

![](images/download-map-inbox.png){width="300" align="left"}

Depois que o mapa for baixado, você poderá selecionar o mapa e usar o ícone Abrir na parte superior para abrir o relatório selecionado.

**Tópico pai:**&#x200B;[ Gerenciar conteúdo](authoring.md)
