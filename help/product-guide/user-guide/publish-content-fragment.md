---
title: Publicar um tópico em um fragmento de conteúdo
description: Publique um tópico ou os elementos dentro de um tópico em um fragmento de conteúdo nos Guias do AEM.  Saiba como visualizar os fragmentos de conteúdo presentes em um tópico e republicá-los.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 0%

---

# Publicar em um fragmento de conteúdo

Fragmentos de conteúdo são partes distintas do conteúdo no AEM. São conteúdos estruturados com base em um modelo de conteúdo. Fragmentos de conteúdo são conteúdo puro sem informações de design ou layout. Eles podem ser criados e gerenciados independentemente dos canais compatíveis com o AEM. Os fragmentos de conteúdo são modulares, em que o conteúdo é dividido em componentes menores.

Guias do AEM permitem publicar um tópico ou os elementos dentro de um tópico em um fragmento de conteúdo. Você pode criar um mapeamento baseado em JSON entre um tópico e um modelo de fragmento de conteúdo. Use esse mapeamento para publicar um tópico ou os elementos dentro de um tópico em um fragmento de conteúdo. Em seguida, você pode usar fragmentos de conteúdo em qualquer site AEM ou extrair os detalhes por meio de APIs compatíveis com fragmentos de conteúdo.


Para criar um fragmento de conteúdo, execute as seguintes etapas:

1. Criar um [modelo de fragmento de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=pt-BR) no AEM Assets.
1. Crie uma pasta onde deseja salvar os fragmentos de conteúdo criados com base no modelo de fragmento de conteúdo. Por exemplo, &quot;stock-content-fragments&quot;.
1. Edite as propriedades da pasta (por exemplo, &quot;stock-content-fragments&quot;) e adicione o caminho da pasta, que contém o modelo de fragmento de conteúdo na configuração da nuvem.
Por exemplo, adicione `/conf/we-retail` na configuração da nuvem. Essa configuração conecta todos os modelos de fragmento de conteúdo com a pasta.\
   ![adicionar detalhes de configuração da nuvem nas propriedades da pasta](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Adicione a configuração da nuvem nas propriedades da pasta para conectá-la aos modelos de fragmento.*
1. Selecione o tópico que deseja publicar na **Visualização do repositório**.
1. No **Opções** selecione **Publicar como** > **Fragmento do conteúdo**.
1. No **Publicar como fragmento de conteúdo** preencha os seguintes detalhes:
   ![Adicionar o modelo de fragmento e os detalhes de mapeamento na caixa de diálogo Publicar como fragmento de conteúdo](images/content-fragment-publish.png){width="500" align="left"}
   *Adicione os detalhes de caminho, modelo e mapeamento para publicar um tópico ou seus elementos como um fragmento de conteúdo. É possível substituir um fragmento de conteúdo existente.*

   * **Caminho**: navegue e selecione o caminho da pasta em que deseja publicar o fragmento de conteúdo. Você também pode selecionar um fragmento de conteúdo existente e publicá-lo.
   * **Título**: insira o título do fragmento de conteúdo.
   * **Nome**: insira o nome do fragmento de conteúdo.
   * **Modelo**: selecione o modelo de fragmento de conteúdo que deseja usar para criar o fragmento de conteúdo. Os modelos são selecionados na pasta que você configurou nos serviços em nuvem.
   * **Mapeamento**: selecione um mapeamento no menu suspenso. Ele escolhe os mapeamentos do *contentFragmentMapping.json* arquivo.



     Com base na sua configuração, o administrador pode adicionar os mapeamentos no *contentFragmentMapping.json* arquivo.

     <details>
        <summary>Cloud Services</summary>

     Saiba como [criar um mapeamento entre um tópico e um fragmento de conteúdo](../cs-install-guide/conf-content-fragment-mapping-cs.md) no Guia de instalação e configuração do Cloud Service.
     </details>

     <details>
        <summary> Software local</summary>

     Saiba como [criar um mapeamento entre um tópico e um fragmento de conteúdo](../install-guide/conf-content-fragment-mapping.md) no Guia de instalação e configuração no local.

     </details>
   * Selecione o **Substituir** se o fragmento de conteúdo já existir e você desejar substituí-lo. O Guias do AEM exibe um erro se você não marcar a caixa de seleção e o fragmento de conteúdo já existir.
1. Clique em **Criar** para publicar o fragmento de conteúdo.
1. Você pode visualizar os fragmentos de conteúdo de um tópico sob o **Fragmentos** na seção **Propriedades do arquivo**.

   ![Exibir os fragmentos de conteúdo de um tópico](images/topic-content-fragments.png){width="300" align="left"}

   *Visualize os fragmentos de conteúdo presentes para um tópico e publique-os novamente.*

Você também pode republicar o fragmento de conteúdo para atualizar o fragmento de conteúdo com o conteúdo mais recente do tópico DITA.



Depois de publicar os fragmentos de conteúdo, você também pode usá-los em qualquer site AEM.
