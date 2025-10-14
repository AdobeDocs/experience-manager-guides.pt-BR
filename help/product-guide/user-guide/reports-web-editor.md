---
title: Relatório de mapa DITA do Console do mapa de guias
description: Gerar relatórios de mapa DITA no console de mapas no AEM Guides. Saiba como visualizar e baixar a planilha do Excel para relatórios de lista de tópicos, multimídia, metadados e links quebrados.
exl-id: 2f202b41-85d9-4a5a-aa28-e25715ce5e2e
feature: Report Generation
role: User
source-git-commit: 0d713f9ff4bd48aa90bce368d6ad7abf86ecbbf7
workflow-type: tm+mt
source-wordcount: '2614'
ht-degree: 0%

---

# Relatório de mapa DITA no Console do mapa {#id231HF0Z0NXA}

O Adobe Experience Manager Guides vem com um recurso no console Mapa que permite verificar a integridade geral do mapa e gerar relatórios para ele.

Você pode exibir a lista de tópicos, gerenciar os metadados de todas as referências, exibir a lista multimídia e corrigir todos os links com falha do mapa atual na guia **Relatórios** do Console de Mapa, que você pode acessar da seguinte maneira:

1. No painel **Repositório**, abra o arquivo de mapa DITA no modo de exibição Mapa.

   >[!NOTE]
   >
   > Você também pode abrir um mapa DITA diretamente na guia **Console do mapa** do menu suspenso no canto superior esquerdo da home page.

1. Selecione o ícone **Abrir no console de mapa**.

   ![](images/map-console.png){width="600" align="left"}

1. Selecione **Relatórios** no painel esquerdo.

Você pode localizar todos os quatro relatórios do painel **Relatórios**. Com base em suas necessidades, você pode selecionar qualquer um dos relatórios mostrados aqui.

![](images/reports-demo.png){align="left"}

O painel Relatórios fornece acesso a quatro tipos diferentes de relatórios. Cada relatório, juntamente com sua acessibilidade e recursos, é discutido detalhadamente abaixo.


## Relatório da lista de tópicos

O relatório **Lista de Tópicos** fornece informações detalhadas sobre seus tópicos, como tipo de referência, estado do documento e autor.

Você pode exibir o relatório da lista de tópicos de um mapa executando as seguintes etapas:

1. Selecione **Lista de Tópicos** no painel Relatórios. A lista de tópicos presentes no mapa DITA é exibida.

   ![](images/web-editor-topiclist-panel-new.png){align="left"}

1. No painel **Filtros**, você pode filtrar seus tópicos com base no **Tipo de referência** \(direto ou indireto\), **Estado do Documento** \(por exemplo, se os tópicos estiverem no estado Editar, Em Revisão ou Revisado, eles serão listados\) ou no **Autor** do tópico.

   >[!NOTE]
   >
   > Todos os filtros fornecem uma lista completa das opções presentes no sistema.


1. Você também pode usar as seguintes opções de filtragem de tópico para exibir as seguintes colunas na lista:

   - **Título** O título do tópico é especificado no mapa DITA. Você pode selecionar o tópico para editá-lo.
   - **Nome do Arquivo** Nome do arquivo.
   - **UUID** O identificador exclusivo universalmente \(UUID\) do arquivo.
   - **Local do Arquivo** O caminho completo do tópico.
   - **Tipo de Referência** O tipo de referência - direta ou indireta.
   - **Estado do Documento** O estado do tópico.
   - **Autor** O usuário que trabalhou por último no tópico. A lista é paginada e carregada de forma assíncrona, mostrando um conjunto limitado de usuários de cada vez e buscando mais à medida que você rola a tela ou navega. Isso melhora a velocidade de carregamento e o desempenho geral, especialmente ao trabalhar com um grande número de usuários.
   - **Mapa Pai** A lista de todos os mapas nos quais o tópico é referenciado diretamente.
   >[!NOTE]
   >
   > Selecione **Atualizar** para obter uma nova lista de tópicos e exibir qualquer alteração no arquivo de mapa ou se qualquer referência no arquivo de tópico for atualizada.

1. Selecione **Baixar** para baixar o instantâneo de todos os tópicos do mapa DITA. A planilha do Excel contém as colunas selecionadas e os tópicos filtrados na exibição **Lista de Tópicos**.

## Relatório de metadados

O **Relatório de metadados** fornece um relatório detalhado de suas referências no mapa DITA atual, como tipo de referência, estado do documento, marcas, local de arquivo etc.

Você pode exibir o relatório de metadados de um mapa executando as seguintes etapas:

1. Selecione **Metadados** no painel Relatórios. A lista de todas as referências de um mapa é exibida junto com seus metadados, como tags, estado do documento e metadados personalizados. Para adicionar uma nova coluna de metadados personalizada, consulte a seção [Adicionar colunas de metadados personalizados](#add-custom-metadata-columns).


   ![](images/web-editor-metadata-panel-new.png){align="left"}


1. No painel **Filtros**, você pode filtrar seus tópicos com base no **Estado do Documento** \(por exemplo, se os tópicos estiverem no estado Editar, Em Revisão ou Revisado, eles serão listados\), **Referências** \(direto ou indireto\), **Tipo de Arquivo** \(Mapa, Tópico, Documento, Imagem, Vídeo e Outros\) da referência.

   >[!NOTE]
   >
   > Todos os filtros fornecem uma lista completa das opções presentes no sistema.

1. Você também pode optar por exibir somente os **Arquivos sem marcas** ou escolher marcas específicas no filtro **Marcas** para exibir os arquivos associados a eles.
1. Você também pode usar as seguintes opções de filtragem de tópico para exibir as seguintes colunas na lista de metadados:
   - **Título** \(selecionado por padrão\) O título do arquivo referenciado é especificado no mapa DITA. Você pode selecionar o arquivo para editá-lo.

     >[!NOTE]
     >
     > Um ícone de check-out também é exibido próximo ao título de um arquivo com check-out. Você pode passar o mouse sobre o ícone para visualizar o nome do usuário.

   - **Nome do Arquivo** O nome do arquivo.
   - **Local do Arquivo** O caminho completo do arquivo.
   - **UUID** O identificador exclusivo universalmente \(UUID\) do arquivo.
   - **Marcas** \(selecionada por padrão\) Marcas aplicadas ao arquivo.

     >[!NOTE]
     >
     > Por padrão, você pode exibir duas tags para um arquivo. Para exibir mais marcas, selecione **Mostrar Mais**. Selecione **Mostrar menos** para contrair a lista novamente.

   - **Estado do Documento** \(selecionado por padrão\) O estado atual do arquivo de referência.
   - **Tipo de Referência** O tipo de referência - direta ou indireta
   - **Tipo de Arquivo** \(selecionado por padrão\) Tipo do arquivo de origem. As opções disponíveis são Mapa, Tópico e Imagem.
   - **Bloqueado por** O usuário que bloqueou o arquivo.


1. Selecione **Baixar** para baixar o instantâneo de todas as referências no mapa DITA. A planilha do Excel contém as colunas selecionadas e as referências filtradas na exibição **Metadados**.

### Gerenciar metadados em massa a partir do Relatório de metadados

Você pode aplicar tags a um tópico individual ou usar o recurso de marcação em massa para aplicar várias tags a vários tópicos, um mapa DITA ou um submapa. Você também pode alterar o estado do documento de todos os tópicos selecionados para o próximo estado de documento comum possível.


### Atualizar metadados

Para atualizar os metadados, execute as seguintes etapas:

1. Para atualizar metadados, selecione os arquivos que deseja atualizar. Você pode selecionar os arquivos que estão aparecendo no painel Metadados, marcando a caixa de seleção que aparece ao lado de **Título**. Se quiser selecionar todos os registros, use a guia **Selecionar tudo** acima da barra de Título, conforme mostrado abaixo.

   >[!NOTE]
   >
   > Não é possível selecionar arquivos com check-out. Um ícone de check-out também é exibido próximo ao título de um arquivo com check-out. Você pode passar o mouse sobre o ícone para visualizar o nome do usuário.

   ![](images/all-selection.png){align="left"}


1. Selecione **Gerenciar** de cima.

   ![](images/web-editor-manage-metadata.png){width="350" align="left"}

1. Se quiser adicionar novas tags, selecione novas tags na lista suspensa para aplicá-las a todos os tópicos selecionados. Também é possível excluir qualquer tag ao selecionar o ícone de cruz próximo à tag.

   >[!NOTE]
   >
   > As tags comuns aplicadas em todos os tópicos selecionados são listadas.

1. Selecione um novo estado do documento se desejar alterar o estado do documento de todas as referências selecionadas. O menu suspenso exibe o estado comum possível de todos os tópicos selecionados. Por exemplo, se o estado atual dos tópicos for Em revisão, você poderá exibir o estado Rascunho, Aprovado ou Revisado.
1. Selecione **Atualizar** para atualizar os metadados. Uma mensagem de confirmação é exibida para os metadados, independentemente de ela ser atualizada com sucesso ou ter atualizações com falha. Você também pode selecionar **Baixar relatório** para baixar o instantâneo do relatório. Este instantâneo contém os detalhes do status atualizado das referências selecionadas.


### Adicionar colunas de metadados personalizadas

Esse recurso permite adicionar colunas de metadados personalizadas de acordo com o requisito, que são exibidas nos relatórios de metadados. Também oferece maior flexibilidade nos relatórios de metadados. Para adicionar uma nova coluna de metadados personalizada, execute as seguintes etapas:

1. Para adicionar uma coluna de metadados personalizada, selecione **Configurações do Workspace** (aparecendo como **Configurações** para **No local**) nos três pontos no canto superior direito da página de metadados.

   ![](images/custom-metadata-setting.png){width="600" align="left"}

1. Selecione **Metadados** no painel esquerdo da janela pop-up exibida.
1. Adicione um novo campo de metadados personalizado de acordo com o requisito usando a guia **Adicionar**.

   ![](images/add-custom-metadata.png){width="600" align="left"}

1. Especifique um caminho de metadados específico e um título apropriado para o mesmo que deseja adicionar nas colunas do relatório de metadados. Por exemplo, metadados personalizados com o idioma do título e um caminho específico são adicionados.

   >[!NOTE]
   >
   > Se quiser remover uma coluna de metadados específica, você poderá excluí-la da lista exibida. Além disso, você pode editar o **Rótulo** para alterar o título de exibição da coluna.

   ![](images/added-custom-field.png){width="600" align="left"}



1. Selecione **Salvar** e **Atualizar** a exibição de metadados. Uma nova coluna personalizada **Idioma** foi adicionada à lista de Colunas no painel Filtro.

   >[!NOTE]
   >
   > A adição de uma nova coluna de metadados também é refletida no painel **Histórico de Versão** do Editor. Para obter mais informações, consulte **[Metadados](web-editor-features.md)**.


   ![](images/updated-custom-field.png){width="600" align="left"}


Da mesma forma, você pode seguir as etapas acima para adicionar quaisquer novos campos de metadados personalizados com base em seus requisitos que sejam necessários nos relatórios de metadados.



## Relatório multimídia

O relatório **Multimídia** fornece informações detalhadas sobre a multimídia usada no mapa, como título, tipo \(áudio, vídeo e imagens\), arquivos nos quais a multimídia é usada e o tipo de referência dos arquivos nos quais eles foram usados. Você também pode visualizar a UUID e o local da multimídia no repositório. É possível exibir um relatório multimídia executando as seguintes etapas:

1. Selecione **Multimídia** no painel Relatório. A lista de multimídia presente no mapa DITA é exibida.
1. No painel **Filtros**, você pode ordenar a lista por multimídia ou pelos nomes de usados nas referências.

   - Quando você ordena por **Multimídia**, o nome da multimídia é exibido na primeira coluna e, em seguida, os nomes de todas as referências nas quais eles foram usados são exibidos em outra coluna na mesma linha. Por exemplo, a captura de tela a seguir mostra o arquivo multimídia testSong.mp3 na primeira coluna e duas referências nas quais ele é usado são exibidas na terceira coluna na mesma linha.

     ![](images/multimedia-report-file-order-new.png){width="650" align="left"}

   - Se ordenar por coluna **Usado em**, você verá a exibição transposta na qual os nomes das referências nas quais o multimídia foi usado são listados na primeira coluna, enquanto os nomes de multimídia são listados em outra coluna em linhas separadas. Por exemplo, a captura de tela a seguir mostra os nomes de duas referências \(testing_indiretamente e conteúdo de vídeo Topic\) na primeira coluna e o testSong.mp3 multimídia é exibido na terceira coluna em duas linhas separadas.

     ![](images/multimedia-report-used-in-order-new.png){width="650" align="left"}

1. Você pode filtrar sua multimídia com base no **Tipo de multimídia** e no **Tipo de Referência**. A lista de arquivos multimídia é exibida com base na sua seleção na lista suspensa. Por exemplo, você pode optar por exibir somente as referências de áudio no mapa DITA, e um arquivo mostra somente as referências de áudio usadas nele.

1. Você também pode usar as seguintes opções de filtro para optar por exibir as seguintes colunas na lista:

   - **Multimídia** \(selecionado por padrão\) O título da multimídia é especificado no mapa DITA. É possível selecionar a multimídia para editá-la.
   - **Local da multimídia** O caminho completo da multimídia.
   - **UUID de multimídia** O identificador exclusivo universalmente \(UUID\) do arquivo.
   - **Tipo de multimídia** \(selecionado por padrão\) Tipo de multimídia. As opções disponíveis são Áudio, Vídeo ou Imagem.
   - **Usado em** \(selecionado por padrão\) As referências nas quais a multimídia foi usada. Você pode selecionar a referência para editá-la.
   - **Tipo de Referência** \(selecionado por padrão\) O tipo de referência - direta ou indireta.
   >[!NOTE]
   >
   > Selecione **Atualizar** para obter uma nova lista de multimídia e exibir qualquer alteração no arquivo de mapa ou se qualquer multimídia no mapa DITA for atualizada.

1. Selecione **Baixar** para baixar o instantâneo de todas as multimídia no mapa DITA. A planilha do Excel contém as colunas selecionadas e a multimídia filtrada na exibição **Multimídia**.


## Relatório de links desfeitos

Os **Links desfeitos** são um relatório útil que fornece os detalhes dos links desfeitos presentes no mapa atual. Você pode visualizar os links quebrados, que podem ser para tópicos DITA, referências de arquivos multimídia, referências de chave de conteúdo e assim por diante. Você também pode corrigi-los aqui.
O relatório fornece informações detalhadas, como o link quebrado, o tipo de link, os arquivos nos quais a referência é usada e os tipos de arquivos nos quais eles foram usados.
Você pode exibir o relatório de links desfeitos executando as seguintes etapas:

1. Selecione **Links desfeitos** no painel Relatórios. A lista de links ou referências corrompidos presentes no mapa DITA é exibida.
1. No painel **Filtros**, é possível ordenar a lista por links ou pelos nomes de usados nas referências.

   - Quando você ordena por **Link quebrado**, os caminhos dos links quebrados são exibidos na primeira coluna e, em seguida, os nomes de todas as referências nas quais eles foram usados são exibidos em outra coluna em linhas separadas. Se o mesmo link quebrado for usado em vários arquivos, eles serão exibidos em uma linha e serão mostrados como agrupados ou sublinhas. Por exemplo, a captura de tela a seguir mostra dois links desfeitos na primeira coluna e a referência na qual eles são usados, `m_ElectricalSpecs_900.ditamap`, é exibida na terceira coluna em duas linhas separadas.


   ![](images/broken-link-report-new.png){align="left"}


   - Se ordenar por **Usado na** coluna, você exibirá a exibição transposta na qual os nomes das referências nas quais os links desfeitos foram usados são listados na primeira coluna, enquanto os links desfeitos são listados em outra coluna na mesma linha. Por exemplo, a captura de tela a seguir mostra a referência (em que o link quebrado é usado) `m_ElectricalSpecs_900.ditamap` na primeira coluna e os links quebrados são exibidos na terceira coluna na mesma linha.


   ![](images/broken-link-filter-usedin-new.png){align="left"}


1. Você pode filtrar os links com falha com base no **Tipo de Arquivo** e no **Tipo de Link**. A lista de links com falha é exibida com base na sua seleção na lista suspensa. Por exemplo, você pode optar por exibir apenas as referências de conteúdo no mapa DITA, e um arquivo mostra apenas as referências de conteúdo corrompidas usadas nele.

   Tópico DITA, Mapa DITA, Referência de arquivo, Referência de chave, Referência de conteúdo, Referência de chave de conteúdo, Referência de imagem, Referência de arquivo multimídia e Referência de chave multimídia estão disponíveis para o menu suspenso **Tipo de link**, e Tópico DITA, Mapa DITA, Documento, Imagem, Vídeo, Áudio e outros estão disponíveis para o menu suspenso **Tipo de arquivo**.
1. Você também pode usar as seguintes opções de filtro para optar por exibir as seguintes colunas na lista:

   - **Link quebrado** (selecionado por padrão) O caminho do link quebrado é especificado no mapa DITA.

   - **Tipo de Link** (selecionado por padrão) O tipo dos links. As opções disponíveis são Tópico DITA, Mapa DITA, Referência do arquivo, Referência da chave, Referência do conteúdo, Referência da chave de conteúdo, Referência da imagem, Referência do arquivo multimídia e Referência da chave multimídia.

   - **Usado em** (selecionado por padrão) As referências nas quais o link corrompido foi usado. Você pode selecionar a referência para exibi-la no modo de autor.

   - **Tipo de Arquivo** (selecionado por padrão) O tipo de referência - Tópico DITA, Mapa DITA, Documento, Imagem, Vídeo, Áudio e Outros.

   Selecione **Atualizar** para obter uma nova lista de links com falha e exibir qualquer alteração no arquivo de mapa ou se algum link com falha no mapa DITA for atualizado.
1. Você pode selecionar no ícone **Corrigir link** (![](images/fix-broken-link.svg)) para corrigir o link corrompido.

   >[!NOTE]
   >
   > Passe o mouse sobre o caminho do link quebrado na coluna Link quebrado para exibir o ícone Corrigir link (![](images/fix-broken-link.svg)).

   Você pode corrigir um link em ambos os modos de exibição - quando solicitado por **Links Desfeitos** ou por **Usados em**.

   >[!NOTE]
   >
   > Ao corrigir um link quebrado enquanto ordenava por Links quebrados, o link será corrigido em todos os arquivos onde é usado (que são agrupados em uma única linha).

1. Você precisa atualizar os detalhes de referência necessários na caixa de diálogo **Atualizar Link**. Os detalhes necessários na caixa de diálogo **Atualizar Link** dependeriam do tipo de referência.\
   Depois de corrigir um link, ele não é exibido abaixo da lista de links quebrados. Em vez disso, você pode visualizá-lo na Lista de tópicos ou nos Metadados.

1. Selecione **Baixar** para baixar o instantâneo de todos os links corrompidos no mapa DITA. O arquivo do Excel contém as colunas selecionadas e os links quebrados filtrados na exibição Links quebrados.


**Tópico pai:**&#x200B;[&#x200B; Introdução aos relatórios](reports-intro.md)
