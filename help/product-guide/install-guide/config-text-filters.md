---
title: Configurar filtros de texto
description: Saiba como Configurar filtros de texto
exl-id: 180e4ab5-5259-4a00-ac3c-bb1d6814ce0d
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/QKz6-i6p4g0QOThLQdoR6HN2uCgZyQClaSizBM4kKO8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 0%

---

# Configurar filtros de texto {#id21BPD0FK0XA}

O AEM Guides fornece o recurso para procurar texto nos arquivos presentes no caminho selecionado do repositório do AEM. Você pode usar a pesquisa de filtro para pesquisar arquivos no painel de repositório ou para procurar arquivos. Ao trabalhar no Editor da Web, é necessário usar a caixa de diálogo de navegação de arquivos para inserir elementos como imagem, referência ou referência de chave.

Por padrão, você pode usar alguns filtros aprimorados para pesquisar os arquivos no repositório do AEM. Você pode filtrar todos os arquivos DITA ou arquivos não DITA presentes no caminho selecionado. Também é possível pesquisar valores específicos nos atributos de elementos DITA. Você também pode procurar arquivos cujo check-out tenha sido feito pelo usuário especificado.

>[!NOTE]
>
> Você também pode configurar o perfil global e adicionar mais filtros para pesquisa.

Execute as seguintes etapas para configurar os filtros de texto:

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

**Tópico pai:**&#x200B;[&#x200B; Personalizar editor da Web](conf-web-editor.md)
