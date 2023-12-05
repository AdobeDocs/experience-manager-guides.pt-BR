---
title: Definir configurações de geração de saída
description: Saiba como definir configurações de geração de saída
exl-id: b5cf4f6c-dc56-428e-a514-6c9f879ac03d
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '5470'
ht-degree: 0%

---

# Definir configurações de geração de saída {#id181AI0B0E30}

O AEM Guides vem com muitas opções de configuração para você personalizar o processo de geração de saída. Este tópico aborda todas as configurações e personalizações que ajudariam você a configurar o processo de geração de saída.

## Configure a guia Linha de base no painel de mapa DITA {#id223MD0D0YRM}

Para ocultar a guia Linha de base no painel do mapa DITA, execute as seguintes etapas:

1. Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração.
1. No arquivo de configuração, forneça os seguintes detalhes \(property\) para configurar a guia de linha de base no painel de mapa.

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `hide.tabs.baseline` | Booleano\(`true/false`\).**Valor padrão**: `true` |

>[!NOTE]
>
> Essa configuração é habilitada por padrão e a guia Linha de base não está disponível no painel de mapa.

## Configurar a publicação combinada em um site AEM existente {#id1691I0V0MGR}

Se você tiver um site AEM com conteúdo DITA, poderá configurar sua saída de site AEM para publicar conteúdo DITA em um local predefinido no seu site. Por exemplo, na captura de tela a seguir de uma página do site AEM, a variável `ditacontent` é reservado para armazenar conteúdo DITA:

![](assets/publish-in-aem-site.png)

Os nós restantes na página são criados diretamente do editor do site AEM. Definir a configuração de publicação para publicar conteúdo DITA em um local predefinido garante que nenhum conteúdo não DITA existente seja modificado pelo processo de publicação dos Guias AEM.

É necessário executar as seguintes configurações no site existente para permitir a publicação de conteúdo DITA em um nó predefinido:

- Configurar as propriedades do modelo do site

- Adicione nós ao site para publicar conteúdo DITA


Execute as seguintes etapas para configurar as propriedades do modelo do site existente:

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/templates/default.

   >[!NOTE]
   >
   > Não faça nenhuma personalização nos arquivos de configuração padrão disponíveis no `libs` nó. É necessário criar uma sobreposição do `libs` no nó `apps` e atualize os arquivos necessários no `apps` somente nó.

1. Adicione as seguintes propriedades:

   | Nome da propriedade | Tipo | Valor |
   |-------------|----|-----|
   | `topicContentNode` | String | Especifique o nome do nó onde deseja publicar o conteúdo DITA. Por exemplo, o nó padrão em que o AEM Guides publica conteúdo DITA é: <br> `jcr:content/contentnode` |
   | `topicHeadNode` | String | Especifique o nome do nó em que você deseja armazenar as informações de metadados do conteúdo DITA. Por exemplo, o nó padrão em que os Guias do AEM armazenam informações de metadados é: <br> `jcr:content/headnode` |


Na próxima vez que você publicar qualquer conteúdo DITA usando as configurações de modelo do seu site, o conteúdo será publicado nos nós especificados na `topicContentNode` e `topicHeadNode` propriedades.

## Personalizar saída do site AEM {#id166TG0B30WR}

Os Guias do AEM permitem a criação de saídas nos seguintes formatos:

- Site AEM
- PDF
- HTML 5
- EPUB
- Saída personalizada através do DITA-OT

Para a saída do site AEM, é possível atribuir modelos de design diferentes com tarefas de saída diferentes. Esses modelos de design podem renderizar o conteúdo DITA em diferentes layouts. Por exemplo, você pode especificar diferentes modelos de design para públicos-alvo internos e externos.

Você também pode usar os plug-ins personalizados do DITA Open Toolkit \(DITA-OT\) com os Guias do AEM. Você pode fazer upload desses plug-ins DITA-OT personalizados para gerar saída de PDF de uma maneira específica.

>[!TIP]
>
> Consulte a *Publicação no site do AEM* no guia de práticas recomendadas para práticas recomendadas sobre a criação de saída do site AEM.


### Personalizar modelo de design para gerar saída {#customize_xml-add-on}

Os Guias do AEM usam um conjunto de modelos de design predefinidos para gerar saída do site AEM. Você pode personalizar os modelos de design dos Guias do AEM para gerar a saída que esteja em conformidade com a marca da sua empresa. Um modelo de design é uma coleção de vários estilos \(CSS\), scripts \(do lado do servidor e do lado do cliente\), recursos \(imagens, logotipos e outros ativos\) e nós JCR que unem todos esses recursos. Um modelo de design pode ser tão simples quanto um único script do lado do servidor com apenas alguns nós JCR, ou uma combinação complexa de estilos, recursos e nós JCR. Os modelos de design são usados pelo subsistema de publicação AEM Guides ao gerar saída do site AEM e eles controlam a estrutura, aparência e comportamento da saída gerada.

Não há restrição quanto ao local onde os recursos do modelo de design devem estar localizados no servidor, mas geralmente são organizados logicamente de acordo com sua função. Por exemplo, o modelo padrão tem todos os arquivos JavaScript e CSS armazenados em `/etc/designs/fmdita/clientlibs/siteoutput/default` pasta. Sempre que esses arquivos estiverem localizados, eles serão vinculados por uma coleção de nós JCR. Juntos, esses nós JCR e os arquivos constituem todo o modelo de design.

O modelo de design padrão enviado com os Guias do AEM permite personalizar os componentes de página de aterrissagem, tópico e pesquisa. Você pode fazer uma cópia do design padrão e dos modelos de referência correspondentes e especificar componentes diferentes para gerar a saída desejada.

Execute as seguintes etapas para especificar seu próprio modelo de design a ser usado para a geração de saída do site AEM:

1. Use o Gerenciador de pacotes para baixar o modelo de design padrão no seguinte local:

   /libs/fmdita/config/templates

1. Crie uma cópia dos arquivos baixados no seguinte local no repositório Git do Cloud Manager:

   /apps/fmdita/config/templates

1. Você também deve baixar e copiar os modelos referenciados do nó de modelo padrão. Os modelos referenciados são colocados em:

   /libs/fmdita/templates/default/cqtemplates

   As propriedades do modelo de design dos Guias do AEM estão descritas na tabela a seguir.

   | Propriedade | Descrição |
   |--------|-----------|
   | `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Especifique a `cq:Template` para essas páginas correspondentes \(landing page, pesquisa e tópico\). Por padrão, a variável `cq:Template` o nó dessas páginas pode ser encontrado em `/libs/fmdita/templates/default/cqtemplates` nó. Esse nó define a estrutura e as propriedades das páginas de aterrissagem, pesquisa e tópico.<br> A variável `shadowPageTemplate` é usado para otimizar o conteúdo fragmentado. É necessário definir o valor dessa propriedade como: `fmdita/templates/default/cqtemplates/shadowpage` <br> **Nota:** Você deve especificar um valor para o `topicPageTemplate`. A variável `landingPageTemplate` e `searchPageTemplate` são propriedades opcionais. Se não quiser que as páginas de pesquisa e de aterrissagem sejam geradas, não especifique essas propriedades. |
   | `title` | Um nome descritivo do modelo de design. |
   | `topicContentNode` | O local do nó que conterá o conteúdo DITA em uma página de tópico. O caminho é relativo à página de tópico. |
   | `topicHeadNode` | O local do nó que conterá os valores de cabeçalho \(ou metadados\) derivados do conteúdo DITA. O caminho é relativo à página de tópico. |
   | `tocNode` | O local do nó que conterá o índice. O caminho é relativo à página inicial ou ao caminho de destino. |
   | `basePathProp` | O nome da propriedade para armazenar o caminho da raiz do site publicado. |
   | `indexPathProp` | O nome da propriedade para armazenar o caminho da página de aterrissagem/índice do site publicado. |
   | `pdfPathProp` | O nome da propriedade para armazenar o caminho do PDF do tópico, se a geração do PDF do tópico estiver ativada. |
   | `pdfTypeProp` | O nome da propriedade para armazenar o tipo da geração de PDF. No momento, essa propriedade sempre contém &quot;Topic&quot;. |
   | `searchPathProp` | O nome da propriedade para armazenar o caminho da página de pesquisa, se o modelo incluir uma página de pesquisa. |
   | `siteTitleProp` | O nome da propriedade para armazenar o título do site que está sendo publicado. Esse título é geralmente o mesmo do mapa que está sendo publicado. |
   | `sourcePathProp` | O nome da propriedade para armazenar o caminho do tópico DITA de origem da página atual. |
   | `tocPathProp` | O nome da propriedade para armazenar o caminho da raiz do índice para o site publicado. |


>[!NOTE]
>
> Depois de criar um nó de modelo de design personalizado, você deve atualizar a opção Design nas predefinições de saída do site AEM para usar o nó de modelo de design personalizado.

Para obter mais informações, consulte [Criação do seu primeiro site do Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=en) e [Noções básicas](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/develop-wknd-tutorial.html?lang=en) de desenvolver seu próprio site sobre AEM.

### Usar o título do documento para gerar a saída do site AEM

Ao gerar a saída do site AEM, a forma como os URLs são gerados desempenha um papel importante na descoberta do seu conteúdo. Caso esteja usando nomes de arquivo baseados em UUID, gerar URLs com base na UUID de seus arquivos não será amigável para pesquisa. Como Administrador ou Editor, você tem o controle sobre como gerar os URLs para a saída do AEM Site. Guias do AEM fornecem uma configuração por meio da qual você pode optar por gerar os URLs de saída do site AEM usando o título do arquivo, em vez dos nomes de arquivo baseados em UUID. Por padrão, para sistemas de arquivos baseados em UUID, essa opção está ativada. Isso implicava que, quando você gera a saída do site AEM para sistemas de arquivos baseados em UUID, os títulos do arquivo são usados para gerar os URLs e não os UUIDs dos arquivos.

>[!NOTE]
>
> Você pode configurar regras adicionais para permitir apenas um conjunto de caracteres nos URLs de uma saída de site AEM. Para obter mais detalhes, consulte [Configurar regras de limpeza de nome de arquivo para criar tópicos e publicar a saída do site AEM](#id2164D0KD0XA).

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(property\) para configurar a geração de URLs na saída do site AEM:

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `aemsite.pagetitle` | Booleano \(true/false\). Caso queira gerar a saída usando o título da página, defina essa propriedade como true. Por padrão, está definido para usar o nome do arquivo.<br> **Valor padrão**: falso |

### Configure o URL da saída do site AEM para usar o título do documento

Você pode usar os títulos dos documentos no URL da saída do site AEM. Se o nome do arquivo não existir ou contiver todos os caracteres especiais, você poderá configurar o sistema para substituir os caracteres especiais por um separador no URL da saída do site AEM. Você também pode configurá-lo para substituí-los pelo nome do primeiro tópico filho.


Para configurar os nomes de página, execute as seguintes etapas:

1. Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração.
1. No arquivo de configuração, forneça os seguintes detalhes (propriedade) para configurar os nomes de página para os tópicos.

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeName` | `nodename.systemDefinedPageName` | Booleano (`true/false`). **Valor padrão**: `false` |

Por exemplo, se a variável *@navtitle* in `<topichead>` tem todos os caracteres especiais e você define o `aemsite.pagetitle` para true, em seguida, por padrão, usa um separador. Se você definir a variável `nodename.systemDefinedPageName` como true, mostra o nome do primeiro tópico filho.


### Configurar regras de limpeza de nome de arquivo para criar tópicos e publicar a saída do site AEM {#id2164D0KD0XA}

Como administrador, você pode definir uma lista de caracteres especiais válidos permitidos em nomes de arquivo, que eventualmente formam o URL de uma saída de site AEM. Em versões anteriores, os usuários podiam definir nomes de arquivo contendo caracteres especiais, como `@`, `$`, `>`e muito mais. Esses caracteres especiais resultavam em URL codificado na geração de páginas do site AEM.

A partir da versão 3.8, foram adicionadas configurações para definir uma lista de caracteres especiais permitidos nos nomes de arquivo. Por padrão, a configuração de nome de arquivo válido contém &quot;`a-z A-Z 0-9 - _`&quot;. Isto implica que, ao criar um arquivo, você pode ter qualquer caractere especial no título do arquivo, mas internamente ele será substituído por um hífen \(`-`\) no nome do arquivo. Por exemplo, você pode ter o título do arquivo como Introdução 1 ou Introduction@1, o nome do arquivo correspondente gerado para ambos os casos seria Introdução-1.

Ao definir uma lista de caracteres válidos, lembre-se de que esses caracteres &quot;`*/:[\]|#%{}?&<>"/+`&quot; e `a space` sempre será substituído por um hífen \(`-`\).

>[!NOTE]
>
> Se você não configurar a lista de caracteres especiais válida, o processo de criação de arquivo poderá fornecer resultados inesperados.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar os caracteres especiais válidos nos nomes de arquivo e na saída do site AEM:

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Certifique-se de que a propriedade esteja definida como ``'<>`@$``. Você pode adicionar mais caracteres especiais a esta lista. |

Você também pode configurar as outras propriedades, como usar letras minúsculas nos nomes de arquivo, separador para lidar com caracteres inválidos e o número máximo de caracteres permitidos nos nomes de arquivo. Para configurar essas propriedades, adicione os seguintes pares de valores principais no arquivo de configuração:

| Chave de propriedade | Valor da propriedade |
|------------|--------------|
| `nodename.uselower` | Booleano \(true/false\).<br> **Valor padrão**: verdadeiro |
| `nodename.separator` | Qualquer caractere. <br> **Valor padrão**: \_ *\(sublinhado\)* |
| `nodename.maxlength` | Valor inteiro.<br> **Valor padrão**: 50 |

### Configurar nivelamento da estrutura do nó do site AEM

Quando você gera a saída do site AEM, um nó para cada elemento nos tópicos é criado internamente. Para um mapa DITA com milhares de tópicos, essa estrutura de nó pode se tornar muito profunda. Esse tipo de estrutura de nó profundamente aninhada pode ter problemas de desempenho em sites maiores. O instantâneo a seguir exibe a estrutura de nó aninhada para uma saída do site AEM:

![](assets/deep-nested-aem-site-node-structure.png)

No instantâneo acima, observe que há um nó criado para cada `p` elemento e seus subelementos subsequentes e uma estrutura semelhante é criada para cada outro elemento usado no tópico.

Guias do AEM permitem configurar como a estrutura de nó da saída do site do AEM é criada internamente. É possível nivelar a estrutura do nó em elementos especificados, o que significa que você pode definir um elemento que será considerado como o elemento principal e todos os subelementos dentro dele serão mesclados com o elemento principal. Por exemplo, se você decidir nivelar a variável `p` elemento, então qualquer elemento que apareça dentro do `p` o elemento será mesclado com o principal `p` elemento. Uma nota separada não seria criada para nenhum subelemento dentro da `p` elemento. O instantâneo a seguir exibe a estrutura do nó nivelada em `p` elemento:

![](assets/flattened-aem-site-node-structure.png)

Para nivelar a estrutura do nó do site AEM, execute as seguintes etapas:

1. Identifique o elemento\(s\) no qual deseja nivelar a estrutura do nó:

1. Sobreposição do `libs` no nó `apps` e abra o arquivo elementmapping.xml.

1. Adicione o `<flatten>true</flatten>` na definição do elemento no qual deseja nivelar a estrutura do nó. Por exemplo, se você deseja nivelar a estrutura do nó na `p` elemento e, em seguida, adicione o atributo nivelado na definição de `p` como mostrado abaixo:

   ```XML
   <ditaelement>
         <name>p</name>
         <class>- topic/p</class>
         <componentpath>fmdita/components/dita/wrapper</componentpath>
         <type>COMPOSITE</type>
         <target>para</target>
         <flatten>true</flatten>
         <wrapelement>div</wrapelement>
      </ditaelement>
   ```

   >[!NOTE]
   >
   > Por padrão, a propriedade do nó nivelado foi configurada no `p` elemento.

1. Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração.
1. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\):

   | PID | Chave de propriedade | Valor da propriedade |
   |---|------------|--------------|
   | `com.adobe.dxml.flattening.FlatteningConfigurationService` | `flattening.enabled` | Booleano \(true/false\).<br> **Valor padrão**: `false` |


Agora, ao gerar a saída do site AEM, os nós dentro do `p` elementos são nivelados e armazenados no `p` elemento em si. É possível encontrar as novas propriedades de nivelamento para o `p` elemento no CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png)

**Pesquisar uma string no conteúdo na saída do site AEM**

Por padrão, você pode pesquisar por uma string nos títulos somente na saída do site AEM. Você pode configurar o sistema para procurar uma string nos títulos e também no conteúdo ou no corpo da saída do site do AEM.

>[!NOTE]
>
> Às vezes, a pesquisa pode funcionar para alguns elementos no conteúdo, mas você pode configurá-la para funcionar para todo o conteúdo.

![](assets/flatten-aem-site-note-props-crxde-search.png)

Para habilitar a pesquisa, você deve configurar o nivelamento da estrutura do nó do site AEM.

CUIDADO:

Você pode pesquisar até 1 MB de conteúdo nivelado. Por exemplo, na captura de tela anterior, você pode pesquisar se o conteúdo em &lt;p> é &lt;= 1Mb.

>[!NOTE]
>
> A pesquisa funciona nos elementos somente se a variável `<flatten>`atributo está definido como verdadeiro. Por padrão, os Guias do AEM têm a `<flatten>` atributo definido como verdadeiro para os elementos de texto comumente usados, como &lt;p> &lt;ul> &lt;li>. No entanto, se você tiver criado alguns elementos personalizados, defina a variável `<flatten>` atributo para true no arquivo elementmapping.xml.

**Impedir nivelamento da estrutura do nó do site AEM**

Semelhante à especificação do nó a ser nivelado na saída do site AEM, você também pode especificar um elemento que deseja excluir dessa configuração. Por exemplo, se você deseja nivelar nós em `body` elemento, mas você não deseja nenhum `table` elemento dentro `body` para nivelar, é possível adicionar a propriedade exclude na variável `table` definição do elemento.

Para excluir o `table` elemento do nivelamento, adicione a seguinte propriedade à variável `table` definição do elemento:

`<preventancestorflattening>true|false</preventancestorflattening>`

### Configurar o controle de versão para páginas excluídas na saída do site AEM

Ao gerar uma saída de site AEM com **Excluir e** Criar ****opção selecionada para a configuração Páginas de saída existentes, uma versão é criada para a página\(s\) que está sendo excluída. Você pode configurar o sistema para interromper a criação de uma versão antes da exclusão.

Execute as seguintes etapas para interromper a criação de uma versão para a página\(s\) que está sendo excluída:

1. Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração.
1. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para configurar o **Não criar versão para páginas excluídas** opção:

   | PID | Chave de propriedade | Valor da propriedade |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `no.version.creation.on.deletion` | Booleano \(true/false\).<br> **Valor padrão**: `true` |

   >[!NOTE]
   >
   > Com essa opção selecionada, os usuários poderão excluir diretamente qualquer página\(s\) sem criar qualquer versão para eles. Se a opção não estiver selecionada, uma versão será criada antes que a página\(s\) seja excluída.

### Configurar reescrita personalizada com guias de Experience Manager {#custom-rewriter}

O Experience Manager Guides tem um sling personalizado [**reescritor**](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html) módulo para tratamento de ligações geradas em caso de mapas cruzados (ligações entre os tópicos de dois mapas diferentes). Essa configuração de reescrita está instalada no seguinte caminho: <br> `/apps/fmdita/config/rewriter/fmdita-crossmap-link-patcher`.

Se você tiver outra reescrita de sling personalizada em sua base de código, use uma `'order'` valor maior que 50, como o sling rewriter dos Guias do Experience Manager usa `'order'` 50.  Para substituir isso, é necessário um valor >50. Para obter mais detalhes, consulte [Pipelines de reescrita de saída](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).


## Usar metadados na saída de publicação por meio do DITA-OT {#id191LF0U0TY4}

Os Guias do AEM fornecem uma maneira de transmitir metadados personalizados ao publicar saída usando DITA-OT. Como administrador e Editor, seria necessário executar as seguintes tarefas para configurar e usar metadados personalizados na saída publicada:

- Como administrador, adicione os metadados necessários no sistema para que ele fique disponível na página Propriedades do mapa DITA.

- Como administrador, adicione os metadados personalizados à lista de metadados para que sejam exibidos no console de mapa DITA.

- Como um Editor, configure e adicione os metadados personalizados com o mapa DITA e gere a saída necessária.


Para adicionar os metadados necessários no sistema, execute as seguintes etapas:

1. Faça logon no Adobe Experience Manager como administrador.

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecionar **Assets** na lista de ferramentas.

1. Clique no link **Esquemas de metadados** bloco.

   A página Forms do Esquema de Metadados é exibida.

1. Selecione o **padrão** formulário da lista.

   >[!NOTE]
   >
   > As propriedades exibidas na página Propriedades de um mapa DITA são obtidas desse formulário.

1. Clique em **Editar**.

1. Adicione os metadados personalizados que deseja usar nas saídas publicadas. Por exemplo, adicionaremos metadados de público-alvo usando as seguintes etapas:

   1. No **Formulário de criação** lista de componentes, arrastar e soltar **Texto em linha única** componente no formulário.

   2. Selecione o novo campo para abrir a variável **Configurações** do campo.

   3. No **Rótulo do campo**, insira o nome dos metadados — Público-alvo.

   4. No **Mapear para a propriedade** , especifique ./jcr:content/metadata/&lt;name of=&quot;&quot; the=&quot;&quot; metadata=&quot;&quot;>. Para o nosso exemplo, vamos defini-lo como ./jcr:content/metadata/audience.

   Usando essas etapas, adicione todos os parâmetros de metadados necessários.

1. Clique em **Salvar**.


O novo parâmetro agora é exibido na página Propriedades para todos os mapas DITA.

![](assets/properties-page-custom-metadata.PNG)

Em seguida, você precisa disponibilizar os metadados personalizados no console de mapas DITA. Execute as seguintes etapas para disponibilizar os metadados personalizados no painel do mapa DITA:

1. Use o gerenciador de pacotes para acessar o arquivo metadataList disponível no seguinte local no repositório Git do Cloud Manager:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > O arquivo metadataList contém uma lista de propriedades que são mostradas no **Propriedades** lista suspensa de um mapa DITA no painel do mapa. Por padrão, há quatro propriedades listadas nesse arquivo: docstate, dc:language, dc:description e dc:title.

1. Adicione os metadados personalizados adicionados na página Forms do Esquema de metadados. Para o nosso exemplo, adicione o parâmetro de público-alvo ao final da lista padrão.


Agora, os metadados personalizados serão exibidos no do console de mapa DITA **Propriedades** lista suspensa.

Por fim, como Editor, é necessário incluir os metadados personalizados na saída publicada. Para processar os metadados personalizados ao gerar a saída, execute as seguintes etapas:

1. Na interface do usuário do Assets, navegue até o mapa DITA que deseja publicar.

1. Selecione o arquivo de mapa DITA e abra a página de propriedades.

1. Na página Propriedades, especifique o valor dos metadados personalizados. Para o nosso exemplo, especificamos um valor Externo para o parâmetro de público-alvo.

   ![](assets/properties-page-custom-metadata-value.png)

1. Clique em **Salvar e fechar**.

1. Clique no arquivo de mapa DITA para abrir o console de mapa DITA.

1. No **Predefinições de saída** selecione a predefinição de saída que deseja usar para gerar a saída.

1. Clique em **Editar**.

1. No **Propriedades** selecione as propriedades que deseja transmitir ao processo de publicação.

   ![](assets/props-in-publish-output.PNG)


As propriedades/metadados selecionados são passados para o processo de publicação e disponibilizados na saída final.

### Validar a transmissão de metadados ao DITA-OT para processamento

Para validar os valores de metadados transmitidos para o DITA-OT, é possível usar o ambiente local usando um jar pronto para nuvem. Como não é possível acessar o sistema de arquivos local na nuvem, a única maneira de validar o arquivo de metadados é por meio do jar pronto para nuvem.

- Nome do arquivo: metadata.xml
- Local do arquivo: crx-quickstart/profiles/ditamaps/&lt;ditamap-1234>

  Para acessar metadata.xml:

   - Faça logon no local do servidor em que a instância do AEM está em execução.
   - Migrar para crx-quickstart/profiles/ditamaps/&lt;newly-created-directory-name>/metadata.xml.
- Formato de arquivo de exemplo:

  **metadata.xml**

  ```XML
  <?xml version="1.0" encoding="UTF-8" standalone="no"?>
  <root>
     <Path id="/absolutePath/sampleMap.ditamap">
        <metadata>
           <meta isArray="false" key="dc:description">This is a file</meta>
           <meta isArray="false" key="dc:title">Myfile</meta>
           <meta isArray="true" key="multivalueText">One;Two;Three</meta>
        </metadata>
     </Path>
     <Path id="/absolutePath/sampleTopic.dita">
        <metadata>
           <meta isArray="false" key="dc:description">description for the accountability</meta>
           <meta isArray="false" key="dc:title">accountability title</meta>
           <meta isArray="true" key="multivalueText">value1</meta>
        </metadata>
     </Path>
  </root>
  ```


- isArray: um atributo booleano que define se os metadados são multivalores \(Array\) ou não. Os valores são delimitados por um ponto e vírgula.
- ID do caminho: caminho absoluto para o arquivo armazenado no diretório temporário.

>[!NOTE]
>
> Se não houver metadados específicos para o arquivo, &lt;meta> A tag com a chave não aparecerá como a propriedade desse arquivo no arquivo metadata.xml.

## Personalizar o mapeamento de elemento DITA com componentes AEM {#id1679J600HEL}

Os elementos DITA nos Guias AEM são mapeados para seus componentes AEM correspondentes. Os Guias do AEM usam esse mapeamento em fluxos de trabalho, como publicação e revisão, para converter o elemento DITA em um componente AEM correspondente. O mapeamento é definido na variável `elementmapping.xml` arquivo, que pode ser acessado usando o gerenciador de pacotes.

>[!NOTE]
>
> Não faça nenhuma personalização nos arquivos de configuração padrão disponíveis no ``libs`` nó. É necessário criar uma sobreposição do ``libs`` no nó ``apps`` e atualize os arquivos necessários no ``apps`` somente nó.

Você pode usar os mapeamentos predefinidos de elementos DITA ou mapear elementos DITA para os componentes personalizados do AEM. Para usar os componentes personalizados do AEM, é necessário compreender a estrutura do `elementmapping.xml` arquivo.

### estrutura elementmapping.xml

Uma visão geral de alto nível da `elementmapping.xml` estrutura é explicada abaixo:

1. Cada elemento DITA é pesquisado primeiro por um mapeamento de componente correspondente com base no nome do elemento. Por exemplo:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   No exemplo acima, todos `substeps` Os elementos DITA são renderizados usando o `dita/components/ditaolist` componente.

1. Se um elemento DITA não encontrar uma correspondência com base no nome, uma correspondência com base na variável `class` está concluído. Por exemplo:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   No exemplo acima, se não houver mapeamento definido para a variável `task` elemento, em seguida, a variável `task` elemento é mapeado para o componente acima porque `task` é herdado do `topic` componente.

1. Quando um elemento tem um mapeamento de componente correspondente, o processamento adicional de seus elementos secundários é determinado por `type`. Por exemplo:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` tem os seguintes valores:

   - COMPOSTO: elemento a componente *o mapeamento continua para elementos secundários* também.

   - INDEPENDENTE: os elementos secundários do elemento atual são *não mapeado*.

   No exemplo acima, se a variável `<title>` elemento tiver qualquer elemento filho, eles não serão mapeados para nenhum outro componente. O componente para `<title>` elemento é responsável por renderizar todos os elementos secundários dentro do `<title>` elemento.

1. Se houver vários componentes mapeados para um único elemento DITA, a melhor correspondência para o elemento será selecionada. Para selecionar o componente de melhor correspondência, a especialização estrutural e de domínio de elementos DITA é considerada.

   Se houver elementos DITA com especialização de domínio e um componente for mapeado para especialização de domínio, esse componente receberá alta prioridade.

   Da mesma forma, se houver elementos DITA com especialização estrutural e um componente for mapeado para especialização estrutural, esse componente receberá alta prioridade.

1. Você pode usar `<attributemap>` no mapeamento de elementos para mapear valores de atributo às propriedades do nó correspondentes.
1. `textprop` pode ser usado para serializar o conteúdo de texto de um elemento DITA para uma propriedade de nó. Além disso, ele pode ser usado várias vezes em uma tag element para serializar o conteúdo do texto em vários locais na hierarquia publicada. Você também pode personalizar a localização e o nome da propriedade do público-alvo. Por exemplo:

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   O mapeamento de elementos acima especifica que o conteúdo do texto de `<title>` O elemento será salvo como valor de uma propriedade chamada `jcr:title` no nó de saída.

1. `xmlprop` pode ser usado para serializar o XML inteiro de um determinado elemento para uma propriedade de nó. O componente pode ler essa propriedade do nó e fazer renderização personalizada. Por exemplo:

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   O mapeamento de elemento acima especifica que toda a marcação XML do elemento `<svg-container>` será salvo como valor de uma propriedade chamada `data` no nó de saída.

1. Há um mapeamento de atributo especial para lidar com a resolução de caminho no processo de geração de saída. Por exemplo:

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Para o exposto acima `attributemap`, o `href` atributo no elemento DITA será mapeado para uma propriedade de nó chamada `fileReference`. Agora desde `ispath` está definida como `true`, o processo de geração de saída resolve esse caminho e o define em `fileReference` propriedade do nó.

   A forma como esta resolução se processa é determinada com base no `rel` atributo no mapeamento de atributos.

   - Se `rel=source`, então valor de `href` é resolvido em relação ao arquivo de origem DITA que está sendo processado no momento. O valor de `href` é resolvido e colocado no valor de `fileReference` propriedade.

   - Se `rel=target`, então valor de `href` é resolvido em relação ao local de publicação raiz. O valor de `href` é resolvido e colocado no valor de `fileReference` propriedade.

   Se não quiser que ocorra nenhum pré-processamento ou resolução nos atributos de caminho, não será necessário especificar o `ispath` atributo. O valor é copiado como está e o componente pode fazer a resolução necessária.


### Esquema de elemento DITA

Veja a seguir um exemplo do esquema do elemento DITA em `elementmapping.xml` arquivo:

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

A tabela a seguir descreve os elementos do esquema de elemento DITA:

| Elemento | Descrição |
|-------|-----------|
| `<ditaelement>` | O nó de nível superior de cada elemento de mapeamento. |
| `<class>` | O atributo de classe do elemento DITA de destino para o qual você está gravando o componente.<br> Por exemplo, o atributo de classe do tópico DITA é: <br> `- topic/topic` |
| `<componentpath>` | O caminho CRXDE do componente AEM mapeado. |
| `<type>` | Valores possíveis:<br> -   **COMPOSTO**: também processa elementos secundários <br> -   **INDEPENDENTE**: ignora o processamento de elementos secundários |
| `<attributeprop>` | Usado para mapear atributos e valores DITA serializados para nós AEM como uma propriedade. Por exemplo, se você tiver `<note type="Caution">` o elemento e o componente mapeado para esse elemento `<attributeprop>attr_t</ attributeprop>`, o atributo e o valor do nó serão serializados para `attr_t` propriedade do nó AEM correspondente \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Salve o `getTextContent()` saída para a propriedade definida por `propname_t.` <br> **Nota:** Esta é uma propriedade otimizada. |
| `<xmlprop>propname_x </xmlprop>` | Salvar XML serializado deste nó na propriedade definida por `propname_x.<br> `**Nota:** Esta é uma propriedade otimizada. |
| `<xpath>` | Se o elemento XPath for fornecido no mapeamento de elementos, juntamente com o nome e a classe do elemento, a condição XPath também deverá ser atendida para que o mapeamento do componente seja usado. |
| `<target>` | Coloque o elemento DITA no repositório crx no local especificado.<br> Valores possíveis: <br> - **head**: No nó head <br> - **texto**: No nó do parágrafo |
| `<wrapelement>` | O elemento HTML para envolver o conteúdo. |
| `<wrapclass>` | O valor do elemento para a propriedade `wrapclass.` |
| `<attributemap>` | Nó de contêiner contendo um ou mais `<attribute>` nós. |
| `<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />` | Mapeia os atributos DITA para propriedades AEM: <br> -   **`from`**: nome do atributo DITA <br> -   **`to`**: nome da propriedade do componente AEM <br> -   **`ispath`**: Se o atributo for um valor de caminho \(por exemplo: *imagem*\) <br> -   **`rel`**: se o caminho for o destino ou origem <br> **Nota:** Se `attrname` começa com `%`, em seguida, mapear `attrname minus '%'` para prop &#39; `propname`&#39;. |

**Observações adicionais**

- Se você planeja substituir o mapeamento de elemento padrão, é recomendável não fazer as alterações no padrão `elementmapping.xml` arquivo. Você deve criar um novo arquivo XML de mapeamento e colocar o arquivo em outro local, de preferência na pasta de aplicativos personalizados que você cria.

- No `elementmapping.xml` , há muitas entradas de mapeamento que fazem referência ao componente fmdita/components/dita/wrapper. Wrapper é um componente genérico que renderiza construções DITA relativamente simples usando propriedades no nó do site para gerar HTML relevante. Ele usa o `wrapelement` para gerar tags delimitadoras e delega a renderização secundária aos componentes correspondentes. Isso é útil nos casos em que você deseja apenas um componente de contêiner. Em vez de criar um novo componente que renderiza uma tag container específica como `div` ou `p`, você pode usar o componente Wrapper com a variável `wrapelement` e `wrapclass` propriedades para obter o mesmo efeito.

- Não é recomendável salvar grandes quantidades de texto nas propriedades de JCR de string. O cálculo do tipo de propriedade otimizada na geração de saída garante que o conteúdo de texto grande não seja salvo como um tipo de sequência. Em vez disso, quando o conteúdo maior que um determinado limite precisa ser salvo, o tipo da propriedade é alterado para binário. Por padrão, esse limite está configurado para 512 bytes, mas pode ser alterado no Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) alterando a variável **Salvar como limite binário** configuração.

- Se você estiver planejando substituir alguns \(e não todos\) dos mapeamentos de elementos, não será necessário replicar todo o `elementmapping.xml` arquivo. É necessário criar um novo arquivo de mapeamento XML e definir apenas os elementos que você está substituindo.

- Depois de criar o arquivo XML no local personalizado, atualize o `Override Element Mapping` configuração no `com.adobe.fmdita.config.ConfigManager` pacote.


## Personalizar o console de mapa DITA {#id188HC08M0CZ}

O Guia de AEM oferece a flexibilidade de estender os recursos do console de mapas DITA. Por exemplo, se você tiver um conjunto de relatórios diferente do que está disponível nos Guias do AEM, poderá adicioná-los ao console de mapas. Para personalizar o console de mapas, é necessário criar uma Biblioteca de clientes AEM \(ou ClientLib\) que conterá o código para executar a funcionalidade necessária.

>[!NOTE]
>
> A modificação direta dos componentes da página não é recomendada, pois será substituída pelas novas versões do produto.

Os Guias do AEM fornecem a `apps.fmdita.dashboard-extn` categoria para personalizar o console de mapas. Sempre que o console de mapa for carregado, a funcionalidade criada no `apps.fmdita.dashboard-extn` A categoria é executada e carregada.

>[!NOTE]
>
> Para obter mais informações sobre como criar a biblioteca do cliente AEM, consulte [Uso de bibliotecas do lado do cliente](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=en).

## Manipular a representação da imagem durante a geração da saída {#id177BF0G0VY4}

O AEM vem com um conjunto de workflows e manipuladores de mídia padrão para processar ativos. No AEM, há fluxos de trabalho predefinidos para lidar com o processamento de ativos para os tipos MIME mais comuns. Normalmente, para cada imagem que você carrega, o AEM cria várias representações da mesma em formato binário. Essas representações podem ser de tamanhos diferentes, com uma resolução diferente, com uma marca d&#39;água adicionada ou alguma outra característica alterada. Para obter mais informações sobre como o AEM lida com ativos, consulte [Processamento de ativos usando manipuladores de mídia e fluxos de trabalho](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=en) na documentação do AEM.

O Guia AEM permite configurar qual representação de imagem usar no momento da geração de saída para seus documentos. Por exemplo, você pode escolher uma das representações de imagem padrão ou criar uma e usar a mesma para publicar seus documentos. O mapeamento de representação de imagem para publicação de seus documentos é armazenado no `/libs/fmdita/config/ **renditionmap.xml**` arquivo. Um trecho de `renditionmap.xml` é o seguinte:

>[!NOTE]
>
> É recomendável criar uma cópia do `renditionmap.xml` arquivo no `apps` pasta para todas as personalizações.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

A variável `mimetype` element especifica o tipo MIME do formato de arquivo. A variável `rendition output` element especifica o tipo de formato de saída e o nome da representação \(por exemplo, `cq5dam.web.1280.1280.jpeg`\) que deve ser usado para publicar a saída especificada. Você pode especificar as representações de imagem a serem usadas para todos os formatos de saída compatíveis: AEMSITE, PDF, HTML5, EPUB e CUSTOM.

Se a representação especificada não estiver presente, o processo de publicação dos Guias do AEM primeiro procurará a representação da Web da imagem fornecida. Se nem mesmo a representação da Web for encontrada, a representação original da imagem será usada.

>[!NOTE]
>
> Essas representações de imagem controlam somente a geração de saída. A representação da Web de uma imagem é usada quando você abre um documento para visualização ou revisão.

## Configurar período de limpeza automática para histórico de saída {#id19AAI070V8Q}

Quando você gera uma saída, ela é criada junto com os logs de saída. Para mapas DITA grandes, esses registros podem ocupar uma grande quantidade de espaço no repositório. Por padrão, os registros são armazenados no seguinte local do repositório:

`/var/dxml/metadata/outputHistory`

Durante um período de tempo, o tamanho coletivo de todos os arquivos de log poderia ficar em GB. Guias do AEM permitem configurar um período para manter esses arquivos de log no repositório. Após o período especificado, os registros, juntamente com o histórico de geração de saída, são excluídos do repositório.

>[!NOTE]
>
> O histórico de geração de saída é a entrada de log na lista Saídas geradas na guia Saídas.

A configuração do recurso de limpeza de histórico afeta a geração de saída para todos os mapas DITA no repositório. Na guia Saídas de um mapa DITA, o histórico é removido após o número especificado de dias e na hora especificada na configuração.

>[!NOTE]
>
> A remoção dos arquivos de log e do histórico de geração de saída não afeta a saída gerada.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(propriedade\) para definir um dia e hora para limpar o histórico e os logs de saída:

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.history.purgeperiod` | Especifique o número de dias após os quais o histórico de saída, juntamente com os logs de saída, será removido. Se você quiser desativar esse recurso, defina essa propriedade como 0.Everyday no horário especificado em que o processo de limpeza é executado nas saídas geradas antes do número de dias especificados nessa propriedade. <br> **Valor padrão**: 5 |
| `output.history.purgetime` | Especifique a hora em que o processo de expurgação será iniciado. <br> **Valor padrão**: 0:00 \(ou meia-noite de 0:00\) |

## Alterar o limite da lista de saídas recém-geradas {#id1679JH0H0O2}

É possível alterar o número máximo de saídas geradas exibidas na guia Saídas de um mapa DITA.

Use as instruções fornecidas em [Substituições de configuração](download-install-additional-config-override.md#) para criar o arquivo de configuração. No arquivo de configuração, forneça os seguintes detalhes \(property\) para alterar o número de saídas a serem exibidas na lista:

| PID | Chave de propriedade | Valor da propriedade |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.historylimit` | Valor inteiro.<br> **Valor padrão**: 25 |

>[!TIP]
>
> Consulte a *Histórico de saída* no guia de práticas recomendadas para práticas recomendadas relacionadas ao trabalho com o histórico de saída.
