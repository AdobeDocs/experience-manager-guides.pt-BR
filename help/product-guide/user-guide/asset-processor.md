---
title: Processamento e reprocessamento de ativos
description: Saiba como processar ativos
feature: Migration
role: Admin
level: Experienced
source-git-commit: b0e744baeb6867bfc9e7d212ec53e581812d8f63
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Processamento ou reprocessamento de ativos

Em fluxos de trabalho com grande volume de dados, como publicações, o gerenciamento eficiente de ativos é fundamental para manter o desempenho e a confiabilidade. O processo de processamento ou reprocessamento de ativos é projetado especificamente para lidar com ativos específicos do usuário que exigem operações intensivas de dados. Essa abordagem aborda dois cenários principais: quando o processamento inicial de ativos encontra erros ou quando os arquivos não foram processados devido à ausência de um acionador de pós-processamento. Ao ativar o processamento direcionado no nível da pasta, os usuários podem isolar e processar apenas os ativos necessários, evitando assim a sobrecarga de cálculos desnecessários. Essa abordagem seletiva melhora significativamente o desempenho, reduzindo o tempo necessário para operações críticas como publicação e geração de relatórios. Em geral, contribui para uma maior eficiência e velocidade no tratamento de tarefas complexas de dados.

>[!NOTE]
>
> Para grandes conjuntos de dados, é melhor executar o processamento fora do horário de pico para evitar impacto no desempenho do sistema. Depois que a tarefa de processamento for concluída, você poderá revisar os detalhes para analisar os resultados.

## Processamento de ativos

Siga as etapas mencionadas abaixo para processar ou reprocessar os ativos:

1. Selecione o logotipo do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. No painel **Ferramentas**, selecione **Guias**.
1. Selecione o Bloco **Processador de ativos**.

   ![processador-ativo-fluxo](images/flow-asset-processor.png){width="550" align="left"}

1. A janela Processador de ativos do Guides é aberta com os detalhes mostrados abaixo. Além disso, apenas as informações relacionadas às cinco últimas migrações são exibidas nessa janela.

   - **ID de Execução**: é a ID exclusiva para cada tarefa de reprocessamento que você executa.

   - **Pasta**: mostra a pasta selecionada para reprocessamento.

   - **Pastas Excluídas**: aponta para a pasta que está excluída do reprocessamento.

   - **Hora de início:** Mostra a data e a hora em que o processo de reprocessamento foi iniciado.

   - **Hora de Término**: mostra a data e a hora em que o processo de reprocessamento termina.

   - **Status**: aponta para o status do reprocessamento como Em andamento, Concluído ou Cancelado.

   ![Guias-ativo-processador](images/guides-asset-processor.png){width="550" align="left"}

1. Selecione a guia **Novo Processo** no canto superior direito da janela para iniciar uma nova tarefa de processamento.

   ![Novo-processador-ativo-processo](images/new-process-asset-processor.png){width="550" align="left"}

1. Selecione a pasta que deseja processar ou reprocessar. Você também pode selecionar as pastas (dentro da pasta principal selecionada) que deseja excluir ou ignorar.

   >[!NOTE]
   >
   >Somente uma pasta pode ser selecionada em um determinado momento para processamento. Para operações específicas, é possível excluir várias pastas.

1. Selecione **Criar**. Você recebe um pop-up mostrando **Sucesso e o Processo acionado com êxito** como mostrado no trecho. O mesmo se reflete na lista. Você pode ver o status da tarefa de reprocessamento na janela.

   ![Processador de ativos de mensagens](images/message-asset-processor.png){width="550" align="left"}


## Opções adicionais para as tarefas de processamento

Opções adicionais estão disponíveis para a tarefa de processamento depois de iniciada. Você pode acessar essas opções ao passar o cursor do mouse sobre a ID de execução da tarefa. Detalhes dessas opções são fornecidos abaixo:

- **Reiniciar** : reinicia a tarefa de processamento de ativos anteriormente bem-sucedida.

  ![reiniciar-processador-ativo](images/restart-asset-processor.png){width="550" align="left"}

- **Retomar** : retoma a tarefa de processamento de ativos cancelada ou com falha anteriormente.

  ![retomar-ativo-processador](images/resume-asset-processor.png){width="550" align="left"}

- **Cancelar** : cancela a tarefa de processamento de ativos em andamento.

  ![cancel-asset-processor](images/cancel-asset-processor.png){width="550" align="left"}

- **Exibir logs**: mostra os logs da tarefa de processamento de ativos. Para tarefas em andamento, o log mostra informações detalhadas de processamento, incluindo o tempo restante estimado e o status do ativo. Esta lista de logs exibe até as 500 entradas mais recentes. O registro completo pode ser baixado.

  ![logs-asset-processor](images/logs-asset-processor.png){width="550" align="left"}




