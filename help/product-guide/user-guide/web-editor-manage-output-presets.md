---
title: Gerenciar predefinições de saída de perfil global e de pasta
description: Saiba como criar, editar, renomear, duplicar e excluir predefinições de saída de perfil global e de pasta como usuários administrativos no AEM Guides.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: 'https://experienceleague.adobe.com/FCtMWJZh9bc9sayuHsMWnd-c6mZ0Uvi0ZAgv2lOSu-4'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: 5445d7f0-b55c-5788-9564-f9ad3a7bee84
    internal-label: Features of Web Editor
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%
---
# Gerenciar predefinições de saída de perfil global e de pasta {#id22BLJ0D0V1U}

As predefinições Global e Perfil de pasta só estão disponíveis para usuários administrativos no nível da pasta.

Como administrador, o Adobe Experience Manager Guides permite criar e gerenciar predefinições de saída para os Perfis global e de pasta. Em seguida, é possível usar facilmente essas predefinições de saída para gerar saída para todos os mapas relacionados a esse Perfil global ou de pasta.

Execute as seguintes etapas para criar uma predefinição de saída para os Perfis global e de pasta:

1. Selecione o mapa DITA para o qual deseja criar uma predefinição de saída.
1. Selecione a opção **Editar Tópicos** no menu **Opções** do arquivo de mapa. O arquivo de mapa é aberto para edição no Editor.
1. Selecione o ícone **Abrir no console de mapa** para abrir o arquivo de mapa no console de Mapa.
1. No console Mapa, navegue até a guia **Predefinições de saída** e selecione o ícone + para criar uma predefinição de saída para seu mapa DITA.

   ![](images/add-global-output-preset.png){width="350"}

1. Insira os seguintes detalhes na caixa de diálogo **Adicionar predefinição**:
   - Tipo
   - Nome
   - Target \(para predefinição da Base de conhecimento\)
1. Marque a caixa de seleção **Adicionar ao perfil de pasta** para criar uma predefinição de saída para o perfil de pasta relacionado e selecione **Adicionar**. A predefinição é criada e aparece na guia **Predefinições de saída** de todos os mapas relacionados. O ícone \( ![](images/global-preset-icon.svg)\) indica uma predefinição de nível de perfil de pasta.
1. Insira os detalhes da configuração. Para obter mais detalhes sobre predefinições de saída, consulte [Noções básicas sobre as predefinições de saída](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Essas predefinições adicionadas ao perfil da pasta são independentes dos mapas, de modo que as configurações específicas do mapa não estão presentes para essas predefinições.

1. Você pode selecionar o ícone **Gerar saída** no canto superior direito para gerar a saída dos mapas relacionados à predefinição de saída criada. Você pode visualizar o status do processo de geração de saída. Para exibir a saída, selecione **Exibir Saída** na caixa de diálogo **Sucesso**.

>[!NOTE]
>
> O Experience Manager Guides também fornece uma predefinição de saída pronta para uso do PDF para gerar a saída para seus mapas DITA.

**Outras operações do menu Opções**

No menu Opções, também é possível executar as seguintes operações na predefinição:

- **Gerar saída**: permite gerar uma saída para uma predefinição existente.
- **Exibir saída** e **Exibir log**: links rápidos para exibir a saída e os logs gerados.
- **Renomear**, **Duplicar** ou **Excluir** uma predefinição de saída existente do menu **Opções**.
- **PDF padrão**: permite selecionar a predefinição PDF existente como predefinição pdf padrão. A predefinição selecionada seria, então usada como a predefinição padrão para gerar a saída do PDF usando a opção **Baixar como PDF** para um mapa.

>[!NOTE]
>
> Quando uma predefinição de saída em Perfis globais e de pasta for excluída, ela será refletida em todos os mapas relacionados e não aparecerá na guia **Predefinições de saída**.

**Tópico pai:**[ Trabalhar com o Editor da Web](web-editor.md)
