---
title: Notas de versão | Correção de problemas na versão 2026.06.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2026.06.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 318f2b7a530e50ca4432313650801b2293d6697e
workflow-type: tm+mt
source-wordcount: '2171'
ht-degree: 0%

---

# Correção de problemas na versão 2026.06.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2026.06.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2026.06.0](whats-new-2026-06-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.06.0](upgrade-instructions-2026-06-0.md).

## Criação

- Ao alternar o foco entre os campos **Largura** e **Altura** na caixa de diálogo de propriedades de imagem usando tamanhos baseados em unidade, como `in`, `mm` ou `px`, os valores continuam aumentando de forma incremental em vez de permanecerem estáveis. (GUIDES-45929)

## Editor 2.0

- Copiar e colar `<keywords>` dentro de `<topicmeta>` dentro de `<keydef>` ou `<topicref>` faz com que as palavras-chave sejam inseridas dentro de marcas estrangeiras indesejadas. (GUIDES-45800)
- As dimensões de imagem especificadas com unidades como `mm` não são renderizadas corretamente, fazendo com que as imagens sejam exibidas em seu tamanho original em vez das dimensões especificadas. (GUIDES-46275)
- Ao executar uma operação de arrastar e soltar com a visualização de tag ativada, a seleção do conteúdo juntamente com as tags XML ou DITA parciais deixa para trás tags órfãs indesejadas, resultando em conteúdo ou visualização incorretos. (GUIDES-28191)
- Na exibição &#39;Marca&#39; de uma tabela, pressionar a tecla de seta para cima quando o cursor estiver posicionado na célula logo abaixo de uma marca de entrada recolhida salta sobre a marca recolhida e move o cursor até o início do documento. (GUIDES-45408)
- A execução de qualquer operação na barra de ferramentas contextual da tabela fecha a barra de ferramentas inesperadamente, interrompendo as operações de tabela subsequentes. (GUIDES-45405)
- Depois de usar **Inserir depois de** ou **Inserir antes de** no modo de exibição de Estrutura de Tópicos ou na navegação estrutural, o cursor se move para uma posição arbitrária em vez de dentro da marca recém-adicionada. (GUIDES-45147)
- Quando a opção **Editar MathML** é exibida incorretamente no modo somente leitura ou quando outro usuário faz check-out de um arquivo, ela permite que os usuários atualizem o conteúdo do MathML mesmo que o arquivo não seja editável. (GUIDES-45172)
- Ao excluir um comentário XML usando a tecla backspace, a tag de comentário não é removida após a exclusão do conteúdo e a operação de exclusão continua no elemento anterior. (GUIDES-45240)
- Usando a opção **Copiar Caminho** ou **Copiar UUID** para imagens, retorna o caminho de representação completo em vez do caminho do ativo original. (GUIDES-45278)
- Copiar/colar o conteúdo no mesmo tópico em um local inválido no Editor insere uma tag `<foreign>` não intencional. (GUIDES-45378)
- No Windows, copiar e colar uma linha de tabela adiciona atributos inesperados, como `data-pm-slice`, ao elemento de tabela, causando erros de marcação que impedem que o documento seja salvo. (GUIDES-45784)
- Usar a opção **Copiar** do menu de contexto em um mapa ou tópico e depois colar o conteúdo insere marcas `<data>` adicionais na saída colada. (GUIDES-45703)
- Ao arrastar uma seleção parcial de um elemento `cmd`, o conteúdo não pode ser solto entre um texto existente ou no final de outro elemento `cmd`. (GUIDES-44883)
- Ao aplicar um atributo `scale` a uma tabela, ela não é renderizada no tamanho configurado nos modos Autor e Visualização. (GUIDES-45984)
- Colar imagens copiadas de fontes externas, como Tinta ou a Ferramenta de recorte, não insere a imagem no tópico. (GUIDES-45983)
- O `keyref` usado em um título de tópico derivado de um mapa de palavra-chave não aparece no índice ou na guia de tópico após salvar, mesmo após a atualização de um navegador. (GUIDES-45799)
- Ao abrir uma tarefa de revisão no Editor usando a exibição Lado a Lado para a versão comentada, o exibe a versão como Nenhum em vez da versão associada para o tópico. (GUIDES-45127)
- Ao acessar a página Tarefa de revisão, as quebras de página entre os tópicos não são exibidas, resultando na renderização contínua das seções de conteúdo. (GUIDES-46777)
- O estilo da página de revisão não é consistente com a experiência do Novo editor, resultando em uma experiência visual inconsistente (GUIDES-46061)

## Gerenciamento de ativos

- Quando um mapa contém um `topicref` externo que aponta para um recurso não DITA (como `.html`), sua visualização não é exibida na interface do usuário do Assets. (GUIDES-45409)
- A caixa de diálogo Ferramenta de movimentação em massa estoura e não tem uma barra de rolagem quando um grande número de pastas de origem é selecionado, tornando o campo de caminho de destino e os botões de ação inacessíveis aos usuários somente com mouse. (GUIDES-45805)
- Quando um ativo é copiado da interface do Assets, recebemos uma notificação para `DXML reprocessing failure`. Essa notificação é enganosa e contribui para a confusão na caixa de entrada desde que a cópia foi bem-sucedida. (GUIDES-45012)
- Ao abrir o painel Filtro no painel esquerdo do Assets em uma pasta, o campo de pesquisa e os aspectos permanecem desativados até que o Painel seja fechado e reaberto. (GUIDES-42652)
- Os fragmentos de conteúdo e os ativos de tradução intermediários criados durante os workflows de tradução são processados involuntariamente pelo trabalho de processamento de ativos agendado, causando exceções nos registros e processamento incorreto de ativos que ainda não estão prontos. (GUIDES-42582)

## Publicação

- Ao trabalhar com arquivos `.plt` e `.css` em modelos PDF, a opção **Gerar IDs** está disponível no menu de contexto do botão direito do mouse, apesar de não ser aplicável a esses tipos de arquivos. (GUIDES-45254)
- Por padrão, o botão **Salvar** é habilitado incorretamente ao reabrir uma predefinição recém-criada do Native AEM Sites após a atualização de um navegador, mesmo quando nenhuma alteração é feita. (GUIDES-45171)
- Ao duplicar uma predefinição de PDF nativa marcada como padrão, a duplicata também é definida como a predefinição padrão. Somente uma predefinição deve ser designada como padrão de cada vez. (GUIDES-44786)
- O atributo `outputclass` não é propagado para a saída HTML ou Native PDF gerada, impedindo que classes personalizadas aplicadas a equações MathML afetem a saída renderizada. (GUIDES-44393)
- A ativação em massa da saída do AEM Sites gerada usando o novo modelo do AEM Sites estava falhando, impedindo a replicação bem-sucedida na instância de publicação. (GUIDES-44049)
- Os JARs `jackson-databind` vulneráveis (versão 2.9.8) agrupados com o AEM Guides no pacote DITA-OT são identificados. (GUIDES-43081)
- Abrir qualquer saída nativa do AEM Sites de uma coleção de mapas resulta em um erro informando que o recurso não foi encontrado, impedindo o acesso à saída gerada. (GUIDES-42065)
- O elemento `<reltable>` em um mapa DITA é ignorado durante a geração do PDF Nativo, fazendo com que &quot;Conceitos relacionados&quot;, &quot;Tarefas relacionadas&quot; e seções de referência cruzada semelhantes geradas automaticamente não apareçam na saída. (GUIDES-38333)
- Ao publicar um mapa DITA com elementos `processing-role=resource-only` no AEM Sites (com mapeamento de componente herdado), páginas de site órfãs são geradas para esses elementos em cenários adicionais, como elementos `topicgroup` e configurações de conteúdo específicas. (GUIDES-37650)
- Quando um mapa com um nome longo é adicionado a uma Coleção de mapas, a interface da coleção de mapas é renderizada em um layout distorcido. Esse problema foi resolvido com a coleção New maps. (GUIDES-42062)
- Publicação com o mecanismo Native PDF v1:
   - Ao gerar uma saída Native PDF para determinado conteúdo, somente a primeira página é renderizada no PDF, apesar do HTML intermediário que contém o conteúdo completo em várias páginas. (GUIDES-28270)
   - A ordem de leitura do conteúdo na saída nativa do PDF com as configurações de acessibilidade ativadas está incorreta. Os números de página dos rodapés são lidos antes do conteúdo principal em vez de no final. (GUIDES-27790)
   - A barra de cores na saída do PDF nativo não se alonga pela largura total da página e se sobrepõe quando o tamanho da página é personalizado, fazendo com que algumas caixas de cores fiquem ocultas. (GUIDES-15505)
   - O seletor de pseudoclasse CSS `:is()` não é respeitado na saída Nativa do PDF, resultando em diferenças de estilo em comparação à renderização do navegador. (GUIDES-11328)

  >[!NOTE]
  >
  > Os problemas acima foram resolvidos com o mecanismo nativo do PDF v2. Para obter detalhes, consulte [Trabalhar com o mecanismo PDF nativo v2](../native-pdf/new-pdf-engine.md).

## Tradução

- Aplicar uma linha de base a um mapa com muitos ativos atrasa o carregamento do relatório de tradução para o idioma selecionado, às vezes levando ao tempo limite da solicitação antes que o relatório seja renderizado. (GUIDES-45508)
- Os grupos de idiomas na guia Tradução, em Configurações do Workspace, não são retidos quando a pasta de idiomas selecionada usa um código de localidade hifenizado (por exemplo, `da-DK`) em vez de um formato de sublinhado (`da_dk`). (GUIDES-37843)

## Revisar

- A dica de ferramenta do ícone **Histórico de Versões** está ausente no painel esquerdo da interface de revisão adjacente ao nome do tópico. (GUIDES-45511)
- Ao editar uma tarefa de revisão ativa, se um tópico que já faz parte da revisão for removido e adicionado novamente sem selecionar **Atualizar**, as informações do revisor para esse tópico serão perdidas. (GUIDES-38774)
- O painel de conteúdo na interface de Revisão exibe uma barra de rolagem horizontal em determinadas resoluções de tela, incluindo a resolução de 1600 px recomendada, fazendo com que os comentários da revisão fiquem ocultos quando o conteúdo se estender além da largura do painel. (GUIDES-44082)

## Conteúdo de aprendizado

- Ao adicionar perguntas a um questionário usando a opção Inserir do banco de perguntas, as perguntas de resposta curta não são listadas, apesar de terem uma ID de pergunta válida. (GUIDES-44942)
- Ao inserir perguntas usando a opção Inserir do banco de perguntas, a caixa de diálogo Inserir do banco de perguntas cintila ou redimensiona inesperadamente ao abrir. (GUIDES-45524)
- Ao inserir perguntas usando a opção Inserir do banco de perguntas, ocorrerá um erro se o título da pergunta contiver uma imagem. (GUIDES-45383)
- A seleção de um modelo de saída SCORM resulta em um erro de aplicativo quando o título do modelo é modificado. (GUIDES-45521)
- Os arquivos de subtítulo (`.vtt`) não ficam visíveis na exibição do Repositório ou do Explorer depois de serem carregados para uma pasta. (GUIDES-46014)
- Ao carregar o conteúdo de vídeo na visualização do HTML, o caminho de origem (`src`) inclui um caminho de representação anexado, em vez de reter o caminho do arquivo original, impedindo a renderização correta do vídeo. (GUIDES-41776)
- A publicação da saída SCORM do navegador Safari resulta no download do pacote como uma pasta em vez de um arquivo zip, juntamente com problemas de renderização e funcionalidade no conteúdo gerado (por exemplo, conteúdo estendido, acordeão sem funcionamento e muito mais). (GUIDES-45119)
- Um atraso é observado antes que o botão Avançar seja ativado para os cursos, afetando a experiência de navegação do aluno. (GUIDES-45113)
- O estilo de pergunta de resposta curta é renderizado incorretamente na saída de publicação, apesar de ser exibido corretamente na pré-visualização. (GUIDES-46478)
- Ao gerar uma saída do PDF para cursos que contêm vídeos, o conteúdo do vídeo não é renderizado e somente o caminho do arquivo é exibido, em vez de uma imagem de espaço reservado, como uma miniatura de vídeo ou imagem de pôster. Esse problema foi resolvido com a habilitação da opção **Incorporar arquivos multimídia** na predefinição de saída do PDF Nativo.(GUIDES-45117)
- As pseudoclasses e os elementos CSS são renderizados em branco no Editor do guia, tornando-os invisíveis ou difíceis de ler em relação ao plano de fundo do editor. (GUIDES-45116)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2026.06.0:

## Editor 2.0

- Alternar entre os modos Source e Autor causa inconsistências no conteúdo, com partes do tópico desaparecendo ou não sendo refletidas entre os modos. (GUIDES-47432)

- Ao trabalhar com a opção Controlar alterações, rejeitar uma inserção de texto importado remove todo o conteúdo da tag, em vez de rejeitar apenas o conteúdo específico inserido. (GUIDES-48319)

- O botão **Exportar como PDF** no modo de Visualização não executa nenhuma ação quando a barra de ferramentas do editor é personalizada usando `editor_toolbar.json` em um perfil de pasta. (GUIDES-47525)

- Ao executar operações de exclusão, algumas pequenas inconsistências no movimento e na navegação do cursor podem ocorrer em mapas de imagem, elementos estruturados, tags de formatação em linha e blocos não mescláveis, ocasionalmente resultando em um comportamento inesperado de cursor ou exclusão. (GUIDES-46756)

- Usar `Ctrl+click` em um link quebrado em um Editor de mapa dispara um erro de aplicativo. (GUIDES-45544)

- Pressionar a tecla backspace no início de um parágrafo imediatamente após o conteúdo somente leitura (como um parágrafo `conref`) pode excluir ou mesclar inesperadamente o parágrafo editável, resultando na exclusão inesperada do parágrafo editável. (GUIDES-45049)

- Quando os indicadores de condição são aplicados a elementos como `bodydiv`, os indicadores sobrecarregam em tags adjacentes na Exibição de Tags Completas, resultando em renderização visual incorreta. (GUIDES-44971)

- Ao trabalhar no Editor, você não pode selecionar `keyrefs` ou chaves derivadas de mapas (incluindo entradas de glossário dentro de mapas referenciados em `term` ou `abbreviated-form` elementos), resultando em uma experiência de criação degradada. (GUIDES-45790) <br> **Solução alternativa**: você pode alterar o valor de `keyref` no painel Direito usando os valores de atributos.

- No modo de exibição de Estrutura de Tópicos, habilitar novamente **Mostrar texto** após fechar e reabrir um tópico não exibe texto com marcas de elemento. (GUIDES-48320) <br> **Solução alternativa**: habilite a opção **Mostrar texto** e reabra o tópico. Depois de reabrir, o texto é exibido corretamente junto com as tags de elemento.

- Quando uma marca embutida é renomeada usando a opção **Renomear elemento**, a navegação estrutural não é atualizada imediatamente e reflete a alteração somente depois que o cursor é movido para a marca ou quando o modo de exibição é alterado. (GUIDES-44993) <br> **Solução alternativa**: atualize o navegador após renomear a marca embutida para atualizar a navegação estrutural.

- Quando uma equação do MathML é inserida como `conref`, ela não é renderizada corretamente. (GUIDES-46601) <br> **Solução alternativa**: envolva a equação de MathML dentro de um elemento `<p>` e use esse elemento `<p>` como a origem conref.

## Revisar

- Quando uma tarefa de revisão é reatribuída a um usuário fora da equipe do projeto, o usuário pode executar ações de revisão apesar da falta de associação ao projeto, enquanto a visibilidade do revisor, o rastreamento do status de revisão e as notificações de delegação não funcionam corretamente. (GUIDES-46602)

## Publicação

- Ao publicar conteúdo com a filtragem DITAVAL, que exclui todos os itens de lista com marcadores por meio da criação de perfil condicional, a saída retém incorretamente um marcador vazio em vez de remover toda a estrutura da lista. (GUIDES-47238)

- Ao publicar uma saída de Site nativo do AEM com uma nova linha de base, a Lista de tópicos aparece em branco e não exibe os tópicos incluídos na linha de base selecionada. (GUIDES-46480) <br> **Solução alternativa**: publique a saída do Site Nativo do AEM usando a linha de base antiga, que pode ser configurada por meio do gerenciador de configurações.





