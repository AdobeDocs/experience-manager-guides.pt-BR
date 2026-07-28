---
title: Notas de versão | Correção de problemas na versão 2026.08.0 do Adobe Experience Manager Guides
description: Saiba mais sobre as correções de erros na versão 2026.08.0 do Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 11d5db19cc352a3750754099a11290e4c0da0846
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 0%

---

# Correção de problemas na versão 2026.08.0

Este artigo aborda os bugs corrigidos nas várias áreas da versão 2026.08.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter mais informações sobre os novos recursos e aprimoramentos, consulte [Novidades na versão 2026.08.0](whats-new-2026-08-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.08.0](upgrade-instructions-2026-08-0.md).

## Criação

- Falha ao abrir tópicos no Editor quando acessados em Relatórios de tópico no painel do mapa. (GUIDES-45277)


## Editor 2.0

- Quando uma equação do MathML é inserida como `conref`, ela não é renderizada corretamente. (GUIDES-46601)
- Copiar e colar `<keywords>` dentro de `<topicmeta>` dentro de `<keydef>` ou `<topicref>` faz com que as palavras-chave sejam inseridas dentro de marcas estrangeiras indesejadas. (GUIDES-45800)
- Usar `Ctrl+click` em um link quebrado em um Editor de mapa dispara um erro de aplicativo. (GUIDES-45544)
- Copiar uma tabela de uma planilha do Excel e colá-la no Novo editor coloca todo o conteúdo da célula copiada em uma única célula de tabela, em vez de distribuí-la pelas células correspondentes. (GUIDES-47435)
- Um botão **Exportar como PDF** personalizado configurado por meio de `editor_toolbar.json` é renderizado e permanece clicável no modo de Visualização, mas não executa nenhuma ação quando clicado. (GUIDES-47402)
- Os elementos MathML e SVG não renderizam seu conjunto completo de atributos, causando a quebra das classes CSS personalizadas e dos atributos condicionais aplicados a esses elementos. (GUIDES-46371)
- A abertura de determinados tópicos contendo tabelas adiciona uma tag `<foreign>` inesperada com duas novas colunas, mesmo quando não foram feitas alterações no tópico. (GUIDES-46748)
- O atributo **Scale** não se aplica a imagens na exibição Autor. (GUIDES-45996)
- Arrastar e soltar um elemento contendo um `keyref` converte o valor `keyref` em um caminho absoluto. (GUIDES-45701)
- Inserir um elemento na posição `tgroup` exibe um aviso **#text não é permitido aqui**, impedindo que uma tabela normal seja inserida nessa posição. (GUIDES-47446)
- Os termos alfanuméricos adicionados ao dicionário ainda são sinalizados pelo verificador ortográfico do AEM em vez de serem ignorados. (GUIDES-48587)

## Gerenciamento de ativos

- O processamento de ativos em massa inclui incorretamente os ativos do Fragmento de conteúdo, causando registros de erros e falhas nos relatórios de processamento. (GUIDES-47085)
- No Painel de Mapa, os tópicos secundários não são carregados e o ícone de expansão desaparece quando a caixa de seleção de mapa é selecionada e desmarcada repetidamente. (GUIDES-43546)

## Publicação

**AEM Sites**

Ao publicar a saída do AEM Sites usando o mapeamento de componente composto:

- Uma **Lista de tópicos** em branco é exibida quando uma nova linha de base é usada na predefinição do AEM Sites com mapeamento de componente composto. (GUIDES-46480)
- Os links de referência cruzada (`xref`) para ativos que não são DITA, como PDF, ZIP, DOCX e arquivos de imagem, não são resolvidos corretamente, resultando em links com falha na página gerada. (GUIDES-44108)

Ao publicar a saída do AEM Sites usando o mapeamento de componente herdado:

- Nomes de arquivo em outros idiomas nos nomes de página gerados são substituídos por hifens, dificultando a identificação do tópico ou arquivo ao qual está associado. (GUIDES-48387)

**PDF nativo**

- Na saída do PDF Nativo, referências de tópico marcadas com o atributo `toc="no"` ainda são incluídas no índice, resultando em um índice longo e confuso. (GUIDES-37940, GUIDES-20156)

**Mapear coleções e ativação em massa**

Os seguintes problemas foram corrigidos com o recurso [Nova coleção de mapas](../user-guide/generate-output-use-new-map-collection-output-generation.md#use-new-map-collection-for-output-generation-beta) disponível na versão 2020.08.0 do Experience Manager Guides:

- Não é possível carregar uma coleção de mapas com mais de 100 entradas devido a um erro de rede. (GUIDES-34007)
- Não é possível selecionar vários mapas ao mesmo tempo de uma pasta na interface da Coleção de Mapas. (GUIDES-29581)
- Não é possível pesquisar ou filtrar coleções de mapas na interface de Coleções de Mapas. (GUIDES-27723)
- Não é possível fechar o painel Publicação/Ativação em Massa ou navegar de volta para **Ferramentas** ou a página inicial sem usar o botão Voltar do navegador. (GUIDES-26797)
- Incapacidade de gerenciar facilmente coleções de mapas com um grande número de mapas ou idiomas. (GUIDES-21735)
- Não é possível exibir ou publicar a saída gerada diretamente das interfaces da Coleção de Mapas ou do Painel de Ativação em Massa. (GUIDES-18712)
- Não é possível usar uma única coleção para gerar e ativar mapas, pois as Coleções de Mapas e o Painel de Ativação em Massa gerenciam conjuntos separados de coleções. (GUIDES-12730)

## Revisar

- Na interface de Revisão, a lista de marcação exibe todos os usuários na tarefa de revisão, o que dificulta a seleção do usuário correto em um comentário ou resposta. (GUIDES-33420)
- Abrir o modo de exibição **lado a lado** no painel Comentários exibe a cópia de trabalho junto com a versão comentada, mas os painéis não rolam em sincronia horizontalmente e clicar em um comentário não move o cursor para o texto correspondente. (GUIDES-44083)

## Banco de dados

- `DatabaseConfiguratorService` lança um erro nos logs mesmo quando não está configurado ou habilitado. (GUIDES-43481)

## Problemas conhecidos

A Adobe identificou os seguintes problemas conhecidos para a versão 2026.08.0:

## Criação

- Fechar um arquivo DITAVAL que foi movido para um local diferente resulta em uma mensagem de erro `ERROR IN FETCHING VERSION DETAILS`. (GUIDES-51420)

## Editor 2.0


- A API de conflito falha e leva a um erro de aplicativo quando o caminho da pasta do repositório termina com uma barra. (GUIDES-51006)
- Selecionar um elemento de instrução de processamento na exibição de Estrutura de Tópicos realça a tag principal inteira em vez do elemento selecionado. (GUIDES-48318)
- Editar uma palavra-chave em um `keyref` na exibição de origem interrompe a palavra-chave quando a exibição é alternada para qualquer outra exibição. (GUIDES-49998)
- Uma equação de MathML encapsulada dentro de um bloco `foreign` e `equation` resulta em espaçamento indesejado, e digitar dentro da equação causa problemas mesmo após ajustar o recuo. (GUIDES-46606)
- Não é possível colocar um cursor dentro de um `topicref` dentro de um `reltable` quando a opção **Mostrar marcas** está habilitada e a opção **Exibir atributos** está desabilitada nas configurações do Editor. (GUIDES-46565)
- Arrastar e soltar uma referência em um `keydef` vazio adiciona um elemento `topicref` em vez de atualizar a referência. (GUIDES-45068)

## Publicação

- Selecionar **Exibir saída** após gerar saída do Edge Delivery Services abre uma URL `hlx.live` que retorna um erro 403 Proibido em vez da URL `aem.live`. (GUIDES-51572)
- Componentes inválidos são exibidos na página `common.plt` ao adicionar uma imagem, hiperlink ou iframe a partir da barra de ferramentas de um modelo. (GUIDES-51165)
- A publicação de um mapa que faça referência a um tópico usando o atributo `copy-to` remove o link do escopo de mesmo nível do tópico correspondente no mapa de origem. (GUIDES-50701)
- Quando um PDF é referenciado como um `xref` com escopo definido como `Peer`, ele é publicado no site do AEM (usando o mapeamento de componente herdado) em vez de ser originado do mapa cruzado. (GUIDES-50213)

**Mapear coleções**

- A exclusão de uma coleção de mapas às vezes falha se você alternar entre guias (como Repositório ou Visão geral) e, em seguida, retornar à página Coleção de mapas antes de excluí-la. (GUIDES-50997)
- Gerar a mesma predefinição enquanto uma geração anterior estiver em andamento não mostra mais uma mensagem indicando que a geração anterior está em andamento. (GUIDES-50523)
- O carimbo de data e hora da última geração não é exibido ou atualizado na interface da Coleção de mapas após a geração de um mapa, e a readição de uma predefinição que foi removida anteriormente faz com que seu histórico de geração seja perdido novamente. (GUIDES-50511)
- A publicação a partir do **Histórico de Geração** sempre publica a saída mais recente de uma predefinição em vez da geração selecionada. (GUIDES-50508)
- O status de publicação não é atualizado automaticamente para coleções de mapas recém-criadas. (GUIDES-50367)

## Tradução

- Iniciar uma tradução com a opção **Criar estrutura somente** retorna um erro. (GUIDES-51261)

## Revisar

- A execução de um tachado usando um atalho de teclado sobre o texto que inclui conteúdo condicional oculto também tachará o conteúdo oculto. (GUIDES-49837)


