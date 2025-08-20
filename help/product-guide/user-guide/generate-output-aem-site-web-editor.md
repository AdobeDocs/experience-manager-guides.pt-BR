---
title: AEM Sites
description: Crie e configure a predefinição do AEM Sites no console do Mapa usando o mapeamento de componente composto e o mapeamento de componente herdado.
feature: Publishing
role: User
exl-id: f3657268-9dee-43af-b643-499dbc3ca948
source-git-commit: 358d38ca761661eaee7aeac2cc7d46c53105c543
workflow-type: tm+mt
source-wordcount: '3592'
ht-degree: 0%

---

# Predefinição do AEM Sites no console Mapa

Você pode criar uma predefinição do AEM Sites no console Mapa e configurá-la para gerar a saída do AEM Sites. Há duas maneiras de criar a saída do AEM Sites:

- [Usar mapeamento de componente composto](#use-composite-component-mapping)
- [Usar mapeamento de componente herdado](#use-legacy-component-mapping)

>[!TIP]
>
> É recomendável usar o mapeamento de componente composto, disponível na versão Experience Manager Guides 2502, e versões mais recentes, para melhorar o desempenho.

## Usar mapeamento de componente composto

O mapeamento de componentes compostos oferece uma publicação mais rápida e escalável no AEM Sites em comparação ao mapeamento de componentes herdados. Ele vem com modelos editáveis prontos para uso, que podem ser personalizados de acordo com seus requisitos usando o editor de modelos do AEM. Os modelos utilizam uma combinação de componentes principais do WCM e o `guides-components` especializado para garantir que os usuários finais obtenham a melhor experiência nas páginas do AEM Sites. Você também pode personalizar seus modelos existentes usando o método de mapeamento de componentes compostos.

O Experience Manager Guides fornece modelos predefinidos para a criação de AEM Sites. Esses modelos ajudam a garantir a consistência no layout e na estrutura do conteúdo.
- [Criar home pages](../cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) com base nesses modelos predefinidos.
- Você pode [editar modelos de tópico](../cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) e aplicar estilos de acordo com suas necessidades.
- Você também pode [personalizar modelos existentes do AEM Sites](../cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).


**Criar Predefinição Do AEM Sites**

Execute as seguintes etapas para criar a predefinição do AEM Sites usando o mapeamento de componente composto:

1. [Abra o arquivo de mapa DITA no console de mapa](./open-files-map-console.md).
1. No painel **Predefinições de saída**, selecione o ícone + para criar uma predefinição de saída.
1. Selecione **AEM Sites** no menu suspenso **Tipo** na caixa de diálogo **Nova predefinição de saída**.
1. Desmarque a opção **Usar mapeamento de componente herdado**.
1. Selecione a opção **Adicionar ao perfil de pasta atual** para criar uma predefinição de saída no perfil de pasta atual. O ![ícone de perfil de pasta](images/global-preset-icon.svg) indica uma predefinição de nível de perfil de pasta.

   Saiba mais sobre [Gerenciar predefinições de saída de perfil Global e de Pasta](./web-editor-manage-output-presets.md).

1. Selecione **Adicionar**.

   A predefinição do AEM Sites é criada.


   ![Novo(a) ](images/new-aem-sites-dialog-box.png){width="300" align="left"}

<!-----------------------
### Generate the AEM Sites output using the templates

Once, the preset is created, you can configure the various options available for AEM Sites output generation. Experience Manager Guides allows you to use the out of the box templates or add your own AEM Sites templates.

You can configure the Out-of-the-box Sites template  in two ways:

- In the **Sites** field, select the AEM sites where you want to publish your output.  For example, `AEMG Docs`.

    The **Publish path** and the **Topic page template** options are automatically set in the dropdown.  For example,  `AEMG-Docs-Site/en/docs/product1` and `Topic page` are set respectively. You can also choose the other options from the dropdown.

- Or, Select the **Use Sites path** option to select the complete Sites path, and then select a **Map page template**. 

    You can browse a predefined Sites path or specify a custom path even if the specified path has not been pre-created within the AEM Sites structure. In such cases, the system creates the necessary structure during the publishing process by using the selected map homepage template.

   For example, you can specify the path `/content/AEMG-Docs-Site/en/docs/product4` where the `product4`does not exist in the strcuture. In this case, the system automatically creates `product4` using the selected **Map page template** and publish the output within this newly created page. 
   
   The **Topic page template** is automatically set as `Topic Page`. However, you can choose to select other available options in the dropdown.

--->

### Configuração de predefinição do AEM Sites para mapeamento de componente composto

>[!NOTE]
>
> Antes de configurar a predefinição do AEM Sites para o Experience Manager Guides, o administrador precisa criar uma estrutura do AEM Sites usando os modelos.

- **Software Local**: saiba mais sobre como [baixar e instalar modelos do AEM Sites](../install-guide/download-install-aem-sites-templates.md) para Software Local.
- **Cloud Service**: saiba mais sobre como [baixar e instalar modelos do AEM Sites](../cs-install-guide/download-install-aem-sites-templates-cs.md) para Cloud Service.

No console Mapa, as opções de configuração predefinidas para o mapeamento de componentes compostos são organizadas nas seguintes guias:

- Geral
- Conteúdo
- Lista de tópicos
- Referências de mapa cruzado

![Novo(a) ](images/aem-sites-new-config.png){width="650" align="left"}

**Geral**

A guia **Geral** contém as seguintes opções de configuração:

| Opções do AEM Sites | Descrição |
| --- | --- |
| Usar caminho do site | Use essa opção para publicar seu conteúdo em um site do Experience Manager. |
| Caminho do site | **Esta opção aparecerá se você selecionar a opção** Usar caminho do site **&#x200B;**. Procure o caminho predefinido do site do Experience Manager ou especifique um caminho personalizado no qual deseja que a saída seja publicada. A opção **Usar sites** permite especificar o caminho de publicação inteiro mesmo que o caminho especificado não tenha sido pré-criado dentro da estrutura do AEM Sites. Nesses casos, o sistema cria a estrutura necessária durante o processo de publicação usando o modelo de página inicial do mapa selecionado.<br><br>Você também pode usar variáveis ao definir o caminho do Site. Para obter detalhes, exiba [Use variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](./generate-output-use-variables.md) |
| Mapear modelo de página | **Esta opção aparecerá se você selecionar a opção** Usar caminho do site **&#x200B;**. Selecione um modelo que deseja aplicar às páginas iniciais do mapa. |
| Site | Nome da Experience Manager Sites na qual você deseja publicar seu conteúdo. As opções na lista suspensa são preenchidas com base na lista de sites disponíveis no AEM Sites. <br>Selecione **Atualizar** ![ícone de atualização](images/navtitle-refresh-icon.svg) para obter uma nova lista de opções e refletir os dados atualizados. |
| Caminho de publicação | O caminho no repositório do AEM onde a saída é armazenada. O Caminho de publicação é preenchido com todos os caminhos que contêm páginas criadas com base no modelo da Página inicial. A saída do AEM Sites do mapa DITA é gerada nesse caminho.  Por exemplo, se você especificar o Site como `AEMG-Docs` e o Caminho de Publicação como `aemg-docs-en/docs/product-abc.`, a saída do AEM Sites será gerada sob o nó `aemg-docs-en/docs/product-abc/` em `crx/de`. |
| Modelo de página de tópico | Selecione o template que deseja aplicar a todos os tópicos de saída. |
| Gerar nomes de página com base em | **Nome do arquivo de tópico**: usa o nome de arquivo do tópico DITA para criar a URL do Site. <br> **Título do tópico**: usa o título do tópico DITA para criar os nomes de site do Experience Manager. |
| Limpar páginas geradas anteriormente | - **Excluir páginas geradas anteriormente para tópico removido do mapa**: se a estrutura do mapa de DTIA for alterada, você poderá usar esta opção para remover as páginas geradas anteriormente para os tópicos removidos. Esse recurso está disponível somente para publicação de mapa completo.<br><br>Digamos que você tenha publicado um mapa DITA, que contém os tópicos a.dita, b.dita e c.dita. Antes de publicar o mapa novamente, você removeu o tópico b.dita do mapa. Agora, se você selecionou essa opção, todo o conteúdo relacionado a b.dita é removido da saída do AEM Sites e somente a.dita e c.dita são publicados.<br><br>**Observação**: informações sobre páginas excluídas também são capturadas nos logs de geração de saída. Para obter mais informações sobre como acessar os arquivos de log, [Exiba e verifique o arquivo de log](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Cuidado**: ao excluir os tópicos, as páginas ficam indisponíveis no site publicado. Portanto, antes que os tópicos sejam excluídos, um aviso é exibido. Você deve confirmar a exclusão deles.<br><br>- **Excluir todas as páginas criadas por outras fontes neste caminho**: se você selecionar esta opção, todas as páginas publicadas neste caminho de outros mapas, tópicos individuais ou qualquer outra fonte serão excluídas. As páginas também se tornam indisponíveis no site publicado. Portanto, antes que os tópicos sejam excluídos, um aviso é exibido. Você deve confirmar a exclusão deles. |
| Fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída. |

**Conteúdo**

A guia **Conteúdo** contém as seguintes opções de configuração:

| Opções do AEM Sites | Descrição |
| --- | --- |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Exibir [Trabalhar com a Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Filtragem condicional | Selecione uma das seguintes opções:<br><br>**None**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.<br>**Usando DITAVAL**: selecione o(s) arquivo(s) DITAVal para gerar conteúdo condicional. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para visualizar o caminho no repositório do AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você selecionar qualquer outro tipo de arquivo.<br>**Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. Essa opção estará visível se você tiver adicionado uma condição para o arquivo de mapa DITA. As configurações condicionais estão disponíveis na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, exiba [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Argumentos adicionais da linha de comando DITA-OT | Especifique os argumentos adicionais que você deseja que o DITA-OT processe ao gerar saída. Para obter detalhes sobre os argumentos de linha de comando com suporte no DITA-OT, exiba a [documentação do DITA-OT](https://www.dita-ot.org/). |
| Metadados <br> Propriedades de <br>Arquivo (Assets) | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa aparecem no campo **Propriedades do arquivo**. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>**Observação**: as propriedades de metadados diferenciam maiúsculas de minúsculas.<br><br>*Se você tiver selecionado uma Linha de Base, os valores das propriedades serão baseados na versão da Linha de Base selecionada.<br>* Se você não tiver selecionado uma Linha de Base, os valores das propriedades serão baseados na versão mais recente.<br><br>Você também pode passar os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Passe os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Observação**: se você não tiver definido a `cq:tags` na opção Propriedades, os valores de `cq:tags` serão escolhidos na cópia de trabalho atual, mesmo que você tenha selecionado uma Linha de Base para publicação. |
| Metadados <br> <br>Usar propriedades do mapa como fallback | Se essa opção for selecionada, as propriedades definidas para o arquivo de mapa também serão copiadas para os tópicos em que essas propriedades não estão definidas. Considere os seguintes pontos ao usar esta opção:<br><br>*Somente as propriedades String, Date ou Long (único e de vários valores) podem ser passadas para as páginas do site do AEM.<br>* Os valores de metadados de uma propriedade do tipo Cadeia de Caracteres não dão suporte a caracteres especiais (como `@, #, " "`).<br>* Esta opção deve ser usada com a opção `Properties`. |

**Lista de tópicos**

A guia **Lista de tópicos** exibe a lista de tópicos presentes na cópia de trabalho atual do mapa DITA. Por padrão, todos os tópicos são incluídos. Você pode selecionar tópicos específicos e gerar a saída do AEM Sites somente para eles. Por exemplo, você atualizou alguns tópicos para poder publicar somente esses tópicos, em vez de publicar o mapa DITA inteiro.

![lista de tópicos do aem sites](images/aem-presets-topic-list.png) {align="left"}


>[!NOTE]
>
> Quando uma Linha de Base é selecionada na guia **Conteúdo**, a lista de Tópicos exibe os tópicos e suas versões da Linha de Base anexada. Além disso, a publicação incremental da lista de Tópicos deve ser usada somente quando não houver alteração na estrutura do mapa. Se houver uma alteração na estrutura do mapa/índice, o mapa inteiro deverá ser publicado uma vez para atualizar o índice.

**Referências entre mapas**

Esta lista contém tópicos que contêm referências entre mapas com `scope ="peer"`. Você pode especificar o contexto de publicação para uma lista de referências de mapa cruzado com `scope="peer"` para tópicos disponíveis em outros mapas DITA. Essa guia será exibida se você usar a versão do Experience Manager Guides (UUID).

Para obter mais detalhes, consulte a seção [Trabalhando com tópicos vinculados](#working-with-linked-topics) abaixo.

Após a configuração, salve as alterações feitas na predefinição e selecione **Gerar** para gerar o AEM Sites para o mapa correspondente.

>[!NOTE]
>
> Se você estiver publicando conteúdo nos sites do AEM pela primeira vez, é recomendável publicar as páginas no nível do site. Isso garante que a saída seja exibida corretamente na instância **Publish** sem nenhuma interrupção de CSS.

## Usar mapeamento de componente herdado

As etapas para criar a predefinição do AEM Sites usando o mapeamento de componente herdado são as mesmas descritas na seção [Mapeamento de componente composto](#use-composite-component-mapping) acima. No entanto, ao criar a predefinição, certifique-se de selecionar a opção **Usar mapeamento de componente herdado** na caixa de diálogo **Nova predefinição de saída**.

![](images/aem-sites-output-legacy.png) {width="300" align="left"}

No console Mapa, as opções de configuração predefinidas para o mapeamento de componentes herdados são organizadas nas seguintes guias:

- Geral
- Conteúdo
- Referências de mapa cruzado

![Novo(a) ](images/aem-sites-preset-legacy-config.png){width="500" align="left"}

**Geral**

A guia **Geral** contém as seguintes opções de configuração:

| Opções do AEM Sites | Descrição |
| --- | --- |
| Nome do site | Um nome de site em que a saída é armazenada no repositório do AEM.<br><br>Um nó no repositório do AEM é criado com o nome especificado aqui. Se você não especificar o Nome do site, o nó do site será criado com o nome do arquivo de mapa DITA.<br><br>O Nome do Site especificado aqui também é usado como o título na guia do navegador.<br><br>Você também pode usar variáveis ao definir o Nome do Site. Para obter detalhes, exiba [Use variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](./generate-output-use-variables.md) |
| Caminho de saída | O caminho no repositório do AEM onde a saída é armazenada. Ao gerar a saída final, o Nome do site e o Caminho de saída são combinados. Por exemplo, se você especificar o nome do site como `user-guide` e o Caminho de Saída como `/content/output/aem-guides`, a saída final será gerada sob o nó `/content/output/aem-guides/user-guide`.<br><br>Você também pode usar variáveis ao definir o caminho de saída. Para obter detalhes, exiba [Use variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](./generate-output-use-variables.md) |
| Páginas de saída existentes | Selecione a opção **Substituir conteúdo** para substituir o conteúdo nas páginas existentes. Essa opção substitui somente o conteúdo presente nos nós de conteúdo e cabeçalho da página. Essa opção permite a publicação combinada de conteúdo. Selecionar essa opção fornece uma opção para selecionar a exclusão de páginas órfãs da saída publicada. Esta também é a opção *padrão* para criar a saída do AEM Sites.<br><br>Selecione a opção **Excluir e Criar** para forçar a exclusão de páginas existentes durante a publicação. Essa opção exclui o nó da página, juntamente com seu conteúdo e todas as páginas secundárias sob ele. Use essa opção se tiver alterado o modelo de design da predefinição de saída ou se desejar que qualquer página extra já presente no destino seja removida. |
| Excluir páginas geradas anteriormente para tópicos removidos do mapa | Se a estrutura do mapa de DTIA for alterada, você poderá usar essa opção para remover as páginas geradas anteriormente para os tópicos removidos. Esse recurso está disponível somente para publicação de mapa completo.<br><br>Digamos que você tenha publicado um mapa DITA, que contém os tópicos a.dita, b.dita e c.dita. Antes de publicar o mapa novamente, você removeu o tópico b.dita do mapa. Agora, se você selecionou essa opção, todo o conteúdo relacionado a b.dita é removido da saída do AEM Sites e somente a.dita e c.dita são publicados.<br><br>**Observação**: informações sobre páginas excluídas também são capturadas nos logs de geração de saída. Para obter mais informações sobre como acessar os arquivos de log, [Exiba e verifique o arquivo de log](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Cuidado**: ao excluir os tópicos, as páginas ficam indisponíveis no site publicado. Portanto, antes que os tópicos sejam excluídos, um aviso é exibido. Você deve confirmar a exclusão deles. |
| Design | Selecione o modelo de design que deseja usar para gerar a saída.<br><br>Para obter detalhes sobre como usar modelos de design personalizados para gerar saída, contate o administrador de publicação. |
| Fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída. |
| Reter arquivos temporários | Selecione essa opção para manter os arquivos temporários gerados pelo DITA-OT. Se ocorrerem erros durante a geração de saída pelo DITA-OT, selecione essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar erros de geração de saída.<br> <br> Depois de gerar a saída, selecione o ícone **Baixar arquivos temporários** ![baixar arquivos temporários](images/download-temp-files-icon.svg) para baixar a pasta ZIP que contém os arquivos temporários. <br><br> **Observação**: se as propriedades do arquivo forem adicionadas durante a geração, os arquivos temporários de saída também incluirão um arquivo *metadata.xml* contendo essas propriedades. |

**Conteúdo**

![Novo(a) ](images/aem-sites-content-tab.png){width="650" align="left"}

A guia **Conteúdo** contém as seguintes opções de configuração:

| Opções do AEM Sites | Descrição |
| --- | --- |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Exibir [Trabalhar com a Linha de Base](./web-editor-baseline.md) para obter mais detalhes. |
| Filtragem condicional | Selecione uma das seguintes opções:<br><br>**None**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.<br>**Usando DITAVAL**: selecione o(s) arquivo(s) DITAVal para gerar conteúdo condicional. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para visualizar o caminho no repositório do AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você selecionar qualquer outro tipo de arquivo.<br>**Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. Essa opção estará visível se você tiver adicionado uma condição para o arquivo de mapa DITA. As configurações condicionais estão disponíveis na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, exiba [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Metadados <br> Propriedades de <br>Arquivo (Assets) | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa aparecem no campo **Propriedades do arquivo**. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>**Observação**: as propriedades de metadados diferenciam maiúsculas de minúsculas.<br><br>*Se você tiver selecionado uma Linha de Base, os valores das propriedades serão baseados na versão da Linha de Base selecionada.<br>* Se você não tiver selecionado uma Linha de Base, os valores das propriedades serão baseados na versão mais recente.<br><br>Você também pode passar os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Passe os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Observação**: se você não tiver definido a `cq:tags` na opção Propriedades, os valores de `cq:tags` serão escolhidos na cópia de trabalho atual, mesmo que você tenha selecionado uma Linha de Base para publicação. |
| Metadados <br> <br>Usar propriedades do mapa como fallback | Se essa opção for selecionada, as propriedades definidas para o arquivo de mapa também serão copiadas para os tópicos em que essas propriedades não estão definidas. Considere os seguintes pontos ao usar esta opção:<br><br>*Somente as propriedades String, Date ou Long (único e de vários valores) podem ser passadas para as páginas do site do AEM.<br>* Os valores de metadados de uma propriedade do tipo Cadeia de Caracteres não dão suporte a caracteres especiais (como `@, #, " "`).<br>* Esta opção deve ser usada com a opção `Properties`. |

**Referências entre mapas**

Esta lista contém tópicos que contêm referências entre mapas com `scope ="peer"`. Você pode especificar o contexto de publicação para uma lista de referências de mapa cruzado com `scope="peer"` para tópicos disponíveis em outros mapas DITA. Essa guia será exibida se você usar a versão do Experience Manager Guides (UUID).

Para obter mais detalhes, consulte a seção [Trabalhando com tópicos vinculados](#working-with-linked-topics) abaixo.

## Trabalhar com tópicos vinculados

O Experience Manager Guides permite criar referências de tópico usando o `peer @scope`. Em seguida, você pode definir o contexto de publicação dessas referências a partir das predefinições do AEM Sites e, finalmente, gerar a saída dos tópicos vinculados.

Para obter mais detalhes, exiba [Gerar saída de tópicos de vinculação de outros mapas](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).


Execute as seguintes etapas para especificar o contexto de publicação para arquivos com links cruzados:

1. Abra a guia **Referências entre mapas**. Para exibir esta guia, verifique se `<xrefs>` tem IDs exclusivas. IDs exclusivas para `<xrefs>` serão geradas automaticamente ao editar/salvar o conteúdo mais antigo se a ID não estiver lá.

   Você não poderá exibir a vinculação entre mapas nos seguintes casos:
   - Para as predefinições criadas antes da versão 4.6, a guia Referências cruzadas é desabilitada e uma dica de ferramenta, **Consulte o painel de Mapa**, é exibida.
   - Para predefinições criadas no painel de mapa, **Consulte a dica de ferramenta Painel de mapa**.
   - Para predefinições OOTB, **Consulte a dica de ferramenta do painel de Mapa**.
   - Para predefinições globais, crie uma cópia local dessa predefinição global para definir referências entre mapas.


1. Uma lista de tópicos e suas referências é exibida

   >[!NOTE]
   >
   >A guia **Referências de mapa cruzado** mostra tópicos que estão vinculados usando somente o `scope="peer"`. Para links com `scope="local"`, não é necessário especificar o contexto de publicação.

   Todos os tópicos vinculados têm sua predefinição de saída e mapa mais recentes selecionados por padrão. O contexto de publicação para todos os tópicos vinculados está definido como `<Most recently generated>` mapear por padrão.

   ![Referências entre mapas](images/aem-sites-preset-cross-map-references.png)

1. Se quiser usar a saída publicada mais recentemente de cada arquivo dependente no mapa, selecione **Usar contexto de publicação gerado mais recentemente** para todos os tópicos dependentes.
Você deve publicar o mapa selecionado como o mapa principal antes de publicar o mapa contendo tópicos vinculados. Se o mapa com tópicos vinculados não for publicado, os links serão exibidos como texto normal em vez de hiperlinks na saída do AEM Sites.
Você deve selecionar o mesmo tipo de predefinição do AEM Sites para o tópico vinculado. Por exemplo, se a predefinição atual do AEM Sites usar o mapeamento de componente herdado, selecione uma predefinição AEM Sites semelhante do tópico vinculado.
1. Na lista suspensa Mapa Pai, selecione o arquivo de mapa com cuja saída você deseja vincular a saída do mapa atual.
Selecionar um arquivo de mapa mostra a UUID do mapa na coluna UUID do Mapa Pai. As Predefinições de saída associadas ao mapa escolhido são listadas na lista Predefinição do Mapa pai. Por exemplo, o Tópico 1 no Mapa A contém uma referência ao Tópico 2. O tópico 2 pode estar presente em mapas únicos ou múltiplos. Você pode selecionar o mapa principal e uma predefinição específica ou a saída publicada mais recentemente para cada link.

1. Se o mesmo tópico for referido mais de uma vez em um arquivo, será possível adicionar um contexto de publicação diferente para cada instância. Isso proporciona maior flexibilidade e controle sobre o conteúdo. Por exemplo, o Tópico 3 está presente no Mapa B e no Mapa C. O Tópico 1 contém duas referências ao Tópico 3. Você pode escolher o Mapa B como o mapa principal do primeiro link e o Mapa C como principal do segundo link.

1. Na lista suspensa Predefinição do mapa principal, selecione a predefinição de saída com a qual deseja vincular a saída do mapa atual.
   >[!NOTE]
   >
   > As diferentes predefinições de AEM Sites do mapa atual são exibidas na lista suspensa. Se você não selecionar uma predefinição, um ícone de aviso será exibido e a geração de saída falhará.

1. Selecione o mapa necessário e sua predefinição de saída para todos os tópicos de origem e selecione **Gerar**.




**Tópico pai:** [Entendendo as predefinições de saída](generate-output-understand-presets.md)