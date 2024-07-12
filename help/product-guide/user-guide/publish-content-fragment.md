---
title: Publish de um tópico para um fragmento de conteúdo
description: Publish um tópico ou os elementos dentro de um tópico para um Fragmento de conteúdo no AEM Guides.  Saiba como visualizar os Fragmentos de conteúdo presentes em um tópico e republicá-los.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
source-git-commit: 7c7e3dcddf733793a5d6db50205ba60d24702451
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 0%

---

# Fragmentos de conteúdo do Publish

Fragmentos de conteúdo são partes distintas do conteúdo no Adobe Experience Manager. São conteúdos estruturados com base em um modelo de conteúdo. Fragmentos de conteúdo são conteúdo puro sem informações de design ou layout. Eles podem ser criados e gerenciados independentemente dos canais compatíveis com o Adobe Experience Manager. Os fragmentos de conteúdo são modulares, em que o conteúdo é dividido em componentes menores.

O Adobe Experience Manager Guides permite publicar um tópico ou os elementos dentro de um tópico em um Fragmento de conteúdo. Você pode criar um mapeamento baseado em JSON entre um tópico e um modelo de Fragmento de conteúdo. Use esse mapeamento para publicar um tópico ou os elementos dentro de um tópico em um Fragmento de conteúdo. Em seguida, você pode usar Fragmentos de conteúdo em qualquer site do Adobe Experience Manager ou extrair os detalhes por meio de APIs compatíveis com Fragmentos de conteúdo.


Para criar um fragmento de conteúdo, execute as seguintes etapas:

1. Crie um [modelo de Fragmento de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=pt-BR) no Adobe Experience Manager Assets.
1. Crie uma pasta na qual deseja salvar os fragmentos de conteúdo criados com base no modelo de fragmento de conteúdo. Por exemplo, &quot;stock-content-fragments&quot;.
1. Edite as propriedades da pasta (por exemplo, &quot;stock-content-fragments&quot;) e adicione o caminho da pasta, que contém o modelo de Fragmento de conteúdo na configuração da nuvem.
Por exemplo, adicione `/conf/we-retail` na configuração de nuvem. Essa configuração conecta todos os modelos de fragmento de conteúdo à pasta.\
   ![adicionar detalhes de configuração da nuvem nas propriedades da pasta](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Adicione a configuração da nuvem nas propriedades da pasta para conectá-la aos modelos de fragmento.*

1. Para gerar um Fragmento de Conteúdo, selecione **Nova Saída** ![novo ícone de saída](./images/Add_icon.svg) na seção **Saídas** em **Propriedades do Arquivo** de um tópico.
1. Selecione **Fragmento do conteúdo**.\
   ![guia de opções de propriedades do arquivo](./images/file-properties-outputs-tab.png){width="300" align="left"}

   *Adicionar um novo Fragmento de Conteúdo das Propriedades de Arquivo de um tópico*.

1. Na caixa de diálogo **Gerar fragmento de conteúdo**, preencha os seguintes detalhes:
   ![Adicionar o modelo do fragmento e os detalhes do mapeamento na caixa de diálogo Publish como Fragmento de Conteúdo](images/content-fragment-publish.png){width="500" align="left"}
   *Adicione o caminho, o modelo e os detalhes de mapeamento para publicar um tópico ou seus elementos como um Fragmento de conteúdo. É possível substituir um fragmento de conteúdo existente.*

   >[!NOTE]
   >
   >Você também pode publicar um fragmento de conteúdo da **Exibição do repositório**. Selecione o tópico que deseja publicar como um Fragmento de conteúdo. Em seguida, no menu **Opções**, selecione **Publish As** > **Fragmento de Conteúdo**.

   * **Caminho**: procure e selecione o caminho da pasta em que deseja publicar o fragmento de conteúdo. Se você selecionar um fragmento de conteúdo existente, ele substituirá o conteúdo dos campos mapeados.
   * **Título**: digite o título do Fragmento de Conteúdo. Por padrão, o título é preenchido com o título do tópico. Você pode editá-lo. Esse título é usado para gerar o nome do fragmento de conteúdo.
   * **Nome**: digite o nome do Fragmento de Conteúdo. Por padrão, o nome é preenchido com o título do tópico e os espaços são substituídos por &quot;_&quot;. Por exemplo, *sample_content_fragment*. Você pode editá-lo.  Esse nome é usado para gerar o URL do fragmento de conteúdo.
   * **Modelo**: selecione o modelo de Fragmento de Conteúdo que você deseja usar para criar seu Fragmento de Conteúdo. Os modelos são selecionados da pasta, que você configurou nos serviços em nuvem.
   * **Mapeamento**: selecione um mapeamento no menu suspenso. Ele escolhe os mapeamentos do arquivo *contentFragmentMapping.json*.



     O administrador pode adicionar os mapeamentos no arquivo *contentFragmentMapping.json*. Saiba mais sobre como [criar um mapeamento entre um tópico e um Fragmento de conteúdo](../cs-install-guide/conf-content-fragment-mapping-cs.md) no Guia de Instalação e Configuração.

   * Você também pode selecionar condições diferentes para publicar o conteúdo.  Selecione uma das seguintes opções:


      * **Nenhum**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.
      * **Usando DITAVAL**: selecione o arquivo DITAVAL para gerar saída, que inclui conteúdo específico. Você pode selecionar o arquivo DITAVAL usando a caixa de diálogo Procurar ou digitando o caminho do arquivo.
      * **Uso de atributos**: você pode definir atributos de condição em seus tópicos DITA. Em seguida, selecione o atributo de condição para publicar o conteúdo relevante.
     >[!NOTE]
     > 
     >As condições serão ativadas somente se os atributos de condição forem definidos no tópico.



   * Selecione **Substituir conteúdo existente** se o fragmento de conteúdo já existir e você desejar substituí-lo. O Experience Manager Guides exibe um erro se você não marcar a caixa de seleção e o fragmento de conteúdo já existir.
1. Clique em **Gerar** para publicar o fragmento de conteúdo.

1. Você pode exibir os Fragmentos de conteúdo de um tópico na seção **Saídas** em **Propriedades do arquivo**.

   ![Exibir os Fragmentos de Conteúdo de um tópico](images/outputs-options-menu.png){width="300" align="left"}

   *Exiba os Fragmentos de Conteúdo presentes para um tópico e publique-os novamente.*


Depois de publicar os fragmentos de conteúdo, você também pode usá-los em qualquer site do Adobe Experience Manager.




## Menu Opções para um Fragmento de conteúdo

Você também pode executar as seguintes ações para um Fragmento de Conteúdo do menu **Opções**:

* **Gerar**: publique novamente o fragmento de conteúdo para atualizá-lo com o conteúdo mais recente do tópico DITA. Ao gerar novamente a saída, não é possível alterar o caminho, o nome, o título, o modelo e o mapeamento do fragmento de conteúdo. No entanto, você pode selecionar condições diferentes ao regenerar a saída.

* **Duplicar**: duplicar um fragmento de conteúdo. É possível alterar o caminho, o nome, o título, o modelo e o mapeamento. Você também pode selecionar condições diferentes ao duplicar um fragmento de conteúdo.

* **Remover**: remover um fragmento de conteúdo da lista de saídas. Um prompt de confirmação é exibido. Depois de confirmar, o fragmento de conteúdo será removido da lista **Saídas**.

  >[!NOTE]
  >
  > Nenhum conteúdo é excluído do fragmento de conteúdo por esta ação.

* **Exibir**: exibir o editor de Fragmento de Conteúdo. Você também pode fazer alterações e salvá-las.


