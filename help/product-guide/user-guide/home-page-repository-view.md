---
title: Repositório na página inicial
description: Conheça o Repositório na Home page. Saiba mais sobre a Interface do repositório e os recursos no Adobe Experience Manager Guides na página inicial.
feature: Authoring
role: User
source-git-commit: 1919e622b1b148d16bcdb85f79e2a1cd706fe33e
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 0%

---

# Conhecer a interface do Repositório

O Repositório serve como um espaço centralizado para melhorar a capacidade de descoberta de pastas e arquivos. Ele fornece uma visualização de lista tabular abrangente de pastas e arquivos com várias colunas, oferecendo detalhes contextuais para todos os arquivos e ativos.

Essa interface unificada simplifica várias funções, incluindo a criação de novos arquivos ou pastas, a edição de arquivos, o upload de ativos e a pesquisa de arquivos com opções de filtragem robustas, garantindo eficiência e facilidade de uso.

![](images/repository-view-home.png){align="left"}

A interface do Repositório é dividida nas seguintes seções:

- Barra de navegação do repositório
- Visualização tabular do repositório

## Barra de navegação do repositório

A barra de navegação do Repositório, localizada na parte superior da interface do Repositório, fornece acesso rápido às ações essenciais listadas.

![](images/tab-bar-repository-view.png){align="left"}


- **Painel de navegação de pasta**: apresenta uma exibição hierárquica em árvore das pastas no Repositório, permitindo uma navegação contínua. Esse painel mostra somente as informações no nível da pasta. Quando uma pasta é selecionada aqui, seu conteúdo, arquivos e subpastas são exibidos na visualização Repositório. Você pode mostrar ou ocultar esse painel usando o ícone destacado abaixo.

  ![](images/folder-navigation-panel.png){align="left"}

- **Navegação estrutural**: indica o caminho atual no Repositório, mostrando a hierarquia de pastas que leva à pasta atual. Você pode selecioná-la para voltar para uma pasta específica na hierarquia.

  ![](images/breadcrumbs.png){width="650" align="left"}

- **Atualizar**: atualiza o repositório para refletir as alterações mais recentes.
- **Carregar Assets**: permite carregar ativos diretamente na pasta atual, como destacado na navegação estrutural.
- **Novo**: permite a criação de novos tópicos, mapas e pastas dentro da pasta atual como destacado na navegação estrutural.
- **Assistente de IA**: uma ferramenta avançada orientada por IA, projetada para aprimorar sua produtividade por meio de recursos de ajuda inteligentes. No momento, o recurso [Assistente de IA](./ai-assistant.md) está disponível apenas para o Adobe Experience Manager as Cloud Service.
- **Mais ações**: fornece acesso a opções adicionais. Selecionar esse botão abre um menu com as seguintes opções:
   - **Assets**: leva você a um destino com base em sua configuração.
      - **Serviços em Nuvem**: se você estiver usando os Serviços em Nuvem, selecionar a opção **Assets** o levará à página Navegação da AEM.
      - **Software Local**: se estiver usando o Adobe Experience Manager Guides (4.2.1 e posterior), selecionar a opção **Assets** levará você ao caminho do arquivo atual na interface do usuário do Assets.
   - **Configurações do Workspace**: Leva você à caixa de diálogo **Configurações do Workspace**. Para obter detalhes, consulte [Definir configurações do Workspace](../cs-install-guide/workspace-settings.md).
- **Expandir exibição**: permite expandir a exibição de página usando o ícone **Expandir**. Nessa visualização, a barra do Cabeçalho está oculta, maximizando o espaço de conteúdo. Para retornar à exibição padrão, use o ícone Sair da exibição expandida.

## Visualização tabular do repositório

O Repository serve como o espaço central fornecendo uma lista tabular de todas as pastas e arquivos. Ele oferece os seguintes recursos:

- **Personalizar**: você pode modificar as colunas exibidas usando a opção **Personalizar**, localizada no canto superior direito do modo de exibição Repositório. Essa opção permite mostrar ou ocultar qualquer coluna e também reorganizar as colunas conforme necessário. As colunas **Name** ou **Title** são obrigatórias e não podem ser desabilitadas juntas. Outros campos, como **Tipo de arquivo**, **UUID**, **Estado do documento**, **Bloqueado por**, **Criado em** e **Modificado em**, podem ser habilitados ou desabilitados conforme necessário. Você pode reorganizá-los simplesmente arrastando e soltando.

  ![](images/customize-repo-view.png){width="350" align="left"}

- **Redimensionamento de colunas**: as colunas podem ser redimensionadas selecionando opções no menu suspenso de colunas.

- **Classificação**: as colunas Nome, Título, Criado em e Última modificação oferecem suporte à classificação em ordem crescente ou decrescente, acessível por meio do menu suspenso de colunas.

- **Editando o arquivo**:

   - É possível selecionar um ou vários arquivos da lista para edição.
   - Depois de marcar os arquivos desejados usando a caixa de seleção, a opção **Editar** fica disponível no canto superior direito da exibição Repositório.
   - Selecionar **Editar** abre o(s) arquivo(s) selecionado(s) na interface do Editor, onde você pode começar a editar o arquivo.

     ![](images/edit-repo-view.png){align="left"}

- **Menu de opções para pastas**: você pode executar as seguintes ações usando o menu **Opções** disponível para uma pasta:

  ![](images/options-folder-repo.png){width="350" align="left"}

   - **Novo**: crie um novo tópico DITA, mapa DITA ou uma pasta.
   - **Carregar Assets**: carregue um arquivo do sistema local para a pasta selecionada no repositório.
   - **Adicionar às coleções**: adiciona a pasta selecionada aos favoritos. Você pode optar por adicioná-la a uma coleção existente ou nova.
   - **Reprocessar ativos**: aciona o processamento de todos os ativos recém-criados e não processados.

- **Menu de opções para arquivos**: você pode executar as seguintes ações usando o menu **Opções** para um arquivo:

  ![](images/options-file-repo.png){width="350" align="left"}

   - **Editar**: abrir o arquivo para edição.
   - **Editar no Oxygen**: selecione essa opção para editar o arquivo selecionado no plug-in do conector do Oxygen.

     >[!NOTE]
     >
     >Entre em contato com a equipe de sucesso do cliente para habilitar esse recurso no ambiente. Isso não é ativado como parte do suporte pronto para uso. Para obter mais detalhes, exiba a opção [Configurar a opção para editar no Oxygen](../cs-install-guide/conf-edit-in-oxygen.md) na seção do Guia de Instalação e Configuração.

   - **Abrir no console de mapa**: caso o arquivo selecionado seja um mapa DITA, essa opção abrirá o console de mapa.
   - **Abrir no painel de mapa**: caso o arquivo selecionado seja um mapa DITA, essa opção abrirá o painel de mapa.
   - **Bloqueio**: obtenha um bloqueio no arquivo selecionado para edição.
   - **Visualização**: obtenha uma visualização rápida do arquivo (.dita, .xml, áudio, vídeo ou imagem) sem abri-lo.
   - **Duplicar**: use esta opção para criar uma duplicata ou uma cópia do arquivo selecionado.
   - **Mover para**: use esta opção para mover o arquivo selecionado para outra pasta.
   - **Renomear**: use esta opção para renomear o arquivo selecionado.
   - **Excluir**: use esta opção para excluir o arquivo selecionado.
   - **Adicionar a**: escolha adicionar a Coleções ou conteúdo Reutilizável.
   - **Copiar**: copia a UUID ou o caminho completo do arquivo.
   - **Propriedades**: use esta opção para abrir a página Propriedades do arquivo selecionado.
   - **Baixar como PDF**: use a opção para gerar a saída do PDF e baixá-la.

### Experiência de pesquisa e filtro

A opção **Pesquisar** ajuda a pesquisar os arquivos necessários no Repositório principalmente com base no **Título do arquivo**, **Nome do arquivo** e **Conteúdo**. Você pode usar qualquer um, dois ou todos os três critérios para sua pesquisa. Se nenhum dos critérios for selecionado, os resultados incluirão informações comuns aos três critérios.

![](images/search-in-repository.png){align="left"}

Selecione o ícone **Filtrar pesquisa** \(![Ícone Filtrar pesquisa](images/filter-search-icon.svg)\) para abrir o painel Filtro à direita.

![](images/Search-filters-repo.png){align="left"}

Você tem as seguintes opções para filtrar os arquivos e restringir sua pesquisa:

- **Pesquisar em**: selecione o caminho no qual deseja pesquisar os arquivos presentes no Repositório.

- **Tipo de arquivo**: você pode procurar todos os **Tópicos DITA**, **Mapas DITA**, **Arquivos DITAVAL**, **Arquivos de Imagem**, **Multimídia**, **Documentos** e **JSON**.

- **Bloqueado por**: exibe uma lista de usuários. A lista é paginada e carregada de forma assíncrona, mostrando um conjunto limitado de usuários de cada vez e buscando mais à medida que você rola a tela ou navega. Isso melhora a velocidade de carregamento e o desempenho geral, especialmente ao trabalhar com um grande número de usuários.

- **Última modificação**: filtrar conteúdo com base na data de modificação. Selecione um intervalo de datas no calendário ou escolha uma das seguintes opções de intervalo de tempo:
   - Na semana passada
   - No mês passado
   - No ano passado

- **Marcas**: filtrar conteúdo com base em marcas.

- **Elemento DITA**: filtre o conteúdo com base em vários elementos DITA.

Depois de aplicar todos os filtros necessários, selecione **Aplicar** no canto inferior direito do painel Filtros.

Os resultados da pesquisa personalizados de acordo com o filtro selecionado aparecem como uma **lista tabular de arquivos somente** (as pastas não são exibidas). É possível remover qualquer filtro individualmente ou vários filtros ao mesmo tempo, e os resultados são atualizados para refletir a seleção atualizada.

![](images/search-results-with-filters.png){align="left"}

Depois que os resultados da pesquisa forem exibidos, você poderá selecionar vários arquivos e abri-los no Editor usando o ícone **Editar** ou trabalhar com todos os resultados enviando os resultados da pesquisa para o Editor por meio da opção **Mostrar no painel de pesquisa**.

![](images/post-search-operation.png){align="left"}

**Mostrar no painel de pesquisa**

A opção **Mostrar no painel de pesquisa** fica disponível após executar uma pesquisa no Repositório. Este recurso permite exibir todos os resultados pesquisados no **painel Pesquisar** dentro do Editor. Para obter mais detalhes, consulte [Painel de pesquisa](./search-panel-explorer.md).

![](images/search-panel-repo.png){align="left"}

