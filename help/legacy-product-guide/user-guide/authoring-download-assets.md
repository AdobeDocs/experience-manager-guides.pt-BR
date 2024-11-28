---
title: Baixar arquivos
description: Saiba como baixar arquivos do console de mapas DITA no AEM Guides e exportar um arquivo de mapas DITA para o repositório AEM.
feature: Content Management
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Baixar arquivos {#id216MC0H0BE8}

Você pode baixar ativos, incluindo arquivos DITA e não DITA. Há várias maneiras de baixar ativos, alguns métodos são nativos do AEM e outros são compatíveis com o AEM Guides. Para obter informações sobre o download de ativos nativos do AEM, consulte [Baixar ativos do Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) na documentação do AEM. A seção a seguir explica o mecanismo de download de arquivos por meio do console de mapa DITA no AEM Guides.

## Exportar um arquivo de mapa DITA

Depois de ter o arquivo de mapa DITA no repositório AEM, você pode baixar o arquivo de mapa junto com seus dependentes. Isso proporciona a flexibilidade de compartilhar o arquivo de mapa completo para edição, validação, revisão ou simplesmente criação de um backup offline.

Execute as seguintes etapas para baixar um arquivo de mapa DITA junto com seus arquivos dependentes:

1. Na interface do usuário do Assets, navegue até o mapa DITA que deseja baixar.

1. Clique no mapa DITA para abri-lo no console do mapa DITA.

1. Selecione a guia **Tópicos** para ver uma lista de tópicos disponíveis no mapa DITA.

1. Na barra de ferramentas principal, clique em **Baixar mapa**.

   A caixa de diálogo Baixar mapa é exibida.

   ![](images/download-map.png){width="300" align="left"}

1. Clique em **Baixar**. Na caixa de diálogo Baixar mapa, escolha as seguintes opções:

   - **Usar Linha de Base**: selecione esta opção para obter uma lista de Linhas de Base criadas para o mapa DITA. Para baixar o arquivo de mapa e seu conteúdo com base em uma Linha de Base específica, selecione a Linha de Base na lista suspensa. Para obter mais detalhes sobre como trabalhar com Linhas de Base, consulte [Trabalhar com Linhas de Base](generate-output-use-baseline-for-publishing.md#).
   - **Nivelar Hierarquia de Arquivos**: selecione esta opção para salvar todos os tópicos e arquivos de mídia referenciados em uma única pasta.
   >[!NOTE]
   >
   > Também é possível baixar o arquivo de mapa sem selecionar nenhuma opção. Nesse caso, a última versão persistente dos tópicos e arquivos de mídia referenciados é baixada.

1. Depois de clicar no botão **Download**, a solicitação de download do mapa é enfileirada. Você receberá a seguinte notificação assim que o mapa estiver pronto para download.

   ![](images/download-map-prompt.png){width="550" align="left"}

   - Clique em **Baixar** para baixar o arquivo de mapa no formato .zip.

   - Clique em **Baixar Mais Tarde** para baixar o arquivo de mapa mais tarde. O link de download pode ser acessado na Caixa de entrada de notificação do AEM. Clique na notificação de mapa gerada na Caixa de entrada para baixar o mapa no formato .zip.

   >[!NOTE]
   >
   > Por padrão, os mapas baixados permanecem por cinco dias na Caixa de entrada de notificação do AEM.

![](images/download-map-inbox.png){width="300" align="left"}

Depois que o mapa for baixado, você poderá selecionar o mapa e usar o ícone Abrir na parte superior para abrir o relatório selecionado.

**Tópico pai:**[ Gerenciar conteúdo](authoring.md)
