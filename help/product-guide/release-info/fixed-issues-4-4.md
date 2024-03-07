---
title: Notas de versão | Correção de problemas na versão 4.4.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 4.4.0 dos Guias do Adobe Experience Manager
role: Leader
source-git-commit: 8f8075b205725a55b93286c804b879353b4d965d
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Correção de problemas na versão 4.4.0 (janeiro de 2024)


Este artigo aborda os bugs corrigidos em várias áreas da versão 4.4.0 dos Guias do Adobe Experience Manager.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades da versão 4.4.0](./whats-new-4-4.md).

Saiba mais sobre [instruções de atualização da versão 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Criação  

- A verificação ortográfica no Editor não permite a seleção de sugestões. (15045)
- O botão de navegação global não está funcionando e o painel não é carregado. (14968)
- No Editor da Web, o recurso de mapa de download não aciona uma notificação pop-up quando está pronto para download. (14626)
- No Editor da Web, o recurso de download de mapa falha ao baixar um mapa com linha de base. (14622)
- Erro de DTD inválido nos guias de Experience Manager. (14482)
- O título na guia Editor da Web é truncado após um ponto (.) “?”. (14372)
- As mensagens de erro para nomes de mapa duplicados na interface do usuário do Assets não foram atualizadas. (14320)
- Ocorre um erro na lógica de criação de versão durante a ação de arrastar e soltar ativos. (14291)
- O conteúdo reutilizável ignora as IDs do elemento. (14213)
- O controle de configuração a ser ocultado **Variáveis de idioma** painel em **Output** guia ausente. (14194)
- O Editor da Web emite erros de aplicação ao adicionar uma nova referência ou tópico usando um esquema especializado na **Layout** exibição. (14094)
- O espaço após conref `<ph>` O elemento desaparece ao salvar o tópico. (13642)
- Ocorre um erro de aplicativo ao tentar salvar arquivos DITA antes que o pós-processamento seja concluído. (13571)
- Um link de âncora para `<dlentry>` ou `<dt>` falha do elemento ao exibir o texto do link. (13543)
- A variável **Favoritos** falha ao carregar a coleção no Editor da Web. (13495)
- Se o título de um tópico contiver uma barra `/`, a guia no Editor da Web mostra apenas as letras que vêm após ela. (13455)
- A visualização da imagem não desaparece após ser exibida no Editor da Web. (13454)
- As citações exibem links não clicáveis quando criadas com uma ID exclusiva com espaços. (13447)
- Ao fechar um tópico após editá-lo, você é redirecionado para a página inicial do AEM em vez de retornar à visualização de pastas. (13306)
- O pop-up Inserir palavra-chave não é exibido ao usar chaves definidas pelo mapa raiz em outros tópicos. 12950)
- Os ícones de fechamento não ficam visíveis quando gráficos muito altos são visualizados no **Histórico da versão** painel. (12867)
- Não é possível modificar o fuso horário de **Versão criada em** para as Linhas de Base. (12711)
- Os arquivos Zip não são reconhecidos no Editor da Web, e você não pode arrastá-los e soltá-los. (12709)
- A variável **Histórico da versão** O painel na interface do usuário do Assets mostra um carimbo de data e hora incorreto para o **Atual** campo. (12624)
- No **Layout** exibição para um Bookmap, uso **Mover para a direita** para tornar um capítulo selecionado um subelemento não funciona. (12567)
- Criar um arquivo DITA a partir de um modelo com um nome de arquivo começando com caracteres numéricos resulta em um erro de namespace. (12188)
- A configuração de mapa de raiz persiste no Editor da Web mesmo se o usuário não a tiver definido explicitamente no **Preferências do usuário**. (11551)
- O conteúdo com alguns atributos aplicados não está sendo realçado em **Autor** ou **Visualizar** modo. (11063)
- No Editor da Web, a variável **Referências principais** é aberta ao inserir a variável `varname` tag. (10940)
- Arrastar um tópico de glossário do repositório para um mapa de glossário cria `topicref`. (10767)
- A janela Visualização do editor XML está truncada nos navegadores Google Chrome e Microsoft Edge. (10755)
- O Editor da Web não tem a capacidade de envolver um elemento dentro dos possíveis elementos principais. (8791)
- O Editor da Web é desinstalado após a reinstalação do Adobe Experience Manager Guides versão 4.3.1. (14519)
- O instalador da versão 4.3.1 encontra um conflito de filtro, resultando na substituição de `apps/cq/core/content/projects/properties`. (14517)
- Um link de autorreferência aparece abaixo da lista de **Links quebrados** em Relatórios. (13539)
- A tela de visualização de trechos está congelada. (14840)
- Os caracteres quebrados aparecem ao criar os trechos no idioma coreano. (13489)

## Publicação

- A publicação do AEM Sites falha e causa erros de escopo para arquivos que têm `xref` ao arquivo DITA que começa com &quot;HTTP&quot;. (15154)
- Na publicação de PDF nativo, as propriedades de metadados do mapa DITA não podem ser usadas para preencher os metadados da saída do arquivo PDF. (15159)
- Na publicação de PDF nativo, os atributos personalizados nas predefinições de condição não funcionam na publicação de PDF nativo. (14943)
- Não é possível adicionar um modelo personalizado do **Saídas** no Editor. (14846)
- **Site AEM** A predefinição não está funcionando devido a um caminho de modelo vazio. (14804)
- A regeneração do site AEM falha para mapas DITA com tópicos que contêm equações MathML. (14790)
- Na publicação de PDF nativo, a geração de PDF gera erros na obtenção de dependências para `Node.js` publicação. (14445)
- **Site AEM** predefinição não permite a seleção de um modelo fora da `/content` hierarquia no Editor da Web. (14260)
- A funcionalidade de publicar como fragmento de conteúdo não está funcionando para os arquivos listados nos resultados da pesquisa. (14090)
- Os componentes da Fmdita têm um caminho codificado de `delegator.jsp`, evitando a sobreposição de componentes do AEM Sites. (13993)
- A exibição marcada do reator de PDF na saída de publicação de PDF nativo não está funcionando como esperado. (13622)
- Na publicação de PDF nativo, a seleção da cor do plano de fundo no **Modelo** o layout requer um recarregamento de página ao reverter para `None`. (13621)
- A publicação do site AEM encontra um problema ao confirmar para o armazenamento de dados de mapas grandes com links de mesmo nível de escopo. (13531)
- Problema ao confirmar o armazenamento de dados de um mapa DITA grande com links de pares de escopo na publicação do Site AEM. (13530)
- Ícone e dica de ferramenta incorretos são exibidos para  **Editar conteúdo** opção no **Layouts de página** barra de ferramentas dos Modelos usados na publicação de PDF nativo. (13492)
- Não é possível ativar um site usando os Guias do Experience Manager **Painel de publicação em massa**. (13439)
- Na publicação de PDF nativo, a acessibilidade é comprometida, pois as imagens no cabeçalho e no rodapé não exibem texto alternativo. (12829)
- Na saída do AEM Sites, o estilo ou as quebras de linha foram perdidas para o `<lines>` elemento com subelementos.(12542)
- A duplicação do layout de página no PDF nativo não funciona com nenhuma extensão adicionada automaticamente. (12534)
- A localização dos rótulos dos elementos não está funcionando corretamente na saída do AEM Sites. (12144)
- Os metadados personalizados não estão disponíveis na saída final. (12116)
- `fmdita rewriter` está em conflito com a configuração de reescrita do usuário e resulta na exibição de URLs longos em vez dos links. (12076)
- Ausente **ditaval** opção em predefinições de saída em nível de perfil de pasta criadas pela interface do usuário do Editor da Web. (11903)
- No **Site AEM**  predefinição, a opção de **Gerar PDF separado para cada tópico** não está funcionando. (11555)
- A publicação de PDF nativo não tem suporte para a conversão de espaço de cores CMYK. (10754)
- Ao atualizar para a versão 4.3.1, ocorrem algumas exceções no nó PDF nativo. (14492)
- Ao gerar a saída de PDF com a publicação de PDF nativo, o nome do arquivo é truncado após um ponto. (13620)


## Gerenciamento

- A referência de conteúdo é quebrada ao copiar e colar os arquivos DITA com links de autorreferência sem GUID. (13540)
- **Filtro de Linha de Base** Os arquivos não estão funcionando com o Nome do arquivo no Editor da Web. (13486)
- No Editor da Web, a linha de base mostra o título da versão anterior em vez da versão selecionada do arquivo DITA. (13444)
- Desativar a indexação do mapa DITA principal para obter um melhor desempenho pode afetar a funcionalidade de determinados recursos.(12213)
- As predefinições de condição para mapas DITA grandes não estão sendo criadas. (10936)
- Não é possível editar as predefinições dos primeiros mapas da coleção ao editar uma coleção de mapas. (10649)
- Rótulos do `labels.json` arquivos aparecem em ordem aleatória no Editor da Web. (10508)
- As chamadas de linha de base dinâmicas estão usando o nome em vez do título, o que resulta na falha da opção Exportar API de mapa DITA. (14268)

## Revisar

- O menu de contexto de clique com o botão direito do mouse não funciona para **Aceitar** ou **Rejeitar** rastrear alterações. (14607)
- Alternar para fechar tópicos DITA na Tela de revisão não funciona na versão 4.3.1 dos Guias do Adobe Experience Manager. (14537)
- Problemas de simetria ocorrem nos painéis de revisão lado a lado das versões anterior e atual no Editor da Web. (14156)
- A personalização de modelos de email para fluxo de trabalho de revisão não funciona com sobreposição. (13954)
- Os anexos coreanos na tela de Revisão dos Guias de Experience Manager não são clicáveis. (13436)
- O título do mapa é cortado na tela de revisão e colaboração, sem a opção de visualizar o título completo. (13012)

## Tradução

- A variável **Aceitar/Rejeitar** Os botões são exibidos incorretamente para a tradução humana aprovada automaticamente. (14318)
- Problemas de internacionalização (i18n) ocorrem durante a transformação de arquivos DITA em outros idiomas para páginas AEM. (14286)
- A aprovação automática às vezes não funciona e ocorrem exceções se um valor incorreto estiver definido em **Status da tradução**. (13607)
- A linha de base exportada do painel Tradução falha e não abre no idioma de destino. (12993)
- O conteúdo traduzido não é sincronizado dos projetos de tradução temporários, e o assistente de tradução do editor XML DITA é exibido incorretamente **Em andamento** status para trabalhos aprovados. (9938)

## Problema conhecido

A Adobe identificou o seguinte problema conhecido para a versão 4.4.0:

- A versão 1.0 não é exibida na interface do usuário do arquivo DITA duplicado.