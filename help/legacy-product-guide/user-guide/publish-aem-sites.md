---
title: Publish de um tópico para uma página do AEM Sites
description: Publish um tópico ou os elementos dentro de um tópico para uma saída Adobe Experience Manager Sites.  Saiba como visualizar a página do Experience Manager Sites presente para um tópico e republicá-la.
feature: Publishing
role: User
exl-id: acbc48b7-93a2-41c6-8565-359fbbdd1fb9
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Páginas do Publish Adobe Experience Manager Sites


A página do Experience Manager Sites se refere ao conteúdo publicado no site da Adobe Experience Manager. O Experience Manager Guides permite publicar um tópico independente em uma página do Sites.

Esse recurso permite publicar um tópico e seus elementos sem criar um mapa DITA e as predefinições de saída. Você pode atualizar facilmente o tópico, republicar a página Sites e reutilizá-la em diferentes páginas da Web. Com esse recurso, você pode publicar facilmente artigos independentes ou conteúdo de marketing.





Para gerar uma página Sites, execute as seguintes etapas:




1. Selecione **Nova Saída** ![novo ícone de saída](./images/Add_icon.svg) na seção **Saídas** em **Propriedades do Arquivo** de um tópico.
1. Selecione a **página Sites**.


1. Na caixa de diálogo **Gerar página de Sites**, preencha os seguintes detalhes:
   ![Adicionar o caminho e os detalhes do modelo na página Gerar Sites](images/aem-sites-page-generate.png){width="500" align="left"}

   *Adicione o caminho, o título, o nome e os detalhes do modelo para publicar um tópico ou seus elementos como uma página do Sites. *

   * **Caminho**: procure e selecione o caminho da pasta em que deseja publicar a página Sites.
   * **Título**: digite o título da página Sites. Por padrão, o título é preenchido com o título do tópico. Você pode editá-lo. Esse título é usado para gerar o nome da página Sites.
   * **Nome**: digite o nome da página Sites. Por padrão, o nome é preenchido com o título do tópico e caracteres não permitidos, como espaços e caracteres especiais, são substituídos por &#39;_&#39;. Por exemplo, *página_de_sites_de_amostra*. Você pode editá-lo. Esse nome é usado para gerar o URL da página Sites.
   * **Modelo de página**: selecione o modelo de página Sites para criar sua página Sites. É possível exibir os modelos na pasta no caminho selecionado. Seu administrador também pode fazer upload de modelos personalizados.


   * Você também pode selecionar condições diferentes para publicar o conteúdo.  Selecione uma das seguintes opções:


      * **Nenhum**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.
      * **Usando DITAVAL**: selecione o arquivo DITAVAL para gerar conteúdo personalizado. Você pode selecionar o arquivo DITAVAL usando a caixa de diálogo Procurar ou digitando o caminho do arquivo.
      * **Uso de atributos**: você pode definir atributos de condição em seus tópicos DITA. Em seguida, selecione o atributo de condição para publicar o conteúdo relevante.

     >[!NOTE]
     > 
     >As condições serão ativadas somente se os atributos de condição forem definidos no tópico.



1. Clique em **Gerar** para publicar a página Sites.
1. Você pode exibir a página Sites de um tópico na seção **Saídas** em **Propriedades do Arquivo**. As páginas do Sites são exibidas de acordo com a data e a hora de sua publicação, sendo que a mais recente é a primeira.

   ![Exibir a página Sites para um tópico](images/aem-sites-outputs.png){width=300 align=&quot;left&quot;}

   *Exiba a página Sites presente para um tópico e republique-os.*




Depois de publicar a página Sites, você também pode usá-los em qualquer site do Adobe Experience Manager.


## Menu de opções para uma Experience Manager Sites

Você também pode executar as seguintes ações para uma Experience Manager Sites no menu **Opções**:

* **Gerar**: publique novamente a página Sites para atualizá-la com o conteúdo mais recente do tópico DITA. Ao gerar novamente a saída sem alterar o caminho, o nome, o título, o modelo e as condições, a página do Sites é simplesmente atualizada com o conteúdo mais recente.

* **Duplicar**: duplicar uma página do Sites. Você pode alterar o caminho, o nome, o título e o modelo. Você também pode selecionar condições diferentes ao duplicar uma página do Sites.

* **Remover**: remover uma página Sites da lista de saídas. Um prompt de confirmação é exibido. Depois que você confirmar, a página Sites será removida da lista **Saídas**. Mas a página Sites não é excluída permanentemente.

* **Exibir**: exibir o editor de páginas do Sites. Você também pode fazer alterações e salvá-las.
