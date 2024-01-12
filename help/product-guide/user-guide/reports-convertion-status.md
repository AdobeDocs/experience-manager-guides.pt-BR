---
title: Relatório de status de conversão
description: Converta documentos de diferentes formatos em DITA em guias AEM. Saiba como adicionar filtros e visualizar um relatório de status de conversão.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Relatório de status de conversão {#id205BBA00WZZ}

O AEM Guides fornece um recurso de conversão robusto para converter documentos de vários formatos em DITA. O Relatório de status de conversão fornece uma exibição consolidada de todas as tarefas de conversão executadas pelos Guias do AEM.

Execute as seguintes etapas para exibir o Relatório de Status de Conversão:

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecionar **Guias** na lista de ferramentas.

1. Clique no link **Relatório de status de conversão** bloco.

   O Relatório de status de conversão é exibido para todas as tarefas de conversão executadas no sistema.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. A página do relatório está dividida em duas partes:

   - **Filtro:**

     Você pode filtrar os dados do relatório com base no Tipo de arquivo e no Status da conversão. No Tipo de Arquivo, você pode optar por ver os dados do relatório dos documentos do Word, do tipo HTML estruturado, XML e DocBook. Em Status, você pode optar por ver os dados do relatório para tarefas que foram executadas com Sucesso, Falharam, Ativas ou Enfileiradas.

     A captura de tela a seguir exibe os dados do relatório para tarefas de conversão com status Falha, Ativo e Em fila.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Dados do relatório:**

     Os dados do relatório contêm as seguintes colunas:

      - **Nome do arquivo**: Nome do arquivo de origem no qual o processo de conversão foi executado. Ao clicar no link Nome do arquivo, você será direcionado ao local do documento de origem.

      - **Tipo de arquivo**: Tipo do documento de origem, que pode ser Word, HTML estruturado, XML e DocBook.

      - **Adicionado por**: Nome do usuário que executou a tarefa de conversão.

      - **Data de adição**: Data em que a tarefa foi executada. Clicar no link Data de adição baixa o arquivo de log.

      - **Caminho**: Caminho completo do documento de origem.

      - **Status**: status das tarefas de conversão - Sucesso, Falha, Ativo ou Em fila.

      - **Output**: Caminho do documento convertido com êxito. Clicar no link Saída leva ao local onde a saída é salva.


**Tópico pai:**[ Relatórios](reports-intro.md)
