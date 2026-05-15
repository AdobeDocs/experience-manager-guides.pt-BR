---
title: Relatório de mapa DITA no painel de mapa
description: Gere relatórios de mapa DITA no painel de mapa no AEM Guides. Saiba como gerar o CSV de um relatório de mapa DITA.
exl-id: 7fe52ee0-e940-467b-9b8d-3d2371de7a84
feature: Report Generation
role: User
TQID: https://experienceleague.adobe.com/NcQKAtcWCay9uHtXYJ5xOkvcyQ2tdQOYWKRDRv-NLBk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: cdab8659-8d50-4417-b6fd-762f347c13ee
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 769
ht-degree: 0%

---

# Relatório de mapa DITA no painel de mapa {#id205BB800EEN}

O Adobe Experience Manager Guides fornece aos administradores os recursos de relatórios para verificar a integridade geral da documentação antes que ela seja ativada ou disponibilizada para os usuários finais. O relatório de mapa DITA no painel de mapa no Experience Manager Guides fornece informações valiosas, como os tópicos ausentes, tópicos com elementos ausentes, UUID de tópicos e arquivos de mídia referenciados e status de revisão de cada tópico. Um relatório detalhado em nível de tópico individual também fornece informações relacionadas ao conteúdo DITA, como referências de conteúdo e imagens ausentes ou referências cruzadas.

>[!NOTE]
>
>O Experience Manager Guides atualiza esse relatório em cada evento que resulta em uma alteração no arquivo de mapa ou quando qualquer referência no arquivo de tópico é atualizada.

Execute as seguintes etapas para exibir o Relatório de mapa DITA:

1. Na interface do usuário do Assets, navegue até o arquivo de mapa DITA e selecione-o para o qual deseja exibir o relatório.

1. Selecione **Relatórios**.

   ![](images/reports-page-uuid-new.png)

   A página Relatórios está dividida em duas partes:

   - **Resumo do tópico:**

     Lista o resumo geral do arquivo de mapa selecionado. Ao observar o Resumo, você pode saber rapidamente o número total de tópicos no mapa, tópicos ausentes, número de tópicos que têm elementos ausentes, estado dos tópicos — no rascunho, em revisão ou no estado Revisado.

   - **Detalhes:**

     Quando você seleciona um tópico, é exibido um relatório detalhado do tópico selecionado.

     ![](images/detailed-report-uuid-new.png)

     Os itens realçados em **A**, **B**, **C** e **D** estão descritos abaixo:

      - **Tópico**: O título do tópico especificado no mapa DITA. Passar o ponteiro do mouse sobre o título do tópico exibe o caminho completo do tópico. Se houver problemas no tópico, como referências ou imagens ausentes, um ponto vermelho será mostrado antes do título do tópico.

      - **Nome do Arquivo**: Nome do arquivo.

      - **UUID**: o identificador exclusivo universalmente \(UUID\) do arquivo.

      - **Autor**: usuário que trabalhou por último neste tópico.

      - **Estado do Documento**: o estado atual do documento - Rascunho, Em Revisão ou Revisado.

      - **Elementos ausentes**: lista o número de imagens ausentes ou referências cruzadas corrompidas, se houver.

      - **Tópicos Ausentes \(B\)**: Se houver tópicos com referências quebradas, esses tópicos serão listados na lista Tópicos Ausentes.

      - **Abrir no Framemaker \(C\)**: lista o número de imagens ausentes ou referências cruzadas corrompidas, se houver.

      - **Abrir no Editor \(D\)**: a seleção desse ícone abre o tópico no Editor.


   Os itens realçados em **E** estão descritos abaixo:

   - **Multimídia**: o caminho das imagens usadas no tópico é mostrado junto com sua UUID. Se você selecionar o caminho da imagem, a imagem correspondente será aberta em uma janela pop-up. Os links de imagem quebrados são listados na cor vermelha.

   - **Referências de conteúdo**: o caminho do conteúdo referenciado no tópico é mostrado junto com sua UUID. Se você selecionar o título do conteúdo referido, o tópico correspondente será aberto no modo de Visualização.

   - **Referência cruzada**: o caminho do conteúdo de referência cruzada é mostrado junto com sua UUID. Se você selecionar o título do conteúdo referido, o tópico correspondente será aberto no modo de Visualização. As referências cruzadas quebradas são listadas na cor vermelha.

   - **Revisão**: mostra o status da tarefa de revisão do tópico. Você pode visualizar o status \(abertura ou fechamento\), a data de vencimento e o destinatário do tópico em revisão. Se você selecionar o link do tópico, ele abrirá o tópico no modo de revisão.

   - **Usado em**: mostra uma lista de outros tópicos ou mapas em que o tópico é usado. A UUID de todos esses tópicos e mapas também é listada.

Além do relatório de cada tópico individual, os administradores também têm acesso a informações como o histórico de publicação de um mapa DITA. Para obter mais informações sobre o histórico de saídas geradas, consulte a seção [Exibir o status da tarefa de geração de saída](generate-output-for-a-dita-map.md#viewing_output_history).

## Gerar o CSV do relatório de mapa DITA

É possível baixar e exportar o CSV de um relatório de mapa DITA. O CSV contém o relatório de mapa DITA detalhado.

Execute as seguintes etapas para gerar o CSV de um relatório de mapa DITA:

1. Selecione **Gerar relatório** no canto superior esquerdo para gerar o relatório de mapa DITA.

   ![](images/generate-DITA-map-report-new.png)

1. Você receberá uma notificação assim que o relatório estiver pronto para download. Selecione **Baixar** para baixar o CSV do relatório gerado.

   ![](images/download-report-dialog-new.png){width="550"}


   Posteriormente, também é possível baixar o CSV do relatório gerado na Caixa de entrada de notificações da Experience Manager.

   Selecione o relatório gerado na Caixa de entrada para baixar o relatório.

   ![](images/report-inbox--notification.png){width="300"}

Depois que o relatório for baixado na Caixa de entrada, você também poderá selecionar o relatório e usar o ícone Abrir na parte superior para abrir o relatório selecionado.

**Tópico pai:**&#x200B;[&#x200B; Introdução aos relatórios](reports-intro.md)
