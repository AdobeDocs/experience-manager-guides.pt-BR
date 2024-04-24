---
title: Notas de versão | Novidades nos Guias da Adobe Experience Manager, versão 2024.2.0
description: Saiba mais sobre os recursos novos e aprimorados da versão 2024.2.0 do Adobe Experience Manager Guides as a Cloud Service.
exl-id: 234d430a-d775-484a-aea8-6e422b0a01eb
source-git-commit: b1bb2b9da71bf0551fe40c84ac382df0e78e007b
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 0%

---

# Novidades da versão 2024.2.0

Este artigo aborda os recursos novos e aprimorados da versão 2024.2.0 dos Guias do Adobe Experience Manager.

Para obter a lista de problemas corrigidos nessa versão, consulte [Correção de problemas na versão 2024.2.0](fixed-issues-2024-2-0.md).


Saiba mais sobre [instruções de atualização da versão 2024.2.0](upgrade-instructions-2024-2-0.md).



## Sugestões inteligentes habilitadas por IA para adicionar referências de conteúdo durante a criação de conteúdo

Agora, você pode aprimorar sua jornada de criação com as Sugestões inteligentes, um novo recurso baseado em IA no Editor da Web. Enquanto você cria seu conteúdo, esse recurso inteligente fornece sugestões em tempo real para referências de conteúdo, melhorando seu fluxo de trabalho, adicionando precisão e garantindo uma eficiência inigualável.


Para manter o conteúdo correto e consistente, a pesquisa e as sugestões estão limitadas ao conteúdo de propriedade da organização e correspondem estreitamente às palavras-chave que você pesquisa.

![Painel de sugestões inteligentes no Editor da Web ](assets/web-editor-smart-suggestion.png) {width="800" align="left"}


*Exiba as Sugestões inteligentes para localizar e adicionar referências de conteúdo correspondentes a partir do seu repositório de conteúdo.*

Você também pode comparar o conteúdo atual com conteúdo semelhante nos outros tópicos. Em seguida, você pode selecionar facilmente as partes do conteúdo de vários tópicos e adicioná-las como referências de conteúdo ao tópico atual. Adicionar as referências de conteúdo torna as atualizações mais gerenciáveis, especialmente em projetos de documentação maiores. Por exemplo, você está criando um folheto sobre os recursos mais recentes do seu produto. Nesse caso, você pode adicionar rapidamente as especificações atualizadas como referências de conteúdo dos documentos de recursos relacionados.

Usar esse recurso inteligente reduz o esforço manual de pesquisa de conteúdo relacionado e ajuda você a se concentrar na criação de novo conteúdo.  Também ajuda a manter a consistência e também facilita uma melhor colaboração em equipe.

Saiba mais sobre [Sugestões inteligentes habilitadas por IA para criar conteúdo](../user-guide/authoring-ai-based-smart-suggestions.md).

## Recurso de histórico de versão remodelado no Editor da Web

Agora, os Guias do Experience Manager fornecem um recurso aprimorado de histórico de versões que permite comparar as alterações feitas em um documento ao longo do tempo. Na nova visualização lado a lado, é possível comparar facilmente o conteúdo e os metadados da versão atual com qualquer versão anterior do mesmo documento. Também é possível exibir os rótulos e comentários das versões comparadas. Como administrador, você pode controlar os metadados da versão do tópico e seus valores a serem exibidos no **Histórico da versão** caixa de diálogo.

![Caixa de diálogo Histórico de versão](assets/version-history-dialog-web-editor.png){width="800" align="left"}
*Visualizar as alterações nas diferentes versões de um tópico.*


Saiba mais sobre o **Histórico da versão** descrição do recurso na [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS) seção.

## Experiência do usuário aprimorada no painel Tradução

A variável **Tradução** foi melhorado.  É possível exibir a **Idiomas disponíveis** e selecione rapidamente o local em que deseja traduzir o projeto. Com uma única seleção, você também pode escolher **Selecionar tudo** para traduzir o projeto para todos os idiomas disponíveis.

![painel tradução](assets/translation-languages-4.4.png){width="300" align="left"}

*Selecione os códigos de idiomas nos quais deseja traduzir o projeto. Escolha o padrão, a linha de base ou a versão mais recente dos arquivos para tradução.*

Saiba como [traduzir conteúdo](../user-guide/translation.md).


## Lógica de pesquisa aprimorada na caixa de diálogo Inserir elemento

Agora é possível encontrar facilmente os elementos na caixa de diálogo Inserir elemento.  Você pode digitar uma string na caixa de pesquisa e obter uma lista de todos os elementos válidos que começam com a string inserida.

Por exemplo, ao editar um parágrafo em que você deseja inserir um elemento, é possível pesquisar um caractere &quot;t&quot; para obter todos os elementos válidos que começam com &quot;t&quot;.


![Caixa de diálogo Inserir](assets/insert-element.png){width="300" align="left"}

*Digite um caractere para procurar todos os elementos válidos que começam com o caractere.*


Para obter mais detalhes, consulte **Inserir elemento** descrição do recurso na [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS) seção.


## Capacidade de dividir a lista atual e iniciar com um novo item de lista no mesmo nível

Agora, você pode dividir facilmente sua lista no Editor da Web. Selecione o **Dividir lista** opção do menu de contexto de um item de lista para dividir a lista atual. Uma nova lista é criada no mesmo nível, começando com o item de lista selecionado para a divisão.

![painel tradução](assets/context-menu-split-list.png){width="300" align="left"}

*Selecione a opção para dividir a lista atual.*

Para obter mais detalhes, consulte **Inserir lista** descrição do recurso na [Painel esquerdo](../user-guide/web-editor-features.md#id2051EA0M0HS) seção.

## Acessar propriedades de arquivo no modo de criação de origem

Agora você pode acessar o painel direito **Propriedades do arquivo** nos quatro modos ou exibições: Layout, Autor, Origem e Visualização.  Isso ajuda a visualizar as propriedades do arquivo, mesmo quando você alterna entre os diferentes modos.

Para obter mais detalhes, consulte **Propriedades do arquivo** descrição do recurso na [Painel direito](../user-guide/web-editor-features.md#id2051EB003YK) seção.

## Capacidade de publicar várias predefinições de saída com linhas de base dinâmicas em paralelo

Experience Manager fornece o recurso para criar linhas de base ao selecionar automaticamente os tópicos de acordo com o rótulo aplicado a eles. Agora, você também pode publicar facilmente várias predefinições de saída com linhas de base automáticas do mesmo mapa DITA. Não é necessário publicar apenas uma predefinição por vez, mas é possível publicar facilmente várias predefinições de saída em paralelo.


## Aprimoramentos de PDF nativo

Os seguintes aprimoramentos do PDF nativo foram feitos na versão 2024.2.0:

### Passar metadados de ativos para a saída do PDF

O Experience Manager agora fornece a capacidade de passar as propriedades de metadados dos ativos do mapa DITA para a saída do PDF.
Na predefinição de saída PDF nativo, é possível escolher os metadados que deseja transmitir ao processo de publicação PDF. Você pode selecionar as propriedades personalizadas e padrão.  As propriedades de metadados selecionadas são passadas para o arquivo de PDF gerado usando o PDF nativo.

Esse recurso é útil, pois ajuda a manter as propriedades do ativo, como autor, data de criação ou título de documento consistente. Isso facilita a organização, pesquisa e categorização de documentos.

Para obter mais detalhes, consulte **Avançado** configurações no [Publicar saída de PDF](../web-editor/native-pdf-web-editor.md).


### Usar metadados adicionados no `topicmeta` elemento para a saída de PDF

O recurso de metadados na publicação de PDF nativo ajuda na gestão de conteúdo e na pesquisa de arquivos na Internet.
<img src="assets/pdf-metadata-4-4.png" alt="guia metadados" width="800">

*Selecione uma opção para adicionar e personalizar opções de metadados.*

Agora, os Guias do Experience Manager oferecem a opção para usar os metadados adicionados no `topicmeta` elemento do mapa DITA para preencher os campos de metadados da saída do PDF. Essa opção é selecionada por padrão.

Esse recurso ajuda no melhor gerenciamento de documentos, garante a consistência e torna os documentos pesquisáveis.

Para saber mais, veja o **Metadados** na guia [Publicar saída de PDF](../web-editor/native-pdf-web-editor.md).
