---
title: Configurar filtros de texto
description: Saiba como Configurar filtros de texto
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---

# Configurar filtros de texto {#id21BPD0FK0XA}

O AEM Guides fornece o recurso para procurar texto nos arquivos presentes no caminho selecionado do repositório do AEM. Você pode usar a pesquisa de filtro para pesquisar arquivos no painel de repositório ou para procurar arquivos. Ao trabalhar no Editor da Web, é necessário usar a caixa de diálogo de navegação de arquivos para inserir elementos como imagem, referência ou referência de chave.

Por padrão, você pode usar alguns filtros aprimorados para pesquisar os arquivos no repositório do AEM. Você pode filtrar todos os arquivos DITA ou arquivos não DITA presentes no caminho selecionado. Também é possível pesquisar valores específicos nos atributos de elementos DITA. Você também pode procurar arquivos cujo check-out tenha sido feito pelo usuário especificado.

>[!NOTE]
>
> Você também pode configurar o perfil global e adicionar mais filtros para pesquisa.

As guias a seguir fornecem instruções para configurar os filtros de texto com base na configuração do Experience Manager Guides: Cloud Service ou No local.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Faça logon no Adobe Experience Manager como administrador.
1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Clique em **Configuração do Editor de XML**.
1. Clique no ícone **Editar** na parte superior.
1. Clique no ícone **Baixar** para baixar o arquivo ui\_config.json em seu sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.
   1. Configure os filtros no arquivo. Também é possível adicionar filtros personalizados, como mostrado no exemplo abaixo:

      O trecho de código a seguir mostra como adicionar opções de filtragem de Arquivos DITA, Não-DITA, Elementos DITA e Arquivos com check-out. Ele também contém um filtro personalizado -Tags.

      ```
       "operation":"like"
                                      },
                                      {
                                      "title":"Checked out by",
                                      "property":"jcr:content/cq:drivelock",
                                      "operation":"like",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Checked out by"
                                      },
                                      "children":[
                                      {
                                      "title":"Check out"
                                      }
                                      ]
                                      },
                                      {
                                      "title":"Tags",
                                      "property":"jcr:content/metadata/cq:tags",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Enter Tag"
                                      },
                                      "children":[
                                      {
                                      "title":"Tags"
                                      }
                                      ]
                                      }
                                      ]
      ```

      No trecho de código acima, o primeiro filtro é para Arquivos DITA. A definição do filtro usa os seguintes parâmetros:

      ****Título****: o nome para exibição do filtro. Este título aparece como a opção de filtragem na caixa de diálogo de procura de arquivo.

      ****Propriedade****: a propriedade que deve corresponder aos metadados do arquivo. Por exemplo, para permitir somente os arquivos que têm os metadados dita\_class em sua propriedade, o filtro de propriedade usa &quot;jcr:content/metadata/dita\_class&quot; como seu valor.

      ****Operação **:**especifique &quot;existe&quot; para corresponder à existência do valor especificado no parâmetro de propriedade

1. Carregue o arquivo ui\_config.json atualizado que contém os filtros adicionados.

Os filtros configurados estão disponíveis no painel Filtros.

>[!TAB No local]

1. Faça logon no Adobe Experience Manager como administrador.
1. Clique no link **Adobe Experience Manager** na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Clique em **Configuração do Editor de XML**.
1. Clique no ícone **Editar** na parte superior.
1. Baixe o arquivo ui\_config.json.
1. Configure os filtros no arquivo. Também é possível adicionar filtros personalizados, como mostrado no exemplo abaixo:

   O trecho de código a seguir mostra como adicionar opções de filtragem de Arquivos DITA, Não-DITA, Elementos DITA e Arquivos com check-out. Ele também contém um filtro personalizado -Tags.

   ```json
   [
     {
       "title": "DITA files",
       "property": "jcr:content/metadata/dita_class",
       "operation": "like",
       "children": [
         {
           "title": "DITA Topics",
           "value": "- topic/topic",
           "checked": true
         },
         {
           "title": "DITA Maps",
           "value": "- map/map",
           "checked": true
         }
       ]
     },
     {
       "title": "DITA elements",
       "property": "jcr:content/ditameta",
       "widgetId": "dita_filter",
       "operation": "like"
     },
     {
       "title": "Checked out by",
       "property": "jcr:content/cq:drivelock",
       "operation": "like",
       "itemConfig": {
         "component": "textfield",
         "placeholder": "Checked out by"
       },
       "children": [
         {
           "title": "Check out"
         }
       ]
     },
     {
       "title": "Tags",
       "property": "jcr:content/metadata/cq:tags",
       "itemConfig": {
         "component": "textfield",
         "placeholder": "Enter Tag"
       },
       "children": [
         {
           "title": "Tags"
         }
       ]
     }
   ]
   ```

   No trecho de código acima, o primeiro filtro é para Arquivos DITA. A definição do filtro usa os seguintes parâmetros:

   - **Título:** o nome para exibição do filtro. Este título aparece como a opção de filtragem na caixa de diálogo de procura de arquivo.

   - **Propriedade:** a propriedade que deve corresponder aos metadados do arquivo. Por exemplo, para permitir somente os arquivos que têm os metadados dita\_class em sua propriedade, o filtro de propriedade usa &quot;jcr:content/metadata/dita\_class&quot; como seu valor.

   - **Operação** Especifique &quot;existe&quot; para corresponder à existência do valor especificado no parâmetro de propriedade

1. Carregue o arquivo ui\_config.json atualizado que contém os filtros adicionados.

Os filtros configurados estão disponíveis no painel Filtros.

>[!ENDTABS]

**Tópico pai:**[ Personalizar editor da Web](customize-overview.md)
