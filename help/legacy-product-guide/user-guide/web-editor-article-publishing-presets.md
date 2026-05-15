---
title: Criar predefinições de saída no Editor da Web
description: Criar predefinições de saída no editor da Web. Saiba como editar, renomear, duplicar e excluir uma predefinição de saída no AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: ce8e3614-907b-4172-a8f0-e81e4dc096df
TQID: https://experienceleague.adobe.com/nCmtXuQXfOVVHbmGrRT6rVzEa6NlR-o9TGmwhqczWPs
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 0%

---

# Criar predefinições de saída no Editor da Web {#id218CL400JW3}

Execute as seguintes etapas para criar predefinições de saída para o mapa DITA:

1. Na interface do usuário do Assets, navegue até o arquivo de mapa que deseja editar.

1. Para obter um bloqueio exclusivo no arquivo de mapa, selecione o arquivo de mapa e clique em **Check-out**.

1. Selecione a opção **Editar Tópicos** no menu de ações no arquivo de mapa.

   O arquivo de mapa é aberto para edição no Editor da Web.

   >[!NOTE]
   >
   > É possível adicionar ou excluir qualquer tópico do mapa usando o Editor de mapa avançado. Para obter mais detalhes, consulte [Trabalhar com o Editor de Mapa Avançado](map-editor-advanced-map-editor.md#).

1. Na guia **Saída**, selecione o ícone + para criar uma predefinição de saída para o mapa DITA.

   ![](images/output-tab-preset_cs.png){width="350"}

1. Insira o nome da predefinição na caixa de diálogo Adicionar predefinição e clique em **Adicionar**.

1. Insira os detalhes de configuração a seguir.

   1. Selecione as opções necessárias na guia **Geral**. É possível optar por criar uma predefinição de saída com ou sem condições. Você também pode usar um arquivo DITVAL. O AEM Guides também permite selecionar uma linha de base para publicar uma versão específica do mapa DITA.
   1. Insira os detalhes do site do AEM na guia **AEM**. O **Site** exibe a lista do AEM Sites disponível no repositório do AEM. **Categoria**, **Modelo de Seção** e **Modelo de Artigo** são os componentes estruturais usados para organizar a aparência da sua saída. Eles são predefinidos no modelo de site do AEM.

      >[!NOTE]
      >
      > Atualize cada lista suspensa para obter mais classificações na próxima lista suspensa.

   1. Na guia **Artigos**, selecione os tópicos para os quais deseja gerar a saída.
1. Selecione o ícone **Gerar predefinição** na parte superior para gerar a saída.

   ![](images/add-preset-articles-tab_cs.png){width="800"}

1. Você verá o status do processo de geração de saída. A coluna **Tópicos** lista os tópicos para os quais a saída está sendo gerada, enquanto a coluna **Status** exibe o status de publicação de cada tópico.

   Para exibir a saída, passe o mouse sobre o tópico e clique em Exibir saída.

   ![](images/add-preset-output-generated_cs.png){width="800"}


>[!NOTE]
>
> Também é possível Editar, Renomear, Duplicar ou Excluir uma predefinição de saída existente no menu Opções.

![](images/edit-preset_cs.png){width="550"}

**Tópico pai:**[ Publicação baseada em artigo do Editor da Web](web-editor-article-publishing.md)
