---
title: IA de guias para o recurso de marcação inteligente
description: Saiba como usar a IA de guias para o recurso de marcação inteligente para tópicos e mapas em uma única operação.
source-git-commit: b866964c30a565eab0f6f9aec4b3fc9013f15f75
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 0%

---


# Introdução à IA de guias

>[!NOTE]
>
> A IA do Guides está disponível no Experience Manager Guides as a Cloud Service a partir da versão 2026.08.0. Entre em contato com a equipe de Sucesso do cliente para habilitar esse recurso.

A IA do Guides torna a marcação de conteúdo mais rápida, fácil e consistente. Usando a habilidade de marcação inteligente do colaborador corporativo do Adobe CX, a IA de guias analisa seu conteúdo e recomenda tags relevantes com base na taxonomia de sua organização, em vez de você ler manualmente o conteúdo para decidir quais tags se aplicam. Você permanece no controle revisando as tags sugeridas e optando por aplicá-las ou rejeitá-las antes de confirmar sua seleção, reduzindo significativamente o esforço manual, melhorando a precisão da marcação e garantindo metadados consistentes em toda a documentação.

## Painel IA de guias

O painel IA de guias fornece todas as ferramentas necessárias para gerar, revisar e aplicar as tags sugeridas pela IA.

![Painel de IA de guias](images/guides-ai-panel.png){width="650"}

Os seguintes componentes da IA do Guides ajudam a adicionar arquivos, configurar recomendações de tags e gerenciar o fluxo de trabalho de marcação inteligente:

- **(A)** Histórico da conversa: exibir e reabrir conversas anteriores para analisar recomendações e ações de marcas anteriores.

  ![Histórico de conversões do painel IA de guias](images/chat-history.png){width="350"}

- **(B)** Novo chat: inicia uma nova sessão de marcação para um tópico, mapa ou conjunto de arquivos diferente.
- Namespace da marca **(C)**: selecione os namespaces de taxonomia de onde a IA de Guias deve gerar recomendações de marca. Somente as tags dos namespaces selecionados são consideradas.

  ![Taxonomia do painel IA de guias](images/taxononmy.png){width="350"}

- **(D)** Espaço de resposta: revise as recomendações de marcas geradas pela IA e escolha aceitá-las, rejeitá-las ou modificá-las antes de aplicar as marcas.
- **(E)** Espaço de prompt: insira uma solicitação de prompt para gerar recomendações de marca para o conteúdo selecionado.
- **(F)** Anexar arquivos ou adicionar contexto: adiciona tópicos, mapas ou arquivos externos de seu sistema local para fornecer o conteúdo que a IA de Guias deve analisar para as recomendações de marca.
- Modelo **(G)**: exibe o modelo de IA usado para analisar o conteúdo e gerar recomendações de marca. Vários modelos OpenAI e Anthropic Claude estão disponíveis para seleção. Por padrão, a opção **Usar padrão do manifesto** está selecionada, que usa o modelo configurado para o assistente selecionado.
- **(H)** Enviar: envia seu prompt e o conteúdo anexado para gerar recomendações de marca habilitada por IA.

## Aplicar tags a um ou vários tópicos com a habilidade de marcação inteligente

Execute as seguintes etapas para usar a IA de guias para aplicar tags a um ou vários tópicos com a habilidade de marcação inteligente:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **IA de guias** na barra de navegação. Certifique-se de que o recurso IA de guias esteja ativado pelo administrador.
1. Adicione o tópico para o qual você deseja gerar recomendações de tag usando um dos seguintes métodos:

   - **Usando prompts sugeridos**: para o primeiro chat na área Resposta, selecione o prompt **Sugerir tags para um arquivo**. O prompt é adicionado automaticamente ao espaço do Prompt. Selecione `[file]` e escolha o tópico no Repositório ou em uma Coleção na caixa de diálogo **Selecionar arquivo**. Você pode selecionar um tópico da caixa de diálogo **Selecionar arquivo**.

     ![Acesse o painel IA de Guias usando os prompts sugeridos](images/suggested-prompts.png){width="650"}

   - **Usando atalho**: Digite `/` no campo Prompt, escolha **Adicionar referência do repositório** para escolher um tópico do Repositório (ou **Adicionar arquivos do dispositivo** para carregar um tópico do seu computador) e insira o prompt sugerido *Sugerir marcas para um arquivo*.

   - **Arrastar e soltar**: arraste e solte um único tópico ou vários tópicos no espaço Solicitação e digite o prompt *Sugerir marcas para um arquivo*.

     ![acesse o painel IA de Guias arrastando e soltando um tópico ou mapa](images/dragging-prompts.png){width="650"}

   - **Especificar caminhos de tópico**: Digite `@` seguido pelos caminhos separados por vírgulas para vários tópicos de mapas iguais ou diferentes e insira o prompt: *Sugerir marcas para um arquivo*.

     ![Adição de tópico em massa do painel IA de guias](images/topics-path-add.png){width="650"}

1. Selecione **Enviar**.

1. A IA de guias analisa o conteúdo do tópico e gera recomendações de tag.

   ![Interface do painel IA de guias durante a análise e o raciocínio](images/guides-ai-analysis.png){width="650"}

1. Revise as tags sugeridas, da seguinte maneira:

   >[!NOTE]
   >
   > Para tópicos que já contêm tags, a IA de guias exibe as tags existentes. Essas tags são somente leitura e não podem ser modificadas ou removidas.

   - Para um único tópico, você pode simplesmente **Aceitar** as recomendações para aplicá-las ou **Rejeitá-las** se elas não forem necessárias.

     ![Resposta do painel de IA do Guides após a análise do conteúdo](images/guides-ai-tags-review.png){width="650"}

   - Para vários tópicos:
     1. Selecione **Visualizar** para analisar as recomendações de marcas geradas pela IA.

        ![Visualização da análise em massa do painel de IA dos guias](images/topics-tag-preview.png){width="650"}

     1. Revise as tags sugeridas para cada tópico e escolha uma das seguintes ações:
        - **Aceitar tudo** para aplicar todas as marcas sugeridas para todos os tópicos.
        - **Rejeitar tudo** para descartar todas as marcas sugeridas para todos os tópicos.
        - **Limpar todas as sugestões** para remover todas as marcas sugeridas para um tópico específico.
        - Selecione o ícone **X** ao lado de uma marca para remover uma sugestão de marca individual.

          ![Caixa de diálogo de visualização da análise em massa do painel do Guides AI](images/topics-tag-preview-dialog.png){width="650"}

1. Quando você aceita as tags sugeridas, a habilidade Marcação inteligente adiciona as tags geradas pela IA às tags já aplicadas ao conteúdo.

Após concluir a revisão, a IA de guias exibe um resumo das tags aplicadas ao tópico e qualquer recomendação de tag rejeitada.

![Resumo da resposta do painel de IA dos guias](images/topic-tag-summary.png){width="650"}

## Aplicar tags a vários tópicos de um mapa usando a habilidade de marcação inteligente

Execute as seguintes etapas para usar a IA de guias para aplicar tags a vários tópicos de um mapa com a habilidade de marcação inteligente:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **IA de guias** na barra de navegação. Certifique-se de que o recurso IA de guias esteja ativado pelo administrador.
1. Adicione o mapa para o qual você deseja gerar recomendações de tag usando qualquer um dos seguintes métodos, conforme discutido nos tópicos:

   - **Usando prompts sugeridos**: para o primeiro chat na área Resposta, selecione o prompt **Sugerir tags para um arquivo**. O prompt é adicionado automaticamente ao espaço do Prompt. Selecione `[file]` e escolha o mapa no Repositório ou em uma Coleção na caixa de diálogo **Selecionar arquivo**.

   - **Arrastar e soltar**: arraste e solte um mapa no espaço Solicitação e digite o prompt *Sugerir marcas para um arquivo*.

   - **Usando atalho**: Digite `/` no campo Prompt, escolha **Adicionar referência do repositório** para escolher um mapa do Repositório (ou **Adicionar arquivos do dispositivo** para carregar um mapa do seu computador) e insira o prompt sugerido *Sugerir marcas para um arquivo*.

     ![Marcação de itens em massa do Guides AI](images/ai-map-selection.png){width="650"}

1. Selecione **Enviar**.
Uma mensagem indica que o mapa selecionado contém vários tópicos. Selecione **Selecionar tópicos** para escolher os tópicos para os quais deseja fazer recomendações de marca.

   ![Guias de marcação em massa de IA ao selecionar tópicos](images/ai-select-topics.png){width="650"}

1. Na caixa de diálogo **Selecionar tópicos**, selecione os tópicos para os quais deseja fazer recomendações de marca.\
   A caixa de diálogo **Selecionar tópicos** fornece o seguinte:

   - **Lista de tópicos:** exibe todos os tópicos do mapa selecionado. Selecione os tópicos para os quais você deseja gerar recomendações de tag.
   - **Painel de visualização:** Exibe uma visualização do tópico selecionado junto com suas marcas existentes.
   - **Filtro:** Filtre os tópicos para exibir somente aqueles com **Marcas adicionadas** ou **Nenhuma marca adicionada**.

     ![Caixa de diálogo Selecionar tópicos ao aplicar marcas](images/select-dialog.png){width="650"}

1. Selecione **Confirmar**. A IA de guias analisa os tópicos selecionados e exibe o número de recomendações de tag geradas para cada tópico.
1. Selecione **Visualizar** para analisar as recomendações de marcas geradas pela IA.
1. Revise as tags sugeridas para cada tópico e escolha uma das seguintes ações:
   - **Aceitar tudo** para aplicar todas as marcas sugeridas para todos os tópicos.
   - **Rejeitar tudo** para descartar todas as marcas sugeridas para todos os tópicos.
   - **Limpar todas as sugestões** para remover todas as marcas sugeridas para um tópico específico.
   - Selecione o ícone **X** ao lado de uma marca para remover uma sugestão de marca individual.

     >[!NOTE]
     >
     > Para tópicos que já contêm tags, a IA de guias exibe as tags existentes. Essas tags são somente leitura e não podem ser modificadas ou removidas.

   ![Caixa de diálogo de visualização da marcação em massa do Guides AI](images/preview-dialog.png){width="650"}

1. Quando você aceita as tags sugeridas, a habilidade de marcação inteligente adiciona as tags geradas pela IA às tags já aplicadas ao conteúdo.

Após concluir a revisão, a IA de guias exibe um resumo das tags aplicadas a cada tópico e qualquer recomendação de tag rejeitada.

