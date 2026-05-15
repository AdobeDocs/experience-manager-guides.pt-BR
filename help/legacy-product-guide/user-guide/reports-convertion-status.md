---
title: Relatório de status de conversão
description: Converta documentos de diferentes formatos em DITA no AEM Guides. Saiba como adicionar filtros e visualizar um relatório de status de conversão.
feature: Report Generation
role: User
hide: true
exl-id: f6bf1033-9c2f-42c7-9ad5-e1060e2c9770
TQID: https://experienceleague.adobe.com/TBeg61eVmHydID-z3dGoQcHJtAY0EzwhuJD9SHpuhwI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 0%

---

# Relatório de status de conversão {#id205BBA00WZZ}

O AEM Guides fornece um recurso de conversão robusto para converter documentos de vários formatos em DITA. O Relatório de status de conversão fornece uma exibição consolidada de todas as tarefas de conversão executadas pelo AEM Guides.

Execute as seguintes etapas para exibir o Relatório de Status de Conversão:

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecione **Guias** na lista de ferramentas.

1. Clique no bloco **Relatório de status de conversão**.

   O Relatório de status de conversão é exibido para todas as tarefas de conversão executadas no sistema.

   ![](images/conversion-status-report.png){width="800"}

1. A página do relatório está dividida em duas partes:

   - **Filtro:**

     Você pode filtrar os dados do relatório com base no Tipo de arquivo e no Status da conversão. No Tipo de Arquivo, você pode optar por ver os dados do relatório dos documentos do Word, HTML estruturado, XML e DocBook. Em Status, você pode optar por ver os dados do relatório para tarefas que foram executadas com Sucesso, Falharam, Ativas ou Enfileiradas.

     A captura de tela a seguir exibe os dados do relatório para tarefas de conversão com status Falha, Ativo e Em fila.

     ![](images/conversion-report-failed-active-queued.png){width="800"}

   - **Dados do relatório:**

     Os dados do relatório contêm as seguintes colunas:

      - **Nome do Arquivo**: Nome do arquivo de origem no qual o processo de conversão foi executado. Ao clicar no link Nome do arquivo, você será direcionado ao local do documento de origem.

      - **Tipo de arquivo**: tipo do documento de origem, que pode ser Word, HTML estruturado, XML e DocBook.

      - **Adicionado por**: nome do usuário que executou a tarefa de conversão.

      - **Data de adição**: data em que a tarefa foi executada. Clicar no link Data de adição baixa o arquivo de log.

      - **Caminho**: caminho completo do documento de origem.

      - **Status**: status das tarefas de conversão - Êxito, Falha, Ativo ou Em fila.

      - **Saída**: Caminho do documento convertido com êxito. Clicar no link Saída leva ao local onde a saída é salva.


**Tópico pai:**&#x200B;[&#x200B; Relatórios](reports-intro.md)
