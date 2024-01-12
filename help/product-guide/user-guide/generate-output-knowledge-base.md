---
title: Knowledge Base
description: Saiba como criar uma predefinição da Base de conhecimento no editor da Web e no painel de mapa. Configurar a saída da knowledge base predefinida nos guias AEM.
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---

# Knowledge Base {#knowledge-base}

Você pode criar o **Knowledge base** predefinição no Editor da Web:

No painel Repositório, abra o arquivo de mapa DITA em **Exibição de mapa**, depois no **Output** , selecione o ícone + para criar uma predefinição de saída e selecione **Knowledge base** do **Tipo** na lista suspensa **Nova predefinição de saída** diálogo. É possível nomear a predefinição e escolher o destino para gerar a saída usando o **Adobe Experience Manager**, **Salesforce** ou **ServiceNow**.




## Configuração da knowledge base{#knowledge-base-configuration}


No editor da Web, as seguintes configurações foram organizadas no **Geral** e **Artigos** guias. Também é possível definir as configurações para a variável **Knowledge base** você selecionou como público alvo, **Adobe Experience Manager**, **Salesforce** ou **ServiceNow**.


### Geral

| Opções da knowledge base | Descrição |
| --- | --- |
| Aplicar condições usando | Selecione uma das seguintes opções:<br><br>* **Nenhum aplicado**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.<br>* **Arquivo DITAVAL**: selecione os arquivos DITAVAL para gerar conteúdo personalizado. Você pode selecionar vários arquivos DITAVAL usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVAL são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVAL for movido para outro local ou excluído, ele não será excluído automaticamente da predefinição. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para visualizar o caminho no repositório do Adobe Experience Manager onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVAL, e um erro será exibido se você selecionar qualquer outro tipo de arquivo.<br>* **Predefinição de condição**: selecione uma predefinição de condição na lista suspensa para aplicar uma condição ao publicar a saída. A opção estará visível se você tiver adicionado uma condição na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre predefinições de condição, exiba [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Exibir [Trabalhar com linha de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração que contém todos os fluxos de trabalho configurados no Adobe Experience Manager é exibida. Você deve selecionar um workflow que deseja executar após a conclusão da geração de saída.<br><br>**Nota**: saiba mais sobre como [personalizar fluxo de trabalho de geração de pós-saída](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) no Guia de instalação e configuração do Cloud Service. |

### ServiceNow

| Opções do ServiceNow | Descrição |
| --- | --- |
| Publicar perfil | Use a lista suspensa para selecionar nos perfis de conexão do ServiceNow que o administrador configura. Para saber mais sobre como o administrador pode criar um perfil de publicação, exiba **Configurações do editor** descrição do recurso na [Painel esquerdo](./web-editor-features.md#id2051EA0M0HS) seção. |
| Knowledge Base | Use esse campo para selecionar a Base de conhecimento necessária do ServiceNow. Você pode configurar bases de conhecimento no site ServiceNow para armazenar o conteúdo com base nas permissões. Os artigos desse mapa do DITA podem ser publicados nessas bases de conhecimento. |
| Categoria e subcategoria | As categorias são como árvores hierárquicas usadas para localizar e classificar artigos da Base de Dados de Conhecimento ServiceNow. Adicione uma categoria e subcategoria para publicar os tópicos e subtópicos do índice nessa categoria e subcategoria no site ServiceNow. |

### Salesforce

| Opções do Salesforce | Descrição |
| --- | --- |
| Publicar perfil | Use o menu suspenso para selecionar entre os perfis de conexão do Salesforce que seu administrador configura. Para saber mais sobre como o administrador pode criar um perfil de publicação, exiba **Configurações do editor** descrição do recurso na [Painel esquerdo](./web-editor-features.md#id2051EA0M0HS) seção. |
| Tipo de registro | Use a lista suspensa para selecionar entre os tipos de registro configurados no Salesforce de acordo com as configurações de visibilidade com base no seu perfil de usuário. Os tipos de registro do Salesforce são uma maneira de agrupar muitos registros de um tipo para esse objeto. Elas definem como a publicação é organizada. Por exemplo, você pode selecionar Tipo de registro de perguntas frequentes e publicar de acordo com o layout e os campos da página Perguntas frequentes. |
| Campo de conteúdo do artigo | É possível ter campos diferentes e um layout exclusivo para cada modelo de tipo de registro. Use esses campos para inserir informações específicas, dependendo do tipo de artigo. Por exemplo, você pode visualizar o título, a resposta e a equação de um artigo de Perguntas frequentes. |
| Categorias | Selecione uma categoria na lista suspensa para publicar os tópicos do índice nessa categoria no site do Salesforce. |

Você também pode exibir as seguintes opções nas predefinições do Salesforce e ServiceNow: | Opções | Descrição | | — | — | |Remova o cabeçalho de tópico do corpo do artigo.|Selecione esta opção para remover o cabeçalho do tópico do artigo na saída publicada. | |Carregar como rascunho | Selecione esta opção para fazer upload do tópico e compartilhá-lo como rascunho antes de disponibilizá-lo aos usuários.| |Carregar imagens| Selecione esta opção se desejar que quaisquer imagens nos tópicos sejam incluídas na saída publicada.| |Fazer upload de documentos vinculados| Selecione essa opção para incluir os documentos vinculados em tópicos na saída publicada.|


### Adobe Experience Manager

>[!NOTE]
>
>Você pode usar a predefinição da Base de conhecimento Adobe Experience Manager se o administrador a tiver configurado. Para obter mais detalhes, consulte [Publicação baseada em artigos no Editor da Web](../install-guide/configure-article-based-publishing.md) no Guia de instalação e configuração.

| Opções do Adobe Experience Manager | Descrição |
| --- | --- |
| Usar caminho do artigo | Selecione essa opção para exibir a **Caminho do artigo** da pasta que contém os modelos da Base de conhecimento. |
| Caminho do artigo | Esse campo aparecerá se você selecionar a opção **Usar caminho do artigo**. Navegue até o site da knowledge base no repositório do Adobe Experience Manager onde a saída está armazenada. |
| Site | Use esse campo para selecionar a Base de conhecimento Adobe Experience Manager necessária. Você pode configurar a base de conhecimento no site do Adobe Experience Manager para armazenar o conteúdo com base nas permissões. Os artigos desse mapa do DITA podem ser publicados nessas bases de conhecimento. |
| Categoria | Selecione uma categoria na lista suspensa para publicar os tópicos do índice nessa categoria no site do Adobe Experience Manager. |
| Modelo de seção e modelo de artigo | Esses são os componentes estruturais usados para organizar o conteúdo da saída. Eles são predefinidos no modelo de site do Adobe Experience Manager. |
| Fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa de Fluxo de trabalho de pós-geração que contém todos os fluxos de trabalho configurados no Adobe Experience Manager é exibida. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída.<br>Saiba como [personalizar fluxo de trabalho de geração de pós-saída](../install-guide/customize-workflows.md#id17A6GI004Y4) no Guia de instalação e configuração. |
>[!TIP]
> 
>Selecionar **Atualizar** ![ícone de atualização](images/navtitle-refresh-icon.svg) para preencher os respectivos modelos nos campos de acordo com o modelo da Base de conhecimento selecionado.

### Artigos

Essa guia exibe a árvore ou a exibição hierárquica do mapa. Escolha os tópicos que deseja publicar em uma base de conhecimento. Expanda um nó do índice e escolha os tópicos que deseja publicar.

**Tópico pai:** [Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
