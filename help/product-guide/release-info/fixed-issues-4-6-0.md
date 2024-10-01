---
title: Notas de versão | Correção de problemas na versão 4.6.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 4.6.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: 17c3d945cb2a2faab1e361385a95e1de5a790a96
workflow-type: tm+mt
source-wordcount: '1970'
ht-degree: 0%

---


# Correção de problemas na versão 4.6.0 (setembro de 2024)


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.6.0 do Adobe Experience Manager Guides.


Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 4.6.0](whats-new-4-6.md).

Saiba mais sobre [as instruções de atualização para a versão 4.6.0](../release-info/upgrade-instructions-4-6-0.md).

## Criação  

- A opção **Localizar** não está funcionando na exibição **Source**. 18610)
- Os ícones **Check-out** e **Check-in** aparecem juntos quando `autocheckout` está configurado no xmleditor. (18088)
- Os mapas DITA grandes são carregados lentamente e demoram para alternar para a exibição **Layout**.  (17590)
- Erros de IDs de imagem duplicadas nos tópicos impedem que o usuário salve ou crie um tópico. (17528)
- A operação de copiar e colar de tópicos acima de 15 KB falha com um erro inesperado. (17171)
- A funcionalidade para alterar o estado do documento do painel **Propriedades do Arquivo** não está funcionando corretamente e muda para o estado *Rascunho*. (17088)
- Ao alterar as configurações do editor XML usando um perfil de pasta personalizado, o `ui_config.json` é atualizado com um arquivo incorreto. (17011)
- Os painéis de conteúdo reutilizáveis não listam elementos quando as **Preferências do usuário** estão definidas para exibir arquivos por **Nome do arquivo**. (16896)
- Os subelementos no elemento de título da tabela não são renderizados no modo de **Visualização** do Experience Manager Guides. (16691)
- **Caracteres especiais** gravados com caracteres de escape são removidos do tópico após serem carregados no Experience Manager Guides. (16495)
- Os vídeos do Vimeo não são compatíveis com a funcionalidade de tela cheia no Experience Manager Guides. (15996)
- Colar longas sequências de texto pré-formatadas em elementos `<pre>` ou `<codeblock>` resulta em texto truncado. (15859)
- A exclusão de conteúdo ocorre devido a GUIDs duplicados quando os modelos são instalados por meio de código, mas permanecem não processados. (15858)
- A Experience Manager Guides não adere ao atributo **Função de Processamento** no modo **Visualização**. (15787)
- O Editor exclui intermitentemente texto extra além da área selecionada. (15708)
- Incapacidade de copiar e colar tabelas grandes de documentos do Word ou HTML no Editor da Web. (15369)
- Falta de APIs ou eventos para capturar a adição de atributo a um elemento ou a inserção de um novo elemento. (15351)
- Incapacidade de adicionar a marca `<data>` dentro da marca `<ol>` no Editor da Web. (15161)
- O componente de espaço reservado **Element** faz com que a interface do usuário congele. (14957)
- O Editor da Web não pode carregar arquivos .pptx. (14837)
- Ao localizar um texto no Editor da Web, o cursor retorna à primeira ocorrência do texto pesquisado, pressionando a tecla Enter. (14820)
- O salvamento automático causa vários problemas, reposiciona o cursor e requer cliques manuais no documento. (14253)
- Pressionar a tecla **Enter** em uma célula de tabela dentro do texto não divide o parágrafo conforme esperado. (14251)
- Arquivos grandes não são carregados no Editor da Web e fazem com que o navegador congele. (13227)
- Os resultados da pesquisa são desabilitados após a abertura de um arquivo encontrado por meio do **Localizar e Substituir** global. (12142)
- Na exibição de origem, `</conbody>` é ocasionalmente inserido em locais incorretos. (11305)
- O caminho do componente `/libs/fmdita/components/versions` está codificado e os usuários não podem sobrepô-lo. (8779)
- `<conref>` para um tópico referenciado em um mapa DITA não está sendo refletido na visualização no editor. (17794)
- O Guia DITA do Experience Manager não aciona a função Salvar após o uso do recurso de recuo automático. (16482)
- O recurso de dica de ferramenta falha ao atualizar o campo Source no Editor XML. (15847)
- O recurso **Compartilhar link de UUID** não está funcionando para as imagens no Adobe Experience Manager. (15598)
- No modo de exibição **Autor**, ocorre um problema de copiar e colar ao usar espaços não separáveis, o que resulta em excesso de texto. (15541)
- Problemas de texto sobrepostos ocorrem nas marcas `<reltable>` e `<fig>`. (15238)
- Problemas de cintilação ocorrem no painel **Atributos**. (15237)
- No elemento `<othermeta>` em `<topicmeta>`, ao adicionar um `<conref>` a outro mapa DITA, a ID do mapa também é anexada junto com a ID do elemento. (15226)
- O cursor salta entre os elementos de bloco ao excluir um caractere ou palavra dentro do conteúdo. (15224)
- A mensagem de erro &quot;Check-out de arquivo&quot; é exibida incorretamente ao editar arquivos que são movidos de outra guia, quando os tokens expiram ou quando o usuário está desconectado. (15223)
- O `<conref>` não pode ser atualizado do painel **Atributos** ao fazer alterações. (15209)
- A célula inteira é selecionada ao selecionar uma imagem em uma célula de tabela. (15188)
- O painel **Atributos** não é exibido no modo de exibição Source do Editor da Web. (14387)
- `<Topicref>` adicionado usando `<keyref>` não é exibido no PDF nativo. (1974)
- Espaços indesejados e não separáveis são adicionados durante a edição no final de uma tag no Editor da Web. (11786)
- O conteúdo é excluído ao corrigir os erros de ortografia em arquivos DITA. (11610)
- Abrir um tópico DITA ou mapa em uma nova guia para edição congela a navegação de seleção na interface do Assets. (4992)
- A exclusão de nós de revisão interrompe a capacidade de abrir e exibir comentários no Adobe Experience Manager Guides. (15366)
- A versão DITA exibe incorretamente o nome de usuário na interface do usuário do Assets. 17580)
- O elemento `<title>` é adicionado automaticamente quando o elemento `<fig>` é inserido como um trecho. (18562)
- Ocorrem problemas ao carregar um grande número de arquivos com conjuntos de dados densos para a Experience Manager Guides.(17008)
- O Editor da Web não exibe a palavra-chave correta por padrão, especialmente se a palavra-chave for definida de forma diferente em mapas secundários. (14748)
- O **Estado do Documento** não é exibido ao editar as propriedades de mais de 50 arquivos em massa na exibição de Mapa do Editor da Web. (14574)
- O comportamento do botão Fechar é inconsistente ao usar a funcionalidade de Salvamento automático. (10996)
- Problemas de validação ocorrem em elementos MathML ao inserir qualquer novo elemento ou modificar equações. (10624)
- A funcionalidade Controlar alterações não funciona com texto que começa com caracteres coreanos. (14538)



## Publicação

- A referência cruzada para a chave não está sendo resolvida na saída de PDF nativo. (18087)
- O erro **duplicate_value** ocorre intermitentemente ao republicar um artigo existente no Salesforce. (17932)
- A validação da conexão do Salesforce falha com o URL do lightning. (17797)
- Ao selecionar a opção **Usar metadados adicionados ao topicmeta**, as propriedades de metadados não são propagadas nas propriedades do documento da saída de PDF nativo.(17283)
- A filtragem de condição na saída de PDF nativo não está funcionando como esperado em comparação ao DITA-OT. (17095)
- O índice não respeita as tags `<sub>` ou `<sup>` na saída de PDF nativo. (17028)
- A vinculação de mapa cruzado não exibe todos os mapas principais nas configurações de contexto de publicação para um link que tem o `scope="peer"`. (16700)
- A geração de sites de AEM e a API de publicação incremental não estão funcionando como esperado. (16666)
- Falha na geração de saída do Site AEM quando a opção **Excluir Site Órfão** está habilitada. (15896)
- Os atributos antigos são mantidos nas **Predefinições de condição** ao adicionar ou remover atributos novos ou existentes. (15890)
- Na saída JSON, os metadados do mapa DITA ou dos tópicos não são propagados para os arquivos de saída JSON. (15713)
- O conteúdo da linguagem RTL não é manipulado corretamente na saída de publicação PDF nativo. (15709)
- A publicação de PDF nativo falha quando a predefinição é renomeada. (15662)
- A propriedade **sourcePath** está incorreta na saída do site AEM publicada. (15502)
- A seleção e a personalização de variáveis de idioma não estão funcionando corretamente na Predefinição de saída de PDF nativo. (15399)
- A geração de PDF nativo falha ao usar uma folha de estilos grande ou modelo de layout. (15344)
- O conteúdo não é renderizado corretamente na saída publicada se `<conref>` for usado com um caminho absoluto. (15222)
- A redução de URL do AEM Sites não está funcionando devido a conflitos entre `fmdita rewriter` e `ResourceResolver`. (14793)
- A geração de PDF nativo falha com um erro relacionado à obtenção de dependências para Node.js. (14445)
- Os atributos **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** e **chunk=&quot;to-content&quot;** aparecem independentemente na saída do AEM Sites. (14442)
- `<Conref>` não é resolvido no modo `Preview` do Editor da Web e da saída PDF nativa. (17827)
- No PDF nativo, os tópicos DITA aninhados são exibidos incorretamente no índice. (16742)
- As miniaturas geradas pelo **Dynamic Media** para arquivos de vídeo não persistem na saída publicada. (15656)
- O PDF referenciado não é ativado no **Painel do Publish em massa** durante a Ativação em massa do conteúdo publicado. (17793)
- Se uma pasta que contém mapas 2k estiver definida no caminho da pasta dentro de qualquer perfil de pasta, as alterações aplicadas à predefinição de saída falharão. (14852)
- A regeneração de tópico falha devido à falha da API de publicação incremental ou de Regeneração de Tópico OOTB. (18452)
- A predefinição de condição não busca atributos atualizados após a atualização do Experience Manager Guides. (18174)
- As referências de conteúdo não serão resolvidas corretamente para a saída de PDF nativo se o arquivo que contém as definições de chave não estiver na mesma pasta que o mapa DITA. (15062)


## Gerenciamento


- A conversão do InDesign em DITA tem um caminho de configuração codificado, de modo que os arquivos de configuração personalizados não são escolhidos. (16891)
- **Resolvedores de Recursos** não fechados causam um aumento na contagem de sessões e `PathNotFoundException` erros após a versão 4.3.1 do Experience Manager Guides. (15604)
- Erro ao instalar pacotes do Guides em repositórios grandes. (15160)
- A criação de uma linha de base usando a API Java não funciona com o Experience Manager Guides. (14787)
- A API `/bin/fmdita/import` permanece presa na solicitação pendente indefinidamente quando os ativos de carregamento excedem 500 MB. (14743)
- A edição de uma linha de base existente e a seleção de uma versão específica aciona erros de aplicação. (14451)
- Falha na execução do script postprocess devido à exceção **FileNotFoundException**. (16517)
- Títulos dinâmicos com `<conkeyref>` não aparecem na lista de tópicos do Relatório. (16967)
- As contagens imprecisas de **Lista de Tópicos** ocorrem na interface do usuário dos Relatórios do Experience Manager Guides devido às propriedades sem patch ao copiar ativos DITA. (15529)
- Tópicos contendo referências externas com %20 na URL exibem referências de arquivo corrompidas. (15347)
- As propriedades fmditaMaprefs e fmditakeydefrefs exibem caminhos relativos, apesar de definir caminhos absolutos para o mapa e os tópicos DITA. (18353)
- O caminho para a funcionalidade de sobreposição é codificado para o arquivo de idioma coreano e não está selecionado corretamente. (17089)
- O horário padrão na criação de Linha de Base no Editor da Web é exibido como 00:00 em vez do horário atual. (15215)

## Revisar

- Se a contagem de usuários exceder 25, a busca da lista de usuários ao criar uma tarefa de revisão falhará. (17329)
- Os tópicos de revisão não aparecem na ordem correta. (16319)
- No Editor da Web, o painel Revisão é carregado lentamente. (14680)
- Os revisores não podem adicionar, realçar ou riscar espaços ao executar uma revisão de documento no Experience Manager Guides. (14752)
- Quando um usuário atualiza uma tarefa de Revisão, nem todos os revisores atribuídos recebem uma notificação sobre a atualização. (9496)

## Tradução

- As referências de ativos traduzidos não são atualizadas. 18086)
- Não é possível criar projetos XLIFF com tradução humana. (16964)
- O título com `<conref>` ou `<conkeyref>` não é resolvido nos painéis Linha de Base e Tradução do Editor da Web. (16961, 16879)
- Os projetos de tradução não conseguem adicionar novos trabalhos de idioma ao Adobe Experience Manager 6.5 SP18 com a versão 4.3.1 do Experience Manager Guides. (15398)
- **Aceitar tradução** falha ao concluir a tradução de arquivos temporários. (14665)
- Adicionar um tópico atualizado em um projeto de tradução ativo resulta em um tópico duplicado e o processo falha. (7688)
- As referências não são filtradas corretamente como Diretas ou Indiretas ao serem traduzidas para vários idiomas. (17891)
- A tradução baseada em XLIFF falha com erro para usuários &quot;Não administradores&quot;.(17296)
- O título dos arquivos traduzidos é revertido para o inglês após a segunda tradução, mesmo que o conteúdo tenha sido traduzido. (15200)
- Ao selecionar um projeto de tradução com o **Status da tradução** como **Em andamento**, uma página incorreta será aberta. (13248)
- Os projetos de tradução criados selecionando a opção **Criar estrutura somente** não têm UUIDs atribuídos. (18980)


## Problemas conhecidos

O Adobe identificou os seguintes problemas conhecidos para a versão 4.6.0:
- Abrir uma predefinição do **AEM Sites** (não herdada) marca o tópico como sujo.
- O painel selecionado não está sendo retido na atualização do navegador da guia **Saída**.
- Não é possível arrastar e soltar tópicos entre dois `topicrefs` na exibição **Autor**.
- A filtragem de condição aplicada na predefinição não está sendo aplicada via **Baixar como PDF**.
- A geração de um único tópico a partir do painel de mapa gera todos os tópicos selecionados na predefinição do **AEM Sites** (não herdado).
- A referência do tópico aparece quebrada na interface do usuário quando inserida na barra de ferramentas superior do mapa DITA.
- A geração de PDF nativo falha para um mapa DITA se houver referências ausentes.
- Depois que o estado do documento de um tópico for atualizado para **Concluído**, o ícone **Iniciar uma Nova Versão** só estará disponível no modo **Visualizar** do tópico.
- Ao selecionar um arquivo DITA na interface do usuário do Assets, a opção **Abrir no FrameMaker** é exibida, mesmo que esteja desabilitada nas definições de configuração.




