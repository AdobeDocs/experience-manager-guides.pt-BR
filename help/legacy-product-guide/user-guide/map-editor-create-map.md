---
title: Criar um mapa
description: Crie um mapa com o Editor de mapas no AEM Guides. Encontre as etapas para criar um arquivo de mapa com base em um modelo de mapa.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 981ecaeb-9b1f-4c7a-8336-7746a739bedc
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '472'
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

   ![](images/map-template.png){width="650" align="left"}

1. Na página Propriedades, especifique o mapa **Título**.

1. \(Opcional\) Especifique o arquivo **Nome**.

   Se o administrador tiver configurado o nome de arquivo automático com base na configuração UUID, você não verá a opção para especificar o nome do arquivo. Um nome de arquivo baseado em UUID é automaticamente atribuído ao arquivo.

   Se a opção de nomenclatura de arquivo estiver disponível, o nome também será sugerido automaticamente com base no Título do mapa. Se você quiser especificar manualmente o nome do arquivo de mapa, certifique-se de que o nome do arquivo não contenha nenhum espaço, apóstrofo ou chaves e termine com `.ditamap`.

1. Clique em **Criar**.

   A mensagem Mapa criado é exibida.

   Todo novo arquivo de mapa criado por você na interface do usuário do Assets **Criar** \> **Mapa DITA** ou no Editor da Web recebe uma ID de mapa exclusiva. Além disso, o novo mapa é salvo como a cópia de trabalho mais recente no DAM. Até salvar uma revisão de um mapa recém-criado, você não verá nenhum número de versão no Histórico de versões. Se você abrir o mapa para edição, as informações da versão serão mostradas no canto superior direito da guia do arquivo de mapa:

   ![](images/first-version-map-none.png){width="650" align="left"}

   As informações de versão para um mapa recém-criado são mostradas como *nenhuma*. When you save a new version, then it is assigned a version number as 1.0. For more information about saving a new version, see [Save As New Version](web-editor-features.md#save-as-new-version-id209ME400GXA).

   You can choose to open the map for editing in the configured map editor, or save the map file in the AEM repository.

   >[!NOTE]
   >
   > To use the Advanced Map Editor, access the map file in the Web Editor. In case your administrator has configured the Advanced Map Editor as the default editor in the map files, then the map file is opened directly in the Advanced Map Editor for editing. See *Set the Advanced Map Editor as default* section in Install and configure Adobe Experience Manager Guides as a Cloud Service.


**Parent topic:**&#x200B;[&#x200B; Work with the Map Editor](map-editor.md)
