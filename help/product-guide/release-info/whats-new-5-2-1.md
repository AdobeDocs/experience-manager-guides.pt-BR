---
title: Notas de versão | Novidades da versão 5.2.0 do Service Pack 1 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 5.2.0 Service Pack 1 do Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 788d0b9a2e2f07d2990bcc4f984f3ba4a4aabf17
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%
---
# Novidades da versão 5.2.0 do Service Pack 1 (setembro de 2026)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 5.2.0 do Service Pack 1 do Adobe Experience Manager Guides.

Para obter a lista de problemas que foram corrigidos nesta versão, consulte [Problemas corrigidos na versão 5.2.0 Service Pack 1](fixed-issues-5-2-0-sp1.md).

Saiba mais sobre as [instruções de atualização para o 5.2.0 Service Pack 1 versão](../release-info/upgrade-instructions-5-2-0-sp1.md).


## O Experience Manager Guides adiciona suporte a MCP

O Experience Manager Guides agora é compatível com o Protocolo de contexto de modelo (MCP). Você pode conectar suas ferramentas de IA, como Claude, Cursor e muito mais, ao Guides sem precisar de trabalho personalizado. Por meio de um único endpoint de MCP, nesta versão, os usuários autenticados podem usar o Guides como um sistema headless e gerenciar tópicos e mapas, criar e exportar linhas de base e gerar relatórios, tudo isso enquanto operam sob as permissões existentes do AEM. Isso permite que as equipes de documentação trabalhem com mais eficiência usando aplicativos e agentes de IA.

Para obter mais detalhes, consulte [Usando o Adobe Experience Manager Guides MCP Server](../install-conf-guide/conf-aem-guides-mcp.md).


## Suporte para fontes de dados externas e citações agora disponíveis no Novo editor

O novo editor agora oferece suporte a dois recursos existentes do Experience Manager Guides: capacidade de se conectar a fontes de dados externas e usar citações nos documentos.

Os autores podem continuar usando fontes de dados externas configuradas ao criar ou atualizar conteúdo no Novo editor. As citações também são compatíveis, de modo que os autores podem adicionar e gerenciar referências em seu conteúdo sem alternar entre editores.

## Suporte para estilo de citação AMA

A Experience Manager Guides agora oferece suporte ao estilo de citação da American Medical Association (AMA), estendendo a estrutura de citação existente para atender aos padrões de documentação exigidos pelos clientes nos setores de saúde, regulamentação e ciências biomédicas.

Quando o AMA é selecionado como estilo de citação nas **configurações do Workspace**, as citações são formatadas automaticamente de acordo com as diretrizes do AMA, incluindo renderização numérica sobrescrita, numeração sequencial e ordenação precisa da lista de referências. A opção **Analisar citação** no Editor está disponível exclusivamente quando o AMA é selecionado, permitindo que os autores adicionem e analisem citações sem alternar contextos.

O estilo de citação AMA é compatível com os formatos de saída nativos PDF e AEM Sites. Para configurar o estilo da citação, vá para **configurações do Workspace** e selecione AMA nas opções de estilo da citação. Para obter detalhes, consulte [Trabalhar com citações](../user-guide/web-editor-apply-citations.md).


