---
title: Notas de versão | Novidades na versão 2026.01.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2026.01.0 do Adobe Experience Manager Guides
role: Leader
source-git-commit: f0ba8dce38a6eef5dedc8a81107c8e31ea6b26b3
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 0%

---

# Novidades da versão 2026.01.0 (fevereiro de 2026)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2026.01.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2026.01.0](fixed-issues-2026-01-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2026.01.0](../release-info/upgrade-instructions-2026-01-0.md).


## Introdução à pesquisa no modo Source em Localizar e substituir

O Experience Manager Guides introduziu várias melhorias no recurso Localizar e substituir, disponível no painel Esquerdo da interface do Editor. Juntamente com uma interface aprimorada para melhor usabilidade, esta versão introduz um novo botão de alternância **Usar modo de origem** no painel **Localizar e substituir**.

Ativar esse modo permite executar uma pesquisa global não apenas no conteúdo visível, mas também no conteúdo original subjacente (estrutura XML, incluindo elementos, tags e valores de atributo) da string pesquisada. Esse modo garante uma pesquisa abrangente em todo o conteúdo.

![](assets/map-find-replace-with-source-mode.png){width="650" align="left"}

Nesse modo, é possível aplicar filtros para restringir a pesquisa por Tipo de arquivo, Estado do documento, Data da última modificação e muito mais. Você também tem a opção de baixar um relatório CSV detalhado após executar a operação Substituir tudo, que fornece um instantâneo de todas as ações de substituição executadas, juntamente com seus status de sucesso e falha.

Para obter mais detalhes, exiba a seção [Localizar e substituir](../user-guide/web-editor-left-panel.md#find-and-replace) no _painel esquerdo do Editor_.

>[!NOTE]
>
> Para o recurso **Usar modo de origem** no painel Localizar e substituir, uma implantação de índice personalizada deve ser concluída primeiro. Depois que a indexação estiver em vigor, entre em contato com a equipe de Sucesso do cliente para ativar esse recurso.

## Experiência aprimorada de navegação em arquivos e pastas

Esta versão apresenta uma interface mais limpa e intuitiva para navegar pelos arquivos e caminhos de pastas no Experience Manager Guides.

Ao navegar pelos arquivos, a caixa de diálogo **Selecionar arquivo** renovada agora apresenta um layout com guias com duas exibições - **Repositório** para navegar por todo o repositório de conteúdo em um formato tabular e **Coleções** para acesso rápido a tópicos, mapas e imagens usados com frequência.

![](assets/select-file.png){width="650" align="left"}

Os principais aprimoramentos incluem:

- Exibição tabular de arquivos e pastas para navegação organizada.
- Navegação estrutural e painel de navegação da pasta para mover-se facilmente pelas pastas.
- Suporte para seleção de vários arquivos para conteúdo reutilizável, referências de tópico, esquema, predefinições de saída (usando DITAVAL) e Workfront.
- Visualize os arquivos selecionados para facilitar a revisão; para várias seleções, visualize todos os arquivos e remova qualquer arquivo do painel Visualização, conforme necessário.
- Opções de pesquisa e filtragem para restringir os resultados por nome, título, tipo de arquivo, estado do documento e tags.

A caixa de diálogo **Selecionar caminho** também apresenta uma exibição estruturada em árvore aprimorada para navegação de pastas, garantindo uma maneira mais organizada e eficiente de selecionar caminhos no repositório de conteúdo.

![](assets/select-path-dialog-new.png){width="350" align="left"}

Para obter mais detalhes, exiba [seção Procurar arquivos e pastas no Experience Manager Guides](../user-guide/web-editor-other-features.md#browse-files-and-folders-in-experience-manager-guides) em _Outros recursos no Editor_.

## Aprimoramentos de pesquisa e filtro de repositório

### Suporte para filtro de estado do documento

Agora, filtre os resultados da pesquisa de Repositório com base no estado atual do documento dos arquivos. Com o novo filtro **Estado do documento**, você pode restringir sua pesquisa usando os valores de filtro disponíveis definidos no arquivo `ui_config.json` dentro do seu perfil de pasta.

![](assets/document-state-filter-repository.png){align="left"}

Os valores de filtro padrão disponíveis para o estado do Documento são: Rascunho, Editar, Em revisão, Aprovado, Revisado e Concluído. Para obter detalhes sobre como personalizar os valores de filtros de estado de documento padrão, exiba [Configurar filtros de estado de documento](../cs-install-guide/config-doc-state-filters.md).

>[!NOTE]
>
> Se você estiver usando configurações personalizadas para `ui_config.json`, certifique-se de fazer um backup delas antes de atualizar. Após a atualização, revise e ajuste suas configurações para alinhar-se às alterações introduzidas na versão mais recente.

### Ícone de miniatura para multimídia

Todos os arquivos multimídia agora são exibidos com ícones de miniatura, facilitando a identificação visual e a localização de imagens no **Repositório**. Esse aprimoramento também se aplica à pesquisa de arquivos no **painel Pesquisar**, ajudando você a distinguir rapidamente os ativos multimídia de outros tipos de arquivos.

![](assets/thumbnail-repository.png){align="left"}

## Aprimoramentos do editor

Os seguintes aprimoramentos do Editor foram feitos como parte desta versão:

### Atualizar tópicos ou mapear no modo de Visualização

Apresentando a nova funcionalidade **Atualizar** para mapas que já estão abertos no modo de Visualização. Com esse novo recurso, você pode atualizar facilmente o conteúdo do mapa inteiro ou de tópicos individuais presentes nele.

- Para atualizar o mapa inteiro (incluindo todos os tópicos), um novo botão **Atualizar** é introduzido no canto superior esquerdo do Editor.

  ![](assets/refresh-map.png){width="600" align="left"}

- Para atualizar o conteúdo de tópicos individuais, uma nova opção **Atualizar tópico** é introduzida no menu de contexto.

  ![](assets/refresh-topic.png){width="600" align="left"}

Para obter mais detalhes, consulte [Recursos do editor de mapas](../user-guide/map-editor-advanced-map-editor.md).

### Indicador de cópia de trabalho para alterações de metadados

Qualquer alteração nos campos de metadados disponíveis em **Propriedades do arquivo** acionará o indicador da cópia de trabalho. Uma versão do documento está marcada como _suja (*)_ sempre que você adiciona, exclui ou modifica campos de metadados padrão ou personalizados. Esse aprimoramento garante que todas as alterações nos metadados sejam controladas com precisão, oferecendo maior visibilidade e controle sobre as versões dos documentos.

### Contagem de palavras para tópicos e mapas

Agora é possível rastrear a contagem de palavras presente em um mapa ou arquivo de tópico. O novo campo **Contagem de palavras** do painel direito exibiria o número total de palavras presentes em um tópico (ou mapa), onde as palavras separadas por espaços são contadas como palavras individuais. Ele é atualizado automaticamente sempre que você salva as alterações. Para referências cruzadas, somente o texto de exibição é incluído, enquanto as teclas são excluídas.

![](assets/file-properties-new.png){width="350" align="left"}

Para obter detalhes, exiba [painel direito no Editor](../user-guide/web-editor-right-panel.md#file-properties).

### Manuseio aprimorado de arquivos somente leitura

A edição das propriedades do Arquivo agora está restrita para arquivos que estão no modo **Somente leitura**. Se um arquivo estiver bloqueado por outro usuário (disponível no modo Somente leitura), você não poderá alterar nenhuma propriedade de metadados, seja do [painel direito](../user-guide/web-editor-right-panel.md#file-properties), da opção **Propriedades** no [menu de contexto de um arquivo](../user-guide/web-editor-other-features.md#context-menu-functions-on-a-files-tab) ou do [Relatório de Metadados](../user-guide/reports-web-editor.md#metadata-report). Isso ajuda a evitar alterações acidentais em arquivos somente leitura.

## Revisar melhorias

### Adicionar ou remover tópicos de uma tarefa de Revisão em andamento

Agora é possível adicionar novos tópicos a uma tarefa de revisão em andamento (se eles não tiverem sido enviados anteriormente para revisão) ou remover tópicos de uma tarefa de revisão em andamento sem afetar o fluxo de trabalho de revisão.

Na página **Detalhes da Tarefa**, você pode simplesmente selecionar ou desmarcar tópicos para modificar a lista de tópicos. Os revisores são notificados (via AEM e email) sobre qualquer alteração nos tópicos atribuídos por meio de notificações do AEM e por email. Para obter mais detalhes, exiba [Enviar tópicos para revisão](../user-guide/review-send-topics-for-review.md).

![](assets/modify-review-topics.png){width="650" align="left"}

## Aprimoramentos de tradução

### Indicador de ativos sem versão enviados para tradução

Ao gerenciar traduções, é importante garantir que todo o conteúdo seja versionado antes de enviá-lo para processamento. Para ajudar nisso, o Experience Manager Guides agora fornece um indicador claro para tópicos que salvaram alterações, mas ainda não têm controle de versão.

Se um arquivo contiver alterações sem controle de versão (não salvas como uma nova versão no mapa), um ícone _info_ será exibido ao lado do arquivo, indicando que existem atualizações. Para focalizar rapidamente nesses arquivos, habilite a opção **Mostrar ativos somente com alterações sem controle de versão** no painel Filtros.

Para obter mais detalhes, exiba [Traduzir documentos do Console de Mapa](../user-guide/translate-documents-web-editor.md).

![](assets/unversioned-changes-translation.png){width="650" align="left"}

## Aprimoramentos de publicação

### Representações de imagem personalizadas para predefinições de saída específicas

Agora é possível configurar diferentes representações de imagem para predefinições de saída individuais no mesmo tipo de saída usando o atributo `outputName` em `renditionmapping.xml`. Esse aprimoramento oferece maior flexibilidade ao publicar conteúdo que requer várias resoluções de imagem para diferentes cenários. Por exemplo, você pode querer uma imagem de alta resolução para a saída principal do HTML5 ao usar uma miniatura menor para uma predefinição leve.

Para obter mais detalhes, exiba [Manipular representação de imagem na geração de saída](../cs-install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).


### Baixar logs para saída gerada

Ao gerar saída por meio da interface do usuário do Assets, um novo botão **Baixar logs** agora está disponível, permitindo baixar o log no dispositivo local para facilitar o acesso e a revisão.


### Variáveis de idioma para referências cruzadas na saída do PDF nativo

Ao publicar a saída do PDF Nativo, você pode usar [variáveis de idioma](../native-pdf/native-pdf-language-variables.md) para traduzir texto estático de referência cruzada, como _Consulte no capítulo_ ou _Consulte na página_. A variável usa o idioma definido no tópico por meio do atributo `xml:lang`.

Para obter detalhes sobre como definir a predefinição de saída nativa do PDF e as configurações de referência cruzada, exiba a [predefinição de saída nativa do PDF](../web-editor/native-pdf-web-editor.md).


### Suporte para mapeamento de componentes no nível do elemento na publicação New AEM Sites (usando mapeamento de componentes compostos)

O Experience Manager Guides agora oferece suporte ao mapeamento de componentes no nível do elemento na saída do AEM Sites (usando o mapeamento de componentes compostos), fornecendo às equipes controle preciso sobre como os elementos DITA são renderizados usando o `componentmapping.json`. Mapeando `topicref`, títulos, imagens, tabelas e muito mais para os Componentes principais apropriados do AEM, você obtém uma estrutura mais limpa em vez de tudo padronizado para o componente de Texto. Isso resulta em melhor desempenho e desbloqueia experiências mais ricas e modernas do Sites.

## Aprimoramentos no processamento de ativos

Esta versão apresenta os seguintes aprimoramentos ao processamento de ativos:

- Executar o processamento de ativos nos níveis de pasta e de arquivo individual
- Filtre ativos escolhendo tipos específicos de ativos, como tópicos, mapas, Markdown, HTML/CSS, DITAVAL ou outros arquivos compatíveis, para processar somente os arquivos necessários.
- Aplique filtros com base em data para limitar o escopo de processamento por um período especificado.
- Reprocesse ativos diretamente usando a nova opção (**Reprocessar ativos**) disponível no menu de contexto de arquivos e pastas no modo de exibição Repositório e no painel Explorador.

Para obter mais detalhes sobre o processamento de ativos, consulte [Processar ativos](../user-guide/asset-processor.md).

## Aprimoramentos na API

As seguintes melhorias na API foram feitas como parte desta versão:

- Novas APIs são introduzidas para criar um novo projeto de tradução e rastrear seu status. Essas APIs ajudam a automatizar o processo de tradução, reduzindo o esforço manual e melhorando a eficiência. Para obter detalhes, exiba [Criar projeto de tradução](../api-reference/translation-project.md)
- APIs de processamento de ativos aprimoradas com capacidade de filtragem aprimorada para arquivos e pastas. Para obter detalhes, consulte [Processar ativos](../api-reference/bulk-assets-processing.md).
















