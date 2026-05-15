---
title: Criar predefinições de saída no Editor da Web
description: Criar predefinições de saída no editor da Web. Saiba como editar, renomear, duplicar e excluir uma predefinição de saída no AEM Guides.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/e5BEPmlmFDY2ipC8nNQPjrgGx3cV6AaD4PmZYw4hAYI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 368
ht-degree: 0%

---

# Criar predefinições de saída para Knowledge Base no Editor {#id218CL400JW3}

Execute as seguintes etapas para criar predefinições de saída para o mapa DITA:

1. Na interface do usuário do Assets, navegue até o arquivo de mapa que deseja editar.

1. Para obter um bloqueio exclusivo no arquivo de mapa, selecione o arquivo de mapa e selecione **Check-out**.

1. Selecione a opção **Editar Tópicos** no menu de ações no arquivo de mapa.

   O arquivo de mapa é aberto para edição no Editor.

   >[!NOTE]
   >
   > É possível adicionar ou excluir qualquer tópico do mapa usando o Editor de mapa avançado. Para obter mais detalhes, consulte [Trabalhar com o Editor de Mapa Avançado](map-editor-advanced-map-editor.md#).

1. Selecione o ícone **Abrir no console de mapa**. O mapa é aberto no console do mapa.

1. Navegue até a guia **Predefinições de saída** e selecione o ícone + para criar uma predefinição de saída para o mapa DITA.

1. Selecione **Base de Dados de Conhecimento** no menu suspenso **Tipo**, digite o nome e selecione **Adobe Experience Manager** na caixa de diálogo **Nova predefinição de saída**.
1. Selecione a opção **Adicionar ao perfil de pasta atual** para criar uma predefinição de saída para o perfil de pasta atual. O ícone ![perfil de pasta](images/global-preset-icon.svg) indica uma predefinição de nível de perfil de pasta.

   Saiba mais sobre [Gerenciar predefinições de saída de Perfil Global e de Pasta](./web-editor-manage-output-presets.md).

1. Selecione **Adicionar**.

   A predefinição da Knowledge Base é criada.


   ![Novo(a) ](images/knowledge-base-preset-dialog-box.png)

Depois que a predefinição é criada, é possível gerar a saída para artigos específicos da base de conhecimento. Para fazer isso, navegue até a guia **Artigos** e selecione os tópicos para os quais deseja gerar a saída.
1. Selecione **Gerar saída** na parte superior para gerar a saída.

   ![](images/add-preset-articles-tab_cs.png)

1. No prompt **Confirmar arquivos para publicação**, selecione os arquivos que deseja publicar e confirme selecionando **Publicar**.

   ![Novo(a) ](images/knowledge-base-confirm-files-for-publishing.png)

Você visualizará o status do processo de geração de saída. A coluna **Tópicos** lista os tópicos para os quais a saída está sendo gerada, enquanto a coluna **Status** exibe o status de publicação de cada tópico.


![](images/add-preset-output-generated_cs.png)

Para exibir a saída, feche a caixa de diálogo Saída Gerada e selecione **Exibir saída** na página predefinida.


>[!NOTE]
>
> Também é possível Renomear, Duplicar ou Excluir uma predefinição de saída existente no menu Opções.



**Tópico pai:**[ Publicação baseada em artigo do Editor](web-editor-article-publishing.md)
