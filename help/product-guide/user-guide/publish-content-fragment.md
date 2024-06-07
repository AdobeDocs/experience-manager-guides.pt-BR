---
title: Publicar um tópico em um fragmento de conteúdo
description: Publique um tópico ou os elementos dentro de um tópico em um Fragmento de conteúdo nas Guias do AEM.  Saiba como visualizar os Fragmentos de conteúdo presentes em um tópico e republicá-los.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
source-git-commit: 7c7e3dcddf733793a5d6db50205ba60d24702451
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 0%

---

# Publicar fragmentos de conteúdo

Fragmentos de conteúdo são partes distintas do conteúdo no Adobe Experience Manager. São conteúdos estruturados com base em um modelo de conteúdo. Fragmentos de conteúdo são conteúdo puro sem informações de design ou layout. Eles podem ser criados e gerenciados independentemente dos canais compatíveis com o Adobe Experience Manager. Os fragmentos de conteúdo são modulares, em que o conteúdo é dividido em componentes menores.

O Adobe Experience Manager Guides permite publicar um tópico ou os elementos dentro de um tópico em um Fragmento de conteúdo. Você pode criar um mapeamento baseado em JSON entre um tópico e um modelo de Fragmento de conteúdo. Use esse mapeamento para publicar um tópico ou os elementos dentro de um tópico em um Fragmento de conteúdo. Em seguida, você pode usar Fragmentos de conteúdo em qualquer site do Adobe Experience Manager ou extrair os detalhes por meio de APIs compatíveis com Fragmentos de conteúdo.


Para criar um fragmento de conteúdo, execute as seguintes etapas:

1. Criar um [Modelo de fragmento de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=pt-BR) no Adobe Experience Manager Assets.
1. Crie uma pasta na qual deseja salvar os fragmentos de conteúdo criados com base no modelo de fragmento de conteúdo. Por exemplo, &quot;stock-content-fragments&quot;.
1. Edite as propriedades da pasta (por exemplo, &quot;stock-content-fragments&quot;) e adicione o caminho da pasta, que contém o modelo de Fragmento de conteúdo na configuração da nuvem.
Por exemplo, adicione `/conf/we-retail` na configuração da nuvem. Essa configuração conecta todos os modelos de fragmento de conteúdo à pasta.\
   ![adicionar detalhes de configuração da nuvem nas propriedades da pasta](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Adicione a configuração da nuvem nas propriedades da pasta para conectá-la aos modelos de fragmento.*

1. Para gerar um fragmento de conteúdo, selecione **Nova saída** ![novo ícone de saída](./images/Add_icon.svg) do **Saídas** na seção **Propriedades do arquivo** de um tópico.
1. Selecionar **Fragmento do conteúdo**.\
   ![guia opções de propriedades do arquivo](./images/file-properties-outputs-tab.png){width="300" align="left"}

   *Adicionar um novo Fragmento de conteúdo das Propriedades do arquivo de um tópico*.

1. No **Gerar fragmento de conteúdo** preencha os seguintes detalhes:
   ![Adicionar o modelo de fragmento e os detalhes de mapeamento na caixa de diálogo Publicar como fragmento de conteúdo](images/content-fragment-publish.png){width="500" align="left"}
   *Adicione o caminho, o modelo e os detalhes de mapeamento para publicar um tópico ou seus elementos como um Fragmento de conteúdo. É possível substituir um fragmento de conteúdo existente.*

   >[!NOTE]
   >
   >Também é possível publicar um fragmento de conteúdo da **Visualização do repositório**. Selecione o tópico que deseja publicar como um Fragmento de conteúdo. Em seguida, do **Opções** selecione **Publicar como** > **Fragmento do conteúdo**.

   * **Caminho**: procure e selecione o caminho da pasta em que deseja publicar o fragmento de conteúdo. Se você selecionar um fragmento de conteúdo existente, ele substituirá o conteúdo dos campos mapeados.
   * **Título**: digite o título do fragmento de conteúdo. Por padrão, o título é preenchido com o título do tópico. Você pode editá-lo. Esse título é usado para gerar o nome do fragmento de conteúdo.
   * **Nome**: digite o nome do fragmento de conteúdo. Por padrão, o nome é preenchido com o título do tópico e os espaços são substituídos por &quot;_&quot;. Por exemplo, *sample_content_fragment*. Você pode editá-lo.  Esse nome é usado para gerar o URL do fragmento de conteúdo.
   * **Modelo**: selecione o modelo de Fragmento de conteúdo que deseja usar para criar o Fragmento de conteúdo. Os modelos são selecionados da pasta, que você configurou nos serviços em nuvem.
   * **Mapeamento**: selecione um mapeamento no menu suspenso. Ele escolhe os mapeamentos do *contentFragmentMapping.json* arquivo.



     O administrador pode adicionar os mapeamentos no *contentFragmentMapping.json* arquivo. Saiba como [criar um mapeamento entre um tópico e um Fragmento de conteúdo](../cs-install-guide/conf-content-fragment-mapping-cs.md) no Guia de instalação e configuração.

   * Você também pode selecionar condições diferentes para publicar o conteúdo.  Selecione uma das seguintes opções:


      * **Nenhum**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.
      * **Uso de DITAVAL**: selecione o arquivo DITAVAL para gerar a saída, que inclui conteúdo específico. Você pode selecionar o arquivo DITAVAL usando a caixa de diálogo Procurar ou digitando o caminho do arquivo.
      * **Uso de atributos**: você pode definir atributos de condição em seus tópicos DITA. Em seguida, selecione o atributo de condição para publicar o conteúdo relevante.
     >[!NOTE]
     > 
     >As condições serão ativadas somente se os atributos de condição forem definidos no tópico.



   * Selecionar **Substituir conteúdo existente** se o fragmento de conteúdo já existir e você desejar substituí-lo. Os Guias de Experience Manager exibem um erro se você não marcar a caixa de seleção e o Fragmento de conteúdo já existir.
1. Clique em **Gerar** para publicar o fragmento de conteúdo.

1. É possível exibir os Fragmentos de conteúdo de um tópico na **Saídas** na seção **Propriedades do arquivo**.

   ![Exibir os Fragmentos de conteúdo de um tópico](images/outputs-options-menu.png){width="300" align="left"}

   *Visualize os Fragmentos de conteúdo presentes em um tópico e publique-os novamente.*


Depois de publicar os fragmentos de conteúdo, você também pode usá-los em qualquer site do Adobe Experience Manager.




## Menu Opções para um Fragmento de conteúdo

Também é possível executar as seguintes ações para um Fragmento de conteúdo da **Opções** menu:

* **Gerar**: publique novamente o fragmento de conteúdo para atualizá-lo com o conteúdo mais recente do tópico DITA. Ao gerar novamente a saída, não é possível alterar o caminho, o nome, o título, o modelo e o mapeamento do fragmento de conteúdo. No entanto, você pode selecionar condições diferentes ao regenerar a saída.

* **Duplicar**: duplicar um fragmento de conteúdo. É possível alterar o caminho, o nome, o título, o modelo e o mapeamento. Você também pode selecionar condições diferentes ao duplicar um fragmento de conteúdo.

* **Remover**: remova um fragmento do conteúdo da lista de saídas. Um prompt de confirmação é exibido. Depois de confirmar, o fragmento de conteúdo é removido da **Saídas** lista.

  >[!NOTE]
  >
  > Nenhum conteúdo é excluído do fragmento de conteúdo por esta ação.

* **Exibir**: visualize o editor de Fragmento de conteúdo. Você também pode fazer alterações e salvá-las.


