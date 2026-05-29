---
title: Notas de versão | Problemas corrigidos no Adobe Experience Manager Guides, versão 5.2.0
description: Saiba mais sobre as correções de erros na versão 5.2.0 do Adobe Experience Manager Guides.
source-git-commit: 5eee826022f798b4eb0014ea4b97d2916eb92f33
workflow-type: tm+mt
source-wordcount: '3559'
ht-degree: 0%

---

# Correção de problemas na versão 5.2.0 (maio de 2026)

Este artigo aborda os bugs corrigidos em várias áreas da versão 5.2.0 do Adobe Experience Manager Guides.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 5.2.0](whats-new-5-2-0.md).

Saiba mais sobre as [instruções de atualização para a versão 5.2.0](upgrade-instructions-5-2-0.md).


## Criação

- Se um elemento `prop` vazio sem atributos ou valores for adicionado a um arquivo DITAVAL, elementos `prop` adicionais não poderão ser adicionados. (GUIDES-33597)
- Depois de atualizar o Experience Manager Guides para a versão 2025.08.0, a opção para habilitar ou desabilitar a guia personalizada do **Acrolinx** não aparece mais nas **configurações do Workspace**. (GUIDES-35261)
- O CSS personalizado aplicado a um perfil de nível de pasta para tópicos ou mapas é revertido para o estilo padrão no modo de Visualização após a atualização do navegador. (GUIDES-31098)
- As operações **Desfazer** e **Refazer** não funcionam como esperado na exibição Source do Editor para arquivos DITA. (GUIDES-24914, GUIDES-25034)
- Ao fazer referência a um mapa DITA em um tópico usando o elemento `Xref`, o nome do arquivo do mapa referenciado é exibido em vez do título do mapa. (GUIDES-21759)
- Ao adicionar vários arquivos do Schematron para validação por meio do painel direito da interface do Editor, um erro **Os arquivos do Schematron não existem ou apresentam erros** é exibido mesmo se os arquivos adicionados forem válidos e não tiverem erros. (GUIDES-33731)
- Equações de MathML grandes ou complexas não são exibidas no Editor. (GUIDES-29095)
- Quando vários mapas DITA ou tópicos são abertos e um dos tópicos é fechado, o botão **>>**, que mostra todas as guias abertas, é sobreposto às guias abertas restantes na barra de guias. (GUIDES-31421)
- Com o **fluxo de trabalho de aprovação** habilitado, o botão **Iniciar uma Nova Versão** não ficará visível na barra de ferramentas do Editor se o painel Esquerdo e o painel Propriedades de conteúdo estiverem abertos. (GUIDES-29093)
- Quando os nomes dos trechos excedem a largura do painel, eles são quebrados incorretamente na próxima linha, resultando em sobreposição com trechos adjacentes e afetando a legibilidade. (GUIDES-22685)
- Quando você adiciona a mesma referência várias vezes a um mapa DITA, a exibição **Mapa** exibe o título somente para a última ocorrência, enquanto as anteriores mostram a UUID da referência. (GUIDES-9699)
- Os arquivos DITAVAL permanecem editáveis, mesmo quando são bloqueados por outro usuário ou quando o servidor tem a opção **Desativar edição sem bloquear o arquivo** habilitada e o arquivo é aberto no modo somente leitura. (GUIDES-27754)
- Os logs de nós ausentes estão sendo gerados de trabalhos de limpeza interna que não são necessários e são marcados incorretamente como erros, resultando em arquivos de log desorganizados. (GUIDES-31765)
- Ao editar um arquivo do Esquematron (`*.sch`) e usar o recurso Localizar e substituir, o painel Localizar e substituir aparece parcialmente fora da tela na parte inferior, impedindo o acesso aos campos e controles de entrada. (GUIDES-38412)
- Não é possível adicionar vários **rótulos de versão** a um tópico da caixa de diálogo **Salvar como nova versão**. (GUIDES-32716)
- Ao selecionar uma imagem no Editor usando a caixa de diálogo **Selecionar arquivo**, somente os formatos de varredura (como JPG, PNG e GIF) são exibidos. Arquivos de vetor (como .ai e .eps) não são exibidos e não podem ser selecionados. (GUIDES-45110)
- No momento da atualização, a configuração `tagsView` é desativada por padrão, mesmo que seu valor padrão em `ui_config.json` esteja definido como `true`. (GUIDES-44651)
- No Editor, as referências de arquivo são exibidas como GUIDs em vez de caminhos de arquivo apesar da configuração `xmleditor.uuid`. (GUIDES-42438)
- Quando esquemas de assunto com valores principais semelhantes são aplicados em um tópico DITA, eles são destacados com cores quase idênticas, dificultando sua distinção e a identificação do esquema aplicado. (GUIDES-38472)
- Ao editar um mapa de esquema de assunto no modo de exibição Autor, a adição do elemento `hasInstance` aciona automaticamente a caixa de diálogo de seleção de arquivo, exigindo que os autores insiram um `href` indesejado que aponte para um ativo do AEM. Além disso, o painel **Propriedades de conteúdo** não carrega esses mapas, o que impede que os autores atualizem atributos de elementos no modo de exibição Autor e exige que eles usem o modo de exibição Source para atualizar atributos. (GUIDES-38164)
- Ao editar um arquivo `.ditaval`, qualquer comentário XML adicionado ao modo de exibição do Source é removido quando você alterna para o modo de exibição Autor e retorna ao modo de exibição do Source. (GUIDES-33228)
- Ao atualizar uma equação de MathML em linha usando a opção Editar MathML do menu de contexto, o valor atualizado não é refletido até que a página seja atualizada. (GUIDES-38198)
- Quando um tópico contém muitos elementos reutilizáveis (aqueles com IDs) adicionados no painel Reutilizável, alguns elementos podem não estar acessíveis devido à altura fixa do contêiner. (GUIDES-37220)
- Ao inserir uma referência cruzada a um arquivo, os ícones de mapas e tópicos são idênticos. (GUIDES-36662)
- Ao editar um mapa, símbolos especiais em `navtitle` não são exibidos para `topichead` no modo de exibição Autor. (GUIDES-35435)

## Gerenciamento de ativos

- Ao fazer upload novamente de uma imagem editada por meio da interface do Experience Manager Guides, a representação original da imagem é atualizada, mas o conteúdo DITA associado continua a exibir a versão anterior da imagem. (GUIDES-33693)
- Ao tentar mover duas ou mais pastas do local de origem para um local diferente (usando a Ferramenta de movimentação em massa), a operação falhará se os nomes das pastas começarem com a mesma cadeia de caracteres (por exemplo, Product e ProductImages). (GUIDES-29096)
- A exclusão de um ativo pesquisado da interface do usuário do Omnisearch Assets ignora a caixa de diálogo de aviso **Forçar exclusão** e exclui o ativo diretamente, mesmo quando ele é referenciado no conteúdo DITA existente. (GUIDES-17232)
- Não é possível remover rótulos de versão do painel **Histórico de versões** na interface do usuário do Assets. (GUIDES-38276)
- A criação de um tópico em uma pasta com espaços em seu nome cria incorretamente uma pasta duplicada em que os espaços são substituídos por hifens, e o tópico é salvo lá em vez da pasta original. (GUIDES-41938)
- Durante a primeira tradução de mapas grandes, arquivos XML vazios são criados para o idioma de destino, resultando em maior carga do servidor e desempenho mais lento. (GUIDES-41613)
- Na pesquisa do Assets, os nós de subativos e metadados (como imagens e PDFs) são incluídos incorretamente nos resultados. Além disso, para uma predefinição de saída quando os filtros DITAVAL são aplicados, a pesquisa retorna arquivos DITAVAL gerados internamente a partir de predefinições de condição. (GUIDES-35418)
- Ao carregar ativos com nome de arquivo contendo caracteres inválidos, o ativo não é carregado e exibe uma mensagem incorreta **O arquivo está bloqueado por outro usuário** apesar de o ativo estar desbloqueado. (GUIDES-32680)

## Publicação

- Ao publicar um mapa DITA usando linha de base no AEM Sites (com mapeamento de componente herdado), os elementos do mapa com o atributo `processing-role = resource-only` também são publicados. (GUIDES-37649)
- Em alguns casos, a propriedade `jcr:content/fmUuidOfSource` é encontrada ausente nas páginas de saída do AEM Sites (com mapeamento de componente herdado), levando a páginas de conteúdo recém-criadas não detectáveis. (GUIDES-34242)
- A filtragem de conteúdo por meio de filtros DITAVal e predefinições condicionais não funcionam para a publicação do Salesforce. (GUIDES-33515)
- Não é possível criar uma predefinição do PDF nativo para um mapa se uma pasta com o mesmo nome existir em sua hierarquia de conteúdo. (GUIDES-33012)
- Quando a saída do PDF Nativo é gerada usando uma linha de base dinâmica, o termo **PDFProject** é exibido como o título do PDF em vez do título do mapa real. (GUIDES-31102)
- Gerar saída Native PDF com determinados `print` valores de atributo em referências de tópico não funciona como esperado. (GUIDES-31101)
- Quando uma pasta contendo mapas DITA é movida usando a interface do usuário do Assets ou a opção **Mover em massa**, as coleções de mapa existentes e as coleções de ativação em massa que referenciam esses mapas não são carregadas. (GUIDES-28355)
- Quando você move uma pasta contendo um mapa com predefinições de condição, as condições não são aplicadas na saída gerada após a movimentação. (GUIDES-28352)
- Ao gerar saída do AEM Sites usando o mapeamento de componente herdado, os tópicos que usam o atributo `copy-to` são publicados com o nome do tópico `copy-from` em vez do nome definido no atributo `copy-to`. (GUIDES-22155)
- Ativar um ou mais mapas DITA do **Painel de publicação em massa** gera logs excessivamente grandes. (GUIDES-20746)
- Ao gerar PDFs, as regras de filtragem em um arquivo DITAVAL serão ignoradas se qualquer nome de propriedade contiver um ponto. (GUIDES-33229)
- A publicação do Salesforce exibe um status de sucesso na interface do usuário mesmo quando um mapa DITA contendo um elemento `topichead` não publica os tópicos nele. (GUIDES-32143)
- Para a predefinição de saída do HTML5, a funcionalidade de filtro de pesquisa não está funcionando no AEM Assets para a filtragem DITAVAL, pois os arquivos correspondentes não são exibidos quando o filtro DITAVAL é selecionado. (GUIDES-28231)
- Ao gerar um PDF Nativo para um mapa DITA com vários tópicos, se qualquer tópico contiver um elemento `fig` em um `figgroup` junto com um `title`, o título `figgroup` será renderizado incorretamente como um título de capítulo no Índice. (GUIDES-23223)
- Ao duplicar modelos do PDF da interface do usuário, a UUID também é duplicada, fazendo com que os arquivos de modelo sejam excluídos e resultando em saídas incorretas do PDF. (GUIDES-30456)
- Ao gerar o PDF Nativo para um mapa DITA, o título do elemento `example` é renderizado como nível de cabeçalho `h1`, resultando em inconsistência visual e estrutura de índice inadequada. (GUIDES-19958)
- Quando o mesmo tópico é reutilizado em vários mapas com diferentes predefinições condicionais, a publicação do mapa mais recente no Salesforce substitui o conteúdo do tópico, resultando na exibição de dados incorretos para os usuários de mapas publicados anteriormente. (GUIDES-37806)
- Ao publicar um PDF nativo para um mapa que inclui processamento condicional ou certos mapas aninhados, o `dc:title` definido no mapa falha ao aparecer na capa do PDF, resultando em um título de capa ausente. (GUIDES-37733)
- Gerar a saída do site do AEM (usando o mapeamento de componente composto) para um mapa falha e resulta em erro quando a variável `map_title` está presente no caminho de saída. (GUIDES-36968)
- Quando um caminho de saída com uma barra à direita é especificado na predefinição de saída nativa do PDF, a interface do usuário anexa automaticamente uma barra à direita adicional, resultando em um caminho de barra dupla que faz com que o upload do PDF falhe em determinados cenários. (GUIDES-34932)
- Publicar páginas do AEM Sites geradas de conteúdo DITA por meio da Publicação rápida ou Gerenciar publicação publica involuntariamente os ativos DITA associados. (GUIDES-27967)
- Ao publicar um mapa no AEM Sites (usando o mapeamento de componente herdado), as referências cruzadas (`xrefs`) com `scope = peer` que direcionam subelementos de um tópico (como parágrafos) em um mapa diferente não resolvem a ID de elemento específica e resolvem somente o tópico pai, fazendo com que a página seja carregada no início do tópico, em vez de rolar até a seção desejada. (GUIDES-21802)
- Ao publicar um mapa DITA usando linha de base no AEM Sites (com mapeamento de componente herdado), os elementos do mapa com o atributo `processing-role = resource-only` também são publicados. (GUIDES-34298)
- Quando alterações em uma predefinição de saída em um perfil de pasta são aplicadas a mapas existentes, o **Contexto de publicação** salvo para a predefinição do AEM Sites é redefinido. (GUIDES-38377)
- O símbolo de marca comercial (®) não é renderizado na página de capa da saída Native PDF quando o elemento `tm` é usado dentro do título de um mapa ou mapa. (GUIDES-28832)
- Ao publicar um mapa usando um modelo PDF Nativo, o **Título do mapa** não inclui o conteúdo dos elementos filho usados no mapa `title`, e a filtragem de conteúdo correspondente não é aplicada ao título.(GUIDES-33730)
- Os links de mesmo nível entre mapas na saída do AEM Sites não são resolvidos quando apontam para um `topicref` que usa `chunk="to-content"`. (GUIDES-37873)
- Durante a publicação, os arquivos associados à sinalização baseada em DITAVAL são movidos para uma nova pasta gerada pelo sistema, em vez de permanecerem no local relativo esperado na saída. (GUIDES-37564)
- Quando vários arquivos DITAVAL com condições conflitantes são usados, a saída PDF nativa falha. (GUIDES-37484)
- Ao criar ou editar um tópico que inclua uma citação, se o campo Autor não for adicionado à caixa de diálogo de citação, a PDF não será gerada. (GUIDES-37934)
- Ao gerar a saída do AEM Sites, os títulos de mapa que contêm palavras-chave e títulos de tópico com o elemento `<ph>` não são incluídos na saída publicada. (GUIDES-36641)
- O arquivo CSS (`rhdefault.css`) é aplicado incorretamente ao modelo PDF apesar de nenhum CSS ser referenciado, causando a ausência de logs de erro do arquivo CSS.(GUIDES-31752)
- Ao baixar arquivos temporários para um mapa com uma linha de base durante a publicação de uma predefinição, o arquivo `metadata.xml` faz referência incorretamente a `versionPath` em vez de `dampath`.(GUIDES-29815)
- Para a saída Native PDF, o elemento `<alt>` para imagens é ignorado, impedindo que o texto alternativo seja aplicado para acessibilidade. (GUIDES-29087)
- Na saída do PDF Nativo, o elemento `abbreviated-form` exibe o `glossterm` em vez do `glossSurfaceForm` ou `glossAcronym` designado. (GUIDES-26393)
- Ao executar a ativação em massa, a criação de pacote adiciona filtros para todos os caminhos listados na propriedade `fileReference` de uma página, incluindo caminhos externos e de mesmo nível. (GUIDES-24887)
- Ao publicar usando uma predefinição personalizada com conteúdo que contenha links para PDFs sem o escopo definido como externo, o processo não é concluído. (GUIDES-21708)
- A publicação do Salesforce falha com um erro de aplicativo, quando já existe um tópico com o mesmo nome e URL. (GUIDES-32390)
- A hifenização automática não está sendo aplicada na saída do PDF Nativo, mesmo quando a configuração **Usar hifenização automática** está habilitada para a predefinição de saída. (GUIDES-19703)

## Tradução

- Ao ampliar a tela da interface de tradução, o botão **Enviar para tradução** fica abaixo das reticências e é habilitado mesmo sem que nenhum ativo seja selecionado. (GUIDES-33720)
- Ao selecionar arquivos com o status **Fora de sincronização** na interface de tradução e a largura da tela estiver restrita devido à abertura dos painéis Esquerdo e Direito, o rótulo **Enviar para tradução** fica truncado. (GUIDES-33692)
- Quando uma imagem gerenciada inicialmente como um ativo específico de idioma com uma versão específica (por exemplo, em `/en/`) é movida para uma pasta global com uma versão atualizada e a exportação da linha de base é executada, a nova linha de base continua a fazer referência a versões desatualizadas específicas de idioma dessa imagem, resultando em uma falha na exportação da linha de base. (GUIDES-39394)
- Ao processar projetos de tradução criados fora do Experience Manager Guides, várias mensagens de log de erros são geradas informando que a propriedade *`fmTarget`não foi encontrada*. (GUIDES-37804)

## Linha de base

- Ao criar uma linha de base dinâmica, o Editor às vezes não responde devido a várias solicitações de API simultâneas, fazendo com que todas as outras operações travem. (GUIDES-39054)
- As referências de tópico em um mapa são exibidas incorretamente como indiretas ao usar um DITA-OT personalizado, mesmo que sejam referenciadas diretamente. Esse problema foi resolvido com a nova experiência da linha de base. (GUIDES-19286)
- Referências com `scope="peer"` são incluídas incorretamente no contexto da linha de base, fazendo com que a publicação demore mais do que o esperado. Esse problema foi resolvido com a nova experiência da linha de base. (GUIDES-41823)


## Revisar

- Ao atribuir um usuário a uma tarefa de revisão, a lista suspensa lista todos os usuários em vez de apenas aqueles associados aos projetos selecionados, resultando em opções de usuário inválidas. (GUIDES-37781)
- Quando um revisor conclui uma tarefa de revisão ou o iniciador atualiza a tarefa de revisão sem inserir comentários, o email de notificação enviado exibe o comentário anterior mais recente. (GUIDES-33590)

## Relatórios

- Ao abrir um Relatório para um mapa, há um atraso no carregamento do painel Filtros (GUIDES-39385)
- O relatório Lista interrompida está incluindo incorretamente links externos, `keyrefs` válidos e palavras-chave que são resolvidas corretamente dentro do escopo do mapa atual. (GUIDES-27774)

## Platform

- Logs de erro gerados ao carregar um ativo por meio da interface do Assets ou ao criar um novo arquivo a partir da interface do Editor, usam incorretamente o termo `predecessor` em vez de `successor` na mensagem de log. (GUIDES-35607)
- Usar `scope="external"` para uma referência ao conteúdo DAM em um tópico ou mapa faz com que o caminho relativo do ativo seja substituído por um GUID. (GUIDES-38783)
- Quando um tópico contém um grande número de referências vinculadas a pastas com muitos arquivos, a instância do Autor pode ficar lenta ou sem resposta, em alguns casos exigindo uma reinicialização da instância. (GUIDES-43547)
- Ao tentar salvar um tópico ou mapa, a operação pode falhar intermitentemente com um erro **Falha ao salvar arquivo**, especialmente durante tarefas de processamento intensivo de ativos ou fluxos de trabalho de tradução em execução em segundo plano. (GUIDES-37837)


## Problemas resolvidos disponíveis com o Editor 2.0

Os seguintes problemas foram corrigidos e não ocorrem mais ao usar o Editor 2.0 (também conhecido como Novo editor):

- Quando duas ou mais colunas são excluídas de uma tabela, a estrutura da tabela se torna inconsistente ou corrompida. (GUIDES-35438)
- Quando uma coluna é excluída de uma tabela que contém células mescladas, uma nova coluna em branco é adicionada. (GUIDES-30147)
- Quando uma nova linha é inserida em uma tabela existente no menu de navegação estrutural, a estrutura da tabela é alterada inesperadamente, resultando em bordas ausentes e em uma coluna extra. (GUIDES-29194)
- Na visualização Autor, copiar e colar uma linha de tabela coloca o conteúdo fora da tabela em vez de inseri-la como uma nova linha dentro da tabela. (GUIDES-24372)
- Quando um elemento de seção selecionado usando a função de arrastar com o mouse no modo Autor é copiado e colado, ele é convertido em elementos do parágrafo `(<p>)` em vez de reter a estrutura de seção. (GUIDES-30023)
- Quando o texto realçado dentro de elementos como step ou uicontrol é editado, o texto selecionado não é substituído corretamente e, em vez disso, é anexado ou anexado, resultando em erros de validação. (GUIDES-24371)
- Quando a largura de uma coluna da tabela é definida usando valores relativos, as colunas restantes não se ajustam proporcionalmente, causando um layout de tabela desalinhado. (GUIDES-26109)
- Quando um título de tópico copiado é colado com tags desativadas, a primeira colagem aplica um estilo incorreto e atribui o tipo nas Propriedades de conteúdo como tópico em vez de título. (GUIDES-28838)
- Quando grandes seções de conteúdo são editadas, o movimento de rolagem não intencional faz com que a visualização do Editor saia do conteúdo ativo. (GUIDES-35436)
- Quando Backspace é usado em elementos, o Editor rola para a parte superior do tópico, independentemente da posição do cursor. (GUIDES-32520)
- Quando a tecla de seta para a esquerda ou para a direita é usada para sair das tags integradas, o cursor salta inesperadamente na primeira tentativa. (GUIDES-26363)
- O AEM Spellcheck funciona somente para o idioma padrão en-US e não respeita outras localidades. (GUIDES-14731)
- Quando grandes tópicos DITA são desbloqueados no Editor, o mesmo tópico é reaberto em uma guia duplicada. Além disso, um aviso de limite de tags é acionado onde `NaN` é exibido, em vez da contagem real de tags. (GUIDES-34008)
- As sugestões do Acrolinx não são realçadas corretamente no Editor para tópicos somente leitura ou bloqueados. (GUIDES-29614)
- Ao criar uma nova `reltable` sem uma linha de cabeçalho no modo de exibição Autor, o layout da tabela muda após a adição de um tópico à primeira célula, fazendo com que a próxima coluna seja reduzida e dificultando a inserção de tópicos relacionados. (GUIDES-19555)
- Quando um link `xref` é adicionado a uma pequena célula da tabela no modo Autor, o link não fica contido na célula e é exibido em células adjacentes na mesma linha. (GUIDES-5489)
- Ao alternar da visualização Autor para Source, a posição do cursor não é mantida e o Editor rola de volta para o topo. Além disso, em tópicos longos, a posição do cursor é perdida e salta aleatoriamente para o meio ou para o topo ao alternar entre as visualizações Autor e Source. (GUIDES-18114, GUIDES-21164)
- Pressionar *Enter* dentro de um elemento `<li>` cria um novo `<li>`, mas navegar de volta para um `<li>` anterior e pressionar *Enter* converte incorretamente o conteúdo do item atual em um elemento `<p>`, quebrando a estrutura da lista. (GUIDES-27505)

## Problemas conhecidos

### Criação

- Ao carregar imagens sinalizadas em arquivos DITAVAL, as imagens são quebradas após a atualização de um navegador quando a configuração `Enable UUIDs` é desabilitada. (GUIDES-45853)
- No Editor, os arquivos `.ditval` e `.md` se tornam não editáveis quando o *Fluxo de Trabalho de Aprovação* está habilitado. (GUIDES-42037)
- Se você selecionar um tópico no modo de Visualização, ele não será destacado na exibição de Mapa se o tópico estiver dentro de tags de mapa (frente, capítulo, parte ou massa) ou de conteúdo cíclico. (GUIDES-42416)
- Quando um arquivo é aberto no Editor e no painel Pesquisar, excluí-lo do painel Explorer remove o arquivo e atualiza a lista do Explorer, mas atualizar a página continua exibindo o arquivo no painel Pesquisar. (GUIDES-41935)

### Gerenciamento de ativos

- Na interface do usuário do Assets, o botão **Mover** não é habilitado na primeira tentativa quando mais de 2 arquivos ou pastas são selecionados. (GUIDES-42721) <br> **Solução alternativa**: depois de selecionar mais de dois arquivos ou pastas, aguarde alguns segundos antes de selecionar a pasta de destino.

### Revisar

- Ao atualizar uma tarefa de revisão ativa, se um tópico que já faz parte da revisão for removido e adicionado novamente sem clicar em Atualizar, as informações do(s) revisor(es) na guia Revisores serão perdidas. (GUIDES-38774)
- Quando um tópico em revisão é removido de uma tarefa de revisão em andamento, seu estado do documento continua a ser **Na revisão**, mesmo que o tópico não faça mais parte de nenhuma tarefa de revisão. (GUIDES-38709)<br>**Solução alternativa**: altere o estado do documento do tópico de **Em Revisão** para o estado apropriado na página Propriedades ou no painel Propriedades do arquivo.

### Editor 2.0

- Copiar/colar o conteúdo no mesmo tópico em um local inválido no Editor insere uma tag externa não intencional. (GUIDES-45378)
- Copiar e colar `<keywords>` dentro de `<topicmeta>` dentro de `<keydef>` ou `<topicref>` insere marcas estrangeiras não intencionais. (GUIDES-45800)
- Quando o conteúdo é copiado de um mapa ou tópico usando a opção Copiar no menu de contexto e, em seguida, colado, `<data>` tags adicionais inesperadas são inseridas no conteúdo colado. (GUIDES-45703)
- No Windows, copiar e colar uma linha de tabela adiciona atributos indesejados à tabela, resultando em erros de marcação e impedindo que o documento seja salvo. (GUIDES-45784)
- Arrastar a seleção ao redor de uma tabela ou uma tabela simples não funciona como esperado. (GUIDES-45406)
- Colar imagens de fontes externas não as insere no tópico. (GUIDES-45983)
- O conteúdo MathML referenciado por meio de `conref` não é renderizado corretamente. (GUIDES-46601)
- A renderização de atributo incompleta para elementos MathML e SVG interrompe as classes CSS personalizadas e a manipulação de atributo de condição. (GUIDES-46371)
- As equações MathML encapsuladas dentro das marcas `foreign` e `equation-block` introduzem espaços indesejados e interrompem o comportamento de edição. (GUIDES-46606)
- Arrastar e soltar um elemento que contenha uma referência de chave converte o `keyref` em um caminho absoluto. (GUIDES-45701)
- No Editor de mapa, `Ctrl+click` em um link quebrado dispara um erro de aplicativo. (GUIDES-45544)
