---
title: Assistente de IA de agente para o recurso de marcação inteligente
description: Saiba como usar o Assistente de IA do Agentic para o recurso de marcação inteligente para tópicos e mapas em uma única operação.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 01ef49b5e26c31359559d9849e6726f704393cd7
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 0%
---

# Marcação inteligente com o Assistente de IA

A habilidade Marcação inteligente, disponível no modo Agente do assistente de IA por meio do Adobe CX Enterprise Coworker, torna a marcação de conteúdo mais rápida, fácil e consistente. Ele analisa seu conteúdo e recomenda tags relevantes com base na taxonomia de sua organização, eliminando a necessidade de revisar o conteúdo manualmente e identificar tags aplicáveis. O administrador pode configurar as taxonomias usadas para gerar recomendações de tags por meio de [configurações do Workspace](../install-conf-guide/workspace-settings.md#general), selecionando os namespaces relevantes para o seu espaço de trabalho.

Mantenha o controle revisando as tags sugeridas e optando por aplicá-las ou rejeitá-las antes de confirmar a seleção. Isso reduz o esforço manual, melhora a precisão da marcação e ajuda a manter metadados consistentes em toda a documentação.


## Aplicar tags a um ou vários tópicos com a habilidade de marcação inteligente

Execute as seguintes etapas para usar o Assistente do AI para aplicar tags a um ou vários tópicos com a habilidade de marcação inteligente:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **Assistente de IA** na barra de navegação. Certifique-se de que o [Assistente de IA no modo Agente](../install-conf-guide/workspace-settings.md) esteja habilitado pelo administrador.
1. Adicione o tópico para o qual você deseja gerar recomendações de tag usando um dos seguintes métodos:

   - **Usando prompts sugeridos**: para o primeiro chat na área Resposta, selecione o prompt **Sugerir tags para um arquivo**. O prompt é adicionado automaticamente ao espaço do Prompt. Selecione `[file]` e escolha o tópico no Repositório ou em uma Coleção na caixa de diálogo **Selecionar arquivo**. Você pode selecionar um tópico da caixa de diálogo **Selecionar arquivo**.

     ![Acesse o painel do Assistente de IA do Agentic usando os prompts sugeridos](images/suggested-prompts.png){width="650"}

   - **Usando atalho**: digite `/` no campo Prompt, escolha **Adicionar referência do repositório** para escolher um tópico do Repositório (ou **Adicionar arquivos do dispositivo** para carregar um tópico do seu computador) e digite um prompt como *Sugerir marcas para um arquivo*.

   - **Arrastar e soltar**: arraste e solte um único tópico ou vários tópicos no espaço Solicitação e insira um prompt como *Sugerir marcas para um arquivo*.

     ![acesse o painel do Assistente de IA do Agentic arrastando e soltando um tópico ou mapa](images/dragging-prompts.png){width="650"}

   - **Especificar caminhos de tópico**: digite `@` seguido pelos caminhos separados por vírgulas para vários tópicos de mapas iguais ou diferentes e insira um prompt como *Sugerir marcas para um arquivo*.

     ![Adição de tópico em massa ao painel Assistente de IA do Agentic](images/topics-path-add.png){width="650"}

1. Selecione **Enviar**.

1. O Assistente de IA analisa o conteúdo do tópico e gera recomendações de tag.

   ![Interface do painel Assistente de IA Agênica durante análise e reflexão](images/guides-ai-analysis.png){width="650"}

1. Revise as tags sugeridas, da seguinte maneira:

   >[!NOTE]
   >
   > Para tópicos que já contêm tags, o Assistente do AI exibe as tags existentes. Essas tags são somente leitura e não podem ser modificadas ou removidas.

   - Para um único tópico, você pode **Aceitar** as recomendações para aplicá-las ou **Rejeitá-las** se elas não forem necessárias.

     ![Resposta do painel do Assistente de IA Agenciada após a análise do conteúdo](images/guides-ai-tags-review.png){width="650"}

   - Para vários tópicos:
     1. Selecione **Visualizar** para analisar as recomendações de marcas geradas pela IA.

        ![Visualização da análise em massa do painel do Assistente de IA de agente](images/topics-tag-preview.png){width="650"}

     1. Revise as tags sugeridas para cada tópico e escolha uma das seguintes ações:
        - **Aceitar tudo** para aplicar todas as marcas sugeridas para todos os tópicos.
        - **Rejeitar tudo** para descartar todas as marcas sugeridas para todos os tópicos.
        - **Limpar todas as sugestões** para remover todas as marcas sugeridas para um tópico específico.
        - Selecione o ícone **X** ao lado de uma marca para remover uma sugestão de marca individual.

          ![Caixa de diálogo de visualização da análise em massa do painel do Assistente de IA Agenciada](images/topics-tag-preview-dialog.png){width="650"}

1. Quando você aceita as tags sugeridas, a habilidade Marcação inteligente adiciona as tags geradas pela IA às tags já aplicadas ao conteúdo.

Após concluir a revisão, o Assistente do AI exibe um resumo das tags aplicadas ao tópico e qualquer recomendação de tag rejeitada.

![Resumo da resposta do painel do Assistente de IA Agenciada](images/topic-tag-summary.png){width="650"}

## Aplicar tags a vários tópicos de um mapa usando a habilidade de marcação inteligente

Execute as seguintes etapas para usar o Assistente de IA para aplicar tags a vários tópicos de um mapa com a habilidade de marcação inteligente:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **Assistente de IA** na barra de navegação. Certifique-se de que o Assistente de IA no modo Agente está ativado pelo seu administrador.
1. Adicione o mapa para o qual você deseja gerar recomendações de tag usando qualquer um dos seguintes métodos, conforme discutido nos tópicos:

   - **Usando prompts sugeridos**: para o primeiro chat na área Resposta, selecione o prompt **Sugerir tags para um arquivo**. O prompt é adicionado automaticamente ao espaço do Prompt. Selecione `[file]` e escolha o mapa no Repositório ou em uma Coleção na caixa de diálogo **Selecionar arquivo**.

   - **Arrastar e soltar**: arraste e solte um mapa no espaço Solicitação e insira um prompt como *Sugerir marcas para um arquivo*.

   - **Usando atalho**: digite `/` no campo Prompt, escolha **Adicionar referência do repositório** para escolher um mapa do Repositório (ou **Adicionar arquivos do dispositivo** para carregar um mapa do seu computador) e digite um prompt como *Sugerir marcas para um arquivo*.

     ![Marcação em massa do Assistente de IA Agencial](images/ai-map-selection.png){width="650"}

1. Selecione **Enviar**.
Uma mensagem indica que o mapa selecionado contém vários tópicos. Selecione **Selecionar tópicos** para escolher os tópicos para os quais deseja fazer recomendações de marca.

   ![Marcação em massa do Assistente de IA Agencial ao selecionar tópicos](images/ai-select-topics.png){width="650"}

1. Na caixa de diálogo **Selecionar tópicos**, selecione os tópicos para os quais deseja fazer recomendações de marca.\
   A caixa de diálogo **Selecionar tópicos** fornece o seguinte:

   - **Lista de tópicos:** exibe todos os tópicos do mapa selecionado. Selecione os tópicos para os quais você deseja gerar recomendações de tag.
   - **Painel de visualização:** Exibe uma visualização do tópico selecionado junto com suas marcas existentes.
   - **Filtro:** Filtre os tópicos para exibir somente aqueles com **Marcas adicionadas** ou **Nenhuma marca adicionada**.

     ![Caixa de diálogo Selecionar tópicos ao aplicar marcas](images/select-dialog.png){width="650"}

1. Selecione **Confirmar**. O AI Assistant analisa os tópicos selecionados e exibe o número de recomendações de tag geradas para cada tópico.
1. Selecione **Visualizar** para analisar as recomendações de marcas geradas pela IA.
1. Revise as tags sugeridas para cada tópico e escolha uma das seguintes ações:
   - **Aceitar** para aplicar todas as marcas sugeridas para todos os tópicos.
   - **Rejeitar** para descartar todas as marcas sugeridas para todos os tópicos.
   - **Limpar todas as sugestões** para remover todas as marcas sugeridas para um tópico específico.
   - Selecione o ícone **X** ao lado de uma marca para remover uma sugestão de marca individual.

     >[!NOTE]
     >
     > Para tópicos que já contêm tags, o Assistente do AI exibe as tags existentes. Essas tags são somente leitura e não podem ser modificadas ou removidas.

   ![Caixa de diálogo de visualização de marcação em massa do Assistente de IA Agentic](images/preview-dialog.png){width="650"}

1. Quando você aceita as tags sugeridas, a habilidade de marcação inteligente adiciona as tags geradas pela IA às tags já aplicadas ao conteúdo.

Após concluir a revisão, o AI Assistant exibe um resumo das tags aplicadas a cada tópico e qualquer recomendação de tag rejeitada.

