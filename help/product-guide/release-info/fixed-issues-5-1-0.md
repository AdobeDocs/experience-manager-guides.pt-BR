---
title: Notas de versão | Correção de problemas na versão 5.1.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 5.1.0 do Adobe Experience Manager Guides.
source-git-commit: 64df76f371867469d738f59a174e7931176e8591
workflow-type: tm+mt
source-wordcount: '1796'
ht-degree: 0%

---

# Correção de problemas na versão 5.1.0 (setembro de 2025)

Este artigo aborda os bugs corrigidos em várias áreas da versão 5.1.0 do Adobe Experience Manager Guides.


Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 5.1.0](whats-new-5-1-0.md).

Saiba mais sobre [as instruções de atualização para a versão 5.1.0](upgrade-instructions-5-1-0.md).


## Criação

- Os arquivos do **CSS** e do **Layout de página** nos modelos nativos do PDF exibem um comportamento de bloqueio de arquivos inconsistente, permitindo edições mesmo quando os arquivos estão bloqueados. (GUIDES-26688)
- Atualizar a página após adicionar botões personalizados ao painel esquerdo cria guias duplicadas. (GUIDES-30899)
- Quando o conteúdo XML que contém colchetes angulares (como &lt;/ ou />) é adicionado em um elemento `code block` em um tópico, o elemento de bloco de código aparece em branco na saída final. (GUIDES-31007)
- Os valores das variáveis globais `canCheckIn` e `canCheckOut` não estão sendo definidos corretamente quando é feito o check-out e o check-in de um arquivo na barra de ferramentas do Editor.(GUIDES-29890)
- Quando um mapa DITA é selecionado na visualização de mapa, a contagem de seleção é exibida incorretamente no início, pois os nós filhos do mapa não são selecionados. A contagem de seleção correta e a inclusão de todos os nós filhos são refletidas somente na seleção subsequente. (GUIDES-25663)
- Os arquivos de marcação não são recuperados quando pesquisados no painel Repositório usando o filtro **tópico DITA**. Além disso, o **Localizar e substituir** não funciona para arquivos do Markdown e conteúdo relacionado. (GUIDES-27133)
- Não é possível personalizar a **Lista suspensa de menus** da barra de ferramentas do Editor usando a estrutura de extensão. Como resultado, não é possível ocultar ou mostrar botões existentes nem adicionar novos botões na lista suspensa Menu. (GUIDES-28748)
- Quando um comentário XML é adicionado em um elemento na exibição do Source, os espaços à esquerda e à direita ao redor do comentário são perdidos ao alternar entre as exibições. (GUIDES-29781)
- As opções de multimídia não funcionam quando presentes dentro do ícone de reticências (o menu **Mais**) na barra de ferramentas. (GUIDES-29583)
- Ao criar um novo tópico por meio da interface do usuário ou do Editor do Assets, o tópico não será aberto automaticamente no Editor se a configuração `xmleditor.uniquefilenames` estiver definida como true no `XMLEditorConfig`. (GUIDES-28171)
- Os espaços adicionados em uma equação do MathML na exibição do Source não são retidos ao alternar as exibições do Editor. (GUIDES-26111)
- Falha ao fechar conexões da sessão JCR ao atualizar ou criar tópicos resulta em vazamentos de memória e tempo de inatividade do serviço. (GUIDES-26282)
- Arrastar as colunas altera a largura de porcentagem para valores de pixel, o que resulta em tabelas distorcidas ou desalinhadas.(GUIDES-23128)
- Quando o conteúdo é colado em um `code block` ou quando espaços são adicionados em `code block` e a exibição é trocada, o espaçamento é perdido. (GUIDES-27478)
- Ao adicionar um mapa ao `bookmap`, ele é armazenado em `fmditatopicrefs` em vez de `fmditamaprefs`. (GUIDES-25480)
- A caixa de diálogo **Inserir imagem** não é renderizada corretamente em telas de alta resolução ou com menos zoom, fazendo com que o título da figura e os campos de texto alternativos desapareçam. (GUIDES-26459)
- A caixa de inserção de caracteres especiais no Editor não é carregada para o locale alemão. (GUIDES-24537)
- Comentários e rótulos adicionados ao salvar uma nova versão de um arquivo DITAVAL não são salvos no Histórico de versões com a nova versão. (GUIDES-24076)
- As referências de saída e de entrada em **Propriedades do arquivo** no painel direito não são atualizadas corretamente ao alternar entre arquivos de mapa. Esse problema ocorre especificamente quando os arquivos de mapa contêm um grande número de referências. (GUIDES-23344)
- O filtro Repository não retém a ordem dos filtros personalizados definidos em `ui_config.json`. (GUIDES-21193)
- A exclusão de várias linhas de texto em um elemento `codeblock` cria um espaço vazio que não pode ser removido da exibição Autor. (GUIDES-20672)
- Não é possível gerar novas IDs para elementos quando esses elementos são adicionados através de trechos ou criados através de modelos, mesmo quando a opção **gerar ID automaticamente** está habilitada em `XMLEditorConfig`. (GUIDES-21734)
- A criação de um novo ativo DITA a partir de modelos DITA copia as propriedades de replicação dos modelos DITA correspondentes. (GUIDES-25145)
- Não é possível acessar as propriedades do arquivo no painel de repositório se o nome da pasta pai incluir o caractere &quot;&amp;&quot;. (GUIDES-25762)
- Fechar um arquivo de tópico permite que ele seja salvo como uma nova versão, mesmo quando o tópico estiver bloqueado. Este problema ocorre especificamente quando a opção **Solicitar nova versão ao fechar** está habilitada em `XMLEditorConfig`. (GUIDES-23875)
- A largura máxima atual do painel do repositório oculta títulos de tópico e mapa quando a hierarquia de conteúdo está profundamente aninhada. (GUIDES-27751)

## Gerenciamento de ativos

- Copiar uma pasta com um grande número de ativos da interface do Assets leva a um tempo limite da API. A operação continua a ser executada no backend e é concluída após algum tempo, mas nenhuma mensagem de sucesso ou falha, ou notificação é mostrada na interface do usuário. (GUIDES-30900)
- A operação de copiar e colar executada em uma pasta na interface do usuário do Assets falha devido a erros de pós-processamento. (GUIDES-30840)
- A operação de copiar e colar falha em pastas que contêm ativos compostos (ativos com subativos) na interface do usuário do Assets. (GUIDES-28107)
- As pastas com um grande número de ativos não são carregadas corretamente no Repositório. (GUIDES-32500)
- Os nomes dos nós de pasta são exibidos incorretamente no lugar dos títulos das pastas no Editor. (GUIDES-32402)
- Erro ao carregar ativos com caracteres não permitidos ou proibidos nos nomes de arquivo. (GUIDES-28845)
- Ao abrir um tópico na visualização Autor após a atualização de um navegador, as tags aplicadas anteriormente no painel Propriedades do arquivo não são mantidas e a adição de novas tags substitui as existentes, principalmente quando um grande número de tags está disponível para seleção. (GUIDES-29078)
- Ao gerar um relatório de Metadados para um mapa DITA contendo um grande número de ativos, o botão **Gerenciar** fica sem resposta ou exibe uma resposta atrasada. (GUIDES-28443)
- O estado do documento da cópia de trabalho de um tópico é exibido em relação a todas as versões desse tópico na interface de Tradução e Linha de base. (GUIDES-20674)

## Revisar

- As tentativas de criar tarefas de revisão por meio do fluxo de trabalho do AEM falham consistentemente porque o nó de revisão não é criado. (GUIDES-28214)
- A exibição de documento na interface de Revisão não envolve o conteúdo para alguns tamanhos de tela, exigindo que os usuários rolem horizontalmente para visualizar o conteúdo completo. (GUIDES-25292)
- Atualizar os detalhes de uma tarefa de revisão no painel Revisão não confirma se a atualização foi bem-sucedida ou malsucedida. (GUIDES-8051)

## Tradução

- As traduções enviadas por meio do Experience Manager Guides não incluem os ativos anexados, fazendo com que o botão **Iniciar** do trabalho de tradução fique indisponível para os usuários. (GUIDES-28237)

## Publicação

- Na saída do PDF nativo, a Lista de índice (LOI) é exibida em uma ordem não alfabética e os termos de índice aninhados não são agrupados corretamente, dificultando a navegação do índice. (GUIDES-29090)
- A lista suspensa **Modelo de página de mapa** e **Modelo de página de tópico** na página predefinida de saída do mapeamento de componente do AEM Sites aparece em branco quando o caminho de destino contém uma variável com dois pontos. (GUIDES-28119)
- Quando um mapa DITA contém diferentes tipos de referências de tópico, como Conceito, Referência ou Tarefa, e é mesclado usando o atributo `chunk=to-content` para gerar saída de página única no AEM Sites com mapeamento de componente, o conteúdo não é publicado corretamente devido a erros de publicação. (GUIDES-28118)
- A publicação de um mapa DITA com o atributo `chunk=to-content` cria nós JCR duplicados na nova saída do AEM Sites, resultando na estrutura de conteúdo redundante no AEM Sites. (GUIDES-28104)
- Ao publicar um mapa DITA usando a nova saída do AEM Sites, se um tópico tiver o atributo `chunk =to-content` e a saída estiver definida para usar títulos de tópico como nomes de página, o nome de página gerado exibirá incorretamente a palavra **parte** em vez de reter o nome do tópico original. (GUIDES-28102)
- A propriedade `cq:template` definida no modelo de tópico do AEM Guides para a nova publicação do AEM Sites exibe um valor incorreto, afetando a estrutura do modelo e a renderização de conteúdo. (GUIDES-27789)
- A publicação do PDF nativo continua indefinidamente se o conteúdo DITA tiver um link da Web sem ter o escopo `external`. (GUIDES-26434)
- A publicação de PDFs nativos e sites do AEM é interrompida e colocada em fila quando há erros no conteúdo. (GUIDES-26516)
- Ao gerar páginas do site do AEM com títulos que incluem várias palavras separadas por espaços, o título do mapa exibe hifens em vez de espaços. (GUIDES-27903)
- Para o PDF Nativo, um nome de propriedade de metadados inválido não está sendo resolvido e é exibido como `unresolved property name` em **propriedades do documento**. (GUIDES-25680)
- O texto multilinha em `codeblock` causa problemas de estouro de texto durante a geração do PDF. (GUIDES-15541)
- Ao adicionar mapas à coleção de mapas, os ativos diferentes dos mapas (curtidas, tópicos etc.) são exibidos e os idiomas do mapa traduzido também não são classificados corretamente.(GUIDES-25085)
- Na saída herdada do AEM Sites, os links de seção dentro de tópicos aninhados de um mapa não são resolvidos corretamente quando definidos manualmente no modo Source ou o conteúdo é importado de uma fonte externa. Em vez de navegar até a seção desejada, eles redirecionam para o tópico principal que contém o tópico aninhado. (GUIDES-26103)
- Se o atributo `scope=external` estiver ausente em links externos em um tópico DITA, a publicação do HTML5 falhará sem indicar os arquivos em que esse atributo está ausente nos logs de erro. (GUIDES-25969)
- Não é possível incorporar links de vídeo no PDF Nativo, mesmo quando a opção **Incorporar Arquivos de Multimídia** está habilitada na predefinição do PDF. (GUIDES-9989)
- Não é possível passar as propriedades de metadados para mapear páginas de aterrissagem geradas usando a nova publicação do AEM Sites. (GUIDES-27288)

## Linha de base

- Copiar um mapa DITA da interface do usuário do Assets também copia sua linha de base anexada para o novo mapa. (GUIDES-11227)
- Ao criar uma nova linha de base com um grande número de rótulos, isso impede que todos os rótulos sejam buscados. (GUIDES-16232)

## Home page

- A Página inicial fica em branco quando um dos arquivos listados no widget **Arquivos recentes** é baseado em um modelo cujo modelo de origem não inclui uma miniatura. (GUIDES-31506)

## Platform

- Problemas de desempenho, como tempos de carregamento mais longos e tempos limite intermitentes, são observados ao trabalhar com coleções grandes. (GUIDES-29065, GUIDES-28793)
- Vulnerabilidades associadas à biblioteca Guava obsoleta que está sendo usada nos componentes do AEM Guides carregados no Experience Manager Guides.(GUIDES-27402)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 5.1.0:


- O comentário mais recente no nível da tarefa é exibido na notificação por e-mail ao iniciador da tarefa se o Revisor concluir a tarefa sem adicionar um comentário. (GUIDES-33590)
- Na caixa de diálogo Mesclar, a lista suspensa exibe incorretamente o Conteúdo principal em vez de mostrar as versões disponíveis do tópico selecionado. (GUIDES-30820)
em que o link se torna operacional. (GUIDES-30820)
- Alternar entre predefinições que usam a mesma Linha de base desativa o botão Salvar da predefinição atual. (GUIDES-28025)
- Uma linha vazia é inserida automaticamente ao colar o novo conteúdo em uma nova linha em um elemento de bloco de código.(GUIDES-27842)
- Um tópico em um mapa DITA não é publicado na saída do AEM Sites quando está sendo usado como keydef e topicref em seus submapas. (GUIDES-22269)
- No painel Propriedades de conteúdo, o campo Atributos é fechado automaticamente quando você tenta atualizar uma referência na caixa de diálogo Atualizar link, impedindo que o link seja atualizado. (GUIDES-17767)