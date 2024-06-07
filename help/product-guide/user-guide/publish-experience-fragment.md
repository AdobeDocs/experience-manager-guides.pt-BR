---
title: Publicar um tópico em um fragmento de experiência
description: Publique um tópico ou os elementos dentro de um tópico em um Fragmento de experiência nas Guias do AEM.  Saiba como visualizar os Fragmentos de experiência presentes em um tópico e republicá-los.
feature: Publishing
role: User
source-git-commit: 7c7e3dcddf733793a5d6db50205ba60d24702451
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 0%

---


# Publicar fragmentos de experiência

Fragmentos de experiência são conteúdo modular no Adobe Experience Manager. Esses blocos de conteúdo são baseados em modelos e encapsulam o conteúdo e seu layout. Esses conteúdos reutilizáveis permitem que os criadores de conteúdo reúnam e entreguem experiências consistentes e dimensionáveis em vários canais compatíveis com o Experience Manager. Esse recurso ajuda você a criar experiências de marketing consistentes com facilidade, como boletins informativos, banners de promoção e depoimentos de clientes.

Os Guias de Experience Manager permitem publicar um tópico ou seus elementos em um Fragmento de experiência. Você pode criar um mapeamento baseado em JSON entre um tópico e seus elementos em um Fragmento de experiência. Em seguida, use o mapeamento para publicar um tópico ou seus elementos em um Fragmento de experiência. Em seguida, você pode usar Fragmentos de experiência em qualquer site do Experience Manager ou extrair os detalhes por meio de APIs compatíveis com Fragmentos de experiência.




Para gerar um fragmento de experiência, execute as seguintes etapas:


1. Crie uma pasta nos Fragmentos de experiência. Use esta pasta para salvar os Fragmentos de experiência criados com base nos modelos de Fragmento de experiência. Por exemplo, *sales-experience-fragments*.
1. Selecione a pasta e, em seguida, selecione a **Propriedades** ícone na parte superior.
1. Edite as propriedades da pasta (por exemplo, *sales-experience-fragments*).


   * **Título**: visualize ou edite o título da pasta.

   * **Modelos permitidos**: contém a lista de modelos que podem ser adicionados como páginas secundárias do fragmento de experiência. Para adicionar o modelo permitido, especifique a expressão regular para recuperar os modelos necessários na **Modelos permitidos** campo.
Por exemplo:
     `/libs/cq/experience-fragments/components/experiencefragment/template`

     Se você não definir um modelo permitido para uma pasta, os modelos serão escolhidos da pasta principal ou da pasta de modelos por padrão.
   * **Solicitável**: permite alterar a ordem dos ativos dentro de uma pasta.
     ![adicionar detalhes de configuração da nuvem nas propriedades da pasta](images/experience-fragment-folder-properties.png){width="650" align="left"}
     *Adicione a configuração da nuvem nas propriedades da pasta para conectá-la aos modelos de fragmento.*
1. Para gerar um fragmento de experiência, selecione **Nova saída** ![novo ícone de saída](./images/Add_icon.svg) do **Saídas** na seção **Propriedades do arquivo** de um tópico.
1. Selecionar **Fragmento de experiência**.\
   ![guia opções de propriedades do arquivo](./images/file-properties-outputs.png){width="300" align="left"}

   *Adicionar um novo Fragmento de experiência das Propriedades do arquivo de um tópico*.

   >[!NOTE]
   >
   > Você também pode publicar um fragmento de experiência do **Visualização do repositório**. Selecione o tópico que deseja publicar como um Fragmento de experiência. Em seguida, do **Opções** selecione **Publicar como** > **Fragmento de experiência**.

1. No **Gerar fragmento de experiência** preencha os seguintes detalhes:
   ![Adicionar o modelo de fragmento e os detalhes de mapeamento na caixa de diálogo Publicar como fragmento de experiência](images/experience-fragment-generate.png){width="500" align="left"}

   *Adicione o caminho, o modelo e os detalhes de mapeamento para publicar um tópico ou seus elementos como um Fragmento de experiência. Você pode substituir um fragmento de experiência existente.*

   * **Caminho**: procure e selecione o caminho da pasta em que deseja publicar o fragmento de experiência. Você também pode selecionar um fragmento de experiência existente e publicá-lo novamente.
   * **Título**: digite o título do Fragmento de experiência. Por padrão, o título é preenchido com o título do tópico. Você pode editá-lo. Esse título é usado para gerar o nome do Fragmento de experiência.
   * **Nome**: digite o nome do Fragmento de experiência. Por padrão, o nome é preenchido com o título do tópico e os espaços são substituídos por &quot;_&quot;. Por exemplo, *sample_experience_fragment*. Você pode editá-lo. Esse nome é usado para gerar o URL do Fragmento de experiência.
   * **Modelo**: selecione o modelo de Fragmento de experiência que deseja usar para criar seu Fragmento de experiência. Os modelos são selecionados da pasta configurada nas propriedades.
   * **Mapeamento**: Ele escolhe o mapeamento do *experienceFragmentMapping.json* arquivo e o exibe.



     O administrador pode adicionar os mapeamentos no *experienceFragmentMapping.json* arquivo.  Saiba como [criar um mapeamento entre um tópico e um Fragmento de experiência](../cs-install-guide/conf-experience-fragment-mapping-cs.md) no Guia de instalação e configuração.

   * Você também pode selecionar condições diferentes para publicar o conteúdo.  Selecione uma das seguintes opções:


      * **Nenhum**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.
      * **Uso de DITAVAL**: selecione o arquivo DITAVAL para gerar conteúdo personalizado. Você pode selecionar o arquivo DITAVAL usando a caixa de diálogo Procurar ou digitando o caminho do arquivo.
      * **Uso de atributos**: você pode definir atributos de condição em seus tópicos DITA. Em seguida, selecione o atributo de condição para publicar o conteúdo relevante.

     >[!NOTE]
     > 
     >As condições serão ativadas somente se os atributos de condição forem definidos no tópico.


   * Selecione o **Substituir conteúdo existente** se o fragmento de experiência já existir e você desejar substituí-lo. Os Guias do Experience Manager exibem um erro se você não marcar a caixa de seleção e o Fragmento de experiência já existir.
1. Clique em **Gerar** para publicar o fragmento de experiência.
1. Você pode exibir os Fragmentos de experiência de um tópico sob o **Saídas** na seção **Propriedades do arquivo**. Os Fragmentos de experiência são exibidos de acordo com a data e a hora de sua publicação, sendo que o mais recente é o primeiro.

   ![Exibir os Fragmentos de experiência de um tópico](images/experience-fragment-outputs.png){width=300 align=&quot;left&quot;}

   *Visualize os Fragmentos de experiência presentes em um tópico e publique-os novamente.*




Depois de publicar os fragmentos de experiência, você também pode usá-los em qualquer site do Adobe Experience Manager.


## Menu Opções para um Fragmento de experiência

Você também pode executar as seguintes ações para um Fragmento de experiência na **Opções** menu:

* **Gerar**: publique novamente o fragmento de experiência para atualizá-lo com o conteúdo mais recente do tópico DITA. Ao gerar novamente a saída, não é possível alterar o caminho, o nome, o título e o modelo do Fragmento de experiência. No entanto, você pode selecionar condições diferentes ao regenerar a saída.

* **Duplicar**: duplicar um fragmento de experiência. Você pode alterar o caminho, o nome, o título e o modelo. Você também pode selecionar condições diferentes ao duplicar um Fragmento de experiência.

* **Remover**: remova um fragmento de experiência da lista de saídas. Um prompt de confirmação é exibido. Depois de confirmar, o fragmento de experiência é removido da **Saídas** lista. Mas o Fragmento de experiência não é excluído da pasta.

* **Exibir**: visualize o editor de Fragmento de experiência. Você também pode fazer alterações e salvá-las.


