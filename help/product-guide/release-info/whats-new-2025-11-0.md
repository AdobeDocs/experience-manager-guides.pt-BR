---
title: Notas de versão | Novidades na versão 2025.11.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2025.11.0 do Adobe Experience Manager Guides
role: Leader
exl-id: 270a5faa-a16f-4939-900e-3c6c54660d2c
TQID: https://experienceleague.adobe.com/IuRSYXzBeHanuEsfc3-dPZuIGW3r67zPMeBILR34FvA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 0%

---

# Novidades da versão 2025.11.0 (novembro de 2025)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2025.11.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2025.11.0](fixed-issues-2025-11-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.11.0](../release-info/upgrade-instructions-2025-11-0.md).


## Introdução de um novo repositório na página inicial e experiência de pesquisa aprimorada

O Repositório, agora acessível diretamente da página inicial, serve como um espaço centralizado para a descoberta aprimorada de pastas e arquivos. Ele apresenta o **painel de navegação de pasta** dedicado e uma **exibição tabular do Repositório** personalizável. A experiência de pesquisa e filtro renovada facilita significativamente a localização e a localização de arquivos. Para obter mais detalhes, consulte [Conhecer a interface do Repositório](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png)

No Editor, a experiência de Pesquisa e filtro para arquivos agora é consistente com a Página inicial. Um novo [painel de Pesquisa](../user-guide/search-panel-explorer.md), localizado na parte inferior da interface do Editor, foi introduzido para exibir resultados de pesquisa. Além disso, o Repositório agora é renomeado para **Explorer** no Editor, permitindo que você procure pastas e arquivos como antes.

![](assets/search-panel-explorer.png)


## Indexação aprimorada para sugestões inteligentes no Assistente de IA

Agora é possível rastrear facilmente o status de cada tentativa de indexação para Sugestões inteligentes no Assistente do AI com novos indicadores de status: Indexação concluída, Não sincronizado, Em andamento e Indexação com falha. O último carimbo de data e hora de indexação agora é gravado no nível do perfil da pasta para melhorar a rastreabilidade. Além disso, as restrições de pasta pai-filho são aplicadas ao especificar uma pasta ou caminho de arquivo para indexação.

Para obter mais detalhes, consulte [Configurar o Assistente de IA para ajuda inteligente e criação](../cs-install-guide/conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring).

## Melhorias de desempenho

### Limpeza automatizada da árvore B para desempenho ideal

Para manter a eficiência do sistema e evitar o congestionamento de recursos, um novo processo de segundo plano limpa regularmente as árvores B no nível do sistema. Isso garante que os ativos que não existem mais ou foram adicionados temporariamente não ocupem espaço desnecessário.

O sistema identifica de forma inteligente os candidatos à limpeza e realiza a remoção automática. Além disso, esse recurso é configurável, dando aos administradores controle sobre seu comportamento com base nas necessidades operacionais.

Para obter mais detalhes, exiba [Configurar limpeza da árvore B](../cs-install-guide/configure-btree-cleanup-cs.md).

### Manuseio de mapas DITA aprimorado com grande número de chaves

Agora você pode trabalhar perfeitamente com mapas DITA que contêm um grande número de chaves. Esse aprimoramento garante carregamento mais rápido e melhor desempenho, facilitando o gerenciamento de mapas complexos sem interrupções.

Após a atualização da build, o sistema pode enfrentar um aumento temporário na carga, causando um atraso no pós-processamento de dados recém-carregados. Isso se deve a um OTS (script único) automatizado em execução em segundo plano. Quando o script for concluído, o desempenho do sistema voltará ao normal.

### Processamento de ativos aprimorado

Um processo automatizado foi introduzido para manter os ativos no `/content/dam` atualizados. O sistema aciona o reprocessamento de ativos a cada 15 minutos. Durante cada ciclo, os ativos que foram adicionados recentemente ou que permaneceram não processados dentro do intervalo de 15 minutos mais recente são coletados e reprocessados, melhorando a eficiência e a consistência em todo o repositório de conteúdo.

Para obter mais detalhes, consulte [Processar ativos](../user-guide/asset-processor.md).
