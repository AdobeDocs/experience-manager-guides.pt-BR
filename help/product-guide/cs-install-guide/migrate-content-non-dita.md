---
title: Migrar conteúdo não DITA
description: Saiba como migrar conteúdo não DITA
exl-id: cf437fb8-ed33-47af-aa7e-ffd8acd232da
feature: Migration
role: Admin
level: Experienced
source-git-commit: 2c20191ba998ad7da98587f1832e1fe8499d023c
workflow-type: tm+mt
source-wordcount: '2521'
ht-degree: 0%

---

# Migrar conteúdo não DITA {#id181AH0R02HT}

Esta seção orienta você durante o processo de migração para migrar documentos não-DITA para o formato DITA. O AEM Guides fornece a migração das seguintes fontes:

- [Microsoft Word](#id1949B040Z5Z)

- [Documentos do InDesign](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Documentos não estruturados do FrameMaker](#id1949B050VUI)

- [Qualquer outro documento estruturado](#id1949B0590YK)


## Migrar documentos do Microsoft Word {#id1949B040Z5Z}

O AEM Guides permite migrar seus documentos existentes do Word \(`.docx`\) para documentos do tipo de tópico DITA. Você precisa especificar os locais das pastas de entrada e saída juntamente com outros parâmetros e o documento é convertido em documento DITA. Dependendo do conteúdo, você pode ter um arquivo .dita e um arquivo .ditamap.

Para converter um documento do Word com êxito, o documento deve estar bem estruturado. Por exemplo, seu documento deve ter um Título, seguido de Título 1, Título 2, e assim por diante. Cada um dos cabeçalhos deve ter algum conteúdo. Se o documento não estiver bem estruturado, o processo poderá não funcionar conforme esperado.

Por padrão, o AEM Guides usa a [estrutura de transformação Word para DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Esta transformação depende do arquivo de configuração [mapeamento de estilo para marca](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html). Para usar a transformação do Word2DITA com sucesso, você deve considerar as seguintes diretrizes para preparar seu documento do Word para conversão:

>[!NOTE]
>
> Se você fizer alterações no arquivo de configuração do mapeamento de estilo para tag padrão, será necessário atualizar e usar as diretrizes que confirmam o mapeamento de estilo atualizado.

- Verifique se o documento começa com um Título; esse Título é mapeado para o título do mapa DITA. Além disso, o Título deve ser seguido de algum conteúdo regular.

- Depois do Título, deve haver Cabeçalho 1, Cabeçalho 2 e assim por diante. Cada cabeçalho deve conter conteúdo. Os Títulos são convertidos em novos tópicos do tipo Conceito. A hierarquia dos tópicos gerados é de acordo com os níveis de Cabeçalho no documento, por exemplo, o Cabeçalho 1 precederá o Cabeçalho 2 e o Cabeçalho 2 precederá o conteúdo do Cabeçalho 3.

- O documento deve ter pelo menos um conteúdo do tipo Cabeçalho.

- Certifique-se de que você não tenha imagens agrupadas. Caso tenha agrupado imagens no documento, desagrupe todas essas imagens.

- Remova todos os cabeçalhos e rodapés.

- Estilos embutidos como negrito, itálico e sublinhado são convertidos em elementos `b`, `i` e `u`.

- Todas as listas ordenadas e não ordenadas são convertidas em elementos `ol` e `ul`. Isso também se aplica a listas aninhadas, listas em tabelas, notas ou notas de rodapé.

- Todos os hiperlinks foram convertidos em `xref`.

- O nome de arquivo dos arquivos convertidos é baseado no texto do cabeçalho seguido por um número de arquivo. O número do arquivo é um número sequencial baseado na posição do texto do cabeçalho no documento. Por exemplo, se um texto de cabeçalho for &quot;Exemplo de cabeçalho&quot; e estiver no décimo cabeçalho do documento, o nome de arquivo resultante para esse tópico será semelhante a Sample\_Heading\_10.dita.


Execute as seguintes etapas para converter documentos existentes do Word em documento do tipo de tópico DITA:

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/w2d\_io.xml.

1. Personalize o arquivo w2d\_io.xml baixado.

1. Adicione o arquivo no seguinte local no repositório Git do Cloud Manager:

   /apps/fmdita/config/w2d\_io.xml

   O arquivo `w2d_io.xml` contém os seguintes parâmetros configuráveis:

   - No elemento `inputDir`, especifique o local da pasta de entrada em que os documentos do Word de origem estão disponíveis. Por exemplo, se seus documentos do Word estiverem armazenados em uma pasta chamada `wordtodita` na pasta `projects`, especifique o local como: `/content/dam/projects/wordtodita/`

   - No elemento `outputDir`, especifique o local da pasta de saída ou mantenha o local de saída padrão para salvar o documento DITA convertido. Se a pasta de saída especificada não existir no DAM, o fluxo de trabalho de conversão criará a pasta de saída.

   - Para o elemento `createRev`, especifique se uma nova versão do tópico DITA convertido deve ser criada \(`true`\) ou não \(`false`\).

   - No elemento `s2tMap`, especifique o local do arquivo de mapa que contém mapeamentos para estilos de documento do Word para elementos DITA. O mapeamento padrão é armazenado no arquivo localizado em:

     ```
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Para obter mais informações sobre a estrutura do arquivo `word-builtin-styles-style2tagmap.xml` e como personalizá-lo, consulte [Style to Tag Mapping](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) no *Guia do Usuário do DITA For Publishers*.

   - No elemento props2Propagate, especifique as propriedades que devem ser passadas para o mapa DITA. Essa propriedade é necessária para transmitir metadados padrão como dc:title,dc:subject,dam:keywords,dam:category dos metadados do documento para ativos DITA convertidos.

1. Execute o pipeline do Cloud Manager para implantar a configuração atualizada.

1. Depois de configurar os parâmetros necessários no arquivo `w2d_io.xml`, faça logon no AEM e abra a interface do usuário do Assets.

1. Navegue até o local da pasta de entrada \(`wordtodita`\).

1. Faça upload dos documentos de origem do Word para esta pasta. Para obter informações sobre como carregar conteúdo no DAM, consulte [Carregar conteúdo DITA existente](migrate-content-upload-existing-dita-content.md#).


Usando o bloco `config` `/config`, você pode definir um ou vários blocos de configurações para conversão. O fluxo de trabalho de conversão é executado e a saída final na forma de um tópico DITA é salva no local especificado no elemento `outputDir`.

**Atualizações de personalização para usuários existentes**

Se você for um usuário existente do AEM Guides as a Cloud Service e estiver atualizando da versão de agosto de 2021 para a de janeiro de 2022 ou versões posteriores, atualize as propriedades fornecidas conforme os arquivos forem movidos.

>[!NOTE]
>
> Essa atualização só será aplicável se você já estiver usando o fluxo de trabalho de conversão do Microsoft Word para o DITA.

- Caminho do arquivo: /apps/fmdita/config/w2d\_io.xml
- Altere o valor de `<s2tMap>` de /apps/dxml/word2dita/word-builtin-styles-style2tagmap.xml para /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
- Faça as alterações necessárias no repositório Git da Cloud Manager, pois, para o serviço em nuvem, todos os arquivos em /apps são sobrepostos por meio do Git da Cloud Manager.

## Migrar documentos do Adobe InDesign {#id195AD0B0K5Z}

O AEM Guides permite converter documentos do InDesign. Semelhante ao FrameMaker, o InDesign também permite criar documentos não estruturados e estruturados. Os documentos não estruturados usam os estilos de parágrafo e caractere para formatar o conteúdo. O documento estruturado usa elementos e seus atributos correspondentes.

O processo de conversão requer o mapeamento dos formatos de estilo de parágrafo e caractere para elementos DITA relevantes. Da mesma forma, no caso de documentos estruturados, o arquivo de mapeamento conterá mapeamento de um para um de elementos e atributos do InDesign com elementos e atributos DITA.

O processo de conversão envolve as seguintes ações no back-end:

- O arquivo *InDesign Markup Language* \(IDML\) está desempacotado em um diretório de trabalho.
- O arquivo designmap.xml é lido para localizar as matérias individuais do InDesign.
- Todas as histórias são mescladas em uma única instância XML, as histórias &quot;vazias&quot; são descartadas.
- Todos os gráficos incorporados são exportados.
- Pré-conversão de estruturas padrão, como tabelas e gráficos, no formato DITA.
- Mapeamento de estilo ou estrutura para saída final com base no arquivo de mapeamento.
- Criação e validação de tópicos e arquivos de mapa DITA individuais.
- Exclusão de arquivos temporários.

De maneira geral, o processo de conversão requer que você [Prepare arquivos do InDesign para a conversão](appendix.md#id195DBF0045Z)[appendix.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) e [Prepare o arquivo de mapeamento para a migração do InDesign para o DITA](appendix.md#id194AF0003HT)[appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT). Em seguida, você precisa seguir o procedimento fornecido para executar o processo de conversão.

Execute as seguintes etapas para converter seus documentos existentes do InDesign em um documento do tipo de tópico DITA:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o arquivo de configuração padrão disponível no seguinte local:

   `/libs/fmdita/config/idml2dita_io.xml`
1. Para criar uma configuração personalizada de acordo com seus requisitos, crie um nó de sobreposição da pasta `config` no nó `apps`.

1. Copie os seguintes arquivos ou pastas da pasta `libs` para a pasta de aplicativos:

   - `/fmdita/config/idml2dita_io.xml`
   - `/fmdita/idml2dita/config`
   - `/fmdita/idml2dita/xsl`

1. Navegue até o arquivo de configuração disponível no nó `apps`:

   `/apps/fmdita/config/idml2dita_io.xml`

1. Adicione o mapeamento das configurações presentes na pasta `idml12dita` dentro do arquivo `idml2dita_io.xml`.
1. Adicionar as seguintes propriedades no arquivo `idml2dita_io.xml`:

   ```
   <entry          key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

1. Crie um nó de sobreposição da pasta `config` no nó `apps`.


   Configure os seguintes parâmetros no arquivo `idml2dita_io.xml`:

   - No elemento `inputDir`, especifique o local da pasta de entrada em que seus documentos do InDesign de origem estão disponíveis. Por exemplo, se seus documentos do InDesign estiverem armazenados em uma pasta chamada `indesigntodita` na pasta `projects`, especifique o local como: `/content/dam/idmlfiles/indesigntodita/`

   - No elemento `outputDir`, especifique o local da pasta de saída ou mantenha o local de saída padrão para salvar o documento DITA convertido. Se a pasta de saída especificada não existir no DAM, o fluxo de trabalho de conversão criará a pasta de saída.

   - No elemento `mapStyle`, especifique o local do arquivo de mapa que contém mapeamentos para estilos de documento do InDesign para elementos DITA. O mapeamento padrão é armazenado no arquivo localizado em:

     ```
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Para obter mais informações sobre a estrutura do arquivo `stmap.adobeidml.xml` e como personalizá-lo, consulte a seção [appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT) no Apêndice.

1. Salve o arquivo `idml2dita_io.xml`.

1. Depois de configurar os parâmetros necessários no arquivo `idml2dita_io.xml`, faça logon no AEM e abra a interface do usuário do Assets.

1. Navegue até o local da pasta de entrada \(`indesigntodita`\).

1. Faça upload dos documentos de origem do InDesign para esta pasta. Para obter informações sobre como carregar conteúdo no DAM, consulte [Carregar conteúdo DITA existente](migrate-content-upload-existing-dita-content.md#).


## Migrar documentos XHTML {#id1949B04L0Y4}

O AEM Guides permite converter documentos XHTML existentes em documentos do tipo de tópico DITA. Você precisa especificar os locais das pastas de entrada e saída juntamente com outros parâmetros e os documentos são convertidos no formato DITA. Há dois métodos que você pode usar para converter seus documentos estruturados do HTML:

- Fazer upload de todos os documentos para a pasta de entrada, ou
- Crie um ZIP de todos os documentos junto com os arquivos de mídia e faça upload deles para a pasta de entrada. Essa abordagem geralmente é usada para um conjunto de arquivos HTML vinculados entre si e há um índice \(index.html\). O arquivo index.html contém links para todos os arquivos HTML no conjunto.

Independentemente de você carregar todos os arquivos individualmente ou em um ZIP, o processo de conversão cria um mapeamento um para um entre os arquivos HTML e os arquivos DITA resultantes. Isso significa essencialmente que há um arquivo .dita criado para cada arquivo .html na pasta de entrada.

Os seguintes pontos devem ser considerados para fazer upload de documentos em um arquivo ZIP:

- Todos os tópicos referenciados devem ser colocados no arquivo ZIP.

- Todos os arquivos de mídia referenciados devem ser referenciados nos arquivos de tópico usando o link relativo.

- Crie um arquivo index.html e adicione links para os tópicos que deseja adicionar ao índice. Esse arquivo index.html é usado para criar o arquivo de mapa DITA. No arquivo index.html, você também pode criar listagens de tópicos aninhados como mostrado na seguinte amostra de código:

  ```
  <?xml version="1.0" encoding="UTF-8"?>
  <html
  xmlns="http://www.w3.org/1999/xhtml">
      <head>
          <title>Sample Index File</title>
      </head>
      <body>
          <h1>Sample Index</h1>
          <div class="content">
              <ul class="book">
                  <li class="topicref">
                      <a href="Topic1.html">Topic 1</a>
                      <ul class="book">
                          <li class="topicref">
                              <a href="Topic1-1.html">Topic 1.1</a>
                          </li>
                          <li class="topicref">
                              <a href="Topic1-2.html">Topic 1.2</a>
                          </li>
                      </ul>
                  </li>
                  <li class="topicref">
                      <a href="Topic2.html">Topic 2</a>
                  </li>
              </ul>
          </div>
      </body>
  </html>
  ```

  Observe que toda marca `ul` deve ter o atributo `class` definido como `book`. Da mesma forma, cada `li` de tag de `class` deve ser definido como `topicref`.

- Se você usar estilos em linha, converta os estilos em linha em classes de estilo baseadas em CSS no arquivo XHTML. Em seguida, use o mapeamento style-attribute para converter esses estilos baseados em classes para o atributo DITA `outputclass` no arquivo DITA convertido.

  Ao gerar a saída do HTML ou do Site do AEM a partir desses arquivos DITA, os atributos `outputclass` podem ser usados para aplicar a classe de estilo no HTML ou no Site do AEM gerado para corresponder ao conteúdo do HTML de origem.


Além das considerações para a criação do arquivo ZIP, o documento XHTML também deve ser bem estruturado. Por exemplo, seu documento deve ter um *Título*, seguido por *Cabeçalho 1*, *Cabeçalho 2* e assim por diante. Cada um dos cabeçalhos deve ter algum conteúdo. Se o documento não estiver bem estruturado, o processo de migração poderá não funcionar conforme esperado.

Para converter o documento XHTML existente em um tópico DITA, execute as seguintes etapas:

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/h2d\_io.xml.

1. Personalize o arquivo h2d\_io.xml baixado.

1. Adicione o arquivo no seguinte local no repositório Git do Cloud Manager:

   /apps/fmdita/config/h2d\_io.xml

   O arquivo `h2d_io.xml` contém os seguintes parâmetros configuráveis:

   - No elemento `inputDir`, especifique o local da pasta de entrada em que os documentos XHTML de origem estão disponíveis. Por exemplo, se seus documentos XHTML estiverem armazenados em uma pasta chamada `xhtmltodita` na pasta `projects`, especifique o local como: `/content/dam/projects/xhtmltodita/`

   - No elemento `outputDir`, especifique o local da pasta de saída ou mantenha o local de saída padrão. Se a pasta de saída especificada não existir no DAM, o fluxo de trabalho de conversão criará a pasta de saída.

   - Para o elemento `createRev`, especifique se uma nova versão do tópico DITA convertido deve ser criada \(`true`\) ou não \(`false`\).

1. Execute o pipeline do Cloud Manager para implantar a configuração atualizada.

1. Depois de configurar os parâmetros necessários no arquivo `w2d_io.xml`, faça logon no AEM e abra a interface do usuário do Assets.

1. *\(Opcional\)* Você também pode adicionar a seção de links relacionados aos documentos convertidos. Execute as seguintes etapas para ativar esse recurso:

   >[!NOTE]
   >
   > Por padrão, a seção de links relacionados não é criada nos documentos convertidos.

   1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/html2dita/h2d.xsl.

   2. Procure o seguinte parâmetro:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Defina o valor do parâmetro acima como `true()`.

   4. Confirme o arquivo atualizado no seguinte local no repositório Git do Cloud Manager:

      /libs/fmdita/html2dita/

   5. Execute o pipeline do Cloud Manager para implantar a configuração atualizada.

1. Navegue até o local da pasta de entrada \(`xhtmltodita`\).

1. Faça upload dos documentos XHTML de origem para esta pasta. Para obter informações sobre como carregar conteúdo no DAM, consulte [Carregar conteúdo DITA existente](migrate-content-upload-existing-dita-content.md#).


Usando o bloco `<config> </config>`, você pode definir um ou vários blocos de configurações para conversão. O fluxo de trabalho de conversão é executado e a saída final na forma de um tópico DITA é salva no local especificado no elemento `outputDir`.

## Migrar documentos não estruturados do FrameMaker {#id1949B050VUI}

Para converter conteúdo não estruturado do Adobe FrameMaker (.fm e .book) em DITA estruturado, você pode usar o mecanismo de tabela de conversão do FrameMaker. O processo se concentra na avaliação do conteúdo existente, usando uma abordagem baseada em modelo e mapeando estilos do FrameMaker para DITA por meio de tabelas de conversão. Para obter mais detalhes, consulte [Migrando documentação técnica de não estruturada para DITA no Adobe FrameMaker](https://migrate-from-unstructured-to-dita-step-by-step-guide.meetus.adobeevents.com/).

Após a conversão, o conteúdo estruturado pode ser migrado para o AEM Guides.  Para obter mais detalhes, consulte [Fazer upload de conteúdo DITA existente](./migrate-content-upload-existing-dita-content.md).

<!-- Deprecated information -
 //The first step is to create style mappings using FrameMaker and save those settings in a .sts file. Next, if you are using custom DITA, then you can map your custom elements with the source FrameMaker formats in the `ditaElems.xml` file. For example, if you have created a custom element named `impnote` to handle all important notes, then you can define this custom element in the `ditaElems.xml` file. Once this custom element is defined, AEM Guides would not raise an error while converting FrameMaker document containing `impnote` element.

Also, If you want to specify some additional attributes with your custom or valid DITA element, you can define those in the style2attrMap.xml file. For example, you can specify the `type` attribute with the value of `important` to be passed on with the `impnote` element. This additional information can be specified in the style2attrMap.xml file.

In addition to specifying

To convert your existing unstructured FrameMaker documents into DITA format, perform the following steps:

1.  Create style mappings in FrameMaker and save those settings in a .sts file.

1.  Log into AEM and open the CRXDE Lite mode.

1.  If you have custom DITA elements, define those in the `ditaElems.xml` file available at the following location:

    `/libs/fmdita/config/ditaElems.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/ditaElems.xml`

    The `ditaElems.xml` file contains a single configurable parameter:

    -   In the `elem` parameter, specify the name of the custom element that you want to use in your converted DITA documents. This element would be passed on as is in the generated DITA documents.

1.  If you want to specify additional attributes, define those in the `style2attrMap.xml` file available at the following location:

    `/libs/fmdita/config/style2attrMap.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/style2attrMap.xml`

    The `style2attrMap.xml` file contains the following configurable parameters:

    -   In the `fmStyle` parameter, specify the source format used in the FrameMaker document that you want to map.

    -   In the`ditaAttr` element, specify the DITA attribute that you want to map with the source format.

    -   In the `ditaVal` element, specify the value for the mapped attribute. If you don't have any value, you can leave this entry blank.

1.  Save the `style2attrMap.xml` file.

1. After configuring the required parameters in the `style2attrMap.xml` file, log into AEM and open the Assets UI.

1. Navigate to and click on the FrameMaker document that you want to convert.

    The DITA map console appears showing the list of Output Presets available to generate output.

1. Select DITA output format and configure the required parameters.

    >[!NOTE]
    >
    > You must use the same settings file \(.sts\) that you created in FrameMaker. Also, specify the Settings Name and Destination Path.

1. Click the **Generate** icon to start the output generation process.


Using the `<attrMap> </attrMap>` block, you can define one or multiple blocks of configurations for conversion. Depending on the content, you could have a .dita file and a .ditamap file as the converted files.

-->

## Migrar qualquer outro documento estruturado {#id1949B0590YK}

O AEM Guides permite converter documentos estruturados existentes em documentos DITA válidos. Você precisa especificar os locais das pastas de entrada e saída, o local do arquivo de transformação, a extensão com a qual a saída final é salva e se uma nova versão do documento é necessária ou não.

Para converter os documentos estruturados existentes no formato DITA, execute as seguintes etapas:

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/XSLConfig.xml.

1. Crie uma cópia do arquivo XSLConfig.xml no seguinte local no repositório Git da Cloud Manager:

   `/apps/fmdita/config/XSLConfig.xml`

   O arquivo `XSLConfig.xml` contém os seguintes parâmetros configuráveis:

   - No elemento `inputDir`, especifique o local da pasta de entrada em que os documentos estruturados de origem estão disponíveis. Por exemplo, se seus documentos estruturados estiverem armazenados em uma pasta chamada `xsltodita` na pasta `projects`, especifique o local como: `/content/dam/projects/xsltodita/`

   - No elemento `outputDir`, especifique o local da pasta de saída ou mantenha o local de saída padrão. Se a pasta de saída especificada não existir no DAM, o fluxo de trabalho de conversão criará a pasta de saída.

   - No elemento `xslFolder`, especifique o local da pasta onde os arquivos de transformação XSL são armazenados.

   - No elemento ``xslPath``, especifique o local do arquivo .XSL principal que é usado para iniciar o processo de conversão.

   - No elemento ``outputExt``, especifique as extensões do arquivo de saída final criado a partir do fluxo de transformação.

   - Para o elemento `createRev`, especifique se uma nova versão do tópico DITA convertido deve ser criada \(`true`\) ou não \(`false`\).

1. Salve o arquivo `XSLConfig.xml`.

1. Depois de configurar os parâmetros necessários no arquivo `XSLConfig.xml`, faça logon no AEM e abra a interface do usuário do Assets.

1. Navegue até o local da pasta de entrada \(`xsltodita`\).

1. Faça upload dos documentos estruturados de origem nesta pasta. Para obter informações sobre como carregar conteúdo no DAM, consulte [Carregar conteúdo DITA existente](migrate-content-upload-existing-dita-content.md#).


Usando o bloco `<config> </config>`, você pode definir um ou vários blocos de configurações para conversão. O fluxo de trabalho de conversão é executado e a saída final na forma de um tópico DITA é salva no local especificado no elemento `outputDir`.

**Tópico pai:**[ Migrar conteúdo existente](migrate-content.md)
