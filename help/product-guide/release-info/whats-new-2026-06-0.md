---
title: Notas de versão | Novidades na versão 2026.06.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2026.06.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 0%

---

# Novidades da versão 2026.06.0 (junho de 2026)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2026.06.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2026.06.0](fixed-issues-2026-06-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.06.0](../release-info/upgrade-instructions-2026-06-0.md).


## Nova coleção de mapas (Beta) para gerenciamento de mapas e publicação de saídas

>[!NOTE]
>
> Esse recurso está disponível no momento como um recurso do Beta e está desativado por padrão. Para ativá-lo em seu ambiente, entre em contato com a equipe de Sucesso do cliente.

A nova coleção de mapas (Beta) reúne o gerenciamento de coleções de mapas e as atividades de geração de saída em uma única interface. Em um único local, é possível gerenciar mapas e predefinições, gerar e publicar saídas, exibir histórico de geração e publicação e muito mais. Reunindo tarefas de publicação relacionadas, é mais fácil trabalhar com coleções de mapas e rastrear a atividade de saída em vários mapas e seus idiomas associados.

![](assets/new-maps-collection.png)

Para obter mais detalhes, consulte [Usar nova coleção de mapas para geração de saída (Beta)](../user-guide/generate-output-use-new-map-collection-output-generation.md).

## Introdução de um novo mecanismo de publicação para o PDF nativo

Um novo mecanismo de publicação, *Mecanismo do PDF nativo v2*, está disponível para o PDF nativo no Experience Manager Guides. Ele inclui aprimoramentos de renderização e correções para problemas de PDF Engine v1 Nativo. Como o comportamento de renderização foi atualizado, a saída do PDF gerada com o *Mecanismo do PDF nativo v2* pode ser diferente da saída gerada com o mecanismo de publicação do PDF nativo existente, *Mecanismo do PDF nativo v1*.

Por exemplo, o texto em PDFs gerados pode parecer um pouco diferente devido a atualizações nas fontes principais usadas pelo *Mecanismo nativo do PDF v2*. Da mesma forma, as imagens podem parecer mais nítidas devido a melhorias na interpolação da imagem e no comportamento de renderização.

Saiba como [habilitar o mecanismo do PDF nativo v2](../native-pdf/conf-new-pdf-engine.md) em seu ambiente.

Para obter informações sobre o **Mecanismo do PDF nativo v2**, consulte [Trabalhar com o Mecanismo do PDF Nativo v2](../native-pdf/new-pdf-engine.md).


## Aprimoramentos do editor

### Suporte para estilo de citação AMA

A Experience Manager Guides agora oferece suporte ao estilo de citação da American Medical Association (AMA), estendendo a estrutura de citação existente para atender aos padrões de documentação exigidos pelos clientes nos setores de saúde, regulamentação e ciências biomédicas.

Quando o AMA é selecionado como estilo de citação nas **configurações do Workspace**, as citações são formatadas automaticamente de acordo com as diretrizes do AMA, incluindo renderização numérica sobrescrita, numeração sequencial e ordenação precisa da lista de referências. A opção **Analisar citação** no Editor está disponível exclusivamente quando o AMA é selecionado, permitindo que os autores adicionem e analisem citações sem alternar contextos.

O estilo de citação AMA é compatível com os formatos de saída nativos PDF e AEM Sites. Para configurar o estilo da citação, vá para **configurações do Workspace** e selecione AMA nas opções de estilo da citação. Para obter detalhes, consulte [Trabalhar com citações](../user-guide/web-editor-apply-citations.md).


### Suporte para fontes de dados externas e citações agora disponíveis no Novo editor

O novo editor agora oferece suporte a dois recursos existentes do Experience Manager Guides: capacidade de se conectar a fontes de dados externas e usar citações nos documentos.

Os autores podem continuar usando fontes de dados externas configuradas ao criar ou atualizar conteúdo no Novo editor. As citações também são compatíveis, de modo que os autores podem adicionar e gerenciar referências em seu conteúdo sem alternar entre editores.

## Revisar melhorias

### Sincronizar a conclusão da tarefa de revisão entre a interface de revisão e a Caixa de entrada do AEM (Beta)

>[!NOTE]
>
> Esse recurso está disponível no momento como um recurso do Beta e está desativado por padrão. Para ativá-lo em seu ambiente, entre em contato com a equipe de Sucesso do cliente.

Agora é possível manter a conclusão da tarefa de revisão em sincronia entre a interface de revisão e a Caixa de entrada do AEM. Quando esse recurso está ativado, a conclusão de uma tarefa na interface de revisão a remove da Caixa de entrada do AEM e a conclusão da tarefa na Caixa de entrada do AEM a marca como concluída na interface de revisão. Isso ajuda a evitar a conclusão da mesma tarefa duas vezes e torna o fluxo de trabalho de revisão mais suave. Os autores e iniciadores de tarefas podem continuar a revisar comentários e reatribuir tarefas quando for necessária uma revisão adicional. Quando uma tarefa é reatribuída, uma nova notificação da Caixa de entrada do AEM é gerada para o revisor, permitindo que o ciclo de revisão continue facilmente.

Para obter mais detalhes, exiba [Concluir a tarefa de revisão como Revisor](../user-guide/review-complete-review-tasks.md).

## Aprimoramentos no conteúdo de aprendizado

Os seguintes aprimoramentos estão disponíveis para o recurso Treinamento e conteúdo de aprendizado do produto nesta versão:

- Os autores agora podem tornar uma verificação de conhecimento obrigatória para os alunos antes de avançarem em um curso. Uma nova opção **Exigir verificação de conhecimento para continuar** foi introduzida para verificações de conhecimento em cursos. Quando ativados, os alunos devem tentar uma verificação de conhecimento antes de prosseguir para o conteúdo subsequente do curso. Isso ajuda a garantir que as verificações de conhecimento necessárias sejam concluídas em pontos designados do curso. Para obter mais detalhes, consulte [Outras opções no menu Inserir](../learning-content/lc-other-insert-options.md).
- Agora é possível usar campos de entrada de texto multilinha ao criar conteúdo de aprendizado. Esse aprimoramento facilita a captura de respostas mais longas do aluno, oferecendo suporte a quebras de linha e quebra automática de texto em um único campo, sem depender de scripts personalizados. Saiba mais sobre [Outras opções no menu Inserir](../learning-content/lc-other-insert-options.md).
- Os modelos de saída SCORM agora permitem atribuir diferentes layouts de página a diferentes tipos de tópico em um curso. Isso permite configurar layouts dedicados para lições, testes, páginas de visão geral e outros tipos de tópicos diretamente das configurações do modelo de saída.

  Isso permite que cada tipo de tópico use um layout apropriado ao seu conteúdo e estrutura, em vez de aplicar o mesmo layout em todas as páginas do curso. Para obter mais detalhes sobre como configurar layouts de página para modelos de saída SCORM, exiba [Configurar perfis de pasta](../lc-config-guide/lc-folder-profile.md).
- O Experience Manager Guides agora oferece suporte à publicação direta de conteúdo SCORM no Adobe Learning Manager (ALM). Após configurar um perfil de publicação do ALM, os autores podem gerar a saída SCORM e carregá-la diretamente no Adobe Learning Manager, sem baixar e importar manualmente o pacote.

  Para obter mais detalhes, consulte [Configurar predefinição de SCORM](../learning-content/config-scorm-preset.md).


