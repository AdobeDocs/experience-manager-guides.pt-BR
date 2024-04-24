---
title: Site AEM
description: Criar e configurar a predefinição do site AEM nos Guias AEM. Use o suporte do site AEM para gerar saída baseada em artigo, tópicos de vinculação de saída, conref de publicação e pesquisar uma string no conteúdo.
exl-id: 019d9fbf-2f23-4669-8022-d693be75c1c3
feature: Publishing
role: User
source-git-commit: b82f1f3b42f85cce8420d3962c69cd3bafc5728d
workflow-type: tm+mt
source-wordcount: '2621'
ht-degree: 0%

---

# Site AEM {#id205BE3008SW}

As seguintes opções estão disponíveis para a saída do site AEM:

É possível criar a predefinição do site AEM de duas maneiras:

**No Editor da Web:** No painel Repositório, abra o arquivo de mapa DITA na Exibição de mapa e, na guia Saída, selecione o ícone + para criar uma predefinição de saída e selecione Site AEM no menu suspenso de tipo na caixa de diálogo Adicionar predefinição. No editor da Web, as configurações foram organizadas em guias Gerais e Avançadas:

**Geral**

A variável **Geral** contém as seguintes configurações:

- Nome do site
- Caminho de saída
- Páginas de saída existentes
- Excluir páginas de sites órfãos
- Aplicar Condições Usando \(Se as condições forem definidas para um mapa\)
- Usar Linha de Base \(Se uma linha de base for criada para um mapa\)
- Fluxo de trabalho de pós-geração

**Avançado**

A guia Advanced contém as seguintes configurações:

- Baixar arquivos temporários
- Gerar PDF separado para cada tópico
- Usar propriedades do Mapa como Padrão

Para obter detalhes, consulte [Configuração do site AEM](#id231KIM004X1).

**No painel do mapa**

Para abrir predefinições de saída para o Site AEM, clique em um arquivo de mapa DITA na interface do usuário do Assets, clique em Predefinições de saída e, em seguida, clique na opção de saída do Site AEM.No painel de mapa, clique em **Editar** na parte superior para atualizar as várias configurações e clique em **Salvar**.

>[!TIP]
>
> Consulte a *Publicação no site do AEM* no guia de práticas recomendadas para práticas recomendadas sobre a criação de saída do site AEM.

## Configuração do site AEM {#id_aem_site_config}

As seguintes opções estão disponíveis para a saída do site AEM:

| Opções do site do AEM | Descrição |
| --- | --- |
| Tipo de saída | O tipo de saída que você deseja gerar. Para gerar uma saída responsiva do site AEM, escolha a opção AEM Site. |
| Nome de configuração | Dê um nome descritivo para as configurações do site de AEM que você está criando. Por exemplo, você pode especificar *Saída interna de clientes* ou *saída de usuários finais*. |
| Nome do site | Um nome de site em que a saída é armazenada no repositório AEM.<br><br>Um nó no repositório AEM é criado com o nome especificado aqui. Se você não especificar o Nome do site, o nó do site será criado com o nome do arquivo de mapa DITA.<br><br>O Nome do site especificado aqui também é usado como o título na guia do navegador.<br><br>Você também pode usar variáveis ao configurar o Nome do site. Para obter mais detalhes sobre o uso de variáveis, consulte [Use variáveis para definir as opções Caminho de destino, Nome do site ou Nome do arquivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Design | Selecione o modelo de design que deseja usar para gerar a saída.<br><br>Para obter detalhes sobre como usar modelos de design personalizados para gerar saída, entre em contato com o administrador de publicação. |
| Caminho de destino | O caminho no repositório AEM onde a saída é armazenada. Ao gerar a saída final, o Nome do site e o Caminho de destino são combinados. Por exemplo, se você especificar o Nome do site como `user-guide` e o Caminho de destino como `/content/output/aem-guides`, então a saída final é gerada sob o `/content/output/aem-guides/user-guide` nó.<br><br>Você também pode usar variáveis ao definir o Caminho de destino. Para obter mais detalhes sobre o uso de variáveis, consulte [Use variáveis para definir as opções Caminho de destino, Nome do site ou Nome do arquivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Aplicar condições usando | Selecione uma das seguintes opções:<br><br>**Nenhum Aplicado**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.<br>**Arquivo DITAVal**: selecione os arquivos DITAVal para gerar conteúdo condicional. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para ver o caminho no repositório AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você selecionar qualquer outro tipo de arquivo.<br>**Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. Essa opção estará visível se você tiver adicionado uma condição para o arquivo de mapa DITA. As configurações condicionais estão disponíveis na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, consulte [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Páginas de saída existentes | Selecione o **Substituir conteúdo** opção para substituir o conteúdo nas páginas existentes. Essa opção substitui somente o conteúdo presente nos nós de conteúdo e cabeçalho da página. Essa opção permite a publicação combinada de conteúdo. Selecionar essa opção fornece uma opção para selecionar a exclusão de páginas órfãs da saída publicada. Esta é também a *padrão* opção para criar a saída do site AEM.<br><br>Selecione o **Excluir e criar** opção para forçar a exclusão de qualquer página existente durante a publicação. Essa opção exclui o nó da página, juntamente com seu conteúdo e todas as páginas secundárias sob ele. Use essa opção se tiver alterado o modelo de design da predefinição de saída ou se desejar que qualquer página extra já presente no destino seja removida. |
| Excluir páginas de sites órfãos | Selecionar o **Substituir conteúdo** no **Páginas de saída existentes** apresenta essa opção. Se você selecionar essa opção, todas as páginas órfãs serão excluídas do site do AEM publicado. Para que esse recurso seja executado com sucesso, você deve publicar o mapa DITA inteiro e não usar a publicação incremental.<br><br>Digamos que você tenha publicado um mapa DITA, que contém os tópicos a.dita, b.dita e c.dita. Antes de publicar o mapa novamente, você removeu o tópico b.dita do mapa. Agora, se você selecionou essa opção, então todo o conteúdo relacionado a b.dita é removido da saída do site AEM e apenas a.dita e c.dita são publicados.<br><br>Este recurso não remove nenhum mapa filho publicado. Por exemplo, se o mapa principal contiver um mapa secundário e você remover todo o mapa secundário, o conteúdo do mapa secundário não será excluído da saída publicada. No entanto, se você remover qualquer tópico de um mapa secundário e republicar, o conteúdo do tópico removido será excluído da saída do site.<br><br>Além disso, se houver algum conteúdo referenciado e esse conteúdo for removido antes da republicação, os dados do conteúdo referenciado não serão removidos.<br><br>**Nota**: informações sobre páginas órfãs excluídas também são capturadas nos logs de geração de saída. Para obter mais informações sobre o acesso aos arquivos de log, consulte [Exibir e verificar o arquivo de log](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Baixar arquivos temporários | Selecione essa opção para baixar os arquivos temporários gerados pelo DITA-OT. O local onde o DITA-OT armazena arquivos temporários pode ser encontrado no log de geração de saída. Se ocorrerem erros durante a geração de saída pelo DITA-OT, selecione essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar problemas de erros de geração de saída.<br> <br>  Após gerar a saída, selecione o **Baixar arquivos temporários** ![ícone baixar arquivos temporários](images/download-temp-files-icon.png) ícone para baixar a pasta ZIP que contém os arquivos temporários. <br><br> **Nota**: se você selecionar algumas propriedades do arquivo e baixar os arquivos temporários, também receberá a *metadata.xml* arquivo na pasta ZIP. |
| Gerar PDF separado para cada tópico | Se selecionada, um PDF também será criado para cada tópico no mapa DITA. Ao escolher essa opção, uma nova opção Dividir caminho de PDF é exibida.<br><br>No campo Dividir caminho do PDF, especifique o caminho para armazenar os PDF gerados para cada tópico.<br><br>**Nota**: o Guias do AEM usa o plug-in DITA-OT chamado pdfx para gerar o PDF para cada tópico. Esse plug-in é fornecido com o pacote DITA-OT pronto para uso. Você pode personalizar esse plug-in para gerar PDF de acordo com seus requisitos. Se você usar um plug-in DITA-OT personalizado, certifique-se de integrar o plug-in pdfx para ter o recurso de geração de PDF no nível do tópico. |
| Executar fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída. |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>**Importante**: Quando você está gerando uma saída incremental para o Site AEM, a saída é criada usando a versão atual dos arquivos e não a Linha de base anexada.<br><br>Consulte [Trabalhar com linha de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Propriedades do arquivo | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa são exibidas na **Propriedades do arquivo** campo. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>**Nota**: as propriedades dos metadados fazem distinção entre maiúsculas e minúsculas.<br><br>*Se você tiver selecionado uma Linha de Base, os valores das propriedades serão baseados na versão da Linha de Base selecionada.<br>* Se você não tiver selecionado uma Linha de Base, os valores das propriedades serão baseados na versão mais recente.<br><br>Também é possível transmitir os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, consulte [Transmita os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Nota**: Se você não tiver definido a variável `cq:tags` na opção Propriedades, os valores de `cq:tags` são separados da cópia de trabalho atual mesmo se você tiver selecionado uma Linha de base para publicação. |
| Usar Propriedades Do Mapa Se Estiver Ausente No Tópico | Se essa opção for selecionada, as propriedades definidas para o arquivo de mapa também serão copiadas para os tópicos em que essas propriedades não estão definidas. Considere os seguintes pontos ao usar essa opção:<br><br>*Somente as propriedades String, Date ou Long (único e com vários valores) podem ser passadas para as páginas do site AEM.<br>* Os valores de metadados de uma propriedade do tipo String não são compatíveis com caracteres especiais (como `@, #, " "`).<br>* Esta opção deve ser usada juntamente com o `Properties` opção. |

## Observação adicional no site AEM

### Gerar saída baseada em artigo no Editor da Web

Você pode gerar a saída do site AEM para um ou mais tópicos ou para o mapa DITA inteiro do Editor da Web. É necessário criar predefinições de saída para o mapa DITA e, em seguida, gerar facilmente a saída do site AEM para o mapa. Se você atualizou alguns tópicos no mapa, também é possível gerar a saída do site AEM somente para esses tópicos do Editor da Web. Para obter mais detalhes, consulte [Publicação baseada em artigos no Editor da Web](web-editor-article-publishing.md#id218CK0U019I).

### Gerar tópicos de vinculação de saída de outros mapas

É um cenário muito comum ter um grande conjunto de documentações espalhadas em várias pastas e mapas DITA. A publicação de conteúdo vinculado de vários lugares torna-se extremamente complexo. Por padrão, todos os links `<xref>` são criados com o `local` `@scope`. A publicação desses tópicos não envolve nenhum desafio, pois usa um link direto para o tópico. Caso o tópico esteja fora do mapa DITA atual, o link não mostra o conteúdo vinculado.

Outra maneira de vincular conteúdo é criar um link usando o `peer` `@scope`. Para esse conteúdo, o link é resolvido no tempo de execução ao escolher o título do arquivo e o contexto configurado para o tópico vinculado no contexto de publicação do mapa DITA. A captura de tela a seguir mostra o painel Propriedades de um link que tem o `peer` `@scope`:

![](images/peer-link-scope-link.png){width="800" align="left"}

Para simplificar a publicação de mapas complexos e tópicos vinculados a outros tópicos em outros mapas, o AEM Guides permite definir o contexto de publicação para cada predefinição de saída.

O contexto de publicação permite especificar qual tópico deve ser usado, de qual mapa para publicar uma saída específica. Vamos entender isso com a ajuda de um exemplo — digamos que você tenha quatro pastas: amostra a, amostra b, amostra c e amostra d. Cada pasta contém um mapa DITA — mapa DITA A, mapa DITA B, mapa DITA C e mapa DITA D. A vinculação entre mapas ocorrerá quando um tópico no mapa DITA A for vinculado a um tópico no mapa DITA B, C ou D. Na captura de tela a seguir, um tópico de conceito de amostra contém links \(ou referências\) para arquivos que fazem parte de outros mapas DITA.

![](images/sample-concept-link-to-other.png){width="350" align="left"}

Agora, ao definir as configurações de publicação do site AEM para o arquivo de mapa que contém esse tópico, é possível selecionar qual contexto de publicação do conteúdo vinculado será usado durante a publicação. Um contexto de publicação é uma combinação do mapa DITA e sua predefinição de saída. A predefinição de saída, por sua vez, contém uma versão específica do conteúdo e predefinições condicionais. Essa combinação completa do mapa DITA, da predefinição de saída, da versão \(files\) e das condições define o contexto de publicação de um mapa vinculado.

Execute as seguintes etapas para especificar o contexto de publicação para arquivos com links cruzados:

1. Abra o **Predefinições de saída** do mapa DITA que deseja publicar.

1. Selecione o **Site AEM** de saída.

   Você obtém as guias Configurações de predefinições de AEM e Contexto de publicação.

   ![](images/aem-site-publish-settings.png){width="800" align="left"}

1. Abra o **Contexto de publicação** guia.

   Você verá uma lista de tópicos dependentes. Estes são os tópicos que são vinculados a partir de algum tópico no mapa atual, mas estão disponíveis em outros mapas DITA.

   >[!NOTE]
   >
   > A guia Contexto de publicação mostra tópicos que são vinculados usando a `peer` `@scope` somente. Para links com `local` `@scope`, não é necessário especificar o contexto de publicação.

   Por padrão, todos os tópicos vinculados têm sua predefinição de saída e mapa mais recentes selecionados.

   ![](images/default-publish-context.png){width="800" align="left"}

1. Para alterar a seleção padrão do mapa e da predefinição DITA, clique em **Editar** \(na barra de ferramentas principal\).

1. Se quiser usar a saída publicada mais recentemente de cada arquivo dependente no mapa, selecione **Use o contexto de publicação gerado mais recentemente para todos os tópicos dependentes**.

1. No **Mapa principal** selecione o arquivo de mapa com cuja saída você deseja vincular a saída do mapa atual.

   Ao selecionar um arquivo de mapa, a UUID do mapa é mostrada na coluna UUID do mapa principal. As Predefinições de saída associadas ao mapa selecionado são listadas na lista Predefinição do Mapa pai.

1. No **Predefinição do mapa principal** selecione a predefinição de saída com a qual deseja vincular a saída do mapa atual.

1. Selecione o mapa necessário e sua predefinição de saída para todos os tópicos dependentes e clique em **Concluído**.

   O contexto para os tópicos dependentes agora está definido. Você pode gerar a saída para o mapa atual. Para obter mais informações sobre a geração de saída, consulte [Gerar saída para um mapa DITA a partir do console de mapas](generate-output-for-a-dita-map.md#).

### Publicação combinada

O Guias do AEM oferece suporte à publicação de conteúdo DITA no site AEM existente. Por exemplo, se você tiver um site existente, poderá usar a saída do Site AEM para publicar somente o conteúdo DITA nesse site. Nesse processo, o conteúdo não DITA existente não é modificado pelo processo de publicação. Para obter mais informações sobre como configurar seu site para publicar somente conteúdo DITA, entre em contato com o administrador de publicação.

### Publicação `conref`

Se você estiver usando `conref` no conteúdo, ele é publicado como conteúdo normal ou incorporado junto com o conteúdo no tópico de origem \(ou de referência\). A variável `conref` o conteúdo é renderizado junto com o conteúdo principal e nenhuma página do site separada é criada para o mesmo. Quando você pesquisa o conteúdo referido na variável `conref`, em seguida, somente o tópico principal ou a página que contém o `conref` o conteúdo é mostrado nos resultados da pesquisa.

>[!NOTE]
>
>Se você tiver gerado páginas separadas para a variável `conref` conteúdo usando o AEM Guides versão 3.5 ou anterior, recomenda-se limpar/excluir essas páginas usando o [Excluir páginas de sites órfãos](#delete-orphan-page-aem-site) opção.


### Pesquisar uma cadeia de caracteres no conteúdo

Você pode procurar por uma string na saída do site AEM. Por padrão, é possível pesquisar a cadeia de caracteres somente nos títulos. Para pesquisar a string no conteúdo ou no corpo da saída do site AEM, entre em contato com o administrador do sistema para ativar a propriedade flattening.enabled.

![Pesquisar saída do site AEM](images/aem-output-search.png){width="650" align="left"}

Para obter mais detalhes, consulte *Configurar nivelamento da estrutura do nó do site AEM* no guia Instalar e configurar o Adobe Experience Manager Guides.

**Tópico pai:**[ Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
