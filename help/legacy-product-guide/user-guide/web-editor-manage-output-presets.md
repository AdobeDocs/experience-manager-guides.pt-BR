---
title: Gerenciar predefinições de saída de perfil global e de pasta
description: Saiba como criar, editar, renomear, duplicar e excluir predefinições de saída de perfil global e de pasta como usuários administrativos no AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: 4e9cd1d5-1c28-4363-917d-f58511c4f809
TQID: https://experienceleague.adobe.com/KH-j3haVf3VmR0QpMgAOCFfdJoCUOuc-nx5Xrc2XTKI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 0%

---

# Gerenciar predefinições de saída de perfil global e de pasta {#id22BLJ0D0V1U}

As predefinições Global e Perfil de pasta só estão disponíveis para usuários administrativos no nível da pasta.

Como administrador, o AEM Guides permite criar e gerenciar predefinições de saída para os Perfis global e de pasta. Em seguida, é possível usar facilmente essas predefinições de saída para gerar saída para todos os mapas relacionados a esse Perfil global ou de pasta.

Execute as seguintes etapas para criar uma predefinição de saída para os Perfis global e de pasta:

1. Selecione o mapa DITA para o qual deseja criar uma predefinição de saída.
1. Selecione a opção **Editar Tópicos** no menu **Opções** do arquivo de mapa. O arquivo de mapa é aberto para edição no Editor da Web.
1. Na guia **Saída**, selecione o ícone + para criar uma predefinição de saída para o mapa DITA.

   ![](images/add-global-output-preset.png){width="350"}

1. Insira os seguintes detalhes na caixa de diálogo **Adicionar predefinição**:
   - Tipo
   - Nome
   - Target \(para predefinição da Base de conhecimento\)
1. Marque a caixa de seleção **Adicionar ao perfil de pasta** para criar uma predefinição de saída para o perfil de pasta relacionado e clique em **Adicionar**. A predefinição é criada e aparece na guia **Saída** de todos os mapas relacionados. O ícone \( ![](images/global-preset-icon.svg)\) indica uma predefinição de nível de perfil de pasta.
1. Insira os detalhes da configuração. Para obter mais detalhes sobre predefinições de saída, consulte [Noções básicas sobre as predefinições de saída](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Essas predefinições adicionadas ao perfil da pasta são independentes dos mapas, de modo que as configurações específicas do mapa não estão presentes para essas predefinições.

1. Você pode selecionar o ícone **Gerar predefinição** na parte superior para gerar a saída para os mapas relacionados à predefinição de saída criada. Você verá o status do processo de geração de saída. Para exibir a saída, passe o mouse sobre o tópico e clique em **Exibir Saída**.

>[!NOTE]
>
> O AEM Guides também fornece uma predefinição de saída pronta para uso do PDF para gerar a saída para seus mapas DITA.

**Outras operações do menu Opções**

No menu Opções, também é possível executar as seguintes operações na predefinição:

- Selecione a predefinição como predefinição de pdf padrão. Em seguida, a predefinição selecionada seria usada como a predefinição padrão para gerar a saída do PDF usando a opção **Baixar como PDF** para um mapa.
- **Editar**, **Renomear**, **Duplicar** ou **Excluir** uma predefinição de saída existente do menu **Opções**.

>[!NOTE]
>
> Quando uma predefinição de saída em Perfis Globais e de Pasta for excluída, ela será refletida em todos os mapas relacionados e não aparecerá na guia **Saída**.

**Tópico pai:**&#x200B;[&#x200B; Trabalhar com o Editor da Web](web-editor.md)
