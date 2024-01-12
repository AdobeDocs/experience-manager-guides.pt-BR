---
title: Migrar conteúdo não DITA
description: Saiba como migrar conteúdo não DITA
exl-id: cf437fb8-ed33-47af-aa7e-ffd8acd232da
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2889'
ht-degree: 0%

---

# Migrar conteúdo não DITA {#id181AH0R02HT}

Esta seção orienta você durante o processo de migração para migrar documentos não-DITA para o formato DITA. Os Guias do AEM fornecem migração das seguintes fontes:

- [Microsoft Word](#id1949B040Z5Z)

- [InDesign de documentos](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Documentos de FrameMaker não estruturados](#id1949B050VUI)

- [Qualquer outro documento estruturado](#id1949B0590YK)


## Migrar documentos do Microsoft Word {#id1949B040Z5Z}

O Guia AEM permite migrar seus documentos existentes do Word \(`.docx`\) em documentos do tipo de tópico DITA. Você precisa especificar os locais das pastas de entrada e saída juntamente com outros parâmetros e o documento é convertido em documento DITA. Dependendo do conteúdo, você pode ter um arquivo .dita e um arquivo .ditamap.

Para converter um documento do Word com êxito, o documento deve estar bem estruturado. Por exemplo, seu documento deve ter um Título, seguido de Título 1, Título 2, e assim por diante. Cada um dos cabeçalhos deve ter algum conteúdo. Se o documento não estiver bem estruturado, o processo poderá não funcionar conforme esperado.

Por padrão, os Guias do AEM usam o [Estrutura de transformação de Word para DITA\ (Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Essa transformação depende da [mapeamento de estilo para tag](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) arquivo de configuração. Para usar a transformação do Word2DITA com sucesso, você deve considerar as seguintes diretrizes para preparar seu documento do Word para conversão:

>[!NOTE]
>
> Se você fizer alterações no arquivo de configuração do mapeamento de estilo para tag padrão, será necessário atualizar e usar as diretrizes que confirmam o mapeamento de estilo atualizado.

- Verifique se o documento começa com um Título; esse Título é mapeado para o título do mapa DITA. Além disso, o Título deve ser seguido de algum conteúdo regular.

- Depois do Título, deve haver Cabeçalho 1, Cabeçalho 2 e assim por diante. Cada cabeçalho deve conter conteúdo. Os Títulos são convertidos em novos tópicos do tipo Conceito. A hierarquia dos tópicos gerados é de acordo com os níveis de Cabeçalho no documento, por exemplo, o Cabeçalho 1 precederá o Cabeçalho 2 e o Cabeçalho 2 precederá o conteúdo do Cabeçalho 3.

- O documento deve ter pelo menos um conteúdo do tipo Cabeçalho.

- Certifique-se de que você não tenha imagens agrupadas. Caso tenha agrupado imagens no documento, desagrupe todas essas imagens.

- Remova todos os cabeçalhos e rodapés.

- Estilos embutidos como negrito, itálico e sublinhado são convertidos em `b`, `i`, e `u` elementos.

- Todas as listas ordenadas e não ordenadas são convertidas em `ol` e `ul` elementos. Isso também se aplica a listas aninhadas, listas em tabelas, notas ou notas de rodapé.

- Todos os hiperlinks são convertidos em `xref`.

- O nome de arquivo dos arquivos convertidos é baseado no texto do cabeçalho seguido por um número de arquivo. O número do arquivo é um número sequencial baseado na posição do texto do cabeçalho no documento. Por exemplo, se um texto de cabeçalho for &quot;Exemplo de cabeçalho&quot; e estiver no décimo cabeçalho do documento, o nome de arquivo resultante para esse tópico será semelhante a Sample\_Heading\_10.dita.


Execute as seguintes etapas para converter documentos existentes do Word em documento do tipo de tópico DITA:

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/w2d\_io.xml.

1. Personalize o arquivo w2d\_io.xml baixado.

1. Adicione o arquivo no seguinte local no repositório Git do Cloud Manager:

   /apps/fmdita/config/w2d\_io.xml

   A variável `w2d_io.xml` O arquivo contém os seguintes parâmetros configuráveis:

   - No `inputDir` elemento, especifique o local da pasta de entrada onde os documentos de origem do Word estão disponíveis. Por exemplo, se seus documentos do Word estiverem armazenados em uma pasta chamada `wordtodita` in `projects` e especifique o local como: `/content/dam/projects/wordtodita/`

   - No`outputDir` especifique o local da pasta de saída ou mantenha o local de saída padrão para salvar o documento DITA convertido. Se a pasta de saída especificada não existir no DAM, o fluxo de trabalho de conversão criará a pasta de saída.

   - Para o `createRev` elemento, especifique se uma nova versão do tópico DITA convertido deverá ser criada \(`true`\) ou não \(`false`\).

   - No `s2tMap` elemento, especifique o local do arquivo de mapa que contém mapeamentos para estilos de documento do Word para elementos DITA. O mapeamento padrão é armazenado no arquivo localizado em:

     ```
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Para obter mais informações sobre a estrutura do `word-builtin-styles-style2tagmap.xml` e como é possível personalizá-lo, consulte [Estilo para mapeamento de tag](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) in *Guia do usuário do DITA para editores*.

   - No elemento props2Propagate, especifique as propriedades que devem ser passadas para o mapa DITA. Essa propriedade é necessária para transmitir os metadados padrão, como dc:title,dc:subject,dam:keywords,dam:category dos metadados do documento para ativos DITA convertidos.

1. Execute o pipeline do Cloud Manager para implantar a configuração atualizada.

1. Após configurar os parâmetros necessários no `w2d_io.xml` arquivo, faça logon no AEM e abra a interface do usuário do Assets.

1. Navegue até o local da pasta de entrada \(`wordtodita`\).

1. Faça upload dos documentos de origem do Word para esta pasta. Para obter informações sobre como carregar conteúdo no DAM, consulte [Fazer upload de conteúdo DITA existente](migrate-content-upload-existing-dita-content.md#).


Usar o `config` `/config` bloco, você pode definir um ou vários blocos de configurações para conversão. O fluxo de trabalho de conversão é executado e a saída final no formato de um tópico DITA é salva no local especificado no `outputDir` elemento.

**Atualizações de personalização para usuários existentes**

Se você for um usuário existente do AEM Guides as a Cloud Service e estiver atualizando da versão de agosto de 2021 para a de janeiro de 2022 ou versões posteriores, atualize as propriedades fornecidas conforme alguns arquivos forem movidos.

>[!NOTE]
>
> Essa atualização só será aplicável se você já estiver usando o fluxo de trabalho de conversão do Microsoft Word para o DITA.

- Caminho do arquivo: /apps/fmdita/config/w2d\_io.xml
- Alterar o valor de `<s2tMap>` de /apps/dxml/word2dita/word-builtin-styles-style2tagmap.xml para /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
- Faça as alterações necessárias no repositório Git do Cloud Manager, pois, para o serviço de nuvem, todos os arquivos em /apps são sobrepostos por meio do Git do Cloud Manager.

## Migrar documentos do Adobe InDesign {#id195AD0B0K5Z}

O Guia AEM permite converter documentos do InDesign. Semelhante ao FrameMaker, o InDesign também permite criar documentos não estruturados e estruturados. Os documentos não estruturados usam os estilos de parágrafo e caractere para formatar o conteúdo. O documento estruturado usa elementos e seus atributos correspondentes.

O processo de conversão requer o mapeamento dos formatos de estilo de parágrafo e caractere para elementos DITA relevantes. Da mesma forma, no caso de documentos estruturados, o arquivo de mapeamento conterá mapeamento de um para um de elementos e atributos de InDesign com elementos e atributos DITA.

O processo de conversão envolve as seguintes ações no back-end:

- A variável *Linguagem de marcação do InDesign* O arquivo \(IDML\) é descompactado em um diretório de trabalho.
- O arquivo designmap.xml é lido para localizar as matérias de InDesign individuais.
- Todas as histórias são mescladas em uma única instância XML, as histórias &quot;vazias&quot; são descartadas.
- Todos os gráficos incorporados são exportados.
- Pré-conversão de estruturas padrão, como tabelas e gráficos, no formato DITA.
- Mapeamento de estilo ou estrutura para saída final com base no arquivo de mapeamento.
- Criação e validação de tópicos e arquivos de mapa DITA individuais.
- Exclusão de arquivos temporários.

Em geral, o processo de conversão requer que você [Preparar arquivos de InDesign para conversão](appendix.md#id195DBF0045Z)[appendix.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) e [Preparar o arquivo de mapeamento para migração do InDesign para o DITA](appendix.md#id194AF0003HT)[appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT), é necessário seguir o procedimento especificado para executar o processo de conversão.

Execute as seguintes etapas para converter seus documentos do InDesign existentes em documento do tipo de tópico DITA:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Navegue até o arquivo de configuração padrão disponível no seguinte local:

   `/libs/fmdita/config/idml2dita_io.xml`

1. Crie um nó de sobreposição do `config` pasta dentro do `apps` nó.

1. Navegue até o arquivo de configuração disponível no `apps` nó:

   `/apps/fmdita/config/idml2dita_io.xml`

   Configure os seguintes parâmetros no `idml2dita_io.xml` arquivo:

   - No `inputDir` elemento, especifique o local da pasta de entrada na qual os documentos do InDesign de origem estão disponíveis. Por exemplo, se os documentos do InDesign estiverem armazenados em uma pasta chamada `indesigntodita` in `projects` e especifique o local como: `/content/dam/idmlfiles/indesigntodita/`

   - No`outputDir` especifique o local da pasta de saída ou mantenha o local de saída padrão para salvar o documento DITA convertido. Se a pasta de saída especificada não existir no DAM, o fluxo de trabalho de conversão criará a pasta de saída.

   - No `mapStyle` elemento, especifique o local do arquivo de mapa que contém mapeamentos para estilos de documento do InDesign para elementos DITA. O mapeamento padrão é armazenado no arquivo localizado em:

     ```
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Para obter mais informações sobre a estrutura do `stmap.adobeidml.xml` arquivo e como personalizá-lo, consulte a seção [appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT) no Apêndice.

1. Salve o `idml2dita_io.xml` arquivo.

1. Após configurar os parâmetros necessários no `idml2dita_io.xml` arquivo, faça logon no AEM e abra a interface do usuário do Assets.

1. Navegue até o local da pasta de entrada \(`indesigntodita`\).

1. Faça upload dos documentos do InDesign de origem para esta pasta. Para obter informações sobre como carregar conteúdo no DAM, consulte [Fazer upload de conteúdo DITA existente](migrate-content-upload-existing-dita-content.md#).


## Migrar documentos XHTML {#id1949B04L0Y4}

Guias de AEM permitem converter documentos XHTML existentes em documentos do tipo de tópico DITA. Você precisa especificar os locais das pastas de entrada e saída juntamente com outros parâmetros e os documentos são convertidos no formato DITA. Há dois métodos que você pode usar para converter seus documentos HTML estruturados:

- Fazer upload de todos os documentos para a pasta de entrada, ou
- Crie um ZIP de todos os documentos junto com os arquivos de mídia e faça upload deles para a pasta de entrada. Essa abordagem geralmente é usada para um conjunto de arquivos HTML que estão vinculados entre si e há um índice \(index.html\). O arquivo index.html contém links para todos os arquivos HTML no conjunto.

Quer você carregue todos os arquivos individualmente ou em um ZIP, o processo de conversão cria um mapeamento um para um entre os arquivos HTML e os arquivos DITA resultantes. Isso significa essencialmente que há um arquivo .dita criado para cada arquivo .html na pasta de entrada.

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

  Observe que a cada `ul` A tag deve ter o `class` atributo definido como `book`. Da mesma forma, cada `li` da tag `class` deve ser definido como `topicref`.

- Se você usar estilos em linha, converta os estilos em linha em classes de estilo baseadas em CSS no arquivo XHTML. Em seguida, use o mapeamento de atributo de estilo para converter esses estilos baseados em classes em DITA `outputclass` no arquivo DITA convertido.

  Ao gerar saída de HTML ou AEM Site desses arquivos DITA, a variável `outputclass` Os atributos podem ser usados para aplicar a classe de estilo no HTML gerado ou no site AEM para corresponder ao conteúdo do HTML de origem.


Além das considerações para a criação do arquivo ZIP, o documento XHTML também deve ser bem estruturado. Por exemplo, seu documento deve ter uma *Título*, seguido por *Cabeçalho 1*, *Cabeçalho 2* e assim por diante. Cada um dos cabeçalhos deve ter algum conteúdo. Se o documento não estiver bem estruturado, o processo de migração poderá não funcionar conforme esperado.

Para converter o documento XHTML existente em um tópico DITA, execute as seguintes etapas:

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/h2d\_io.xml.

1. Personalize o arquivo h2d\_io.xml baixado.

1. Adicione o arquivo no seguinte local no repositório Git do Cloud Manager:

   /apps/fmdita/config/h2d\_io.xml

   A variável `h2d_io.xml` O arquivo contém os seguintes parâmetros configuráveis:

   - No `inputDir` elemento, especifique o local da pasta de entrada onde os documentos XHTML de origem estão disponíveis. Por exemplo, se os documentos XHTML estiverem armazenados em uma pasta chamada `xhtmltodita` in `projects` e especifique o local como: `/content/dam/projects/xhtmltodita/`

   - No`outputDir` especifique o local da pasta de saída ou mantenha o local de saída padrão. Se a pasta de saída especificada não existir no DAM, o fluxo de trabalho de conversão criará a pasta de saída.

   - Para o `createRev` elemento, especifique se uma nova versão do tópico DITA convertido deverá ser criada \(`true`\) ou não \(`false`\).

1. Execute o pipeline do Cloud Manager para implantar a configuração atualizada.

1. Após configurar os parâmetros necessários no `w2d_io.xml` arquivo, faça logon no AEM e abra a interface do usuário do Assets.

1. *\(Opcional\)* Você também pode adicionar a seção links relacionados aos documentos convertidos. Execute as seguintes etapas para ativar esse recurso:

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

1. Faça upload dos documentos XHTML de origem para esta pasta. Para obter informações sobre como carregar conteúdo no DAM, consulte [Fazer upload de conteúdo DITA existente](migrate-content-upload-existing-dita-content.md#).


Usar o `<config> </config>` bloco, você pode definir um ou vários blocos de configurações para conversão. O fluxo de trabalho de conversão é executado e a saída final no formato de um tópico DITA é salva no local especificado no `outputDir` elemento.

## Migrar documentos de FrameMaker não estruturados {#id1949B050VUI}

Guias de AEM permitem converter seu FrameMaker não estruturado existente \(`.fm` e `.book`\) documentos em documentos DITA. A primeira etapa é criar mapeamentos de estilo usando o FrameMaker e salvar essas configurações em um arquivo .sts. Em seguida, se estiver usando DITA personalizado, você poderá mapear seus elementos personalizados com os formatos de FrameMaker de origem no `ditaElems.xml` arquivo. Por exemplo, se você criou um elemento personalizado chamado `impnote` para lidar com todas as notas importantes, é possível definir esse elemento personalizado na `ditaElems.xml` arquivo. Depois que esse elemento personalizado é definido, os Guias do AEM não geram erros ao converter um documento do FrameMaker que contém `impnote` elemento.

Além disso, se você quiser especificar alguns atributos adicionais com seu elemento DITA personalizado ou válido, defina-os no arquivo style2attrMap.xml. Por exemplo, você pode especificar a variável `type` atributo com o valor de `important` a transmitir com a `impnote` elemento. Essas informações adicionais podem ser especificadas no arquivo style2attrMap.xml.

Além de especificar

Para converter os documentos de FrameMaker não estruturados existentes no formato DITA, execute as seguintes etapas:

1. Crie mapeamentos de estilo no FrameMaker e salve essas configurações em um arquivo .sts.

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/ditaElems.xml.

1. Se você tiver elementos DITA personalizados, defina-os na variável `ditaElems.xml` arquivo disponível no seguinte local:

   `/libs/fmdita/config/ditaElems.xml`

1. Crie uma cópia do arquivo ditaElems.xml no seguinte local no repositório Git do Cloud Manager:

   `/apps/fmdita/config/ditaElems.xml`

1. Navegue até o arquivo de configuração disponível no `apps` nó:

   `/apps/fmdita/config/ditaElems.xml`

   A variável `ditaElems.xml` O arquivo contém um único parâmetro configurável:

   - No `elem` especifique o nome do elemento personalizado que deseja usar em seus documentos DITA convertidos. Esse elemento seria transmitido como está nos documentos DITA gerados.

1. Se quiser especificar atributos adicionais, defina-os na variável `style2attrMap.xml` arquivo disponível no seguinte local:

   `/libs/fmdita/config/style2attrMap.xml`

1. Crie um nó de sobreposição do `config` pasta dentro do `apps` nó.

1. Navegue até o arquivo de configuração disponível no `apps` nó:

   `/apps/fmdita/config/style2attrMap.xml`

   A variável `style2attrMap.xml` O arquivo contém os seguintes parâmetros configuráveis:

   - No `fmStyle` especifique o formato de origem usado no documento do FrameMaker que você deseja mapear.

   - No`ditaAttr` especifique o atributo DITA que deseja mapear com o formato de origem.

   - No `ditaVal` elemento, especifique o valor do atributo mapeado. Se você não tiver nenhum valor, poderá deixar essa entrada em branco.

1. Salve o `style2attrMap.xml` arquivo.

1. Após configurar os parâmetros necessários no `style2attrMap.xml` arquivo, faça logon no AEM e abra a interface do usuário do Assets.

1. Navegue até o documento do FrameMaker que deseja converter e clique nele.

   O console do mapa DITA é exibido mostrando a lista de Predefinições de saída disponíveis para gerar saída.

1. Selecione o formato de saída DITA e configure os parâmetros necessários.

   >[!NOTE]
   >
   > Você deve usar o mesmo arquivo de configurações \(.sts\) que você criou no FrameMaker. Além disso, especifique o Nome das configurações e o Caminho de destino.

1. Clique em **Gerar** ícone para iniciar o processo de geração de saída.


Usar o `<attrMap> </attrMap>` bloco, você pode definir um ou vários blocos de configurações para conversão. Dependendo do conteúdo, você pode ter um arquivo .dita e um arquivo .ditamap como os arquivos convertidos.

## Migrar qualquer outro documento estruturado {#id1949B0590YK}

O Guia AEM permite converter documentos estruturados existentes em documentos DITA válidos. Você precisa especificar os locais das pastas de entrada e saída, o local do arquivo de transformação, a extensão com a qual a saída final é salva e se uma nova versão do documento é necessária ou não.

Para converter os documentos estruturados existentes no formato DITA, execute as seguintes etapas:

1. Use o Gerenciador de pacotes para baixar o arquivo /libs/fmdita/config/XSLConfig.xml.

1. Crie uma cópia do arquivo XSLConfig.xml no seguinte local no repositório Git do Cloud Manager:

   `/apps/fmdita/config/XSLConfig.xml`

   A variável `XSLConfig.xml` O arquivo contém os seguintes parâmetros configuráveis:

   - No `inputDir` elemento, especifique o local da pasta de entrada onde os documentos estruturados de origem estão disponíveis. Por exemplo, se seus documentos estruturados estiverem armazenados em uma pasta chamada `xsltodita` in `projects` e especifique o local como: `/content/dam/projects/xsltodita/`

   - No`outputDir` especifique o local da pasta de saída ou mantenha o local de saída padrão. Se a pasta de saída especificada não existir no DAM, o fluxo de trabalho de conversão criará a pasta de saída.

   - No `xslFolder` especifique o local da pasta onde os arquivos de transformação XSL são armazenados.

   - No ``xslPath`` elemento, especifique o local do arquivo .XSL principal usado para iniciar o processo de conversão.

   - No ``outputExt`` element, especifique as extensões do arquivo de saída final que é criado do fluxo de transformação.

   - Para o `createRev` elemento, especifique se uma nova versão do tópico DITA convertido deverá ser criada \(`true`\) ou não \(`false`\).

1. Salve o `XSLConfig.xml` arquivo.

1. Após configurar os parâmetros necessários no `XSLConfig.xml` arquivo, faça logon no AEM e abra a interface do usuário do Assets.

1. Navegue até o local da pasta de entrada \(`xsltodita`\).

1. Faça upload dos documentos estruturados de origem nesta pasta. Para obter informações sobre como carregar conteúdo no DAM, consulte [Fazer upload de conteúdo DITA existente](migrate-content-upload-existing-dita-content.md#).


Usar o `<config> </config>` bloco, você pode definir um ou vários blocos de configurações para conversão. O fluxo de trabalho de conversão é executado e a saída final no formato de um tópico DITA é salva no local especificado no `outputDir` elemento.

**Tópico pai:**[ Migrar conteúdo existente](migrate-content.md)
