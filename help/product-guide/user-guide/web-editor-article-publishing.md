---
title: Gerar saída da knowledge base
description: Saiba como publicar um ou mais artigos no console Mapa. Gere saída para um ou mais tópicos em um mapa DITA no AEM Guides.
exl-id: d89ce69d-8d4c-4265-bfca-60763f561afd
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Gerar saída da knowledge base {#id218CL05J0M1}

O Adobe Experience Manager Guides vem com um recurso de publicação baseado em artigos que permite que os usuários publiquem um ou mais artigos da Base de conhecimento simultaneamente.

Esse mecanismo também vem com um modelo de conteúdo OOTB, criado sobre os componentes principais do Adobe Experience Manager, que permite que os usuários criem um repositório baseado em conhecimento do conteúdo técnico. Esse modelo pode ser personalizado para atender às necessidades dos clientes. Esse mecanismo permite que os usuários criem o mapa DITA de forma aditiva e publiquem tópicos quando e conforme estiverem prontos.

Se você atualizou o conteúdo apenas para alguns tópicos no mapa DITA, nem sempre é necessário publicar o mapa inteiro. Você pode selecionar e publicar somente os tópicos atualizados.

Para uma publicação baseada em artigo, é necessário criar a predefinição de saída para o mapa DITA da knowledge base. Seu mapa deve incluir os tópicos que você deseja publicar. Também é possível aplicar condições e especificar os detalhes do AEM Sites para a predefinição de saída. Em seguida, você poderá gerar saída usando o recurso **Gerar saída**.

Execute as seguintes etapas para gerar uma saída baseada em artigo:

1. [Criar a predefinição da Base de Dados de Conhecimento](./generate-output-knowledge-base.md) para saída baseada em artigo.
1. Navegue até a guia **Artigos** e selecione os tópicos para os quais deseja gerar a saída.
1. Selecione **Gerar saída** na parte superior para gerar a saída.

   ![](images/add-preset-articles-tab_cs.png){align="left"}

1. No prompt **Confirmar arquivos para publicação**, selecione os arquivos que deseja publicar e confirme selecionando **Publicar**.

   ![Novo(a) &#x200B;](images/knowledge-base-confirm-files-for-publishing.png){align="left"}

   Você visualizará o status do processo de geração de saída. A coluna **Tópicos** lista os tópicos para os quais a saída está sendo gerada, enquanto a coluna **Status** exibe o status de publicação de cada tópico.


   ![](images/add-preset-output-generated_cs.png){align="left"}

   Para exibir a saída, feche a caixa de diálogo **Saída gerada** e selecione **Exibir saída** na página predefinida.


   >[!NOTE]
   >
   > Também é possível Renomear, Duplicar ou Excluir uma predefinição de saída existente no menu Opções.


**Tópico pai:**&#x200B;[&#x200B; Trabalhar com o editor](web-editor.md)
