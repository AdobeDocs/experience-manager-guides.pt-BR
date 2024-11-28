---
title: AEM Sites
description: Crie e configure a predefinição do AEM Sites no Editor da Web e gere a saída do AEM Sites para o mapa DITA, tópicos selecionados e tópicos vinculados.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '2732'
ht-degree: 0%

---

# Predefinições do AEM Sites no Editor da Web


Você pode criar predefinições do AEM Sites no Editor da Web e configurá-las para gerar a saída do AEM Sites. A saída do AEM Sites é baseada no mapeamento de componentes compostos juntamente com o `guides-components`, facilitando a criação e o gerenciamento eficientes de conteúdo.

O Experience Manager Guides fornece modelos predefinidos para a criação de AEM Sites. Essas predefinições ajudam a garantir a consistência no layout e na estrutura do conteúdo.
- [Criar home pages](../cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) com base nesses modelos predefinidos.
- Você pode [editar modelos de tópico](../cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) e aplicar estilos de acordo com suas necessidades.
- Você também pode [personalizar modelos existentes do AEM Sites](../cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).



## Criar predefinições do AEM Sites

Execute as seguintes etapas para criar as predefinições do AEM Sites a partir do Editor da Web:

1. No painel Repositório, abra o arquivo de mapa DITA na Exibição de mapa.
1. Na guia **Saída**, selecione o ícone + para criar uma predefinição de saída.
1. Selecione **AEM Sites** no menu suspenso **Tipo** na caixa de diálogo **Nova predefinição de saída**.
1. Desmarque a opção **Usar mapeamento de componente herdado** da caixa de diálogo **Nova predefinição de saída**.

![Novo(a) ](images/new-aem-sites-dialog-box.png)





>[!NOTE]
>
>Antes de configurar as predefinições do AEM Sites para o Experience Manager Guides, o administrador precisa criar uma estrutura do AEM Sites usando os modelos.
- **Software Local**: saiba mais sobre como [baixar e instalar modelos do AEM Sites](../install-guide/download-install-aem-sites-templates.md) para Software Local.
- **Cloud Service**: saiba mais sobre como [baixar e instalar modelos do AEM Sites](../cs-install-guide/download-install-aem-sites-templates-cs.md) para Cloud Service.




### Adicionar predefinições ao perfil da pasta atual

Como administrador, o Experience Manager Guides permite criar e gerenciar predefinições de saída para os Perfis global e de pasta. Selecione a opção **Adicionar ao perfil de pasta atual** na caixa de diálogo **Nova predefinição de saída** para criar uma predefinição de saída para o perfil de pasta atual. O ícone ![perfil de pasta](images/global-preset-icon.svg) indica uma predefinição de nível de perfil de pasta.  Saiba mais sobre [Gerenciar predefinições de saída de Perfil Global e de Pasta](./web-editor-manage-output-presets.md).

### Predefinições do AEM Sites com base no mapeamento de componente herdado

Também é possível criar as predefinições do AEM Sites usando o mapeamento de componente herdado. Para criar as predefinições do AEM Sites com base no mapeamento de componente herdado, selecione a opção **Usar mapeamento de componente herdado** na caixa de diálogo **Nova predefinição de saída**.

Algumas opções podem diferir para as predefinições que usam o mapeamento de componente herdado.



## Configurar as predefinições do AEM Sites

As configurações estão organizadas nas guias **Geral**, **Conteúdo**, **Lista de tópicos** e **Referências entre mapas**.

![configurações de predefinição do aem sites](images/aem-sites-new-config.png)
**Geral**

A guia **Geral** contém as seguintes configurações relacionadas à geração de saídas:

- Usar caminho do site
- Caminho do site
- Site
- Caminho do Publish
- Modelo de página de tópico
- Gerar nomes de página com base em
   - Nome do arquivo de tópico
   - Título do tópico
- Limpar páginas geradas anteriormente
   - Excluir páginas geradas anteriormente para tópicos removidos do mapa
   - Exclua todas as páginas criadas por outras fontes neste caminho:
- Fluxo de trabalho de pós-geração



**Conteúdo**

A guia **Conteúdo** contém as seguintes configurações:

- Usar Linha de Base
- Filtragem de condição
- Argumentos adicionais da linha de comando DITA-OT
- Metadados
   - Propriedades do arquivo (Assets)
   - Usar propriedades do mapa como fallback


Para obter detalhes, consulte [configuração do AEM Sites](#aem_sites_config).

**Lista de Tópicos**

A **Lista de Tópicos** exibe a lista de tópicos presentes na cópia de trabalho atual do mapa DITA. Por padrão, todos os tópicos são incluídos. Você pode selecionar tópicos específicos e gerar a saída do AEM Sites somente para eles. Por exemplo, você atualizou alguns tópicos para poder publicar somente esses tópicos, em vez de publicar o mapa DITA inteiro.

A guia **Lista de Tópicos** está presente nas predefinições de AEM que não são criadas com base no mapeamento herdado.

**Referências entre mapas**
Esta lista contém tópicos que contêm referências entre mapas com `scope ="peer"`. Você pode especificar o contexto de publicação para uma lista de referências de mapa cruzado com `scope="peer"` para tópicos disponíveis em outros mapas DITA. Essa guia será exibida se você usar a versão do Experience Manager Guides (UUID).



Saiba como [publicar tópicos vinculados](#publish-linked-topics).





## Configuração do AEM Sites {#aem_sites_config}

As seguintes opções estão disponíveis para a saída do AEM Sites:

| Opções do AEM Sites | Descrição |
| --- | --- |
| Usar caminho do site | Use essa opção para publicar seu conteúdo em um Site Experience Manager. Selecione essa opção se você souber o caminho exato do site em que deseja que a saída seja publicada. Além disso, mencione o caminho completo no campo Site path. |
| Caminho do site | Esta opção será exibida se você selecionar a opção **Usar caminho do site**. Navegue pelo caminho exato do site Experience Manager onde deseja que a saída seja publicada. |
| Site | Nome da Experience Manager Sites na qual você deseja publicar seu conteúdo. As opções na lista suspensa são preenchidas com base na lista de sites disponíveis no AEM Sites. <br>Selecione **Atualizar** ![ícone de atualização](images/navtitle-refresh-icon.svg) para obter uma nova lista de opções e refletir os dados atualizados. |
| Caminho do Publish | O caminho no repositório AEM onde a saída é armazenada. O Caminho do Publish é preenchido com todos os caminhos que contêm páginas criadas com base no modelo Página inicial. A saída do AEM Sites do mapa DITA é gerada nesse caminho.  Por exemplo, se você especificar o Site como `AEMG-Docs` e o Caminho do Publish como `aemg-docs-en/docs/product-abc.`, a saída do AEM Sites será gerada no nó `aemg-docs-en/docs/product-abc/` em `crx/de`. |
| Modelo de página de tópico | Os componentes estruturais que você pode usar para organizar o conteúdo de forma consistente em vários documentos. Esses modelos são predefinidos no modelo de site do Adobe Experience Manager. As opções são preenchidas com todos os modelos de página de tópico disponíveis para o Site selecionado. Selecione o template que deseja aplicar a todos os tópicos de saída. |
| Gerar nomes de página com base em | **Nome do arquivo de tópico**: usa o nome de arquivo do tópico DITA para criar a URL do Site. <br> **Título do tópico**: usa o título do tópico DITA para criar os nomes de site de Experience Manager. |
| Limpar páginas geradas anteriormente | - **Excluir páginas geradas anteriormente para tópico removido do mapa**: se a estrutura do mapa de DTIA for alterada, você poderá usar esta opção para remover as páginas geradas anteriormente para os tópicos removidos. Esse recurso está disponível somente para publicação de mapa completo.<br><br>Digamos que você tenha publicado um mapa DITA, que contém os tópicos a.dita, b.dita e c.dita. Antes de publicar o mapa novamente, você removeu o tópico b.dita do mapa. Agora, se você selecionou essa opção, todo o conteúdo relacionado a b.dita é removido da saída do AEM Sites e somente a.dita e c.dita são publicados.<br><br>**Observação**: informações sobre páginas excluídas também são capturadas nos logs de geração de saída. Para obter mais informações sobre como acessar os arquivos de log, [Exiba e verifique o arquivo de log](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Cuidado**: ao excluir os tópicos, as páginas ficam indisponíveis no site publicado. Portanto, antes que os tópicos sejam excluídos, um aviso é exibido. Você deve confirmar a exclusão deles.<br><br>- **Excluir todas as páginas criadas por outras fontes neste caminho**: se você selecionar esta opção, todas as páginas publicadas neste caminho de outros mapas, tópicos individuais ou qualquer outra fonte serão excluídas. As páginas também se tornam indisponíveis no site publicado. Portanto, antes que os tópicos sejam excluídos, um aviso é exibido. Você deve confirmar a exclusão deles. |
| Fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída. |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>**Importante**: quando você está gerando saída incremental para o Site AEM, a saída é criada usando a versão atual dos arquivos e não a Linha de Base anexada.<br><br>Exibir [Trabalhar com a Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Filtragem condicional | Selecione uma das seguintes opções:<br><br>**None**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.<br>**Usando DITAVAL**: selecione o(s) arquivo(s) DITAVal para gerar conteúdo condicional. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para visualizar o caminho no repositório AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você selecionar qualquer outro tipo de arquivo.<br>**Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. Essa opção estará visível se você tiver adicionado uma condição para o arquivo de mapa DITA. As configurações condicionais estão disponíveis na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, exiba [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Argumentos adicionais da linha de comando DITA-OT | Especifique os argumentos adicionais que você deseja que o DITA-OT processe ao gerar saída. Para obter detalhes sobre os argumentos de linha de comando com suporte no DITA-OT, exiba a [documentação do DITA-OT](https://www.dita-ot.org/). |
| Metadados <br> Propriedades de <br>Arquivo (Assets) | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa aparecem no campo **Propriedades do arquivo**. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>**Observação**: as propriedades de metadados diferenciam maiúsculas de minúsculas.<br><br>*Se você tiver selecionado uma Linha de Base, os valores das propriedades serão baseados na versão da Linha de Base selecionada.<br>* Se você não tiver selecionado uma Linha de Base, os valores das propriedades serão baseados na versão mais recente.<br><br>Você também pode passar os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Passe os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Observação**: se você não tiver definido a `cq:tags` na opção Propriedades, os valores de `cq:tags` serão escolhidos na cópia de trabalho atual, mesmo que você tenha selecionado uma Linha de Base para publicação. |
| Metadados <br> <br>Usar propriedades do mapa como fallback | Se essa opção for selecionada, as propriedades definidas para o arquivo de mapa também serão copiadas para os tópicos em que essas propriedades não estão definidas. Considere os seguintes pontos ao usar esta opção:<br><br>*Somente as propriedades String, Date ou Long (único e de vários valores) podem ser passadas para as páginas do Site do AEM.<br>* Os valores de metadados de uma propriedade do tipo Cadeia de Caracteres não dão suporte a caracteres especiais (como `@, #, " "`).<br>* Esta opção deve ser usada com a opção `Properties`. |
| Reter arquivos temporários | Selecione essa opção para manter os arquivos temporários gerados pelo DITA-OT. Se ocorrerem erros durante a geração de saída pelo DITA-OT, selecione essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar erros de geração de saída.<br> <br> Depois de gerar a saída, selecione o ícone **Baixar arquivos temporários** ![baixar arquivos temporários](images/download-temp-files-icon.png) para baixar a pasta ZIP que contém os arquivos temporários. <br><br> **Observação**: se as propriedades do arquivo forem adicionadas durante a geração, os arquivos temporários de saída também incluirão um arquivo *metadata.xml* contendo essas propriedades. |


### Gerar a saída do AEM Sites usando os templates

O Experience Manager Guides permite usar os modelos prontos para uso ou adicionar seus próprios modelos do AEM Sites.

Antes de configurar as predefinições do AEM Sites, crie uma estrutura do AEM Sites usando os modelos.\
Para obter mais detalhes, consulte [Baixar e instalar modelos do AEM Sites](../install-guide/download-install-aem-sites-templates.md).



Execute as seguintes etapas para criar e configurar uma predefinição do AEM Sites:
1. Abra a guia **Predefinições de saída** do mapa DITA que deseja publicar.
1. Selecione a predefinição de saída **AEM Sites**.
1. (Opcional) Desmarque a opção **Usar mapeamento de componente herdado** para criar uma predefinição de AEM Sites não herdada.
1. Clique em **Adicionar**. A predefinição do AEM Sites é criada.
1. Você pode configurar o modelo de Sites pronto para uso de duas maneiras:
   1. Selecione **Site** e escolha o caminho de publicação e os modelos de página de tópico entre as opções preenchidas:
      1. Selecione o site.
      1. Selecione **Site**. Por exemplo, `AEMG Docs`.
      1. As opções **caminho do Publish** e **modelo de página de Tópico** são definidas automaticamente na lista suspensa. Você também pode escolher as opções. Por exemplo, `AEMG-Docs-Site/en/docs/product1` e `Topic page` estão definidos respectivamente.
   1. Selecione o caminho completo do site:
      1. Selecione a opção **Usar caminho do site**.
      1. Selecione o caminho completo do site. Por exemplo, `/content/AEMG-Docs-Site/en/docs/product1`.
      1. O &quot;Modelo de página de tópico&quot; é automaticamente definido como `Topic Page`.


1. Salvar as alterações feitas na predefinição.
1. Selecione a opção **Gerar**.
1. Gere AEM Sites para o mapa correspondente. Por exemplo, `/content/AEMG-Docs-Site/en/docs/product`.


   >[!NOTE]
   >
   > Se você estiver publicando conteúdo em um site AEM pela primeira vez, é recomendável publicar as páginas no nível do site. Isso garante que a saída seja exibida corretamente na instância do **Publish**, sem interrupção de CSS.



### Tópicos vinculados do Publish

O Experience Manager Guides simplifica a publicação de documentos complexos permitindo que você crie referências de tópico usando o `peer @scope`. Em seguida, você pode definir o contexto de publicação dessas referências a partir das predefinições do AEM Sites e, finalmente, gerar a saída dos tópicos vinculados.
Para obter mais detalhes, exiba [Gerar saída de tópicos de vinculação de outros mapas](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).




Execute as seguintes etapas para especificar o contexto de publicação para arquivos com links cruzados:
1. Abra a guia **Predefinições de saída** do mapa DITA que deseja publicar.
1. Selecione a predefinição de saída **AEM Sites**.

   Você pode exibir as guias **Geral**, **Conteúdo**, **Lista de tópicos** e **Referências entre mapas**. A guia **Referências de mapa cruzado** será exibida se você usar a versão do Experience Manager Guides (UUID).

   Você não poderá exibir a vinculação entre mapas nos seguintes casos:
   - Para as predefinições criadas antes da versão 4.6. A guia Referências cruzadas está desativada e uma dica de ferramenta, Consulte Painel de mapa é exibida.
   - Para predefinições criadas no painel de mapa. Consulte A dica de ferramenta do painel de mapa é exibida.
   - Para predefinições OOTB, consulte Dica de ferramenta do painel de Mapa.
   - Para predefinições globais, crie uma cópia local dessa predefinição global para definir referências de mapa cruzado.
Se quiser usar predefinições do AEM Sites no Editor da Web, crie uma nova predefinição ou duplique a existente.

1. Abra a guia **Referências entre mapas**.

   Você verá uma lista de tópicos e suas referências. Você pode especificar o contexto de publicação para uma lista de referências a tópicos disponíveis em outros mapas DITA com `scope="peer"`.

   Para usar o painel de referência entre mapas do Editor da Web, `<xrefs>` deve ter IDs exclusivas. IDs exclusivas para `<xrefs>` serão geradas automaticamente ao editar/salvar o conteúdo mais antigo se a ID não estiver lá.

   >[!NOTE]
   >
   >A guia **Referências de mapa cruzado** mostra tópicos que estão vinculados usando somente o `scope="peer"`. Para links com `scope="local"`, não é necessário especificar o contexto de publicação.

   Todos os tópicos vinculados têm sua predefinição de saída e mapa mais recentes selecionados por padrão. O contexto de publicação para todos os tópicos vinculados está definido como `<Most recently generated>` mapear por padrão.

   ![Referências entre mapas](images/aem-sites-cross-map-references.png)

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
