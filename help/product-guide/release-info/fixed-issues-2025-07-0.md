---
title: Notas de versão | Correção de problemas na versão 2025.07.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2025.07.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: bf8b295444a1e21fc19bfbc04efaa20fe78f71bb
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 1%

---

# Correção de problemas na versão 2025.07.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2025.07.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2025.07.0](whats-new-2025-07-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.07.0](upgrade-instructions-2025-07-0.md).

## Criação

- Quando um comentário XML é adicionado em um elemento na exibição do Source, os espaços à esquerda e à direita ao redor do comentário são perdidos ao alternar entre as exibições. (GUIDES-29781)
- As opções de multimídia não funcionam quando presentes dentro do ícone de reticências (o menu **Mais**) na barra de ferramentas. (GUIDES-29583)
- Ao criar um novo tópico por meio da interface do usuário ou do Editor do Assets, o tópico não será aberto automaticamente no Editor se a configuração `xmleditor.uniquefilenames` estiver definida como true no `XMLEditorConfig`. (GUIDES-28171)
- Os espaços adicionados em uma equação do MathML na exibição do Source não são retidos ao alternar as exibições do Editor. (GUIDES-26111)

## Gerenciamento de ativos

- Ao abrir um tópico na visualização Autor após a atualização de um navegador, as tags aplicadas anteriormente no painel Propriedades do arquivo não são mantidas e a adição de novas tags substitui as existentes, principalmente quando um grande número de tags está disponível para seleção. (GUIDES-29078)
- Ao gerar um relatório de Metadados para um mapa DITA contendo um grande número de ativos, o botão **Gerenciar** fica sem resposta ou exibe uma resposta atrasada. (GUIDES-28443)

## Revisar

- As tentativas de criar tarefas de revisão por meio do fluxo de trabalho do AEM falham consistentemente porque o nó de revisão não é criado. (GUIDES-28214)

## Publicação

- Ocorre um erro de qualidade de código ao implantar o pacote `guides-components.all-1.3.0.zip` de componentes de publicação do AEM Sites por meio do Cloud Manager. (GUIDES-28873)
- A publicação de um mapa DITA com o atributo `chunk=to-content` cria nós JCR duplicados na nova saída do AEM Sites, resultando na estrutura de conteúdo redundante no AEM Sites. (GUIDES-28104)
- Ao publicar um mapa DITA usando a nova saída do AEM Sites, se um tópico tiver o atributo `chunk =to-content` e a saída estiver definida para usar títulos de tópico como nomes de página, o nome de página gerado exibirá incorretamente a palavra **parte** em vez de reter o nome do tópico original. (GUIDES-28102)
- A propriedade `cq:template` definida no modelo de tópico do AEM Guides para a nova publicação do AEM Sites exibe um valor incorreto, afetando a estrutura do modelo e a renderização de conteúdo. (GUIDES-27789)


## Platform

- Problemas de desempenho, como tempos de carregamento mais longos e tempos limite intermitentes, são observados ao trabalhar com coleções grandes. (GUIDES-29065, GUIDES-28793)
- Vulnerabilidades associadas à biblioteca Guava obsoleta que está sendo usada nos componentes do AEM Guides carregados no Experience Manager Guides.(GUIDES-27402)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2025.07.0:

- Ao trabalhar com tópicos do Markdown, o botão **Referência de tópico** aparece na barra de ferramentas do editor, mas não funciona. (GUIDES-31038)
- Quando as pastas com nomes em maiúsculas são carregadas usando o aplicativo de desktop Adobe Experience Manager, o uso de maiúsculas e minúsculas não é mantido e os nomes são exibidos em minúsculas no Editor. (GUIDES-30909)
- Na caixa de diálogo **Mesclar**, a lista suspensa exibe incorretamente **Conteúdo principal**, em vez de mostrar as versões disponíveis do tópico selecionado. (GUIDES-30820)
- Ao abrir um mapa DITA com o Unified Shell ativado, o editor é atualizado intermitentemente.(GUIDES-26919)