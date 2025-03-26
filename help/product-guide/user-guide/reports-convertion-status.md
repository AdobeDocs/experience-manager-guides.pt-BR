---
title: Relatório de status de conversão
description: Converta documentos de diferentes formatos em DITA no AEM Guides. Saiba como adicionar filtros e visualizar um relatório de status de conversão.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Relatório de status de conversão {#id205BBA00WZZ}

O Adobe Experience Manager Guides fornece um recurso de conversão robusto para converter documentos de vários formatos em DITA. O Relatório de status de conversão fornece uma exibição consolidada de todas as tarefas de conversão executadas pelo Experience Manager Guides.

Execute as seguintes etapas para exibir o Relatório de Status de Conversão:

1. Selecione o logotipo do Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecione **Guias** na lista de ferramentas.

1. Selecione o bloco **Relatório de status de conversão**.

   O Relatório de status de conversão é exibido para todas as tarefas de conversão executadas no sistema.

   ![](images/conversion-status-report-new.png){align="left"}

1. A página do relatório está dividida em duas partes:

   - **Filtro:**

     Você pode filtrar os dados do relatório com base no Tipo de arquivo e no Status da conversão. No Tipo de Arquivo, você pode optar por exibir os dados do relatório para documentos do Word, HTML estruturado, XML, DocBook e os tipos de documentos IDML. Em Status, você pode optar por exibir os dados do relatório para tarefas que foram executadas com Sucesso, Falharam, Ativas ou Enfileiradas.

     A captura de tela a seguir exibe os dados do relatório para tarefas de conversão com status de Sucesso.

     ![](images/conversion-report-failed-active-queued-new.png){align="left"}

   - **Dados do relatório:**

     Os dados do relatório contêm as seguintes colunas:

      - **Nome do Arquivo**: Nome do arquivo de origem no qual o processo de conversão foi executado. A seleção do link Nome do Arquivo leva você ao local do documento de origem.

      - **Tipo de arquivo**: tipo do documento de origem, que pode ser Word, HTML estruturado, XML, IDML e DocBook.

      - **Adicionado por**: nome do usuário que executou a tarefa de conversão.

      - **Data de adição**: data em que a tarefa foi executada. Selecionar no link Data de adição baixa o arquivo de log.

      - **Caminho**: caminho completo do documento de origem.

      - **Status**: status das tarefas de conversão - Êxito, Falha, Ativo ou Em fila.

      - **Saída**: Caminho do documento convertido com êxito. A seleção no link Saída o direciona ao local onde a saída é salva.


**Tópico pai:**[ Introdução aos relatórios](reports-intro.md)
