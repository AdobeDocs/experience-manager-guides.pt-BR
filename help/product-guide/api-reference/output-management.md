---
title: REST APIs para gerenciamento de saída
description: Saiba mais sobre as REST APIs para gerenciamento de saída
exl-id: dab654f5-555d-4a89-bc94-55b1e938f255
feature: Rest API Output Management
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 0%

---

# REST APIs para gerenciamento de saída {#id175UB30E05Z}

As seguintes APIs REST estão disponíveis para gerenciar a saída em Guias AEM.

## Obter todas as predefinições de saída para um mapa DITA {#get-output-presets-dita-map}

Um método POST que recupera todas as predefinições de saída configuradas para um mapa DITA.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parâmetros**:\
|Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`:operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é `getalloutputs`.<br> **Nota:** O valor não diferencia maiúsculas de minúsculas.| |`sourcePath`|String|Yes|Caminho absoluto do arquivo de mapa DITA.|

**Valores de resposta**: retorna uma matriz de objetos de Predefinição de saída JSON, cada objeto contendo os seguintes elementos:

| Elemento | Descrição |
|-------|-----------|
| `outputName` | Nome da predefinição de saída. Os nomes de saída são exclusivos no escopo do mapa DITA em que estão definidos. |
| `outputType` | Tipo de saída gerado usando essa predefinição, por exemplo, AEM Site, PDF, EPUB ou outro. As opções disponíveis são:<br>- AEMSITE <br>- PDF <br>- HTML 5 <br>- EPUB <br>- PERSONALIZADO |
| `outputTitle` | Um nome descritivo para as configurações de predefinição de saída. Isso é usado para definir o valor da propriedade Nome da configuração para a predefinição de saída. |
| `ditaValPathList` | Matriz de caminhos de arquivo DITAVAL a serem usados para gerar a saída desejada. |
| `targetPath` | Caminho onde a saída é publicada ou armazenada. |
| `siteName` | *\(Para saída do site AEM\)* Nome do site do AEM. |
| `templatePath` | *\(Para saída do site AEM\)* Caminho do nó do modelo a ser usado para gerar a saída desejada. |
| `searchScope` | Especifique o escopo da operação de pesquisa. O valor desse parâmetro deve ser definido como `local`. |
| `generateTOC` | *\(Para saída do site AEM\)* Especifique se um índice é gerado \(true\) ou não \(false\). |
| `generateBreadcrumbs` | *\(Para saída do site AEM\)* Especifique se as navegações estruturais são geradas \(true\) ou não \(false\). |
| `overwriteStrategy` | *\(Para saída do site AEM\)* Especifique se os arquivos no destino são substituídos \(true\) ou não \(false\). |
| `pdfGenerator` | Especifique o mecanismo de geração de PDF a ser usado. Os valores possíveis são:<br>- DITAOT <br>- FMPS |

>[!NOTE]
>
> `DitaValPath` O elemento não é mais compatível.

## Criar predefinição de saída

Um método POST que cria uma nova predefinição de saída para um mapa DITA.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`:operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é ``createoutput``.<br> **Nota:** O valor não diferencia maiúsculas de minúsculas.| |`sourcePath`|String|Sim|Caminho absoluto do arquivo de mapa DITA.| |`outputTitle`|String|Sim|Um nome descritivo para as configurações de predefinição de saída. Isso é usado para definir o valor da propriedade Nome da configuração para a predefinição de saída.<br> **Nota:** Quando uma nova predefinição de saída é criada, o sistema de back-end direciona um nome exclusivo para a predefinição de saída a partir do título fornecido.| |`outputType`|String|Sim|Tipo de saída gerado usando essa predefinição, por exemplo, AEM Site, PDF, EPUB, ou outro. As opções disponíveis são:<br>- AEMSITE <br>- PDF <br>- HTML 5 <br>- EPUB <br>- PERSONALIZADO|

**Valores de resposta**: |Elemento|Descrição| |—|—| |`outputName`|Um nome exclusivo para a predefinição de saída recém-criada. Esse nome é derivado do valor de `outputTitle` parâmetro.|

## Salvar predefinição de saída

Um método POST que salva as alterações feitas em uma predefinição de saída.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`:operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é ``saveoutput``.<br> **Nota:** O valor não diferencia maiúsculas de minúsculas.| |`sourcePath`|String|Sim|Caminho absoluto do arquivo de mapa DITA.| |`outputObj`|String|Sim|Um objeto JSON que contém propriedades da predefinição de saída que está sendo atualizada. A variável `outputObj.outputName` A propriedade contém o nome da predefinição de saída que deve ser atualizada. Para obter o formato do objeto JSON, consulte o **Valores de resposta** tabela em [Obter todas as predefinições de saída para um mapa DITA](#get-output-presets-dita-map).|

**Valores de resposta**: retorna uma resposta HTTP 200 \(Successful\).

## Obter uma predefinição de saída específica

Um método POST que recupera uma predefinição de saída existente.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`:operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é `getoutput`. <br>**Nota:** O valor não diferencia maiúsculas de minúsculas.| |`sourcePath`|String|Sim|Caminho absoluto do arquivo de mapa DITA.| |`outputName`|String|Sim|Nome da predefinição de saída para a qual os detalhes devem ser recuperados.|

**Valores de resposta**: |Elemento|Descrição| |—|—| |`outputName`|Nome da predefinição de saída. Os nomes de saída são exclusivos no escopo do mapa DITA em que estão definidos.| |`outputType`|Tipo de saída gerado usando essa predefinição, por exemplo, AEM Site, PDF, EPUB ou outro. As opções disponíveis são:<br>- AEMSITE <br>- PDF <br>- HTML 5 <br>- EPUB <br>- PERSONALIZADO <br>| |`outputTitle`|Um nome descritivo para as configurações de predefinição de saída. Isso é usado para definir o valor da propriedade Nome da configuração para a predefinição de saída.| |`ditaValPathList`|Matriz de caminhos de arquivo DITAVAL a serem usados para gerar a saída desejada.| |`targetPath`|Caminho onde a saída é publicada ou armazenada.| |`siteName`|\(Para saída do site AEM\) Nome do site AEM.| |`siteTitle`|\(Para saída do site AEM\) Título do site AEM.| |`templatePath`|\(Para saída do site AEM\) Caminho do nó de modelo a ser usado para gerar a saída desejada.| |`searchScope`|Especifique o escopo da operação de pesquisa. O valor desse parâmetro deve ser definido como `local`.| |`generateTOC`|\(Para saída do site AEM\) Especifique se um índice é gerado \(true\) ou não \(false\).| |`generateBreadcrumbs`|\(Para saída do site AEM\) Especifique se as navegações estruturais são geradas \(true\) ou não \(false\).| |`overwriteFiles`|\(Para saída do site AEM\) Especifique se os arquivos no destino são substituídos \(true\) ou não \(false\).| |`pdfGenerator`|Especifique o mecanismo de geração de PDF a ser usado. Os valores possíveis são:<br>- DITAOT <br>- FMPS|

>[!NOTE]
>
> `DitaValPath` O elemento não é mais compatível.

## Gerar saída

Um método GET que gera saída usando uma ou mais predefinições de saída.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é `GENERATEOUTPUT`.<br> **Nota:** O valor diferencia maiúsculas e minúsculas.| |`source`|String|Sim|Caminho absoluto do arquivo de mapa DITA.| |`outputName`|String|Sim|Nome da predefinição de saída\(s\) a ser usada para gerar saída. Várias predefinições de saída podem ser especificadas usando um delimitador de barra vertical \(&quot;\|&quot;\), por exemplo `aemsite|pdfoutput`.|

**Valores de resposta**: retorna uma resposta HTTP 200 \(Successful\).

## Gerar saída incremental

Um método GET que gera saída incremental para um site AEM usando uma ou mais predefinições de saída.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é `INCREMENTALPUBLISH`. <br>**Nota:** O valor diferencia maiúsculas e minúsculas.| |`contentPath`|JSON|Sim|Caminho absoluto do arquivo de mapa DITA e dos arquivos de tópico, juntamente com o nome das predefinições de saída. Use o exemplo a seguir como bloco de construção:|

```XML
{
   {   
   "ditamap": 
      "/content/dam/sample/sample.ditamap",   
   "topics": [     
      "/content/dam/sample/topic1.xml",     
      "/content/dam/sample/topic2.xml"   
         ],   
   "fullMaps": [     
      "/content/dam/sample/submap.ditamap"   
      ],   
   "maps": [     
      "/content/dam/sample/keyspace.ditamap"   
      ],   
   "outputs": [     
      "aemsite"   
      ] 
   }
}
```

- A variável `ditamap` O atributo pega o caminho absoluto do mapa DITA usado para gerar a saída.
- A variável `topics` O atributo pega uma matriz de tópicos que são atualizados e precisam ser republicados.
- A variável `fullMaps` O atributo contém o caminho dos arquivos de mapa \(como submapas fragmentados\) que são necessários junto com seus tópicos para a geração de saída incremental.
- A variável `maps` O atributo contém o caminho dos arquivos de mapa \(para resolver referências de espaço-chave\) que são extraídos no disco sem tópicos.
- A variável `outputs` O atributo recebe uma matriz de nomes de predefinições de saída usados para gerar a saída.

**Valores de resposta**: retorna uma resposta HTTP 200 \(Successful\).

## Excluir predefinição de saída

Um método POST que exclui uma predefinição de saída.

**URL de solicitação**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parâmetros**: |Nome|Tipo|Obrigatório|Descrição| |—|—|—|—| |`:operation`|String|Sim|Nome da operação que está sendo chamada. O valor desse parâmetro é `deleteoutput`.<br> **Nota:** O valor não diferencia maiúsculas de minúsculas.| |`sourcePath`|String|Sim|Caminho absoluto do arquivo de mapa DITA.| |`outputName`|String|Sim|Nome da predefinição de saída a ser excluída.|

**Valores de resposta**: retorna uma resposta HTTP 200 \(Successful\).
