---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 5.2.0 Service Pack 3
description: Saiba mais sobre as correções de erros na versão 5.2.0 Service Pack 3 do Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: a3144f0078b2073289043befacc5e2358b9c0e02
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%
---
# Correção de problemas na versão 5.2.0 do Service Pack 3 (novembro de 2026)

Este artigo aborda os bugs corrigidos em várias áreas da versão 5.2.0 Service Pack 3 do Adobe Experience Manager Guides.

Saiba mais sobre [as instruções de atualização para o 5.2.0 Service Pack 3 versão](upgrade-instructions-5-2-0-sp3.md).

## Editor 2.0

- Copiar uma tabela do modo Autor e colá-la no modo Autor remove atributos como `colwidth` e quaisquer outros atributos definidos em `colspec`, causando a perda das configurações de largura da coluna. (GUIDES-52916)
- Quando uma tabela é colada do Microsoft Word, as células da linha de cabeçalho são criadas, mas seu conteúdo é perdido. (GUIDES-49847)
- Quando o código é colado em um elemento `codeblock`, do Microsoft Word ou de editores de texto similares, usando Ctrl+V, quebras de linha e espaços à esquerda são perdidas e o código é nivelado em uma única linha. (GUIDES-33247)

## Gerenciamento de ativos

- A API de status do ativo não retorna o status correto para ativos cujo caminho contém uma vírgula. (GUIDES-49065)

## Publicação

- Ao publicar um mapa DITA com elementos `processing-role=resource-only` no AEM Sites (com mapeamento de componente herdado), páginas de site órfãs são geradas para esses elementos em cenários adicionais, como elementos `topicgroup` e configurações de conteúdo específicas. (GUIDES-37650)
- A filtragem de ramificação gera páginas extras para tópicos indesejados usados como `keydef` (que são marcados `resource-only ="true"` por DITA-OT). (GUIDES-19701)
- No painel de Mapa, selecionar uma predefinição diferente aciona uma chamada para buscar links de colegas, resultando em processamento adicional. (GUIDES-53703)
- Na saída do PDF Nativo, referências de tópico marcadas com o atributo `toc="no"` ainda são incluídas no índice, resultando em um índice longo e confuso. (GUIDES-20156)
- Em alguns casos, quando um mapa DITA completo é gerado e publicado no AEM Sites usando uma linha de base dinâmica, determinados tópicos são publicados com versões anteriores ou não aprovadas em vez das versões aprovadas atuais. (GUIDES-55646)
- Ao processar um grande número de ativos, o `PurgePresetExecutionDataJob` às vezes encontra um `RuntimeNodeTraversalException` sem tratamento, fazendo com que o trabalho fique preso em um loop infinito e gere logs excessivos. (GUIDES-53897)
- Na saída do PDF Nativo, o atributo `outputclass` definido em um elemento `topichead` ou `topicgroup` não é aplicado ou transportado para a seção PDF resultante. (GUIDES-22950)
- Em alguns casos, ao publicar com o mecanismo Native PDF v1, a ordem de leitura do conteúdo com acessibilidade `settingsenabled` está incorreta. Os números de página dos rodapés são lidos antes do conteúdo principal em vez de no final.(GUIDES-27790)


## Tradução

- Aplicar uma linha de base a um mapa com muitos ativos atrasa o carregamento do relatório de tradução para o idioma selecionado, às vezes levando ao tempo limite da solicitação antes que o relatório seja renderizado. (GUIDES-45508)
- Os grupos de idiomas na guia Tradução, em Configurações do Workspace, não são retidos quando a pasta de idiomas selecionada usa um código de localidade hifenizado (por exemplo, `da-DK`) em vez de um formato de sublinhado (`da_dk`). (GUIDES-37843)
- Iniciar uma tradução usando um projeto XLIFF cria um projeto vazio que nunca é movido para um estado em andamento. (GUIDES-51759)
- A configuração `propagateVersionLabel` no perfil de pasta global é redefinida intermitentemente para `false` quando um usuário somente com a função de Colaborador acessa o Editor. (GUIDES-51870)

## Linha de base

- A seleção de linha de base salva de uma predefinição é exibida incorretamente como *Nenhuma Linha de Base* após a exclusão da linha de base ou enquanto uma linha de base dinâmica ainda estiver sendo criada. (GUIDES-52690)
- Em alguns casos, as linhas de base dinâmicas permanecem presas no estado de processamento após uma recriação com falha, fazendo com que a geração de exportação e saída use tópicos desatualizados e versões de mapa sem exibir nenhum erro. (GUIDES-56739)

## Revisar

- Em cenários envolvendo um grande número de tarefas de revisão, abrir o painel Revisão ou aplicar um filtro de projeto demora mais do que o esperado para carregar a lista de tarefas. (GUIDES-48893)
- O painel de conteúdo na interface de Revisão exibe uma barra de rolagem horizontal em determinadas resoluções de tela, incluindo a resolução de 1600 px recomendada, fazendo com que os comentários da revisão fiquem ocultos quando o conteúdo se estender além da largura do painel. (GUIDES-44082)

## Platform

- A API de movimentação, a API de renomeação e a interface do usuário do Assets impedem que um ativo DITA seja renomeado com um nome de arquivo baseado em GUID para um nome de arquivo legível. O Assets agora pode ser renomeado para nomes de arquivo legíveis por humanos. No entanto, renomear um nome de arquivo baseado em GUID para outro nome de arquivo baseado em GUID ainda não é permitido. (GUIDES-43006, GUIDES-59684)
- Quando um ativo não DITA, como uma imagem, que foi migrado de uma configuração não UUID para uma configuração UUID é revertido ou ramificado para outra versão, sua UUID é alterada. As referências existentes ao ativo não são mais resolvidas e a imagem aparece quebrada nos tópicos que fazem referência a ele. (GUIDES-58414)
- A instalação do Service Pack do Experience Manager Guides remove ferramentas externas instaladas anteriormente, como ACS Commons, da seção **Ferramentas** do AEM. (GUIDES-60365)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 5.2.0 Service Pack 3:

- Após a instalação do service pack, a validação do Schematron pode falhar com uma exceção `NoClassDefFoundError` e não é possível salvar tópicos no Editor. (GUIDES-60062)<br>**Solução alternativa:** atualize o pacote `com.adobe.fmdita.schematron-wrapper` do Console da Web do AEM (`/system/console/bundles`).
