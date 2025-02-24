---
title: Gerar saída
description: Gere uma saída para um mapa DITA no console do mapa e no painel Mapa no AEM Guides.
exl-id: d6cbd44c-e74c-4192-bcc4-fb7752c59508
feature: Publishing
role: User
source-git-commit: f6ff978305d9a1587366acbe96d274408bf457f4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# Gerar saída

Há duas maneiras de gerar saída para um mapa DITA:

- [Gerar saída para um mapa DITA a partir do console de Mapa](#generate-output-for-a-dita-map-from-the-map-console)
- [Gerar saída para um mapa DITA no painel Mapa](#generate-output-for-a-dita-map-from-the-map-dashboard)

## Gerar saída para um mapa DITA a partir do console Mapa

Execute as seguintes etapas para gerar saída para um mapa DITA usando o console Mapa:

1. [Abra um arquivo de mapa no Console de mapa](./open-files-map-console.md).
2. O console do mapa DITA é exibido com a lista de **predefinições de saída** disponíveis para gerar saída.

3. Abra a predefinição que deseja usar para gerar a saída e selecione **Gerar saída** para iniciar o processo de geração.

   <img src="images/generate-output-pdf.png" alt="guia metadados" width="600">

   Ou passe o mouse sobre a predefinição e selecione **Gerar** no menu de contexto predefinido.


   <img src="images/generate-preset-map-console.png" alt="guia metadados" width="600">

Quando a geração de saída estiver concluída, selecione **Exibir saída** para exibir a saída.

Uma caixa de diálogo **Êxito** está visível no canto inferior direito da tela.

Se uma saída não for bem-sucedida, a mensagem de erro abaixo será exibida.

<img src="images/error-log.png" alt="log de erros" width="250">

Para exibir o log de erros, selecione **Ignorar**, passe o mouse sobre a guia de predefinição selecionada e selecione **Exibir log** no menu de contexto predefinido.

## Gerar saída para um mapa DITA no painel Mapa

Execute as seguintes etapas para gerar saída para um mapa DITA usando o painel Mapa:

1. Na interface do usuário do Assets, navegue até o arquivo de mapa DITA que deseja publicar e selecione-o.

   O console do mapa DITA é exibido com a lista de Predefinições de saída disponíveis para gerar a saída.

1. Selecione uma ou várias Predefinições de saída que deseja usar para gerar a saída.

   ![](images/generate-multiple-outputs-uuid.png){width="800" align="left"}

1. Selecione o ícone **Gerar** para iniciar o processo de geração de saída.


Você pode visualizar o status atual da solicitação de geração de saída na guia **Saídas**. Para obter mais informações, consulte [Exibir o status da tarefa de geração de saída](./generate-output-manage-process.md#view-the-status-of-the-output-generation-task).

>[!IMPORTANT]
>
> Se um processo de geração de saída para uma predefinição estiver na fila ou em andamento, não será possível iniciar outra tarefa de geração de saída para a mesma predefinição.

Você também pode gerar a saída do AEM Sites para um ou mais tópicos, ou todo o mapa DITA no console Mapa. Para obter mais detalhes, exiba [Gerar saída da Base de Dados de Conhecimento](web-editor-article-publishing.md#id218CK0U019I).




**Tópico pai:**[ Geração de saída](generate-output.md)
