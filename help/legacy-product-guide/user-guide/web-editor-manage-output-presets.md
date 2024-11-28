---
title: Gerenciar predefinições de saída de perfil global e de pasta
description: Saiba como criar, editar, renomear, duplicar e excluir predefinições de saída de perfil global e de pasta como usuários administrativos no AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Gerenciar predefinições de saída de perfil global e de pasta {#id22BLJ0D0V1U}

As predefinições Global e Perfil de pasta só estão disponíveis para usuários administrativos no nível da pasta.

Como administrador, o AEM Guides permite criar e gerenciar predefinições de saída para os Perfis global e de pasta. Em seguida, é possível usar facilmente essas predefinições de saída para gerar saída para todos os mapas relacionados a esse Perfil global ou de pasta.

Execute as seguintes etapas para criar uma predefinição de saída para os Perfis global e de pasta:

1. Selecione o mapa DITA para o qual deseja criar uma predefinição de saída.
1. Selecione a opção **Editar Tópicos** no menu **Opções** do arquivo de mapa. O arquivo de mapa é aberto para edição no Editor da Web.
1. Na guia **Saída**, selecione o ícone + para criar uma predefinição de saída para o mapa DITA.

   ![](images/add-global-output-preset.png){width="350" align="left"}

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
> O AEM Guides também fornece uma predefinição de saída de PDF para gerar a saída para seus mapas DITA.

**Outras operações do menu Opções**

No menu Opções, também é possível executar as seguintes operações na predefinição:

- Selecione a predefinição como predefinição de pdf padrão. Em seguida, a predefinição selecionada será usada como a predefinição padrão para gerar a saída de PDF usando a opção **Baixar como PDF** para um mapa.
- **Editar**, **Renomear**, **Duplicar** ou **Excluir** uma predefinição de saída existente do menu **Opções**.

>[!NOTE]
>
> Quando uma predefinição de saída em Perfis Globais e de Pasta for excluída, ela será refletida em todos os mapas relacionados e não aparecerá na guia **Saída**.

**Tópico pai:**[ Trabalhar com o Editor da Web](web-editor.md)
