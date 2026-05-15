---
title: Gerar saída da knowledge base
description: Saiba como publicar um ou mais artigos no console Mapa. Gere saída para um ou mais tópicos em um mapa DITA no AEM Guides.
exl-id: d89ce69d-8d4c-4265-bfca-60763f561afd
feature: Publishing
role: User
TQID: https://experienceleague.adobe.com/ZoHALUOHRMDqjz0JjR4ZQFXtYju6LQOdy1nwuzwvw5E
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: afb45297-4313-4f67-818e-bc0b03abe086
subfeature_v2: id: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 346
ht-degree: 0%

---

# Gerar saída da knowledge base {#id218CL05J0M1}

O Adobe Experience Manager Guides vem com um recurso de publicação baseado em artigos que permite que os usuários publiquem um ou mais artigos da Base de conhecimento simultaneamente.

Esse mecanismo também vem com um modelo de conteúdo OOTB, criado sobre os componentes principais do Adobe Experience Manager, que permite que os usuários criem um repositório baseado em conhecimento do conteúdo técnico. Esse template pode ser personalizado para atender às necessidades dos clientes.Esse mecanismo permite que os usuários criem o mapa DITA de forma aditiva e publiquem tópicos quando estiverem prontos.

Se você atualizou o conteúdo apenas para alguns tópicos no mapa DITA, nem sempre é necessário publicar o mapa inteiro. Você pode selecionar e publicar somente os tópicos atualizados.

Para uma publicação baseada em artigo, é necessário criar a predefinição de saída para o mapa DITA da knowledge base. Seu mapa deve incluir os tópicos que você deseja publicar. Também é possível aplicar condições e especificar os detalhes do AEM Sites para a predefinição de saída. Em seguida, você poderá gerar saída usando o recurso **Gerar saída**.

Execute as seguintes etapas para gerar uma saída baseada em artigo:

1. [Criar a predefinição da Base de Dados de Conhecimento](./generate-output-knowledge-base.md) para saída baseada em artigo.
1. Navegue até a guia **Artigos** e selecione os tópicos para os quais deseja gerar a saída.
1. Selecione **Gerar saída** na parte superior para gerar a saída.

   ![](images/add-preset-articles-tab_cs.png)

1. No prompt **Confirmar arquivos para publicação**, selecione os arquivos que deseja publicar e confirme selecionando **Publicar**.

   ![Novo(a) ](images/knowledge-base-confirm-files-for-publishing.png)

   Você visualizará o status do processo de geração de saída. A coluna **Tópicos** lista os tópicos para os quais a saída está sendo gerada, enquanto a coluna **Status** exibe o status de publicação de cada tópico.


   ![](images/add-preset-output-generated_cs.png)

   Para exibir a saída, feche a caixa de diálogo **Saída gerada** e selecione **Exibir saída** na página predefinida.


   >[!NOTE]
   >
   > Também é possível Renomear, Duplicar ou Excluir uma predefinição de saída existente no menu Opções.


**Tópico pai:**[ Trabalhar com o editor](web-editor.md)
