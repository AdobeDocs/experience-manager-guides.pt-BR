---
title: Notas de versão | Correção de problemas na versão 2025.11.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2025.11.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: d9a46a009477b1110208a509d4ad8c0616139661
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Correção de problemas na versão 2025.11.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2025.11.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2025.11.0](whats-new-2025-11-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.11.0](upgrade-instructions-2025-11-0.md).

## Criação

- Se um elemento `prop` vazio sem atributos ou valores for adicionado a um arquivo DITAVAL, elementos `prop` adicionais não poderão ser adicionados. (GUIDES-33597)
- Depois de atualizar o Experience Manager Guides para a versão 2025.08.0, a opção para habilitar ou desabilitar a guia personalizada do **Acrolinx** não aparece mais nas **configurações do Workspace**. (GUIDES-35261)
- O CSS personalizado aplicado a um perfil de nível de pasta para tópicos ou mapas é revertido para o estilo padrão no modo de Visualização após a atualização do navegador. (GUIDES-31098)
- As operações **Desfazer** e **Refazer** não funcionam como esperado na exibição Source do Editor para arquivos DITA. (GUIDES-24914, GUIDES-25034)
- Ao fazer referência a um mapa DITA em um tópico usando o elemento `Xref`, o nome do arquivo do mapa referenciado é exibido em vez do título do mapa. (GUIDES-21759)
- Ao adicionar vários arquivos do Schematron para validação por meio do painel direito da interface do Editor, um erro **Os arquivos do Schematron não existem ou apresentam erros** é exibido mesmo se os arquivos adicionados forem válidos e não tiverem erros. (GUIDES-33731)
- Equações de MathML grandes ou complexas não são exibidas no Editor. (GUIDES-29095)

## Gerenciamento de ativos

- Ao fazer upload novamente de uma imagem editada por meio da interface do Experience Manager Guides, a representação original da imagem é atualizada, mas o conteúdo DITA associado continua a exibir a versão anterior da imagem. (GUIDES-33693)
- Ao tentar mover duas ou mais pastas do local de origem para um local diferente (usando a Ferramenta de movimentação em massa), a operação falhará se os nomes das pastas começarem com a mesma cadeia de caracteres (por exemplo, Product e ProductImages). (GUIDES-29096)
- A exclusão de um ativo pesquisado da interface do usuário do Omnisearch Assets ignora a caixa de diálogo de aviso **Forçar exclusão** e exclui o ativo diretamente, mesmo quando ele é referenciado no conteúdo DITA existente. (GUIDES-17232)

## Publicação

- Ao publicar um mapa DITA usando linha de base no AEM Sites (com mapeamento de componente herdado), os elementos do mapa com o atributo `processing-role = resource-only` também são publicados. (GUIDES-37649)
- Em alguns casos, a propriedade `jcr:content/fmUuidOfSource` é encontrada ausente nas páginas de saída do AEM Sites (com mapeamento de componente herdado), levando a páginas de conteúdo recém-criadas não detectáveis.
- A filtragem de conteúdo por meio de filtros DITAVal e predefinições condicionais não funcionam para a publicação do Salesforce. (GUIDES-33515)
- Não é possível criar uma predefinição do PDF nativo para um mapa se uma pasta com o mesmo nome existir em sua hierarquia de conteúdo. (GUIDES-33012)
- Quando a saída do PDF Nativo é gerada usando uma linha de base dinâmica, o termo **PDFProject** é exibido como o título do PDF em vez do título do mapa real. (GUIDES-31102)
- Gerar saída Native PDF com determinados `print` valores de atributo em referências de tópico não funciona como esperado. (GUIDES-31101)
- Quando uma pasta contendo mapas DITA é movida usando a interface do usuário do Assets ou a opção **Mover em massa**, as coleções de mapa existentes e as coleções de ativação em massa que referenciam esses mapas não são carregadas. (GUIDES-28355)
- Quando você move uma pasta contendo um mapa com predefinições de condição, as condições não são aplicadas na saída gerada após a movimentação. (GUIDES-28352)
- Ao gerar saída do AEM Sites usando o mapeamento de componente herdado, os tópicos que usam o atributo `copy-to` são publicados com o nome do tópico `copy-from` em vez do nome definido no atributo `copy-to`. (GUIDES-22155)
- Ativar um ou mais mapas DITA do **Painel de publicação em massa** gera logs excessivamente grandes. (GUIDES-20746)

## Platform

- Logs de erro gerados ao carregar um ativo por meio da interface do Assets ou ao criar um novo arquivo a partir da interface do Editor, usam incorretamente o termo `predecessor` em vez de `successor` na mensagem de log. (GUIDES-35607)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2025.11.0:

- Criar um tópico duplicado usando o atributo `copy-to` e referenciá-lo com o atributo `scope=peer` causa problemas de redirecionamento na saída do AEM Sites, onde os links são redirecionados do AEM Sites (com mapeamento de componente composto) para o AEM Sites (com mapeamento de componente herdado) e vice-versa. (GUIDES-37656)











