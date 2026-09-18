---
title: Documentação do Experience Manager Guides
description: Encontre a documentação do Adobe Experience Manager Guides. Saiba mais sobre o suporte ao DITA nativo, criação estruturada e publicação multicanal no Experience Manager.
feature: AEM Guides Tutorials
role: User
TQID: https://experienceleague.adobe.com/S4wTM-7gfU7D-JfKVbb9nK3qoQIG6PdiY7jtpsc6kDs
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: aad65a09-20cc-4780-ad44-329d14dc8481
    internal-label: Workflows
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: 6ec4546ab632167e8e49baacc8e771a44563f394
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 5%
---
# Documentação do Experience Manager Guides

O Experience Manager Guides é um CCMS de nível empresarial com suporte ao DITA nativo para criação estruturada, publicação multicanal e gerenciamento do ciclo de vida do conteúdo.

**Implantação:** [!BADGE Cloud Service]{type=Informative} [!BADGE No Local]{type=Informative} [!BADGE Serviços gerenciados]{type=Informative}

## Comece pela sua função

<!-- Author note: The landing-cards-container component is in beta with known display issues in preview and review environments. Verify rendering in production before publishing. Update icon paths below once confirmed against the ExL CDN icon library. Role card links point to the first topic in each role's section of the left nav — update paths to match the actual repo structure. -->

::::landing-cards-container

:::card
![Ícone de autores](./user-guide/images/author.png)

Autores

Crie e gerencie tópicos DITA, mapas, reutilização de conteúdo e fluxos de trabalho de revisão.

[Visão geral da criação](./user-guide/authoring-content.md)
:::

:::card
![Ícone de administradores](./user-guide/images/admin.png)

Administradores

Configure perfis de pasta, permissões, configurações de fluxo de trabalho e modelos de saída.

[Guia de administração](./install-conf-guide/introduction.md)
:::

:::card
![Ícone de editores](./user-guide/images/publish.png)

Editores

Configure predefinições de saída, gerencie linhas de base e gere saída entre canais.

[Gerenciamento e publicação de mapas](./user-guide/map-console-overview.md)
:::

<!--
:::card
![Architects icon](./user-guide/images/architect.svg)

Architects

Design DITA specializations, schemas, and content architecture for your implementation.

[DITA specialization](./install-conf-guide/dita-ot-specialization.md)
:::
-->
::::

## Explorar por área de recurso

<!-- Author note: Six cards will wrap to two rows of three in production. Same beta caveat as the role cards above applies here. -->

::::landing-cards-container

:::card
![Ícone de criação](./user-guide/images/author.svg)

Criação

Editor da Web, integração do FrameMaker, conteúdo reutilizável e ciclos de revisão.

[Criar conteúdo](./user-guide/web-editor.md)
:::

:::card
![Ícone de revisão](./user-guide/images/review.svg)

Revisar

Revise tópicos, gerencie tarefas de revisão e revise notificações.

[Introdução à revisão](./user-guide/review.md)
:::

:::card
![Ícone de publicação](./user-guide/images/publish.svg)

Publicação

Tipos de saída PDF, AEM Sites, HTML5, EPUB e JSON.

[Publicar seu conteúdo](./user-guide/generate-output.md)
:::

:::card
![Ícone de tradução](./user-guide/images/Smock_GlobeGrid_18_N.svg)

Tradução

Fluxos de trabalho de tradução humana e automática para conteúdo multilíngue.

[Traduzir conteúdo](./user-guide/translation.md)
:::

:::card
![Ícone de relatórios](./user-guide/images/Smock_Report_18_N.svg)

Relatórios

Lista de tópicos, multimídia, links quebrados e relatórios de metadados.

[Gerar relatórios](./user-guide/reports-intro.md)
:::

:::card
![Ícone de configuração](./user-guide/images/config.svg)

Configuração

Perfis de pasta, personalização de DITA-OT e modelos de saída.

[Configurar perfis de pasta](./install-conf-guide/conf-profiles.md)
:::

::::

## Novidades

<!-- Author note: Badges render correctly in markdown table cells per ExL spec. <br> is supported within cells. Update release version, links, and descriptions each release cycle. The What's new table is the primary update touchpoint on this page — aim to refresh it within one week of each cloud service release. -->


<table>
<tr>
<td>

[!BADGE Recurso]{type=Neutral} <br> [**Importar conteúdo usando o Conector Git**](./user-guide/web-editor-git-connector.md)<br> Importar conteúdo para os Guias diretamente dos repositórios Git.

</td>
<td>

[!BADGE Recurso]{type=Neutral} <br> [**Nova coleção de mapas**](./user-guide/generate-output-use-new-map-collection-output-generation.md)<br> Interface unificada para gerenciar mapas e publicar saídas

</td>
<td>

[!BADGE Aprimoramento]{type=Neutral} <br> [**Delegar uma tarefa de revisão**](./user-guide/review-complete-review-tasks.md#delegate-a-review-task-to-another-reviewer) <br> Os revisores podem delegar uma tarefa de revisão a outro revisor

</td>
</tr>
</table>

## Recursos adicionais

* [Notas de versão do Cloud Service](./release-info/latest-release-info-cs.md)
* [Notas de versão para No local](./release-info/latest-release-info.md)
* [comunidade do AEM Guides](https://experienceleaguecommunities.adobe.com/adobe-experience-manager-guides-11){target="_blank"}
* [Repositório do GitHub](https://github.com/AdobeDocs/experience-manager-guides.en){target="_blank"}
* [Suporte](https://experienceleague.adobe.com/support/v2/en/){target="_blank"}
* [Tutoriais em vídeo](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/getting-started/overview){target="_blank"}
