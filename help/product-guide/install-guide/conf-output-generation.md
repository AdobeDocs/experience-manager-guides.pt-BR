---
title: Definir configurações de geração de saída
description: Saiba como definir configurações de geração de saída
exl-id: 6df31e3c-683c-4188-b917-9c1855d9b95b
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '5762'
ht-degree: 0%

---

# Definir configurações de geração de saída {#id181AI0B0E30}

O AEM Guides vem com muitas opções de configuração para você personalizar o processo de geração de saída. Este tópico aborda todas as configurações e personalizações que ajudariam você a configurar o processo de geração de saída.

## Configure a guia Linha de base no painel de mapa DITA {#id223MD0D0YRM}

É possível configurar e ocultar a guia Linha de base disponível no painel do mapa.

A variável **Ocultar guia Linha de base** A opção não está habilitada por padrão e você precisa habilitá-la no configMgr. Execute as seguintes etapas para habilitar a opção por padrão no Editor da Web:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Selecione o **Ocultar guia Linha de base** opção.

1. Clique em **Salvar**.

   >[!NOTE]
   >
   > Essa configuração é desabilitada por padrão e a guia Linha de base está disponível no painel de mapa.


## Configurar o FrameMaker Publishing Server {#id1678G0Z0TN6}

Você pode usar o FrameMaker Publishing Server \(FMPS\) para gerar saída para seu conteúdo DITA. A configuração do FMPS permitirá gerar saída em vários formatos suportados pelo FMPS.

>[!NOTE]
>
> Para gerar saída usando FMPS, você precisa ter o servidor FMPS configurado. Para obter detalhes sobre a instalação e a configuração, consulte o Guia do usuário do FrameMaker Publishing Server.

Para configurar o AEM Guides para usar o FMPS, atualize as seguintes propriedades do `com.adobe.fmdita.config.ConfigManager` no Console da Web.

>[!NOTE]
>
> Acessar http://&lt;server name=&quot;&quot;>:&lt;port>/system/console/configMgr URL para abrir o Console da Web.

| Propriedade | Descrição |
|--------|-----------|
| Domínio de logon do FrameMaker Publishing Server | Especifique o nome de domínio ou o nome do grupo de trabalho no qual o FrameMaker Publishing Server está hospedado. Com base na versão FMPS, forneça o nome de domínio como:-   **FMPS 2020**: Endereço IP como 192.168.1.101 <br>- **FMPS 2019 e anterior**: Endereço IP ou o nome do domínio |
| URL do FrameMaker Publishing Server | Especifique o URL do FrameMaker Publishing Server. Com base na versão do FMPS, forneça o URL do FMPS como:<br>- **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 e anterior**: `http://<fmps_ip>:<port>/fmserver/v1/` |
| Versão do FMPS | Especifique o número da versão do FrameMaker Publishing Server. Com base na versão FMPS, forneça as informações da versão como: <br>- **FMPS 2020**: 2020 <br> - **FMPS 2019 e anterior**: 2019 ou 2017 |
| Nome de usuário e senha do FrameMaker Publishing Server | Especifique o nome de usuário e a senha para acessar o FrameMaker Publishing Server. |
| Tempo Limite de FMPS | \(*Opcional*\) Especifique o tempo \(em segundos\) durante o qual o AEM Guides aguarda uma resposta do FrameMaker Publishing Server. Se nenhuma resposta for recebida no tempo especificado, os Guias do AEM encerram a tarefa de publicação e a tarefa é sinalizada como com falha. <br> Valor padrão: 300 segundos \(5 minutos\) |
| URL externo do AEM | *\(Opcional\)* O URL do AEM no qual o FrameMaker Publishing Server colocará os arquivos de saída gerados. Por exemplo, `http://<server-name>:<port>/`. |
| Nome de usuário e senha do administrador do AEM | *\(Opcional\)* O nome de usuário e a senha de um administrador da configuração do AEM. Ele será usado pelo FrameMaker Publishing Server para se comunicar com AEM. |
| Tempo Limite de Espera de Execução de Tarefa FMPS | Esta configuração só é aplicável para o FMPS 2020. Especifique o tempo \(em segundos\) após o qual o FMPS deixará de aguardar a execução desse processo. |

## Configurar a publicação combinada em um site AEM existente {#id1691I0V0MGR}

Se você tiver um site AEM com conteúdo DITA, poderá configurar sua saída de site AEM para publicar conteúdo DITA em um local predefinido no seu site. Por exemplo, na captura de tela a seguir de uma página do site AEM, a variável `ditacontent` é reservado para armazenar conteúdo DITA:

![](assets/publish-in-aem-site.png){width="300" align="left"}

Os nós restantes na página são criados diretamente do editor do site AEM. Definir a configuração de publicação para publicar conteúdo DITA em um local predefinido garante que nenhum conteúdo não DITA existente seja modificado pelo processo de publicação dos Guias AEM.

É necessário executar as seguintes configurações no site existente para permitir a publicação de conteúdo DITA em um nó predefinido:

- Configurar as propriedades do modelo do site

- Adicione nós ao site para publicar conteúdo DITA


Execute as seguintes etapas para configurar as propriedades do modelo do site existente:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o nó de configuração de modelo do site. Por exemplo, o AEM Guides armazena as configurações de template padrão no seguinte nó:

   `/libs/fmdita/config/templates/default`

   >[!NOTE]
   >
   > Não faça nenhuma personalização nos arquivos de configuração padrão disponíveis no `libs` nó. É necessário criar uma sobreposição do `libs` no nó `apps` e atualize os arquivos necessários no `apps` somente nó.

1. Adicione as seguintes propriedades:

   | Nome da propriedade | Tipo | Valor |
   |-------------|----|-----|
   | `topicContentNode` | String | Especifique o nome do nó onde deseja publicar o conteúdo DITA. Por exemplo, o nó padrão em que o AEM Guides publica conteúdo DITA é: <br>`jcr:content/contentnode` |
   | `topicHeadNode` | String | Especifique o nome do nó em que você deseja armazenar as informações de metadados do conteúdo DITA. Por exemplo, o nó padrão em que os Guias do AEM armazenam informações de metadados é: <br>`jcr:content/headnode` |


A captura de tela a seguir mostra as propriedades adicionadas ao nó de modelo padrão dos Guias AEM:

![](assets/add-content-node.png){width="800" align="left"}

Na próxima vez que você publicar qualquer conteúdo DITA usando as configurações de modelo do seu site, o conteúdo será publicado nos nós especificados na `topicContentNode` e `topicHeadNode` propriedades.

No entanto, para sites existentes, é necessário adicionar manualmente o `topicContentNode` e `topicHeadNode` nós.

Execute as seguintes etapas para adicionar os nós necessários ao site existente:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Localizar `jcr:content` no nó do site.

1. Adicionar `topicContentNode` e `topicHeadNode` nós com o mesmo nome que você especificou nas configurações de modelo do site.


## Personalizar saída do site AEM {#id166TG0B30WR}

O AEM Guides permite a criação de saídas nos seguintes formatos:

- Site AEM

- PDF

- HTML 5
- EPUB
- Saída personalizada através do DITA-OT

Para a saída do site AEM, é possível atribuir modelos de design diferentes com tarefas de saída diferentes. Esses modelos de design podem renderizar o conteúdo DITA em diferentes layouts. Por exemplo, você pode especificar diferentes modelos de design para públicos-alvo internos e externos.

Você também pode usar os plug-ins personalizados do DITA Open Toolkit \(DITA-OT\) com guias do AEM. Você pode fazer upload desses plug-ins DITA-OT personalizados para gerar saída de PDF de uma maneira específica.

>[!TIP]
>
> Consulte a *Publicação no site do AEM* no guia de Práticas recomendadas[appendix.md\#](appendix.md#) para obter as práticas recomendadas sobre como criar a saída do site AEM.

### Personalizar modelo de design para gerar saída {#customize_xml-add-on}

Guias de AEM usam um conjunto de modelos de design predefinidos para gerar a saída do site AEM. Você pode personalizar os modelos de design dos Guias do AEM para gerar a saída que esteja em conformidade com a marca da sua empresa. Um modelo de design é uma coleção de vários estilos \(CSS\), scripts \(do lado do servidor e do lado do cliente\), recursos \(imagens, logotipos e outros ativos\) e nós JCR que unem todos esses recursos. Um modelo de design pode ser tão simples quanto um único script do lado do servidor com apenas alguns nós JCR, ou uma combinação complexa de estilos, recursos e nós JCR. Os modelos de design são usados pelo subsistema de publicação AEM Guides ao gerar saída do site AEM e eles controlam a estrutura, aparência e comportamento da saída gerada.

Não há restrição quanto ao local onde os recursos do modelo de design devem estar localizados no servidor, mas geralmente são organizados logicamente de acordo com sua função. Por exemplo, o modelo padrão tem todos os arquivos JavaScript e CSS armazenados em `/etc/designs/fmdita/clientlibs/siteoutput/default` pasta. Sempre que esses arquivos estiverem localizados, eles serão vinculados por uma coleção de nós JCR. Juntos, esses nós JCR e os arquivos constituem todo o modelo de design.

O modelo de design padrão enviado com o AEM Guides permite personalizar os componentes de página de aterrissagem, tópico e pesquisa. Você pode fazer uma cópia do design padrão e dos modelos de referência correspondentes e especificar componentes diferentes para gerar a saída desejada.

Execute as seguintes etapas para especificar seu próprio modelo de design a ser usado para a geração de saída do site AEM:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o nó do modelo de design padrão. O local do nó do modelo de design padrão é:

   `/libs/fmdita/config/templates/`

   ![](assets/templates-node.png){width="300" align="left"}

   >[!NOTE]
   >
   > Faça uma cópia dos modelos de design padrão do `libs` pasta para a `apps` e faça alterações no `apps` pasta. Você também deve fazer alterações nos templates referenciados a partir do nó de template padrão. Os modelos referenciados são colocados em `/libs/fmdita/templates/default/cqtemplates` nó. Faça uma cópia dos modelos referenciados na `apps` antes de fazer qualquer alteração.

1. Clique em *padrão* componente no *modelos* para acessar suas propriedades.

   As propriedades do modelo de design dos Guias de AEM são descritas na tabela a seguir.

   | Propriedade | Descrição |
   |--------|-----------|
   | `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Especifique a `cq:Template` para essas páginas correspondentes \(landing page, pesquisa e tópico\). Por padrão, a variável `cq:Template` o nó dessas páginas pode ser encontrado em `/libs/fmdita/templates/default/cqtemplates` nó. Esse nó define a estrutura e as propriedades das páginas de aterrissagem, pesquisa e tópico. <br>A variável `shadowPageTemplate` é usado para otimizar o conteúdo fragmentado. É necessário definir o valor dessa propriedade como: <br> `fmdita/templates/default/cqtemplates/shadowpage` <br> **Nota** Você deve especificar um valor para o `topicPageTemplate`. A variável `landingPageTemplate` e `searchPageTemplate` são propriedades opcionais. Se não quiser que as páginas de pesquisa e de aterrissagem sejam geradas, não especifique essas propriedades. |
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

Para obter mais informações, consulte [Criação do seu site First Adobe Experience Manager 6.3](https://helpx.adobe.com/experience-manager/using/first_aem63_website.html) e [Noções básicas](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/the-basics.html) de desenvolver seu próprio site sobre AEM.

### Usar o título do documento para gerar a saída do site AEM

Ao gerar a saída do site AEM, a forma como os URLs são gerados desempenha um papel importante na descoberta do seu conteúdo. Caso esteja usando nomes de arquivo baseados em UUID, gerar URLs com base na UUID de seus arquivos não será amigável para pesquisa. Como Administrador ou Editor, você tem o controle sobre como gerar os URLs para a saída do AEM Site. Guias do AEM fornecem uma configuração por meio da qual você pode optar por gerar os URLs de saída do site AEM usando o título do arquivo, em vez dos nomes de arquivo baseados em UUID. Por padrão, para sistemas de arquivos baseados em UUID, essa opção está ativada. Isso implicava que, quando você gera a saída do site AEM para sistemas de arquivos baseados em UUID, os títulos do arquivo são usados para gerar os URLs e não os UUIDs dos arquivos.

Ao gerar a saída do site AEM, a forma como os URLs são gerados desempenha um papel importante na descoberta do seu conteúdo. No caso de sistemas de arquivos não baseados em UUID, a saída do site AEM é gerada usando os nomes dos arquivos e não os títulos dos arquivos. Como Administrador ou Editor, você tem o controle sobre como gerar os URLs para a saída do AEM Site. Guias do AEM fornecem uma configuração por meio da qual você pode optar por gerar os URLs de saída do site AEM usando o título do arquivo em vez dos nomes dos arquivos. Por padrão, essa opção está desativada. Isso implicava que, quando você gera a saída do site AEM, os nomes dos arquivos são usados para gerar os URLs e não o título do arquivo. Você pode optar por gerar os URLs com base nos títulos dos arquivos ativando essa opção.

>[!NOTE]
>
> Você pode configurar regras adicionais para permitir apenas um conjunto de caracteres nos URLs de uma saída de site AEM. Para obter mais detalhes, consulte [Configurar regras de limpeza de nome de arquivo para criar tópicos e publicar a saída do site AEM](#id2164D0KD0XA).

Para configurar a geração de URLs na saída do site AEM, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. Selecione o **Usar título para nomes de página do site do AEM** opção.

   >[!NOTE]
   >
   > Caso deseje gerar saída usando os nomes de arquivo, desmarque essa opção.

1. Clique em **Salvar**.


### Configurar regras de limpeza de nome de arquivo para criar tópicos e publicar a saída do site AEM {#id2164D0KD0XA}

Como administrador, você pode definir uma lista de caracteres especiais válidos permitidos em nomes de arquivo, que eventualmente formam o URL de uma saída de site AEM. Em versões anteriores, os usuários podiam definir nomes de arquivo contendo caracteres especiais, como `@`, `$`, `>`e muito mais. Esses caracteres especiais resultavam em URL codificado na geração de páginas do site AEM.

A partir da versão 3.8, foram adicionadas configurações para definir uma lista de caracteres especiais permitidos nos nomes de arquivo. Por padrão, a configuração de nome de arquivo válido contém &quot;`a-z A-Z 0-9 - _`&quot;. Isto implica que, ao criar um arquivo, você pode ter qualquer caractere especial no título do arquivo, mas internamente ele será substituído por um hífen \(`-`\) no nome do arquivo. Por exemplo, você pode ter o título do arquivo como Introdução 1 ou Introduction@1, o nome do arquivo correspondente gerado para ambos os casos seria Introdução-1.

Ao definir uma lista de caracteres válidos, lembre-se de que esses caracteres &quot;`*/:[\]|#%{}?&<>"/+`&quot; e `a space` sempre será substituído por um hífen \(`-`\).

>[!NOTE]
>
> Se você não configurar a lista de caracteres especiais válida, o processo de criação de arquivo poderá fornecer resultados inesperados.

Para configurar os caracteres especiais válidos nos nomes de arquivo e na saída do site AEM, execute as seguintes etapas:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link *com.adobe.fmdita.common.SanitizeNodeNameImpl* pacote.

1. No **Conjunto de caracteres não permitido para publicação no AEM Sites** propriedade, certifique-se de que a propriedade esteja definida como ```'<>`@$```. Você pode adicionar mais caracteres especiais a essa lista, no entanto, ela deve ter esses caracteres especiais necessários.

   >[!NOTE]
   >
   > Também é possível configurar outras propriedades, como **Usar Minúsculas** em nomes de arquivo, **Separador** para manipular caracteres inválidos e **Número máximo de caracteres** permitido nos nomes de arquivo.

1. Clique em **Salvar**.

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. No **Regex para caracteres válidos** propriedade, certifique-se de que a propriedade esteja definida como `[-a-zA-Z0-9_]`. Você pode adicionar mais caracteres a esta lista, no entanto, ela deve ter esses caracteres básicos e a lista deve começar com um hífen \(`-`\).

   >[!NOTE]
   >
   > Essa propriedade define a lista de caracteres válidos usados para criar um novo arquivo.

1. Clique em **Salvar**.


### Configurar nivelamento da estrutura do nó do site AEM

Quando você gera a saída do site AEM, um nó para cada elemento nos tópicos é criado internamente. Para um mapa DITA com milhares de tópicos, essa estrutura de nó pode se tornar muito profunda. Esse tipo de estrutura de nó profundamente aninhada pode ter problemas de desempenho em sites maiores. O instantâneo a seguir exibe a estrutura de nó aninhada para uma saída do site AEM:

![](assets/deep-nested-aem-site-node-structure.png){width="300" align="left"}

No instantâneo acima, observe que há um nó criado para cada `p` elemento e seus subelementos subsequentes e uma estrutura semelhante é criada para cada outro elemento usado no tópico.

Guias do AEM permitem configurar como a estrutura de nó da saída do site do AEM é criada internamente. É possível nivelar a estrutura do nó em elementos especificados, o que significa que você pode definir um elemento que será considerado como o elemento principal e todos os subelementos dentro dele serão mesclados com o elemento principal. Por exemplo, se você decidir nivelar a variável `p` elemento, então qualquer elemento que apareça dentro do `p` o elemento será mesclado com o principal `p` elemento. Uma nota separada não seria criada para nenhum subelemento dentro da `p` elemento. O instantâneo a seguir exibe a estrutura do nó nivelada em `p` elemento:

![](assets/flattened-aem-site-node-structure.png){width="300" align="left"}

Para nivelar a estrutura do nó do site AEM, execute as seguintes etapas:

1. Especifique o elemento no qual deseja nivelar a estrutura do nó.

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

1. Habilite a configuração de nivelamento do nó do site no configMgr.

   1. Abra a página Configuração do console da Web do Adobe Experience Manager.

      O URL padrão para acessar a página de configuração é:

      ```http
      http://<server name>:<port>/system/console/configMgr
      ```

   1. Procure por e clique no link *com.adobe.dxml.flattening.FlatteningConfigurationService* pacote.

   1. Selecione o **Nivelamento de propriedade.enabled** opção.

   1. Clique em **Salvar**.


>[!IMPORTANT]
>
> Se você tiver feito qualquer alteração no arquivo elementmapping.xml, abra o configMgr e salve qualquer pacote para que as alterações entrem em vigor.

Agora, ao gerar a saída do site AEM, os nós dentro do `p` elementos são nivelados e armazenados no `p` elemento em si. É possível encontrar as novas propriedades de nivelamento para o `p` elemento no CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

**Impedir achatamento da estrutura de nota do site AEM**

Semelhante à especificação do nó a ser nivelado na saída do site AEM, você também pode especificar um elemento que deseja excluir dessa configuração. Por exemplo, se você deseja nivelar nós em `body` elemento, mas você não deseja nenhum `table` elemento dentro `body` para nivelar, é possível adicionar a propriedade exclude na variável `table` definição do elemento.

Para excluir o `table` elemento do nivelamento, adicione a seguinte propriedade à variável `table` definição do elemento:

`<preventancestorflattening>true|false</preventancestorflattening>`

### Configurar o controle de versão para páginas excluídas na saída do site AEM

Ao gerar uma saída de site AEM com **Excluir e** Criar ****opção selecionada para a configuração Páginas de saída existentes, uma versão é criada para a página\(s\) que está sendo excluída. Você pode configurar o sistema para interromper a criação de uma versão antes da exclusão.

Execute as seguintes etapas para interromper a criação de uma versão para a página\(s\) que está sendo excluída:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link *com.adobe.fmdita.config.ConfigManager* pacote.

1. Selecionar **Não criar versão para páginas excluídas** opção.

   >[!NOTE]
   >
   > Com essa opção selecionada, os usuários poderão excluir diretamente qualquer página\(s\) sem criar qualquer versão para eles. Se a opção não estiver selecionada, uma versão será criada antes que a página\(s\) seja excluída.

1. Clique em **Salvar**.

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

   1. Selecione o novo campo para abrir a variável **Configurações** do campo.

   1. No **Rótulo do campo**, insira o nome dos metadados — Público-alvo.

   1. No **Mapear para a propriedade** , especifique ./jcr:content/metadata/&lt;name of=&quot;&quot; the=&quot;&quot; metadata=&quot;&quot;>. Para o nosso exemplo, vamos defini-lo como ./jcr:content/metadata/audience.

   Usando essas etapas, adicione todos os parâmetros de metadados necessários.

1. Clique em **Salvar**.


O novo parâmetro agora é exibido na página Propriedades para todos os mapas DITA.

![](assets/properties-page-custom-metadata.PNG){width="650" align="left"}

Em seguida, você precisa disponibilizar os metadados personalizados no console de mapas DITA. Execute as seguintes etapas para disponibilizar os metadados personalizados no painel do mapa DITA:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Acesse o arquivo metadataList disponível no seguinte local:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > O arquivo metadataList contém uma lista de propriedades que são mostradas no **Propriedades** lista suspensa de um mapa DITA no painel do mapa. Por padrão, há quatro propriedades listadas nesse arquivo: docstate, dc:language, dc:description e dc:title.

1. Adicione os metadados personalizados adicionados na página Forms do Esquema de metadados. Para o nosso exemplo, adicione o parâmetro de público-alvo ao final da lista padrão.

1. Clique em **Salvar tudo**.


Agora, os metadados personalizados serão exibidos no do console de mapa DITA **Propriedades** lista suspensa.

Por fim, como Editor, é necessário incluir os metadados personalizados na saída publicada. Para processar os metadados personalizados ao gerar a saída, execute as seguintes etapas:

1. Na interface do usuário do Assets, navegue até o mapa DITA que deseja publicar.

1. Selecione o arquivo de mapa DITA e abra a página de propriedades.

1. Na página Propriedades, especifique o valor dos metadados personalizados. Para o nosso exemplo, especificamos um valor Externo para o parâmetro de público-alvo.

   ![](assets/properties-page-custom-metadata-value.png){width="650" align="left"}

1. Clique em **Salvar e fechar**.

1. Clique no arquivo de mapa DITA para abrir o console de mapa DITA.

1. No **Predefinições de saída** selecione a predefinição de saída que deseja usar para gerar a saída.

1. Clique em **Editar**.

1. No **Propriedades** selecione as propriedades que deseja transmitir ao processo de publicação.

   ![](assets/props-in-publish-output.PNG){width="650" align="left"}


As propriedades/metadados selecionados são passados para o processo de publicação e disponibilizados na saída final.

## Personalizar o mapeamento de elemento DITA com componentes AEM {#id1679J600HEL}

Os elementos DITA nos guias AEM são mapeados para seus componentes AEM correspondentes. Os Guias do AEM usam esse mapeamento em fluxos de trabalho, como publicação e revisão, para converter o elemento DITA em um componente AEM correspondente. O mapeamento é definido na variável `elementmapping.xml` arquivo, que pode ser acessado no modo CRXDE Lite. Acesse o seguinte URL no modo CRXDE Lite:

`/libs/fmdita/config/elementmapping.xml`

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
       <class>- topic/title</class> 
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
    <attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />     
    </attributemap>     
    <skip>true|false</skip> 
</ditaelement>
```

A tabela a seguir descreve os elementos do esquema de elemento DITA:

| Elemento | Descrição |
|-------|-----------|
| `<ditaelement>` | O nó de nível superior de cada elemento de mapeamento. |
| `<class>` | O atributo de classe do elemento DITA de destino para o qual você está gravando o componente. <br>Por exemplo, o atributo de classe do tópico DITA é: <br>`topic/topic` |
| `<componentpath>` | O caminho CRXDE do componente AEM mapeado. |
| `<type>` | Valores possíveis: <br>- **COMPOSTO**: também processa elementos secundários <br>- **INDEPENDENTE**: ignora o processamento de elementos secundários |
| `<attributeprop>` | Usado para mapear atributos e valores DITA serializados para nós AEM como uma propriedade. Por exemplo, se você tiver `<note type="Caution">` o elemento e o componente mapeado para esse elemento `<attributeprop>attr_t</ attributeprop>`, o atributo e o valor do nó serão serializados para `attr_t` propriedade do nó AEM correspondente \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Salve o `getTextContent()` saída para a propriedade definida por `propname_t.` **Nota:**  Esta é uma propriedade otimizada. |
| `<xmlprop>propname_x </xmlprop>` | Salvar XML serializado deste nó na propriedade definida por `propname_x.` **Nota:** Esta é uma propriedade otimizada. |
| `<xpath>` | Se o elemento XPath for fornecido no mapeamento de elementos, juntamente com o nome e a classe do elemento, a condição XPath também deverá ser atendida para que o mapeamento do componente seja usado. |
| `<target>` | Coloque o elemento DITA no repositório crx no local especificado. <br>Valores possíveis:<br>- **head**: No nó head <br>- **texto**: No nó do parágrafo |
| `<wrapelement>` | O elemento HTML para envolver o conteúdo. |
| `<wrapclass>` | O valor do elemento para a propriedade `wrapclass.` |
| `<attributemap>` | Nó de contêiner contendo um ou mais `<attribute>` nós. |
| `<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />` | Mapeia os atributos DITA para propriedades AEM:<br>- **`from`**: nome do atributo DITA<br>- **`to`**: nome da propriedade do componente AEM <br>- **`ispath`**: Se o atributo for um valor de caminho \(por exemplo: *imagem*\)<br>- **`rel`**: se o caminho for o destino ou origem <br>**Nota:** Se `attrname` começa com `%`, em seguida, mapear `attrname minus '%'` para prop &#39; `propname`&#39;. |

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
> Para obter mais informações sobre como criar a biblioteca do cliente AEM, consulte [Uso de bibliotecas do lado do cliente](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/clientlibs.html).

## Manipular a representação da imagem durante a geração da saída {#id177BF0G0VY4}

O AEM vem com um conjunto de workflows e manipuladores de mídia padrão para processar ativos. No AEM, há fluxos de trabalho predefinidos para lidar com o processamento de ativos para os tipos MIME mais comuns. Normalmente, para cada imagem que você carrega, o AEM cria várias representações da mesma em formato binário. Essas representações podem ser de tamanhos diferentes, com uma resolução diferente, com uma marca d&#39;água adicionada ou alguma outra característica alterada. Para obter mais informações sobre como o AEM lida com ativos, consulte [Processamento de ativos usando manipuladores de mídia e fluxos de trabalho](https://helpx.adobe.com/experience-manager/6-5/assets/using/media-handlers.html) na documentação do AEM.

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

/var/dxml/metadata/outputHistory/

Durante um período de tempo, o tamanho coletivo de todos os arquivos de log poderia ficar em GB. Guias do AEM permitem configurar um período para manter esses arquivos de log no repositório. Após o período especificado, os registros, juntamente com o histórico de geração de saída, são excluídos do repositório.

>[!NOTE]
>
> O histórico de geração de saída é a entrada de log na lista Saídas geradas na guia Saídas.

A configuração do recurso de limpeza de histórico afeta a geração de saída para todos os mapas DITA no repositório. Na guia Saídas de um mapa DITA, o histórico é removido após o número especificado de dias e na hora especificada na configuração.

>[!NOTE]
>
> A remoção dos arquivos de log e do histórico de geração de saída não afeta a saída gerada.

Execute as seguintes etapas para definir um dia e hora para expurgar o histórico e os logs de saída:

1. Abra a página Configuração do console da Web do Adobe Experience Manager.

   O URL padrão para acessar a página de configuração é:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Procure por e clique no link **com.adobe.fmdita.config.ConfigManager** pacote.

1. No **Período de Expurgação do Histórico de Saída** especifique o número de dias após os quais o histórico da saída, juntamente com os logs de saída, será removido. Por padrão, é definido como 5 dias. Se você quiser desativar esse recurso, defina essa propriedade como 0.

1. No **Tempo de Limpeza do Histórico de Saída** especifique a hora em que o processo de expurgação será iniciado. Por padrão, é definido como 0:00 \(ou 12:00 meia-noite\). Todos os dias neste momento, o processo de limpeza é executado em saídas geradas antes do número de dias especificado no **Período de Expurgação do Histórico de Saída** propriedade.

   >[!NOTE]
   >
   > Por padrão, o recurso de limpeza é executado a cada meia-noite em saídas com mais de 5 dias.

1. Clique em **Salvar**.


## Alterar o limite da lista de saídas recém-geradas {#id1679JH0H0O2}

É possível alterar o número máximo de saídas geradas exibidas na guia Saídas de um mapa DITA. Por padrão, uma lista das últimas 25 saídas é exibida. Para alterar o número de saídas a serem exibidas na lista, atualize o **Limite da lista de saídas** configuração no `com.adobe.fmdita.config.ConfigManager` pacote.

>[!TIP]
>
> Consulte a *Histórico de saída* no guia de Práticas recomendadas[appendix.md\#](appendix.md#) para obter as práticas recomendadas sobre como trabalhar com o histórico de saída.

## Otimização do desempenho da geração de saída {#id176LB050VUI}

Guias do AEM permitem configurar o tamanho do pool de processos de geração de saída que controla o número de processos de geração de saída executados simultaneamente. Por padrão, o tamanho do pool de processos é definido como o número de núcleos de processamento disponíveis no sistema mais um. Talvez você queira alterar esse valor para 1 se quiser publicação sequencial. Nesse caso, a primeira tarefa de publicação é executada e a próxima tarefa de publicação é armazenada na fila de publicação.

Para alterar o tamanho do pool de processamento da geração de saída, atualize o **Tamanho do Pool de Geração** configuração no `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` pacote.
