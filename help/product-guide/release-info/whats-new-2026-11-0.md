---
title: Notas de versão | Novidades na versão 2026.11.0 do Adobe Experience Manager Guides
description: Explore novos recursos na versão 2026.11.0 do Adobe Experience Manager Guides, incluindo a ramificação no nível do mapa e a criação de conteúdo do Assistente de IA.
role: Leader
source-git-commit: ef5e433214f15b12102af7c9e38031536183ca72
workflow-type: tm+mt
source-wordcount: '1512'
ht-degree: 0%
---

# Novidades da versão 2026.11.0 (novembro de 2026)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2026.11.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2026.11.0](fixed-issues-2026-11-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.11.0](../release-info/upgrade-instructions-2026-11-0.md).

## Introdução à ramificação e mesclagem em nível de mapa

O Adobe Experience Manager Guides apresenta o recurso de ramificação e mesclagem no nível do mapa, permitindo que os autores trabalhem em várias versões de documentação, atualizações de recursos e correções críticas em paralelo, sem afetar o conteúdo principal. Os autores podem criar ramificações isoladas de um mapa DITA e suas dependências, garantindo que as edições, bloqueios e visualizações permaneçam específicas para cada ramificação.

Esse recurso ajuda as equipes de documentação a gerenciar fluxos de trabalho paralelos, colaborar com eficiência e manter a estabilidade da versão principal da documentação. É possível:

- **Crie ramificações** a partir da versão principal de um mapa DITA para trabalhar independentemente em recursos, aprimoramentos ou correções críticas.
- **Alternar entre ramificações** no Editor para gerenciar várias versões de documentação.
- **Gerencie versões de conteúdo** para organizar alterações por meio de ramificação e mesclagem.
- **Resolver conflitos de mesclagem** usando um fluxo de trabalho de comparação guiado com mesclagem de três vias.
- **Mesclar alterações** na versão principal.
- **Publicar diretamente de uma ramificação** usando a publicação padrão sem modificar a versão principal.

Saiba mais sobre [Ramificação e mesclagem](../user-guide/branching-overview.md).

![](./assets/branching.png){width="650"}


## Habilidades de criação e importação de conteúdo habilitado por IA no Assistente de IA

>[!NOTE]
>
>Para usar o Assistente de IA no modo Agente, sua organização deve ser integrada ao Adobe CX Enterprise Coworker e ter os créditos necessários.

Agora, você pode usar o **Assistente do AI** para criar e importar conteúdo DITA usando prompts em linguagem natural. Com a tecnologia **Adobe CX Enterprise Coworker**, as novas habilidades do **Create** e do **Import** simplificam a criação de conteúdo estruturado e ajudam os autores a trabalhar com conteúdo DITA sem exigir uma ampla experiência em DITA.

- **Criar:** Gerar tópicos e mapas DITA a partir de prompts em linguagem natural, documentos de referência ou conteúdo existente, usando modelos de repositório. Você pode revisar o conteúdo gerado antes de salvá-lo e refinar iterativamente o conteúdo novo ou existente para atender aos seus requisitos.
- **Importar:** converta arquivos PDF, DOCX ou Markdown existentes em tópicos e mapas DITA estruturados. Você pode visualizar e revisar o conteúdo convertido antes de salvá-lo no repositório.
- **Marcação inteligente:** obtenha recomendações de marcas relevantes para seu conteúdo com base na taxonomia de sua organização. A experiência aprimorada permite que os administradores de perfis de pastas configurem namespaces de taxonomia nas configurações do Workspace, garantindo recomendações de tags consistentes e controladas.

O painel **Assistente de IA** também introduz um modo de tela cheia e uma seção **Conversações ativas** para obter uma experiência de conversação aprimorada.

Para obter mais detalhes, consulte [Usar o Assistente de IA no modo Agencial](../user-guide/ai-assistant.md#agentic-mode).

![](./assets/preview-import.png){width="650"}


## Novo painel do assistente de Ajuda no Experience Manager Guides

O recurso **Ajuda Inteligente** alimentado por IA generativa está disponível por meio do painel **Assistente de Ajuda** dedicado, acessível nas interfaces da Página Inicial, do Editor e do Console de Mapas. O painel oferece uma experiência de pesquisa conversacional, permitindo que você faça perguntas em linguagem natural e encontre rapidamente informações relevantes na documentação do Experience Manager Guides. Isso ajuda você a acessar orientação contextual e resolver consultas sem sair do Editor, simplificando seu fluxo de trabalho de criação.

Os administradores podem gerenciar a disponibilidade do painel do assistente de Ajuda por meio das configurações do Workspace. A seção **Assistente de Ajuda da IA** inclui um botão para ativar ou desativar o painel para os usuários.

Para obter mais informações, consulte o [Assistente de ajuda](../user-guide/ai-based-smart-help.md).

![](./assets/help-assistant.png){width="650"}

## Aprimoramentos de criação

### Painel Controlar alterações no novo editor

O painel **Controlar alterações** agora está disponível no Novo Editor, permitindo que você visualize todas as inserções e exclusões controladas em um tópico. É possível rastrear edições feitas por vários usuários e aceitar ou rejeitar alterações diretamente do painel.

Você também pode controlar como o conteúdo excluído aparece no Editor usando a configuração **Mostrar exclusões rastreadas em linha**, que permite exibir o conteúdo excluído como texto tachado ou substituí-lo por um ícone de lápis vinculado à alteração correspondente. Saiba mais sobre [Controlar alterações](../user-guide/config-editor-settings.md#track-changes).

![Configurações do editor](./assets/track-changes-all.png){width="650"}

### Classificar arquivos e pastas no painel Explorer

O painel **Explorer** do Editor permite classificar arquivos e pastas em ordem crescente ou decrescente usando o botão **Classificar**. Por padrão, os itens são classificados em ordem crescente por título ou nome de arquivo, com base na configuração **Exibição de arquivos do editor** em **Preferências do usuário**. Isso facilita a navegação e a localização do conteúdo no Editor.

Para obter mais informações, consulte a seção [Explorer](../user-guide/paginated-loading-assets.md#explorer) em Carregamento paginado de arquivos e pastas.

### Gerenciar versões e rótulos para arquivos não DITA no Editor

O Experience Manager Guides permite visualizar o histórico de versões e gerenciar rótulos de versão para arquivos não DITA, como imagens, multimídia, ZIP, PDF e arquivos DOCX, diretamente do Editor. Você pode visualizar esses arquivos, revisar seu histórico de versões, comparar versões e reverter para uma versão anterior sem navegar para a interface do usuário do Assets. Você também pode aplicar ou atualizar rótulos de versão para versões de arquivo existentes para simplificar a identificação e o gerenciamento de versões.

Para obter mais informações, consulte [Trabalhar com mídia e outros arquivos não DITA](../user-guide/authoring-file-management.md#work-with-media-and-other-non-dita-files).


![Configurações do editor](./assets/version-management-non-dita-files.png){width="650"}


## Revisar melhorias

### Colaboração aprimorada de revisão com comentários do iniciador

Os iniciadores da revisão podem adicionar comentários e anotações em linha a tópicos em uma tarefa de revisão usando a interface de revisão. Isso permite que eles forneçam contexto adicional, destaquem conteúdo específico e chamem a atenção dos revisores para áreas que exigem feedback.

Esses comentários aparecem no painel **Comentários** junto com comentários de outros revisores, fornecendo uma exibição consolidada das discussões de revisão. Os revisores também recebem uma notificação do AEM quando o iniciador adiciona um comentário, ajudando a simplificar a colaboração e a comunicação durante todo o processo de revisão. Para obter mais informações, exiba [Adicionar comentários para revisores](../user-guide/review-send-topics-for-review.md#add-comments-for-reviewers).

## Aprimoramentos de publicação

### Exibir e gerenciar o histórico de saída no Console do Mapa

O console de Mapa no Experience Manager Guides agora inclui uma guia **Histórico de saída**, permitindo que você visualize e gerencie tarefas de geração de saída diretamente do Editor sem navegar até o painel de mapa.

A guia fornece uma exibição consolidada de tarefas de geração de saída, incluindo status, detalhes predefinidos, data de geração e duração. Você pode pesquisar e filtrar tarefas, cancelar gerações em andamento, acessar saídas e logs gerados e remover entradas concluídas do histórico. Você também pode exportar o histórico de saída como um arquivo CSV para análise adicional. Os status de geração de saída usam indicadores de cor compatíveis com o painel Mapa.

Para obter detalhes, exiba [Gerenciar processo de geração de saída](../user-guide/generate-output-manage-process.md#view-and-manage-output-generation-tasks-from-the-editor).

![Configurações do editor](./assets/output-history-editor-view.png){width="650"}


### Opções aprimoradas de limpeza do histórico de saídas

Você pode limpar o histórico de saída **Por idade** (removendo entradas com mais de um número especificado de dias) ou **Por contagem** (mantendo apenas um número especificado de entradas recentes).

Você também pode optar por expurgar somente os logs de saída, preservando as entradas do histórico para fins de auditoria, ou remover os logs e suas entradas associadas. Essas opções ajudam a otimizar o armazenamento do repositório, ao mesmo tempo em que fornecem maior controle sobre a eliminação do histórico de saída.

Para obter mais informações, consulte [Configurar período de limpeza automática para o histórico de saída](../install-conf-guide/conf-output-generation.md#configure-auto-purging-period-for-output-history-id19aai070v8q).

### Suporte do GitLab para perfis de publicação do Edge Delivery Services

A publicação do Edge Delivery Services é compatível com repositórios hospedados no GitLab ao lado do GitHub, fornecendo maior flexibilidade no gerenciamento e na publicação de conteúdo DITA. Para publicar em um site hospedado no GitLab, selecione GitLab como tipo de servidor ao criar um perfil de publicação do Edge Delivery Services e forneça o token de acesso ao projeto do repositório no campo Token de acesso.

As predefinições de publicação também incluem um campo para uma subpasta, para que você possa publicar conteúdo em uma subpasta na pasta raiz especificada no perfil.

Para obter mais detalhes, consulte [Configurar uma Edge Delivery Services](../knowledge-base/publishing/configure-eds.md).

### Melhorias na publicação do Salesforce

O Experience Manager Guides aprimora a publicação do Salesforce com segurança, desempenho e eficiência de publicação aprimorados. Esses aprimoramentos incluem suporte à chave de prova para troca de código (PKCE), autenticação baseada em token de atualização, status de publicação em nível de artigo, logs de publicação detalhados, histórico de saída e publicação de ativos otimizada para reduzir uploads redundantes.

Para obter mais informações, exiba [Publicação aprimorada do Salesforce usando processamento de back-end](../user-guide/web-editor-article-publishing.md#enhanced-salesforce-publishing-using-backend-processing).


### Suporte para imagens de metadados de mapa no PDF nativo

A publicação nativa do PDF é compatível com a exibição dinâmica de imagens definidas nos metadados de mapas DITA, bookmaps e mapas personalizados. Você pode usar um único modelo do PDF em vários mapas enquanto exibe imagens específicas de mapa, como imagens de capa de produto, na saída gerada.

Ao adicionar um alocador de espaço de imagem ao layout de página, você pode preenchê-lo automaticamente com a imagem referenciada nos metadados do mapa durante a publicação. Isso elimina a necessidade de manter modelos separados para imagens diferentes e simplifica o gerenciamento de modelos.

Para obter mais informações, exiba [Adicionar uma imagem dos metadados do mapa](../native-pdf/design-page-layout.md#add-an-image-from-map-metadata-add-image-map-metadata).

### Validar a qualidade do conteúdo com a verificação de integridade do conteúdo no Editor antigo

A verificação de integridade do conteúdo está disponível no Editor antigo (já compatível com o Novo editor), ajudando a validar a qualidade do conteúdo em mapas DITA antes da publicação. Os administradores podem criar predefinições reutilizáveis de verificação de integridade combinando verificações de links desfeitos, IDs duplicadas e validação de Schematron.

Os autores podem executar uma verificação de integridade em um mapa DITA ou em uma linha de base selecionada no Editor antigo para gerar um relatório consolidado de problemas em tópicos e mapas associados. Para obter detalhes, exiba [Executar verificação de integridade em um mapa](../user-guide/map-editor-other-features.md#run-health-check-on-a-map).

## Substituir API para migração de conteúdo herdado

Essa API permite criar ou atualizar o conteúdo e seus metadados por meio de uma única API. Ela é compatível com a especificação do conteúdo do tópico, metadados e um GUID na solicitação. A API está disponível na documentação da API do Swagger em `/bin/guides/v1/asset/upsert/`.