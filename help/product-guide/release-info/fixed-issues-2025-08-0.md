---
title: Notas de versão | Correção de problemas na versão 2025.08.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2025.08.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 5abe5c153d8cedc7b555d6ca82709557cc38d28f
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# Correção de problemas na versão 2025.08.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2025.08.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2025.08.0](whats-new-2025-08-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.08.0](upgrade-instructions-2025-08-0.md).

## Criação

- Os arquivos do **CSS** e do **Layout de página** nos modelos nativos do PDF exibem um comportamento de bloqueio de arquivos inconsistente, permitindo edições mesmo quando os arquivos estão bloqueados. (GUIDES-26688)
- Atualizar a página após adicionar botões personalizados ao painel esquerdo cria guias duplicadas. (GUIDES-30899)
- Quando o conteúdo XML que contém colchetes angulares (como &lt;/ ou />) é adicionado em um elemento `code block` em um tópico, o elemento de bloco de código aparece em branco na saída final. (GUIDES-31007)
- Os valores das variáveis globais `canCheckIn` e `canCheckOut` não estão sendo definidos corretamente quando é feito o check-out e o check-in de um arquivo na barra de ferramentas do Editor.(GUIDES-29890)
- Ao abrir um mapa DITA com o Unified Shell ativado, o Editor é atualizado intermitentemente.(GUIDES-26919)
- Quando um mapa DITA é selecionado na visualização de mapa, a contagem de seleção é exibida incorretamente no início, pois os nós filhos do mapa não são selecionados. A contagem de seleção correta e a inclusão de todos os nós filhos são refletidas somente na seleção subsequente. (GUIDES-25663)
- Os arquivos de marcação não são recuperados quando pesquisados no painel Repositório usando o filtro **tópico DITA**. Além disso, o **Localizar e substituir** não funciona para arquivos do Markdown e conteúdo relacionado. (GUIDES-27133)
- Não é possível personalizar a **Lista suspensa de menus** da barra de ferramentas do Editor usando a estrutura de extensão. Como resultado, não é possível ocultar ou mostrar botões existentes nem adicionar novos botões na lista suspensa Menu. (GUIDES-28748)

## Gerenciamento de ativos

- Copiar uma pasta com um grande número de ativos da interface do Assets leva a um tempo limite da API. A operação continua a ser executada no backend e é concluída após algum tempo, mas nenhuma mensagem de sucesso ou falha, ou notificação é mostrada na interface do usuário. (GUIDES-30900)
- A operação de copiar e colar executada em uma pasta na interface do usuário do Assets falha devido a erros de pós-processamento. (GUIDES-30840)
- A operação de copiar e colar falha em pastas que contêm ativos compostos (ativos com subativos) na interface do usuário do Assets. (28107)
- As pastas com um grande número de ativos não são carregadas corretamente no Repositório. (GUIDES-32500)
- Os nomes dos nós de pasta são exibidos incorretamente no lugar dos títulos das pastas no Editor. (GUIDES-32402)
- Erro ao carregar ativos com caracteres não permitidos ou proibidos nos nomes de arquivo. (GUIDES-28845)

## Publicação

- Na saída do PDF nativo, a Lista de índice (LOI) é exibida em uma ordem não alfabética e os termos de índice aninhados não são agrupados corretamente, dificultando a navegação do índice. (GUIDES-29090)
- A lista suspensa **Modelo de página de mapa** e **Modelo de página de tópico** na página predefinida de saída do mapeamento de componente do AEM Sites aparece em branco quando o caminho de destino contém uma variável com dois pontos. (GUIDES-28119)
- Quando um mapa DITA contém diferentes tipos de referências de tópico, como Conceito, Referência ou Tarefa, e é mesclado usando o atributo `chunk=to-content` para gerar saída de página única no AEM Sites com mapeamento de componente, o conteúdo não é publicado corretamente devido a erros de publicação. (GUIDES-28118)

## Linha de base

- Copiar um mapa DITA da interface do usuário do Assets também copia sua linha de base anexada para o novo mapa. (GUIDES-11227)

## Home page

- A Página inicial fica em branco quando um dos arquivos listados no widget **Arquivos recentes** é baseado em um modelo cujo modelo de origem não inclui uma miniatura. (GUIDES-31506)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2025.08.0:

- Quando um arquivo aberto no Editor é renomeado ou movido, alternar entre os modos (como **Autor**, **Visualização** e outros) atualiza o conteúdo na área de edição, mas não realça visualmente o modo ativo no canto inferior direito. (GUIDES-32719) <br> **Solução alternativa**: atualize a página para resolver o problema.
- Imagens com espaços em nomes de arquivo não são exibidas na saída quando sinalizadas usando atributos condicionais. (GUIDES-33858)
- No painel **Propriedades de conteúdo**, o campo Atributos é fechado automaticamente quando você tenta atualizar uma referência da caixa de diálogo **Atualizar link**, impedindo a atualização do link. (GUIDES-17767)



