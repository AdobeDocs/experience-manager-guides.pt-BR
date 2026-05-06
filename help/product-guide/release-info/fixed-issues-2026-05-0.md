---
title: Notas de versão | Correção de problemas na versão 2026.05.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2026.05.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: a6b8ed1df3e10db69586686bac53cf8169cc5e02
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 0%

---

# Correção de problemas na versão 2026.05.0

Este artigo aborda os bugs corrigidos em várias áreas da versão 2026.05.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2026.05.0](whats-new-2026-05-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.05.0](upgrade-instructions-2026-05-0.md).

## Criação

- Ao selecionar uma imagem no Editor usando a caixa de diálogo **Selecionar arquivo**, somente os formatos de varredura (como JPG, PNG e GIF) são exibidos. Arquivos de vetor (como .ai e .eps) não são exibidos e não podem ser selecionados. (GUIDES-45110)
- No momento da atualização, a configuração `tagsView` é desativada por padrão, mesmo que seu valor padrão em `ui_config.json` esteja definido como `true`. (GUIDES-44651)
- No Editor, as referências de arquivo são exibidas como GUIDs em vez de caminhos de arquivo apesar da configuração `xmleditor.uuid`. (GUIDES-42438)
- Quando esquemas de assunto com valores principais semelhantes são aplicados em um tópico DITA, eles são destacados com cores quase idênticas, dificultando sua distinção e a identificação do esquema aplicado. (GUIDES-38472)
- Ao editar um mapa de esquema de assunto no modo de exibição Autor, a adição do elemento `hasInstance` aciona automaticamente a caixa de diálogo de seleção de arquivo, exigindo que os autores insiram um `href` indesejado que aponte para um ativo do AEM. Além disso, o painel **Propriedades de conteúdo** não carrega esses mapas, o que impede que os autores atualizem atributos de elementos no modo de exibição Autor e exige que eles usem o modo de exibição Source para atualizar atributos. (GUIDES-38164)
- Ao editar um arquivo `.ditaval`, qualquer comentário XML adicionado ao modo de exibição do Source é removido quando você alterna para o modo de exibição Autor e retorna ao modo de exibição do Source. (GUIDES-33228)


## Gerenciamento de ativos

- A criação de um tópico em uma pasta com espaços em seu nome cria incorretamente uma pasta duplicada em que os espaços são substituídos por hifens, e o tópico é salvo lá em vez da pasta original. (GUIDES-41938)
- Durante a primeira tradução de mapas grandes, arquivos XML vazios são criados para o idioma de destino, resultando em maior carga do servidor e desempenho mais lento. (GUIDES-41613)
- Em ambientes baseados em BD, os links DITA internos válidos aparecem como links desfeitos em **Propriedades do ativo**, mesmo que funcionem corretamente no Editor e na saída publicada. (GUIDES-35048)

## Publicação

- Quando alterações em uma predefinição de saída em um perfil de pasta são aplicadas a mapas existentes, o **Contexto de publicação** salvo para a predefinição do AEM Sites é redefinido. (GUIDES-38377)
- O símbolo de marca comercial (®) não é renderizado na página de capa da saída Native PDF quando o elemento `tm` é usado dentro do título de um mapa ou mapa. (GUIDES-28832)
- Ao publicar um mapa usando um modelo PDF Nativo, o **Título do mapa** não inclui o conteúdo dos elementos filho usados no mapa `title`, e a filtragem de conteúdo correspondente não é aplicada ao título.(GUIDES-33730)
- Os links de mesmo nível entre mapas na saída do AEM Sites não são resolvidos quando apontam para um `topicref` que usa `chunk="to-content"`. (GUIDES-37873)
- Durante a publicação, os arquivos associados à sinalização baseada em DITAVAL são movidos para uma nova pasta gerada pelo sistema, em vez de permanecerem no local relativo esperado na saída. (GUIDES-37564)
- Quando vários arquivos DITAVAL com condições conflitantes são usados, a saída PDF nativa falha. (GUIDES-37484)

## Linha de base

- As referências de tópico em um mapa são exibidas incorretamente como indiretas ao usar um DITA-OT personalizado, mesmo que sejam referenciadas diretamente. Esse problema foi resolvido com a nova experiência da linha de base. (GUIDES-19286)
- Referências com `scope="peer"` são incluídas incorretamente no contexto da linha de base, fazendo com que a publicação demore mais do que o esperado. Esse problema foi resolvido com a nova experiência da linha de base. (GUIDES-30048)

## Platform

- Quando tópicos ou mapas grandes são abertos, a instância do Autor fica sem resposta, exigindo uma reinicialização em alguns casos. (GUIDES-43547)

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

A Adobe identificou os seguintes problemas conhecidos para a versão 2026.05.0:

- Quando um mapa contém um `topicref` externo que aponta para um recurso não DITA (como `.html` ou `.htm`), sua visualização não é exibida na interface do usuário do Assets. (GUIDES-45409)
- Na interface do Assets, o conteúdo referenciado com o `conref` não é exibido para tópicos DITA, embora seja renderizado corretamente na visualização do Editor. (GUIDES-45505)<br>**Solução alternativa**: para esse conteúdo, você pode usar a visualização do Editor.
- Quando a propriedade `xmleditor.uniquefilenames` é habilitada, os novos tópicos criados usando um modelo não incluem o título do tópico. (GUIDES-44737)

