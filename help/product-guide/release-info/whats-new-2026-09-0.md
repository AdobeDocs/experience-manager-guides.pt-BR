---
title: Notas de versão | Novidades na versão 2026.09.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2026.09.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: 5d42c75d75b85b97fc3795c87004510eb43acd29
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 0%
---
# Novidades da versão 2026.09.0 (setembro de 2026)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2026.09.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2026.09.0](fixed-issues-2026-09-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.09.0](../release-info/upgrade-instructions-2026-09-0.md).

## Introdução à marcação inteligente habilitada por IA no Assistente de IA

Agora, você pode usar o Assistente de IA para sugerir e adicionar tags ao seu conteúdo. Com o novo recurso de marcação inteligente, os autores podem solicitar ao Assistente de IA que sugira tags para um ou mais tópicos, potencializados pela habilidade Marcação inteligente fornecida pelo Adobe CX Enterprise Coworker. A habilidade revisa o conteúdo, gera recomendações de tag e as apresenta para sua revisão. Depois de confirmar, as tags sugeridas são aplicadas aos tópicos relevantes em um mapa.

Para obter mais detalhes, consulte [Usar o Assistente de IA no modo Agencial](../user-guide/ai-assistant-agentic.md).

![](./assets/guides-ai-tags-review.png)

Atualmente, o recurso de marcação inteligente está disponível quando o Assistente do AI está configurado no modo **Agente**. Os administradores podem optar por habilitar o modo **Agente** ou **Padrão** nas **configurações do Workspace** para uma instância.

- O **Modo de agente** fornece aos autores a interface de marcação inteligente para recomendação e aplicativo de marca.
- O **modo Padrão** fornece a experiência existente do Assistente de IA, com as guias **Ajuda** e **Criação** no painel Assistente de IA.

## Aprimoramentos do editor

### Impedir substituições de conteúdo durante a edição simultânea

Quando dois autores trabalham no mesmo tópico ao mesmo tempo, um autor pode ter o tópico aberto enquanto outro autor o bloqueia, faz alterações e salva uma versão mais recente. O tópico já aberto pode ter conteúdo desatualizado e a edição desta versão pode substituir as alterações mais recentes.

Para evitar esses conflitos, a versão salva mais recente agora é carregada automaticamente no Editor quando você bloqueia um tópico. Isso garante que você trabalhe com o conteúdo mais recente e impede que substitua as alterações feitas por outro autor.

Isso se aplica quando a configuração **Desabilitar edição sem bloquear o arquivo** está habilitada.

Para obter mais detalhes, consulte [Impedir substituições de conteúdo durante a edição simultânea](../user-guide/web-editor-edit-topics.md#prevent-content-overwrite-during-concurrent-editing).

### Visualizar o conteúdo do mapa como uma linha de base estática selecionada

Quando um mapa tem uma ou mais linhas de base estáticas, agora é possível visualizar o mapa com base em uma linha de base selecionada, em vez da cópia de trabalho atual no Editor.

Todas as versões dos tópicos, ativos, imagens e referências associadas à linha de base selecionada são exibidas na Pré-visualização, fornecendo uma exibição precisa do conteúdo do mapa no momento em que a linha de base foi criada. Para obter mais detalhes, consulte [Exibições do editor para tópicos](../user-guide/web-editor-views.md#preview-content-using-baseline).

## Revisar melhorias

### Marcar tópicos individuais como concluídos em uma tarefa de revisão

O Experience Manager Guides introduz o rastreamento de progresso em nível de tópico para revisores, proporcionando uma melhor visibilidade do progresso da revisão para tarefas com vários tópicos. Como Revisor, agora você pode marcar tópicos individuais como concluídos e distinguir entre tópicos concluídos e aqueles que ainda precisam de atenção.

![](./assets/mark-topics-done-review-ui.png)

Para respaldar isso, os tópicos da exibição Documento da interface do usuário de Revisão são organizados de acordo com uma caixa de seleção **Marcar tópico como concluído**. Os tópicos marcados como revisados usando a caixa de seleção são indicados no painel **Tópicos**, enquanto o contador de **Tópicos revisados** na parte superior mostra o progresso em relação aos tópicos atribuídos a você. Juntos, eles fornecem uma visão clara do que você cobriu e do que resta, mesmo ao retornar a uma tarefa de análise mais longa após uma interrupção.

Para obter mais detalhes, consulte [Tópicos da revisão](../user-guide/review-topics.md#mark-individual-topics-as-done-in-a-review-task).


### Identificar usuários com funções ao marcar comentários

Revisores e autores agora podem visualizar a função de um usuário, como Revisor, Autor ou Proprietário, juntamente com seu nome de usuário e endereço de email (se disponível), ao marcar alguém em um comentário ou resposta. Isso facilita a identificação rápida do usuário certo para marcar, especialmente em projetos com um grande número de participantes.

Saiba mais sobre [como marcar usuários em um comentário](../user-guide/review-topics.md#tag-task-users-in-a-comment).

### Exibir a hierarquia do mapa ao selecionar tópicos para revisão

Ao selecionar o conteúdo para uma revisão, como Autor ou iniciador de uma tarefa de revisão, agora você pode exibir mapas, submapas e tópicos em sua hierarquia existente na página **Conteúdo**, em vez de exibir todos os tópicos como uma lista simples. A exibição hierárquica facilita a compreensão da estrutura do conteúdo e a seleção de tópicos individuais ou submapas inteiros para revisão.

Para obter mais detalhes, exiba [Exibir a hierarquia do mapa ao selecionar tópicos para revisão](../user-guide/review-send-topics-for-review.md#view-the-map-hierarchy-while-selecting-topics-for-review).

![](assets/review-map-hierarchy.png)

## Aprimoramentos de publicação

### Publicar saída nativa do PDF usando o idioma do mapa

A página de predefinição de saída do PDF nativo agora inclui uma nova opção **Usar linguagem de mapa**. Quando selecionadas, as variáveis de modelo de saída resolvem seu idioma a partir do atributo `xml:lang` do mapa raiz em vez de um idioma selecionado explicitamente na predefinição. Isso significa que não é mais necessário manter uma predefinição de saída separada para cada idioma ao publicar mapas traduzidos. Se o mapa não tiver `xml:lang` definido, a saída assumirá o padrão inglês (en_US).

Para obter mais detalhes, exiba a [configuração de predefinição nativa do PDF](../web-editor/native-pdf-web-editor.md) e [Use variáveis de idioma nos modelos de saída](../native-pdf/native-pdf-language-variables.md#use-language-variables-in-the-output-templates).

## Aprimoramentos no conteúdo de aprendizado

### Ativar a visualização de tela cheia para conteúdo H5P em um curso de aprendizado

Os autores agora podem ativar ou desativar a exibição em tela cheia para cada elemento H5P usado em um curso de aprendizado. Use o botão de alternância **Habilitar tela cheia** no painel **Propriedades de conteúdo** para controlar essa configuração. Quando ativado, os alunos podem expandir o conteúdo H5P para tela cheia. Quando desativado, o conteúdo permanece em linha na exibição padrão. Essa configuração se aplica de forma consistente na saída publicada e no modo de Visualização.

Saiba mais sobre [Outras opções no menu Inserir](../learning-content/lc-other-insert-options.md) do conteúdo de Treinamento e Aprendizado do Produto.

![](./assets/h5p-fullscreen.png)

## Aprimoramentos de desempenho

### Desempenho aprimorado com carregamento paginado de arquivos e pastas

O Experience Manager Guides agora oferece suporte ao carregamento paginado de arquivos e pastas para obter uma experiência de navegação aprimorada, especialmente em pastas com um grande número de ativos. Em vez de carregar todo o conteúdo de uma só vez, as pastas são carregadas progressivamente em lotes de 50 ativos, com ativos adicionais recuperados à medida que você rola a tela ou seleciona **Carregar mais**, dependendo do painel ou da caixa de diálogo.

A classificação é realizada no lado do servidor, portanto, a aplicação de uma ordem de classificação busca resultados recém-classificados em vez de reordenar dados já carregados no navegador. Operações comuns, como renomear, excluir, adicionar e mover, não recarregam mais uma pasta inteira. Em vez disso, atualizam somente o item afetado ou atualizam a primeira página de resultados.

O carregamento paginado está disponível na tabela Repositório inicial, Coleções, Explorer, painéis Pesquisar e Modelo e na caixa de diálogo Selecionar caminho.

Para obter mais detalhes, exiba [Carregamento paginado de arquivos e pastas](../user-guide/paginated-loading-assets.md).

![paginação para o painel de navegação da pasta](../user-guide/images/home-tree-pagination.png){width="650"}









