---
title: Criar um mapa
description: Crie um mapa com o Editor de mapas no AEM Guides. Encontre as etapas para criar um arquivo de mapa com base em um modelo de mapa.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 981ecaeb-9b1f-4c7a-8336-7746a739bedc
TQID: https://experienceleague.adobe.com/ezadQbcoT3y2-owiIZ5MgsnBbNegmCb2lCIwxgwhcAE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 472
ht-degree: 0%

---

# Criar um mapa {#id176FEN0D05Z}

O AEM Guides fornece dois modelos de mapa prontos para uso - mapa DITA e mapa de livros. Você também pode criar seus próprios modelos de mapa e compartilhá-los com seus autores para criar arquivos de mapa.

Execute as seguintes etapas para criar um arquivo de mapa:

1. Na interface do usuário do Assets, navegue até o local em que deseja criar o arquivo de mapa.

1. Clique em **Criar** \> **Mapa DITA**.

1. Na página Blueprint, selecione o tipo de modelo de mapa que deseja usar e clique em **Próximo**.

   >[!NOTE]
   >
   > A forma como os tópicos são referenciados em um arquivo de mapa depende do modelo de mapa. Por exemplo, se o modelo de Mapa for selecionado, as referências de tópico \(`topicref`\) serão usadas para fazer referência a tópicos. No caso de um Bookmap, as referências de tópico são criadas usando o elemento `chapter` no DITA.

   ![](images/map-template.png){width="650"}

1. Na página Propriedades, especifique o mapa **Título**.

1. \(Opcional\) Especifique o arquivo **Nome**.

   Se o administrador tiver configurado o nome de arquivo automático com base na configuração UUID, você não verá a opção para especificar o nome do arquivo. Um nome de arquivo baseado em UUID é automaticamente atribuído ao arquivo.

   Se a opção de nomenclatura de arquivo estiver disponível, o nome também será sugerido automaticamente com base no Título do mapa. Se você quiser especificar manualmente o nome do arquivo de mapa, certifique-se de que o nome do arquivo não contenha nenhum espaço, apóstrofo ou chaves e termine com `.ditamap`.

1. Clique em **Criar**.

   A mensagem Mapa criado é exibida.

   Todo novo arquivo de mapa criado por você na interface do usuário do Assets **Criar** \> **Mapa DITA** ou no Editor da Web recebe uma ID de mapa exclusiva. Além disso, o novo mapa é salvo como a cópia de trabalho mais recente no DAM. Até salvar uma revisão de um mapa recém-criado, você não verá nenhum número de versão no Histórico de versões. Se você abrir o mapa para edição, as informações da versão serão mostradas no canto superior direito da guia do arquivo de mapa:

   ![](images/first-version-map-none.png){width="650"}

   As informações de versão para um mapa recém-criado são mostradas como *nenhuma*. Ao salvar uma nova versão, um número de versão é atribuído como 1.0. Para obter mais informações sobre como salvar uma nova versão, consulte [Salvar como nova versão](web-editor-features.md#save-as-new-version-id209ME400GXA).

   Você pode optar por abrir o mapa para edição no editor de mapa configurado ou salvar o arquivo de mapa no repositório do AEM.

   >[!NOTE]
   >
   > Para usar o Editor de Mapa Avançado, acesse o arquivo de mapa no Editor da Web. Caso o administrador tenha configurado o Editor de mapa avançado como o editor padrão nos arquivos de mapa, o arquivo de mapa será aberto diretamente no Editor de mapa avançado para edição. Consulte *Definir o Editor de Mapa Avançado como padrão* na seção Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service.


**Tópico pai:**[ Trabalhar com o Editor de Mapa](map-editor.md)
