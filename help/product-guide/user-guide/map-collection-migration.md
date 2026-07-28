---
title: Migrar coleções de mapas antigas para novas coleções de mapas
description: Saiba como migrar coleções de mapas de Coleções de mapas antigas para novas
source-git-commit: aa9f0768e2c6f23294f926c2ed9a1f7e51db7610
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 1%

---


# Migrar coleções de mapas antigas para novas coleções de mapas

Se você já tiver coleções de mapas configuradas no formato antigo, não será necessário recriá-las do zero ao migrar para a nova experiência. Você pode recriá-los manualmente ou usar a ferramenta de migração integrada para mover tudo em uma única etapa.

A ferramenta de migração, adicionada como um novo tipo de processo no **Processador em massa**, lê suas coleções de mapas antigas existentes e cria automaticamente novas coleções de mapas correspondentes para você. Este artigo mostra como executar a migração e destaca alguns comportamentos principais que você deve conhecer antes de usá-la.

>[!NOTE]
>
> O recurso de ativação em massa não é migrado para a Nova experiência de coleção de mapas. Recrie todas as coleções de mapas usadas para Ativação em massa na experiência Nova coleção de mapas, se necessário.

## Migrar para nova coleção de mapas

Execute as seguintes etapas para migrar as coleções de mapa antigas para novas coleções de mapa:

1. Selecione o logotipo do Adobe Experience Manager e escolha **Ferramentas**.
1. No painel **Ferramentas**, selecione **Guias**.
1. Selecione o bloco **Processador em Massa**.

   ![Realça o bloco do processador em massa](images/flow-asset-processor.png)

1. A janela Guides Bulk Processor é aberta com os seguintes detalhes:

   - **Tipo de recurso**: mostra o recurso do processo que está sendo executado.

   - **ID de Execução**: é a ID exclusiva para cada tarefa de migração executada.

   - **Criado por**: mostra quem criou a tarefa.

   - **Hora de início**: mostra a data e a hora em que a migração foi iniciada.

   - **Hora de término**: mostra a data e a hora em que a migração termina.

   - **Status**: mostra o status da migração como Em andamento, Concluído ou Falha.

   ![A janela do Processador em Massa de Guias](images/guides-asset-processor-migration.png)

1. Selecione a guia **Novo processo** no canto superior direito da janela para iniciar uma nova tarefa de migração.

   A caixa de diálogo **Novo processo** é aberta.

   ![Caixa de diálogo Novo processo para migração](images/new-process-migration.png) {width="350"}

1. Selecione **Coleção de mapas** na lista suspensa **Tipo de recurso**.

   ![Recurso de coleção de mapas para a tarefa de migração](images/new-process.png) {width="350"}

1. Selecione **Criar**.

Isso executa um único trabalho que migra todas as coleções de mapas antigas existentes para novas coleções de mapas. Nenhuma configuração adicional é necessária.

>[!NOTE]
>
> Se a tarefa de migração falhar, você poderá verificar a opção **Exibir logs** passando o mouse sobre a ID de Execução.

## Considerações importantes

- **Reexecutando a migração:** Se o processo de migração for executado novamente, ele não verificará se há alterações nas coleções de mapa de origem (antigas). Ela fará uma remigração incondicional ou substituirá as novas coleções de mapas.
- **Carimbos de data e hora e exclusividade:** cada coleção de mapas migrada armazena o carimbo de data e hora de quando foi migrada pela primeira vez. Esse carimbo de data e hora é usado para manter a exclusividade do registro migrado. Por causa disso, a coleção de mapas migrada não refletirá as atualizações posteriores feitas na coleção de mapas original (origem). Somente o estado no momento da migração é capturado.


