---
title: Configurar filtros para a caixa de diálogo de procura de arquivos
description: Saiba como Configurar filtros para a caixa de diálogo de procura de arquivos
exl-id: 1ef2cec8-2e77-40c1-9ed2-324048bf65fb
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# Configurar filtros para a caixa de diálogo de procura de arquivos {#id20CIL7009GN}

Ao trabalhar no Editor da Web, é necessário usar a caixa de diálogo de navegação de arquivos para inserir elementos como imagem, referência ou referência de chave. A caixa de diálogo de procura de arquivo padrão não oferece nenhuma opção de filtragem de arquivo. É possível adicionar seus próprios filtros, permitindo acessar os arquivos necessários de forma fácil e rápida.

Execute as seguintes etapas para adicionar as opções de filtragem de arquivo personalizado à caixa de diálogo Procurar arquivo:

1. Para baixar o arquivo de configuração da interface do usuário, faça logon no Adobe Experience Manager como administrador.

1. Clique no link do Adobe Experience Manager na parte superior e escolha **Ferramentas**.
1. Selecione **Guias** na lista de ferramentas e clique em **Perfis de Pasta**.
1. Clique no bloco **Perfil Global**.
1. Selecione a guia **Configuração do editor XML** e clique no ícone **Editar** na parte superior
1. Clique no ícone **Baixar** para baixar o arquivo ui\_config.json em seu sistema local. Em seguida, você pode fazer alterações no arquivo e fazer upload do mesmo.
1. No arquivo `ui_config.json`, adicione a definição dos filtros que deseja adicionar.

   O trecho de código a seguir mostra como adicionar duas opções de filtragem — Arquivos DITA e Arquivos de imagem.

   ```
   "browseFilters": [
                       {
                       "title": "DITA Files",
                       "property": "jcr:content/metadata/dita_class",
                       "operation": "exists"
                       },
                       {
                       "title": "Image Files",
                       "property": "jcr:content/metadata/dc:format",
                       "value": [
                       "image/jpeg",
                       "image/gif",
                       "image/png"
                       ]
                       }
                       ]
   ```

   No trecho de código acima, o primeiro filtro é para Arquivos DITA. A definição do filtro usa os seguintes parâmetros:

   título
:   O nome de exibição do filtro. Este título aparece como a opção de filtragem na caixa de diálogo de procura de arquivo.

   propriedade
:   A propriedade a ser correspondida nos metadados do arquivo. Por exemplo, para permitir somente os arquivos que têm os metadados `dita_class` em sua propriedade, o filtro de propriedade assume &quot; `jcr:content/metadata/dita_class`&quot; como seu valor.

   operação
:   Especifique &quot; `exists`&quot; para corresponder a existência do valor especificado no parâmetro de propriedade.

   O segundo filtro é para Arquivos de imagem. Os parâmetros são semelhantes ao primeiro filtro, exceto o parâmetro `value`. O parâmetro `value` usa uma matriz de tipos de imagem como seu valor. Todos os tipos de arquivos especificados no parâmetro value são pesquisados e mostrados na caixa de diálogo de procura de arquivos, todos os outros tipos de arquivos são ignorados.

1. Salve o arquivo *ui\_config.json* e carregue o mesmo. Em seguida, recarregue o Editor da Web.

   Quando você inicia a caixa de diálogo de navegação de arquivos, as opções de filtro configuradas no arquivo ui\_config.json são exibidas.

   ![](assets/file-browse-custom-filters.png)


**Tópico pai:**&#x200B;[ Personalizar editor da Web](conf-web-editor.md)
