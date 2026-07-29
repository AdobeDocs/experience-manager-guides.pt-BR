---
title: Notas de versão | Novidades na versão 2026.08.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2026.08.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: b866964c30a565eab0f6f9aec4b3fc9013f15f75
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 0%

---

# Novidades da versão 2026.08.0 (agosto de 2026)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2026.08.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2026.08.0](fixed-issues-2026-08-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.08.0](../release-info/upgrade-instructions-2026-08-0.md).


## Nova coleção de mapas para gerenciamento de mapas e publicação de saídas

A nova coleção de mapas reúne o gerenciamento de coleções de mapas e as atividades de geração de saída em uma única interface. Em um único local, é possível gerenciar mapas e predefinições, gerar e publicar saídas, exibir histórico de geração e publicação e muito mais. Reunindo tarefas de publicação relacionadas, é mais fácil trabalhar com coleções de mapas e rastrear a atividade de saída em vários mapas e seus idiomas associados. Essa atualização também aborda problemas de desempenho observados com grandes coleções de mapas.

![](assets/new-maps-collection.png)

Para obter mais detalhes, consulte [Usar nova coleção de mapas para geração de saída](../user-guide/generate-output-use-new-map-collection-output-generation.md).


## Buscar conteúdo de repositórios Git usando o conector Git

O Experience Manager Guides agora apresenta o Conector Git, que permite importar conteúdo de repositórios Git para o Experience Manager Guides. Depois que o conteúdo for importado, as equipes poderão continuar usando o Experience Manager Guides para seus fluxos de trabalho de criação, revisão, tradução e publicação.

Para ajudar a manter o conteúdo importado atualizado, o Conector Git também oferece suporte à recuperação de conteúdo do repositório de origem para trazer atualizações. Ele inclui a detecção inteligente de alterações para identificar atualizações de conteúdo, preserva tópicos e mapeia GUIDs durante operações de importação e rebusca, e fornece recursos de resolução de conflitos para ajudar a gerenciar diferenças entre o conteúdo do repositório e o conteúdo já disponível no Experience Manager Guides. Para obter mais detalhes, consulte [Importar conteúdo usando o Conector Git](../user-guide/web-editor-git-connector.md).

![](assets/git-bulk-importer-import-all.png)


## O Experience Manager Guides adiciona suporte a MCP para integração com o Assistente de IA

O Experience Manager Guides agora oferece suporte à integração MCP (Model Context Protocol), permitindo que os assistentes de IA, como Anthropic Claude, se conectem diretamente ao ambiente do AEM Guides.

Por meio de um único endpoint de MCP, os usuários autenticados podem gerenciar tópicos e mapas, criar e exportar linhas de base e gerar relatórios usando linguagem natural, tudo isso enquanto operam com as permissões existentes do AEM. Isso elimina tarefas repetitivas e de navegação intensa e permite que as equipes de documentação trabalhem com mais eficiência em aplicativos de bate-papo e ferramentas de desenvolvedor compatíveis com MCP, como o Cursor e o Visual Studio Code. Para obter mais detalhes, consulte [Usando o Adobe Experience Manager Guides MCP Server](../install-conf-guide/conf-aem-guides-mcp.md).


## Revisar melhorias

### Delegar uma tarefa de revisão a outro Revisor

Os revisores agora podem recomendar que outro usuário participe de uma revisão antes que ela retorne ao Autor, usando a nova opção **Delegar** disponível para uma tarefa de revisão. Isso é útil quando parte do conteúdo não se enquadra no conhecimento do Revisor ou quando uma segunda opinião é necessária antes de concluir a revisão, sem precisar encaminhar a solicitação por meio de um administrador de projeto.

Selecionar a opção Delegar envia a recomendação ao Autor, que decide se adiciona o revisor recomendado à tarefa. Saiba mais sobre [Delegar uma tarefa de revisão a outro Revisor](../user-guide/review-complete-review-tasks.md#delegate-a-review-task-to-another-reviewer).

![](assets/review-delegate-option.png){width="350"}

### A descrição da tarefa agora está visível na interface de revisão

Os revisores agora podem visualizar a descrição da tarefa diretamente na experiência de revisão, em vez de depender apenas do email de notificação. A descrição inserida ao criar uma tarefa de revisão agora é exibida na caixa de diálogo Detalhes da revisão, acessível por meio do ícone **Informações** na interface de Revisão e na interface de Editor.

Isso dá aos revisores acesso a instruções, escopo e áreas de foco ao longo da revisão. Para obter mais detalhes, exiba [Enviar tópicos para revisão](../user-guide/review-send-topics-for-review.md).

![](assets/review-details.png){width="350"}

### Identificação de usuário na lista de marcação durante a revisão

Ao marcar usuários nos comentários de revisão ou respostas, a lista suspensa de marcação agora exibe o endereço de email de cada usuário junto com sua ID de usuário. Isso facilita a identificação e a seleção do Revisor correto, especialmente em grandes organizações onde os nomes de exibição sozinhos podem ser ambíguos.

Se um endereço de email não estiver disponível, a ID do usuário será exibida. Para obter mais detalhes sobre como trabalhar com a Interface de revisão, exiba [Marcar usuários de tarefas em um comentário](../user-guide/review-topics.md#tag-task-users-in-a-comment).


### Exibir todas as tarefas de revisão de um tópico

Os autores agora podem exibir todas as tarefas de revisão, abertas ou fechadas, associadas ao tópico atualmente aberto diretamente no painel Comentários. Uma lista suspensa lista todas as tarefas de revisão das quais o tópico faz parte, juntamente com o estado e o projeto de cada tarefa, e permite alternar entre elas para exibir comentários sem sair do tópico ou alternar entre projetos de revisão. Saiba mais sobre [Exibir todas as tarefas de revisão de um tópico](../user-guide/review-address-review-comments.md#view-all-review-tasks-for-a-topic).

![](assets/review-task-selection-dropdpwn.png){width="350"}

### Experiência de revisão aprimorada com condições DITAVAL

Quando uma tarefa de revisão inclui um ou mais arquivos DITAVAL anexados, o painel Condições agora apresenta cada condição como um botão de alternância, predefinido para corresponder aos arquivos DITAVAL anexados, para que os revisores vejam o conteúdo da maneira pretendida pelo iniciador da revisão. Desativar um botão de alternância oculta esse conteúdo da revisão; ativá-lo o restaura.

Para obter detalhes, exiba o painel [Condições com condições baseadas em DITAVAL](../user-guide/review-topics.md#conditions-panel-with-ditaval-based-conditions).

![](assets/review-condition-panel-ditaval.png){width="350"}

## Aprimoramentos de publicação

### Usar predefinições de saída como modelos

Agora, os administradores podem designar predefinições de saída como modelos, aplicando configurações padronizadas em todos os mapas em um perfil de pasta com uma única ação por meio do Console de mapas. Quando um modelo é aplicado, o sistema exibe o número de mapas afetados, dando aos administradores visibilidade total antes da implantação. Para preservar a consistência, as predefinições do modelo só podem ser modificadas pelos administradores e a geração de saída está desabilitada para predefinições do modelo (a menos que a saída já tenha sido gerada antes de definir as predefinições como modelo).

Para obter detalhes, exiba [Configurar predefinições de modelo para geração de saída](../install-conf-guide/template-presets-output-generation.md).

### Validar a qualidade do conteúdo com a verificação de integridade do conteúdo

A verificação de integridade do conteúdo ajuda a validar a qualidade do conteúdo em mapas DITA antes da publicação. Os administradores podem criar predefinições reutilizáveis de verificação de integridade combinando verificações de links desfeitos, IDs duplicadas e validação de Schematron.

Os autores podem executar uma verificação de integridade em um mapa DITA ou em uma linha de base selecionada para gerar um relatório consolidado de problemas em tópicos e mapas associados. Para obter detalhes, exiba [Executar verificação de integridade em um mapa](../user-guide/map-editor-other-features.md#run-health-check-on-a-map).


## Aprimoramentos de tradução

### Especificar um caminho de pasta personalizado para projetos de tradução

Ao enviar conteúdo para tradução, agora é possível selecionar a pasta na qual um novo projeto de tradução é criado, em vez de todos os projetos assumirem como padrão um único local em `/content/projects`. Isso ajuda a evitar uma estrutura de projeto desorganizada e melhora o desempenho do carregamento de página conforme o número de projetos de tradução aumenta.

Para obter detalhes, consulte [Criar projeto de tradução](../user-guide/translate-documents-web-editor.md#create-a-translation-project).

## Aprimoramentos no conteúdo de aprendizado

Os seguintes aprimoramentos estão disponíveis para o recurso Treinamento e conteúdo de aprendizado do produto nesta versão:

- Uma nova guia **Experiência do aluno** está disponível na configuração de saída SCORM, permitindo que você configure como os alunos interagem com a saída SCORM e como navegam pela saída SCORM. As configurações são organizadas em Geral, Navegação e Questionário, fornecendo controle sobre a acessibilidade do conteúdo, o fluxo de navegação e o comportamento do questionário para obter uma experiência de aprendizado personalizada.

  Em **Navegação**, agora você pode controlar se o botão **Avançar** está ativado ou desativado em uma página, permitindo que os alunos avancem somente depois que as condições especificadas nessa página forem atendidas, como abrir todos os elementos interativos, assistir a todas as mídias e muito mais. Para obter detalhes, consulte [Configurar predefinição de SCORM](../learning-content/config-scorm-preset.md).

  ![](assets/learner-experience.png){width="650"}

- Agora você pode ativar os downloads do PDF para alunos na saída SCORM. Quando essa opção está ativada, um ícone de download do PDF é adicionado à saída SCORM publicada, permitindo que os alunos baixem uma versão do PDF do conteúdo do curso para referência offline. Isso proporciona maior flexibilidade na forma como os alunos acessam os materiais do curso, enquanto proporciona aos autores mais controle sobre a experiência publicada. Para obter detalhes sobre a configuração e os pré-requisitos, consulte [Permitir que os alunos baixem o curso PDF](../learning-content/config-scorm-preset.md).

  ![](assets/pdf-icon.png){width="650"}

- Na saída publicada de um curso, os alunos agora podem usar a opção **Revisar respostas** depois de concluir uma tentativa de questionário para rever as respostas enviadas e ver quais respostas estavam corretas ou incorretas. Saiba mais sobre [Propriedades da pergunta em um questionário](../learning-content/quiz-insert-questions.md#question-properties).

  ![](assets/review-answer-quiz.png){width="650"}

- Em Perguntas de verificação de conhecimento em um curso, o botão **Tentar novamente** agora é exibido quando um aluno seleciona uma resposta incorreta, permitindo que ele tente novamente a pergunta. Esse comportamento é consistente em verificações de conhecimento de seleção única e seleção múltipla. Para obter detalhes, exiba [Outras opções no menu Inserir](../learning-content/lc-other-insert-options.md).

- Quando um tópico do HTML é adicionado a um mapa do grupo de aprendizado, o atributo `format="html"` agora é automaticamente adicionado ao `topicref` correspondente, garantindo o processamento e a publicação corretos no DITA-OT 4.x. Para obter mais detalhes, consulte [Adicionar conteúdo existente no curso](../learning-content/manage-course.md#add-existing-content).

## Aprimoramento da API

Esta versão apresenta novas APIs do Swagger para gerenciamento, tradução e publicação de ativos, facilitando a conexão desses fluxos de trabalho com suas ferramentas e sistemas existentes. Para obter detalhes, exiba [atualizações de API nas versões do Experience Manager Guides](../api-reference/api-update-swagger.md).

