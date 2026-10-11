---
title: Configurar filtros para a caixa de diálogo de procura de arquivos
description: Saiba como Configurar filtros para a caixa de diálogo de procura de arquivos
exl-id: 1ef09820-3b18-4762-b177-4d40926e21f0
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/7AzojwFiEQkwYtDnwsHhmMOwSCG3vWgsZW5oXZRsTFw'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%
---
# Configurar filtros para a caixa de diálogo de procura de arquivos {#id20CIL7009GN}

Ao trabalhar no Editor, é necessário usar a caixa de diálogo de navegação de arquivos para inserir elementos como imagem, referência ou referência de chave. A caixa de diálogo de procura de arquivo padrão não oferece nenhuma opção de filtragem de arquivo. É possível adicionar seus próprios filtros, permitindo acessar os arquivos necessários de forma fácil e rápida.

Execute as seguintes etapas para adicionar as opções de filtragem de arquivo personalizado à caixa de diálogo Procurar arquivo:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o arquivo de configuração padrão disponível no seguinte local:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Crie uma cópia do arquivo de configuração padrão no seguinte local:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navegue e abra o arquivo `ui_config.json` no nó `apps` para edição.

1. No arquivo `ui_config.json`, adicione a definição dos filtros que deseja adicionar.

   O trecho de código a seguir mostra como adicionar duas opções de filtragem — Arquivos DITA e Arquivos de imagem.

   ```json
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

   - **título:** o nome para exibição do filtro. Este título aparece como a opção de filtragem na caixa de diálogo de procura de arquivo.

   - **propriedade:** a propriedade que deve corresponder aos metadados do arquivo. Por exemplo, para permitir somente os arquivos que têm os metadados `dita_class` em sua propriedade, o filtro de propriedade assume &quot;`jcr:content/metadata/dita_class`&quot; como seu valor.

   - **operação:** especifique &quot;`exists`&quot; para corresponder à existência do valor especificado no parâmetro de propriedade.

   O segundo filtro é para Arquivos de imagem. Os parâmetros são semelhantes ao primeiro filtro, exceto o parâmetro `value`. O parâmetro `value` usa uma matriz de tipos de imagem como seu valor. Todos os tipos de arquivos especificados no parâmetro value são pesquisados e mostrados na caixa de diálogo de procura de arquivos, todos os outros tipos de arquivos são ignorados.

1. Salve o arquivo *ui\_config.json* e recarregue o Editor.

   Quando você inicia a caixa de diálogo de navegação de arquivos, as opções de filtro configuradas no arquivo ui\_config.json são exibidas.

   ![](assets/file-browse-custom-filters.png){width="300"}
