---
title: Notas de versão | Correção de problemas na versão Adobe Experience Manager Guides 4.4.0
description: Saiba mais sobre as correções de erros na versão 4.4.0 do Adobe Experience Manager Guides
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
TQID: https://experienceleague.adobe.com/0mdTs2Pg1Zos-Y-jMaYUEasFRhyF2kzl6Sz8MBisJ5Q
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1439
ht-degree: 5%

---

# Correção de problemas na versão 4.4.0 (janeiro de 2024)


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.4.0 do Adobe Experience Manager Guides.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 4.4.0](./whats-new-4-4.md).

Saiba mais sobre [as instruções de atualização para a versão 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Criação

- A verificação ortográfica no Editor não permite a seleção de sugestões. (15045)
- O botão de navegação global não está funcionando e o painel não é carregado. (14968)
- No Editor da Web, o recurso de mapa de download não aciona uma notificação pop-up quando está pronto para download. (14626)
- No Editor da Web, o recurso de download de mapa falha ao baixar um mapa com linha de base. (14622)
- Erro de DTD inválido no Experience Manager Guides. (14482)
- O título na guia Editor da Web é truncado após um ponto (.) caractere. (14372)
- As mensagens de erro para nomes de mapa duplicados na interface do Assets não são atualizadas. (14320)
- Ocorre um erro na lógica de criação de versão durante a ação de arrastar e soltar ativos. (14291)
- O conteúdo reutilizável ignora as IDs do elemento. (14213)
- O controle de configuração para ocultar o painel **Variáveis de Idioma** na guia **Saída** está ausente. (14194)
- O Editor da Web lança erros de aplicativo ao adicionar uma nova referência ou tópico usando um esquema especializado na exibição **Layout**. (14094)
- O espaço após o elemento conref `<ph>` desaparece ao salvar o tópico. (13642)
- Ocorre um erro de aplicativo ao tentar salvar arquivos DITA antes que o pós-processamento seja concluído. (13571)
- Um link de âncora para o elemento `<dlentry>` ou `<dt>` não exibe o texto do link. (13543)
- Falha ao carregar a coleção **Favoritos** no Editor da Web. (13495)
- Se o título de um tópico contiver uma barra `/`, a guia no Editor da Web mostrará apenas as letras que vêm após ele. (13455)
- A visualização da imagem não desaparece após ser exibida no Editor da Web. (13454)
- As citações exibem links não clicáveis quando criadas com uma ID exclusiva com espaços. (13447)
- Ao fechar um tópico após editá-lo, você é redirecionado para a Página inicial do AEM em vez de retornar à exibição de pasta. (13306)
- O pop-up Inserir palavra-chave não é exibido ao usar chaves definidas pelo mapa raiz em outros tópicos. (12950)
- Os ícones de fechamento não ficam visíveis quando gráficos muito altos são visualizados no painel **Histórico de Versão**. (12867)
- Não é possível modificar o fuso horário da coluna **Versão Criada em** para as Linhas de Base. (12711)
- Os arquivos Zip não são reconhecidos no Editor da Web, e você não pode arrastá-los e soltá-los. (12709)
- O painel **Histórico de Versão** na interface do usuário do Assets mostra um carimbo de data/hora incorreto para o campo **Atual**. (12624)
- Na exibição de **Layout** de um Bookmap, usar **Mover para a Direita** para transformar um capítulo selecionado em um subelemento não funciona. (12567)
- Criar um arquivo DITA a partir de um modelo com um nome de arquivo começando com caracteres numéricos resulta em um erro de namespace. (12188)
- A configuração de mapa de roteiro persiste no Editor da Web mesmo que o usuário não o tenha definido explicitamente nas **Preferências do usuário**. (11551)
- O conteúdo com alguns atributos aplicados não está sendo realçado no modo **Author** ou **Preview**. (11063)
- No Editor da Web, a janela **Referências de Chave** é aberta ao inserir a marca `varname`. (10940)
- Arrastar um tópico de glossário do repositório para um mapa de glossário cria `topicref`. (10767)
- A janela Visualização do editor XML está truncada nos navegadores Google Chrome e Microsoft Edge. (10755)
- O Editor da Web não tem a capacidade de envolver um elemento dentro dos possíveis elementos principais. (8791)
- O Editor da Web é desinstalado após a reinstalação do Adobe Experience Manager Guides versão 4.3.1. (14519)
- O instalador da versão 4.3.1 encontrou um conflito de filtro, resultando na substituição de `apps/cq/core/content/projects/properties`. (14517)
- Um link de autorreferência aparece na lista de **Links quebrados** em Relatórios. (13539)
- A tela de visualização de trechos está congelada. (14840)
- Os caracteres quebrados aparecem ao criar os trechos no idioma coreano. (13489)

## Publicação

- A publicação do AEM Sites falha e causa erros de escopo para arquivos com `xref` para o arquivo DITA que começam com &quot;HTTP&quot;. (15154)
- Na publicação do PDF nativo, as propriedades de metadados do mapa DITA não podem ser usadas para preencher os metadados para saída de arquivo do PDF. (15159)
- Na publicação do PDF nativo, os atributos personalizados nas predefinições de condição não funcionam na publicação do PDF nativo. (14943)
- Não é possível adicionar um modelo personalizado da guia **Saídas** no Editor. (14846)
- A predefinição **Site do AEM** não está funcionando devido a um caminho de modelo vazio. (14804)
- A regeneração do site do AEM falha para mapas DITA com tópicos que contêm equações do MathML. (14790)
- Na publicação do PDF Nativo, a geração de PDF gera erros ao obter dependências para a publicação `Node.js`. (14445)
- A predefinição **Site do AEM** não permite a seleção de um modelo fora da hierarquia `/content` no Editor da Web. (14260)
- A funcionalidade de publicar como fragmento de conteúdo não está funcionando para os arquivos listados nos resultados da pesquisa. (14090)
- Os componentes da Fmdita têm um caminho codificado de `delegator.jsp`, impedindo a sobreposição de componentes do AEM Sites. (13993)
- A exibição marcada do reator do PDF na saída de publicação nativa do PDF não está funcionando como esperado. (13622)
- Na publicação do PDF Nativo, a seleção da cor do plano de fundo no layout **Modelo** requer um recarregamento de página ao reverter para `None`. (13621)
- A publicação do site do AEM encontra um problema ao confirmar no armazenamento de dados para mapas grandes com links de mesmo nível de escopo. (13531)
- Problema ao confirmar o armazenamento de dados de um mapa DITA grande com links de pares de escopo na publicação do Site do AEM. (13530)
- Ícone e dica de ferramenta incorretos são exibidos para a opção **Editar conteúdo** na barra de ferramentas **Layouts de Página** dos Modelos usados na publicação do PDF Nativo. (13492)
- Não é possível ativar um site usando o **Painel de publicação em massa** do Experience Manager Guides. (13439)
- Na publicação do PDF nativo, a acessibilidade é comprometida, pois as imagens no cabeçalho e no rodapé não exibem texto alternativo. (12829)
- Na saída do AEM Sites, o estilo ou as quebras de linha foram perdidas para o elemento `<lines>` com subelementos.(12542)
- A duplicação do layout de página no PDF nativo não funciona sem uma extensão adicionada automaticamente. (12534)
- A localização dos rótulos dos elementos não está funcionando corretamente na saída do AEM Sites. (12144)
- Os metadados personalizados não estão disponíveis na saída final. (12116)
- `fmdita rewriter` entra em conflito com a configuração de reescrita do usuário e leva à exibição de URLs longas em vez de links. (12076)
- Opção **ditaval** ausente em predefinições de saída em nível de perfil de pasta criadas pela interface do usuário do Editor da Web. (11903)
- Na predefinição **Site do AEM**, a opção para **Gerar PDF separada para cada tópico** não é funcional. (11555)
- A publicação nativa do PDF não é compatível com a conversão de espaço de cores CMYK. (10754)
- Ao atualizar para a versão 4.3.1, ocorrem algumas exceções no nó PDF nativo. (14492)
- Ao gerar a saída do PDF com a publicação nativa do PDF, o nome do arquivo é truncado após um ponto. (13620)


## Gerenciamento

- A referência de conteúdo é quebrada ao copiar e colar os arquivos DITA com links de autorreferência sem GUID. (13540)
- Os arquivos do **Filtro de Linha de Base** não estão funcionando com o Nome de Arquivo no Editor da Web. (13486)
- No Editor da Web, a linha de base mostra o título da versão anterior em vez da versão selecionada do arquivo DITA. (13444)
- Desabilitar a indexação do mapa DITA principal para obter um melhor desempenho pode afetar a funcionalidade de determinados recursos.(12213)
- As predefinições de condição para mapas DITA grandes não estão sendo criadas. (10936)
- Não é possível editar as predefinições dos primeiros mapas da coleção ao editar uma coleção de mapas. (10649)
- Os rótulos do arquivo `labels.json` aparecem em ordem aleatória no Editor da Web. (10508)
- As chamadas de linha de base dinâmicas estão usando o nome em vez do título, o que resulta na falha da opção Exportar API de mapa DITA. (14268)

## Revisar

- O menu de contexto de clique com o botão direito do mouse não funciona para **Aceitar** ou **Rejeitar** alterações de controle. (14607)
- Alternar para fechar tópicos DITA na Tela de revisão não funciona na versão 4.3.1 do Adobe Experience Manager Guides. (14537)
- Problemas de simetria ocorrem nos painéis de revisão lado a lado das versões anterior e atual no Editor da Web. (14156)
- A personalização de modelos de email para fluxo de trabalho de revisão não funciona com sobreposição. (13954)
- Os anexos coreanos na tela Revisão da Experience Manager Guides não são clicáveis. (13436)
- O título do mapa é cortado na tela de revisão e colaboração, sem a opção de visualizar o título completo. (13012)

## Tradução

- Os botões **Aceitar/Rejeitar** aparecem erroneamente para tradução humana aprovada automaticamente. (14318)
- Problemas de internacionalização (i18n) ocorrem durante a transformação de arquivos DITA em outros idiomas para páginas do AEM. (14286)
- A aprovação automática às vezes não funciona, e ocorrem exceções se um valor incorreto for definido em **Status da tradução**. (13607)
- A linha de base exportada do painel Tradução falha e não abre no idioma de destino. (12993)
- O conteúdo traduzido não é sincronizado dos projetos de tradução temporários, e o assistente de tradução do editor XML DITA mostra incorretamente o status **Em andamento** para trabalhos aprovados. (9938)

## Problema conhecido

A Adobe identificou o seguinte problema conhecido para a versão 4.4.0:

- A versão 1.0 não é exibida na interface do usuário do arquivo DITA duplicado.
