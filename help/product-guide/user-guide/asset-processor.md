---
title: Processamento de ativos
description: Saiba como processar ativos
feature: Migration
role: Admin
level: Experienced
exl-id: 27786098-119c-4b7a-8275-8a89d435294f
source-git-commit: 62221031e445ccdbf1f2567f38fa888ff52017d4
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Processar ativos

Em fluxos de trabalho com grande volume de dados, como publicações, o gerenciamento eficiente de ativos é fundamental para manter o desempenho e a confiabilidade. O fluxo de trabalho de processamento de ativos foi projetado para gerenciar ativos específicos do usuário que exigem operações de dados intensivas. Ele aborda principalmente dois casos: quando o processamento inicial falha devido a erros ou quando os arquivos permanecem não processados porque nenhum acionador de processamento de ativos foi iniciado. Ao ativar o processamento direcionado no nível da pasta, os usuários podem isolar e processar apenas os ativos necessários, evitando assim a sobrecarga de cálculos desnecessários. Essa abordagem seletiva melhora significativamente o desempenho, reduzindo o tempo necessário para operações críticas como publicação e geração de relatórios. Em geral, contribui para uma maior eficiência e velocidade no tratamento de tarefas complexas de dados.

>[!NOTE]
>
> - Para grandes conjuntos de dados, é melhor executar o processamento fora do horário de pico para evitar impacto no desempenho do sistema. Após a conclusão da tarefa de processamento, você poderá revisar os detalhes para analisar os resultados.<br>
>- O sistema aciona o processamento de ativos para a pasta `/content/dam` a cada 15 minutos. Durante cada ciclo, os ativos que foram adicionados recentemente ou permaneceram não processados no intervalo de 15 minutos mais recente são coletados e reprocessados. Para configurar a exibição de recurso de processamento automático de ativos, [Configure o recurso de processamento de ativos](../cs-install-guide/configure-asset-processing-cs.md).

## Processamento de ativos

Siga as etapas mencionadas abaixo para processar os ativos:

1. Selecione o logotipo do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. No painel **Ferramentas**, selecione **Guias**.
1. Selecione o bloco **Processador em Massa**.

   ![processador-ativo-fluxo](images/flow-asset-processor.png){align="left"}

1. A janela Guias de processador em massa é aberta com os detalhes mostrados abaixo. Além disso, apenas as informações relacionadas às cinco últimas migrações são exibidas nessa janela.

   - **Tipo de recurso**: mostra o recurso do processo que está sendo executado.

   - **ID de Execução**: é a ID exclusiva para cada tarefa de processamento que você executa.

   - **Pasta**: mostra a pasta selecionada para processamento.

   - **Pastas Excluídas**: mostra a pasta que foi excluída do processamento.

   - **Criado por**: mostra quem criou a tarefa ou o processo. Pode ser você, assim como o sistema.

   - **Hora de início:** Mostra a data e a hora em que o processo de processamento foi iniciado.

   - **Hora de Término**: mostra a data e a hora em que o processo de processamento termina.

   - **Status**: mostra o status do processamento como Em andamento, Concluído ou Cancelado.

   ![Guias-ativo-processador](images/guides-asset-processor-new.png){align="left"}

1. Selecione a guia **Novo Processo** no canto superior direito da janela para iniciar uma nova tarefa de processamento.

   A caixa de diálogo **Novo processo** é aberta.

   ![Novo-processador-ativo-processo](images/new-asset-processor.png){width="350" align="left"}

1. Forneça os seguintes detalhes na caixa de diálogo:

   1. **Tipo de recurso**: selecione **Processamento de ativo** na lista suspensa.
   1. **Selecionar pastas e arquivos**: navegue e escolha uma ou várias pastas e arquivos para processar.
   1. **Selecionar pastas a serem ignoradas**: como opção, selecione subpastas dentro da pasta pai escolhida para excluir do processamento.
   1. **Tipo de ativo**: na lista suspensa, selecione o tipo de ativo específico a ser processado (por exemplo, Tópico DITA, Mapa DITA, Markdown, HTML/CSS, DITAVAL ou outros arquivos). Somente o tipo de ativo selecionado é processado das pastas especificadas anteriormente.
Exemplo: a seleção de Tópico DITA processa apenas tópicos DITA dentro da pasta selecionada, permitindo a filtragem direcionada.
   1. **Criado após/Criado antes**: aplique filtros de data para processar ativos criados dentro do período de tempo especificado.

   >[!NOTE]
   >
   > Se um processo já estiver em execução para uma pasta, não será possível iniciar um novo processo para a mesma pasta até que a tarefa atual seja concluída.

1. Selecione **Criar**. Você recebe um pop-up mostrando **Sucesso e o Processo acionado com êxito**. Você pode ver o status da tarefa de processamento na janela.

   ![Processador de ativos de mensagens](images/message-asset-processor.png){width="350" align="left"}


## Opções adicionais para tarefas de processamento de ativos

Opções adicionais estão disponíveis para a tarefa de processamento depois de iniciada. Você pode acessar essas opções ao passar o cursor do mouse sobre a ID de execução da tarefa. Detalhes dessas opções são fornecidos abaixo:

- **Reiniciar** : reinicia a tarefa de processamento de ativos anteriormente bem-sucedida.

  ![reiniciar-processador-ativo](images/restart-asset-processor.png){width="650" align="left"}

- **Retomar** : retoma a tarefa de processamento de ativos cancelada ou com falha anteriormente.

  ![retomar-ativo-processador](images/resume-asset-processor.png){width="650" align="left"}

- **Cancelar** : cancela a tarefa de processamento de ativos em andamento.

  ![cancel-asset-processor](images/cancel-asset-processor.png){width="650" align="left"}

- **Exibir logs**: mostra os logs da tarefa de processamento de ativos. Para tarefas em andamento, o log mostra informações detalhadas de processamento, incluindo o tempo restante estimado e o status do ativo. Esta lista de logs exibe até as 500 entradas mais recentes. O registro completo pode ser baixado.

  ![logs-asset-processor](images/logs-asset-processor.png){width="650" align="left"}
