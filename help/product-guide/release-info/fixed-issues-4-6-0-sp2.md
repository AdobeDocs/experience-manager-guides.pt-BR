---
title: Notas de versão | Correção de problemas na versão do Adobe Experience Manager Guides 4.6.0 Service Pack 3
description: Saiba mais sobre as correções de erros na versão 4.6.0 Service Pack 3 do Adobe Experience Manager Guides
role: Leader
source-git-commit: d60fea16831af458c479df24c877ef7095b2fd15
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Correção de problemas na versão 4.6.0 Service Pack 3 (janeiro de 2025)


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.6.0 Service Pack 3 do Adobe Experience Manager Guides.

Saiba mais sobre [as instruções de atualização para o 4.6.0 Service Pack 3 versão](upgrade-instructions-4-6-0-sp2.md).

## Criação  

- Todos os grupos de condição são perdidos e as condições são niveladas ao atualizar as condições do perfil da pasta. (23526)
- A alteração do valor das linhas de cabeçalho de uma tabela no painel **Propriedades de conteúdo** não aplica o valor atualizado. (23213)
- Ao adicionar novas referências de tópico no mapa DITA usando a caixa de diálogo de elemento **Referência de tópico** no modo de exibição de layout, as referências adicionadas são mostradas como link corrompido. (22859)
- Ao adicionar tópicos no mapa DITA usando a caixa de diálogo de elemento **Referência de tópico** na exibição do autor, os tópicos selecionados são inseridos na ordem inversa de serem selecionados. (22858)
- Ao copiar uma imagem de qualquer produto externo (por exemplo, MS PowerPoint) e colá-la nos Guias, a funcionalidade de fazer upload do ativo instantaneamente para uso no arquivo do é interrompida. (24983)
- Ao pesquisar arquivos no repositório usando a funcionalidade **Pesquisar e filtrar**, não é possível selecionar vários arquivos. (25104)

## Publicação

- A publicação no Salesforce falha quando o conteúdo contém espaços não separáveis. (23664)
- Para tópicos com erros como links quebrados, a publicação no Salesforce falha e a barra de progresso é exibida indefinidamente. (22985)
- Para mapas com links quebrados, a publicação do Salesforce falha e a barra de progresso é exibida indefinidamente. (24963)
- Se um link externo contiver uma UUID, ele entrará no pós-processamento e converterá o link externo em link UUID, quebrando o link no editor da Web e também nos sites de publicação. (22574)
- O `xref` converte em link relativo mesmo quando o **escopo** do link está definido como **externo**. (23059)
- Falha na geração de PDF nativo para conteúdo com o atributo **chunk** definido como **to-content**. (21772)
- A caixa de diálogo **Editar propriedades** de uma linha de base não mostra os critérios salvos anteriormente para a linha de base dinâmica. (23964)


## Tradução

- Para tradução não herdada (para não UUID), mover um tópico no caminho de origem para uma pasta diferente resulta em referências corrompidas no local de destino. (24152)
