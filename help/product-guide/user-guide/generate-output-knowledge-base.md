---
title: Knowledge Base
description: Saiba como criar uma predefinição da Base de conhecimento no editor da Web e no painel de mapa. Configure a predefinição de saída da knowledge base no AEM Guides.
feature: Publishing
role: User
exl-id: 31fdfd96-377c-406b-96ed-59a80bf6e03e
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---

# Knowledge Base {#knowledge-base}

Você pode criar a predefinição da **Base de Dados de Conhecimento** no Editor da Web:

No painel Repositório, abra o arquivo de mapa DITA na **Exibição do Mapa** e, na guia **Saída**, selecione o ícone + para criar uma predefinição de saída e selecione **Base de Dados de Conhecimento** na lista suspensa **Tipo** da caixa de diálogo **Nova predefinição de saída**. É possível nomear a predefinição e escolher o destino para gerar a saída usando o **Adobe Experience Manager**, **Salesforce** ou **ServiceNow**.




## Configuração da knowledge base{#knowledge-base-configuration}


No editor da Web, as configurações a seguir foram organizadas nas guias **Geral** e **Artigos**. Você também pode definir as configurações da **Base de Dados de Conhecimento** específica que você selecionou como destino, **Adobe Experience Manager**, **Salesforce** ou **ServiceNow**.


### Geral

| Opções da knowledge base | Descrição |
| --- | --- |
| Aplicar condições usando | Selecione uma das seguintes opções:<br><br>* **Nenhuma aplicada**: selecione esta opção se não quiser aplicar nenhuma condição na saída publicada.<br>* **Arquivo DITAVAL**: selecione o(s) arquivo(s) DITAVAL para gerar conteúdo personalizado. Você pode selecionar vários arquivos DITAVAL usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVAL são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVAL for movido para outro local ou excluído, ele não será excluído automaticamente da predefinição. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para visualizar o caminho no repositório do Adobe Experience Manager onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVAL, e um erro será exibido se você selecionar qualquer outro tipo de arquivo.<br>* **Predefinição de condição**: selecione uma predefinição de condição na lista suspensa para aplicar uma condição ao publicar a saída. A opção estará visível se você tiver adicionado uma condição na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre predefinições de condição, exiba [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Exibir [Trabalhar com a Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração que contém todos os fluxos de trabalho configurados no Adobe Experience Manager é exibida. Você deve selecionar um workflow que deseja executar após a conclusão da geração de saída.<br><br>**Observação**: saiba mais sobre como [personalizar a seção do fluxo de trabalho de geração de pós-saída](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) no Guia de Instalação e Configuração para Cloud Service. |

### ServiceNow

| Opções do ServiceNow | Descrição |
| --- | --- |
| Perfil do Publish | Use a lista suspensa para selecionar nos perfis de conexão do ServiceNow que o administrador configura. Para saber mais sobre como o administrador pode criar um perfil de publicação, exiba a descrição do recurso **Configurações do editor** na seção [Painel esquerdo](./web-editor-features.md#id2051EA0M0HS). |
| Knowledge Base | Use esse campo para selecionar a Base de conhecimento necessária do ServiceNow. Você pode configurar bases de conhecimento no site ServiceNow para armazenar o conteúdo com base nas permissões. Os artigos desse mapa do DITA podem ser publicados nessas bases de conhecimento. |
| Categoria e subcategoria | As categorias são como árvores hierárquicas usadas para localizar e classificar artigos da Base de Dados de Conhecimento ServiceNow. Adicione uma categoria e subcategoria para publicar os tópicos e subtópicos do índice nessa categoria e subcategoria no site ServiceNow. |

### Salesforce

| Opções do Salesforce | Descrição |
| --- | --- |
| Perfil do Publish | Use o menu suspenso para selecionar entre os perfis de conexão do Salesforce que seu administrador configura. Para saber mais sobre como o administrador pode criar um perfil de publicação, exiba a descrição do recurso **Configurações do editor** na seção [Painel esquerdo](./web-editor-features.md#id2051EA0M0HS). |
| Tipo de registro | Use a lista suspensa para selecionar entre os tipos de registro configurados no Salesforce de acordo com as configurações de visibilidade com base no seu perfil de usuário. Os tipos de registro do Salesforce são uma maneira de agrupar muitos registros de um tipo para esse objeto. Elas definem como a publicação é organizada. Por exemplo, você pode selecionar Tipo de registro de perguntas frequentes e publicar de acordo com o layout e os campos da página Perguntas frequentes. |
| Campo de conteúdo do artigo | É possível ter campos diferentes e um layout exclusivo para cada modelo de tipo de registro. Use esses campos para inserir informações específicas, dependendo do tipo de artigo. Por exemplo, você pode visualizar o título, a resposta e a equação de um artigo de Perguntas frequentes. |
| Categorias | Selecione uma categoria na lista suspensa para publicar os tópicos do índice nessa categoria no site do Salesforce. |

Você também pode exibir as seguintes opções nas predefinições do Salesforce e ServiceNow:

| Opções | Descrição |
| --- | --- |
| Remova o cabeçalho do tópico do corpo do artigo. | Selecione essa opção para remover o cabeçalho do tópico do artigo na saída publicada. |
| Carregar como rascunho | Selecione esta opção para fazer upload do tópico e compartilhá-lo como rascunho antes de disponibilizá-lo aos usuários. |
| Carregar imagens | Selecione esta opção se desejar que quaisquer imagens nos tópicos sejam incluídas na saída publicada. |
| Fazer upload de documentos vinculados | Selecione essa opção para incluir os documentos vinculados em tópicos na saída publicada. |


### Adobe Experience Manager

>[!NOTE]
>
>Você pode usar a predefinição da Base de conhecimento Adobe Experience Manager se o administrador a tiver configurado. Para obter mais detalhes, exiba a [publicação baseada em artigo da seção Editor da Web](../install-guide/configure-article-based-publishing.md) no Guia de Instalação e Configuração.

| Opções do Adobe Experience Manager | Descrição |
| --- | --- |
| Usar caminho do artigo | Selecione esta opção para exibir o **Caminho do artigo** da pasta que contém os modelos da Base de Dados de Conhecimento. |
| Caminho do artigo | Este campo aparecerá se você selecionar a opção **Usar caminho do artigo**. Navegue até o site da knowledge base no repositório do Adobe Experience Manager onde a saída está armazenada. |
| Site | Use esse campo para selecionar a Base de conhecimento Adobe Experience Manager necessária. Você pode configurar a base de conhecimento no site do Adobe Experience Manager para armazenar o conteúdo com base nas permissões. Os artigos desse mapa do DITA podem ser publicados nessas bases de conhecimento. |
| Categoria | Selecione uma categoria na lista suspensa para publicar os tópicos do índice nessa categoria no site do Adobe Experience Manager. |
| Modelo de seção e modelo de artigo | Esses são os componentes estruturais usados para organizar o conteúdo da saída. Eles são predefinidos no modelo de site do Adobe Experience Manager. |
| Fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa de Fluxo de trabalho de pós-geração que contém todos os fluxos de trabalho configurados no Adobe Experience Manager é exibida. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída.<br>Saiba mais sobre como [personalizar a seção do fluxo de trabalho de geração pós-saída](../install-guide/customize-workflows.md#id17A6GI004Y4) no Guia de Instalação e Configuração. |

>[!TIP]
> 
>Selecione **Atualizar** ![ícone atualizar](images/navtitle-refresh-icon.svg) para preencher os respectivos modelos nos campos de acordo com o modelo da Base de Dados de Conhecimento selecionado.

### Artigos

Essa guia exibe a árvore ou a exibição hierárquica do mapa. Escolha os tópicos que deseja publicar em uma base de conhecimento. Expanda um nó do índice e escolha os tópicos que deseja publicar.

**Tópico pai:** [Entendendo as predefinições de saída](generate-output-understand-presets.md)
