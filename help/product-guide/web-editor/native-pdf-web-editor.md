---
title: PDF nativo | Geração de saída do PDF
description: Saiba como usar a publicação nativa do PDF, criar e gerar uma predefinição de saída do PDF, baixar arquivos temporários após gerar a saída nativa do PDF e usar variáveis de idioma no Adobe Experience Manager Guides.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Native PDF Output
role: User
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '3064'
ht-degree: 0%

---

# Predefinição de saída nativa do PDF

Ao criar conteúdo, é essencial garantir que o conteúdo seja otimizado para visualização, edição e impressão. Usando padrões como o W3C CSS3 para estilos de conteúdo e padrões de mídia paginada CSS para propriedades de definição de página, como tamanho, margens, orientação, quebras de página, cabeçalhos, rodapés e numeração de página, você pode definir a exibição e o layout do documento do PDF, garantindo consistência e usabilidade. O recurso de publicação do PDF nativo usa esses padrões para gerar uma PDF.

Com a publicação nativa do PDF, você pode usar modelos predefinidos para garantir consistência no layout e na estrutura do conteúdo, aplicar folhas de estilos para alterar a aparência da saída, otimizar o PDF, definir marcas de impressora, permitir suporte a leitores de tela, definir a conformidade do PDF, incorporar fontes e muito mais.

A geração de uma PDF usando a publicação nativa do PDF tem dois aspectos:

* Uso de modelos para aplicar o estilo ao conteúdo, definir layouts de página e várias configurações para ajustar o PDF. Os autores podem optar por usar/modificar os modelos de amostra fornecidos ou criar modelos personalizados e definir opções de configuração avançadas usadas por editores e desenvolvedores.

* Crie ou configure uma predefinição de saída do PDF para controlar as configurações do PDF. Depois de criar uma predefinição de saída do PDF, você pode gerar a PDF.

## Criar uma predefinição de saída

Execute as seguintes etapas para criar a predefinição do PDF a partir do console Mapa:

1. [Abra um arquivo de mapa DITA no Console de mapa](../user-guide/open-files-map-console.md).

   Você também pode acessar o arquivo de mapa no widget **Arquivos recentes** na [seção Visão geral](../user-guide/intro-home-page.md#overview). O arquivo de mapa selecionado seria aberto no console Mapa.
1. Na guia **Predefinições de saída**, selecione o ícone + para criar uma predefinição de saída.
1. Selecione **PDF** na lista suspensa Tipo na caixa de diálogo **Nova predefinição de saída**.
1. No campo **Nome**, forneça um nome para esta predefinição.
1. No campo **Gerar PDF Usando**, selecione **Native-PDF**.
1. Selecione a opção **Adicionar ao perfil de pasta atual** para criar uma predefinição de saída no perfil de pasta atual. O ![ícone de perfil de pasta](./assets/global-preset-icon.svg) indica uma predefinição de nível de perfil de pasta.

   Saiba mais sobre [Gerenciar predefinições de saída de perfil Global e de Pasta](../user-guide/web-editor-manage-output-presets.md).

1. Selecione **Adicionar**.

   A predefinição do PDF é criada.

## Configuração de predefinição nativa do PDF

Depois que a predefinição é criada, defina as configurações de predefinição do PDF nativo. As opções de configuração predefinidas para DITA-OT estão organizadas nas guias **Geral**, **Metadados**, **Layout**, **Segurança**, **Imprimir** e **Avançado**.

<img src="assets/preset-panel.png" alt="painel predefinido" width="800">

**Geral**

Use para especificar configurações básicas de saída, como especificar o caminho de saída, o nome do arquivo do PDF e muito mais.

| Configuração | Descrição |
| --- | --- |
| **Caminho de saída** | O caminho no repositório do AEM onde a saída do PDF está armazenada. Verifique se o caminho de saída não está localizado na pasta do projeto. Se deixado em branco, a saída é gerada no local de saída do mapa DITA padrão.<br>Você também pode usar as variáveis prontas para uso a seguir para definir o Caminho de Saída. Você pode usar uma única variável ou uma combinação de variáveis para definir essa opção. <br> `${map_filename}`: usa o nome dos arquivos de mapa DITA para criar o caminho de destino. <br> `${map_title}`: usa o título do mapa DITA para criar o caminho de destino. <br>`${preset_name}`: usa o nome da predefinição de saída para criar o caminho de destino. <br> `${language_code}`: Usa o código de idioma em que o arquivo de mapa está localizado para criar o caminho de destino. <br> `${map_parentpath}`: Usa o caminho completo do arquivo de mapa para criar o caminho de destino.  <br>`${path_after_langfolder}`: Usa o caminho do arquivo de mapa após a pasta de idioma para criar o caminho de destino. |
| **Arquivo PDF** | Especifique um nome de arquivo para salvar a PDF. Por padrão, o nome de arquivo do PDF adiciona o nome do mapa DITA ao nome predefinido. Por exemplo, ditamap é &#39;TestMap&#39; e o nome da predefinição é &#39;preset1&#39;, então o nome padrão do pdf será &#39;TestMap_preset1.pdf&#39;. <br>Você também pode usar as variáveis prontas para uso a seguir para definir o Arquivo do PDF. Você pode usar uma única variável ou uma combinação de variáveis para definir essa opção. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Aplicar Condições Usando** | Para conteúdo condicional, escolha entre as opções abaixo para gerar uma saída do PDF com base nessas condições: <br><ul> <li> **Nenhum Aplicado** Selecione esta opção se não quiser aplicar nenhuma condição no mapa e no conteúdo de origem. <br><li> **Arquivo Digital** Selecione um arquivo DITAVAL para gerar conteúdo condicional. Para selecionar, selecione Predefinição de condição e localize o arquivo. <br> <li> **Predefinição de condição** Selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. Essa opção estará visível se você tiver adicionado uma condição para o arquivo de mapa DITA. As configurações condicionais estão disponíveis na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, exiba [Usar predefinições de condição](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Usar Linha de Base** | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar. Exiba [Trabalhar com Linha de Base](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) para obter mais detalhes. |
| **Criar PDF com Barra de Alterações entre Versões Publicadas** | Use as seguintes opções para criar uma PDF mostrando as diferenças no conteúdo entre duas versões usando barras de alteração:   <br><ul><li> **Linha de Base da Versão Anterior** Escolha a versão de linha de base que você deseja comparar com a versão atual ou outra linha de base. Uma barra de alteração é exibida na PDF para indicar o conteúdo modificado. Uma barra de alteração é uma linha vertical que identifica visualmente o conteúdo novo ou revisado. A barra de alterações aparece à esquerda do conteúdo que foi inserido, alterado ou excluído. <br> **Observação**: se você selecionar **Usar Linha de Base** e escolher uma linha de base para publicar, a comparação será feita entre as duas versões de linha de base selecionadas. Por exemplo, se você escolher Versão 1.3 da linha de base em **Usar linha de base** e Versão 1.1 em **Linha de base da Versão Anterior**, a comparação será feita entre a Versão 1.1 da linha de base e a Versão 1.3 da linha de base. <br><li> **Mostrar Texto Adicionado** Selecione para mostrar o texto inserido na cor verde e sublinhado. Essa opção é selecionada por padrão. <br> <li> **Mostrar texto excluído** Selecione para mostrar o texto excluído em vermelho e marcado com um tachado. Essa opção é selecionada por padrão. <br>**Observação** Você também pode personalizar o estilo da barra de alterações, o conteúdo inserido ou o conteúdo excluído usando a folha de estilos.<br></ul> |
| **Fluxo de Trabalho de Pós-Geração** | Selecione para mostrar uma lista suspensa que contém todos os workflows configurados no AEM. Você pode selecionar o workflow que deseja executar após a conclusão do workflow de geração do PDF. |

**Metadados**

Os metadados são a descrição ou definição do seu conteúdo. Os metadados ajudam na gestão de conteúdo e na pesquisa de arquivos na Internet.

Use a guia Metadados para definir os campos de metadados, como nome do autor, título do documento, palavras-chave, informações de copyright e outros campos de dados para a saída do PDF. Você também pode adicionar metadados personalizados para a saída do PDF.

Estes metadados estão mapeados para os metadados na guia **Descrição** nas **Propriedades do Documento** do PDF de saída.



<img src="assets/pdf-metadata.png" alt="guia metadados" width="600">

Nas predefinições de Saída, selecione **PDF** > **Native-PDF** > **Metadata** para adicionar e personalizar opções de metadados.
* **Usar metadados adicionados ao topicmeta**

  Essa opção é selecionada por padrão. Você pode usar os metadados adicionados no elemento topicmeta do mapa DITA para preencher os campos de metadados da saída do PDF.

* **Fornecer arquivo XMP**

  Você também pode preencher diretamente os campos de metadados importando o arquivo [XMP](https://www.adobe.com/products/xmp.html) (Plataforma de Metadados Extensível). Você pode baixar um arquivo de amostra do XMP aqui.

[Download](assets/SampleXMP.xmp)

  Como alternativa, você pode gerar um arquivo XMP usando o Adobe Acrobat.
   1. Selecione **Arquivo** > **Propriedades** no Acrobat.
   1. Em **Descrição**, selecione **Metadados Adicionais**.
   1. No painel esquerdo, selecione **Avançado**.
   1. Selecione **Salvar**.

  O arquivo XMP é salvo no dispositivo.

* **Forneça nomes e valores de metadados**

   1. Adicione um nome selecionando no menu suspenso ou adicione um metadado personalizado digitando diretamente no campo de nome.
   1. Insira o valor dos metadados e selecione o ícone &quot;+&quot;.
Os metadados são adicionados à lista para o PDF.

Também é possível usar variáveis para definir os valores de metadados.  Você pode usar os metadados definidos para o mapa DITA ou arquivo de mapa como variáveis. Os metadados podem ser encontrados no nó `/jcr:content/metadata` do mapa DITA ou do arquivo de mapa.
Quando você usa uma variável, seu valor é escolhido das propriedades dos metadados.

Para usar uma variável, você precisa defini-la no formato `${<variable>}`.

Por exemplo, uma das propriedades de metadados definidas no nó /`jcr:content/metadata` é
`dc:title`. Você pode especificar `${dc:title}`, e o valor do título é usado na saída final.

Você pode usar uma única variável ou uma combinação de variáveis para definir os metadados. Por exemplo, `${dc:title} ${dc:docstate}`. Também é possível usar a combinação de uma variável e uma string.  Por exemplo, `View ${dc:title} in ${dc:language}`.

Use variáveis de idioma para definir o valor localizado das propriedades de metadados. Dependendo do idioma escolhido, o valor localizado é escolhido automaticamente na saída do PDF. Por exemplo, você pode imprimir &quot;Author&quot; como o valor dos metadados em inglês e &quot;Autorin&quot; em alemão.

Formato: `${lng:<variable name>}`. Por exemplo, `${lng:author-label}` onde `author-label` é uma variável de idioma.

Focalizar <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo à opção para ver mais detalhes sobre ele.


**Layout**

Use para definir layouts de página e especificar opções de exibição de página para saída do PDF, como Exibição de página e definir níveis de Zoom.

| Configuração | Descrição |
| --- | --- |
| **Modelo do PDF** | Os modelos do PDF fornecem uma estrutura clara para definir layouts de página, estilo do conteúdo e aplicar várias configurações à saída do PDF. Selecione nas opções suspensas do modelo PDF para escolher o modelo preferido. <br> Você também pode selecionar **Procurar Modelo** <img src="./assets/browse-templates-icon.svg"  alt= "ícone procurar modelos" width="25"> para escolher um modelo. Na caixa de diálogo **Selecionar modelo de PDF**, você também pode visualizar a miniatura e exibir o título e a descrição do modelo selecionado. |
| **Exibição de página** | Use a Exibição de página para a exibição de página que mostra como a PDF é exibida quando aberta. Selecione nas opções suspensas Exibição da página para escolher uma exibição preferencial. <br><ul><li> **Padrão** É exibido de acordo com a configuração padrão do visualizador do PDF no computador de um usuário.  <br> <li> **Exibição de página única** Exibe uma página de cada vez.   <br> <li> **Rolagem de Página Única** Exibe uma única página em uma coluna vertical contínua.  <br> <li> **Exibição de duas páginas** Exibe duas páginas espelhadas lado a lado de cada vez. .<br> <li> **Rolagem de Duas Páginas** Exibe duas páginas espelhadas lado a lado com rolagem contínua. </ul> |
| **Zoom** | Selecione para redimensionar a exibição de página que mostra como o PDF é exibido quando é aberto.  <br><ul><li> **Padrão** É exibido de acordo com a configuração padrão do visualizador do PDF no computador de um usuário    <br> <li> **100%** Faz com que a página apareça em seu tamanho real.     <br> <li> **Ajustar página** Faz com que a largura e a altura da página caibam no painel de documentos.   .<br> <li> **Ajustar largura da página** Faz com que a largura da página preencha a largura do painel de documentos.  <br> <li> **Ajustar altura da página** Faz com que a altura da página preencha a altura do painel de documentos. </ul> |

**Segurança**

Proteja seu PDF adicionando restrições para abrir e ler o arquivo. Use as opções abaixo para evitar acesso não autorizado.

| Configuração | Descrição |
| --- | --- |
| **Definir senha para abrir o documento** | Selecione para adicionar uma senha segura para exibir seu arquivo do PDF. Especifique uma senha no campo **Senha do usuário**. Os usuários podem abrir o PDF somente digitando a senha fornecida neste campo. |
| **Definir as restrições de documento** | Selecione para restringir como os usuários podem interagir com o PDF. Especifique uma senha no campo **Senha do Proprietário** para que as configurações de restrição abaixo funcionem.  <br><ul><li> **Impressão** Selecione para permitir que um usuário imprima a PDF. <br> <li> **Impressão com qualidade de rascunho** Selecione para permitir que um usuário imprima o PDF em uma resolução mais baixa.  <br> <li> **Cópia de conteúdo** Selecione para permitir que um usuário copie conteúdo do PDF.   <br> <li> **Anotações** Selecione para permitir que um usuário adicione uma observação ou comentário na PDF. <br> <li> **Modificações de conteúdo** Selecione para permitir que um usuário altere o conteúdo na PDF. <br> <li> **Cópia de conteúdo para acessibilidade** Selecione para permitir que os leitores de tela leiam e naveguem no conteúdo do PDF. <br>  **Assembly do documento** Selecione para permitir que os usuários insiram páginas no PDF. <br> **Observação**: os usuários precisam digitar a senha de proprietário para alterar quaisquer restrições em Arquivo > Propriedades no Adobe Acrobat. |

**Imprimir**

>[!NOTE]
>
> A partir da versão 5.0/2025.02.0 do Experience Manager Guides, a seção Imprimir agora faz parte da **predefinição de Saída Nativa do PDF**. Para os modelos existentes com configurações de impressão salvas, os dados de impressão permanecerão intactos, mas não aparecerão mais na interface do usuário nem serão aplicados durante a saída. Para continuar usando essas configurações, você deve reconfigurá-las na predefinição de Saída nativa do PDF.

Defina as configurações de produção de impressão para atribuir marcas de impressora, selecionar modelos de cores e especificar propriedades relacionadas à impressão da saída do PDF.

* **Marcas da impressora**: quando você prepara um documento para produção de impressão, marcas da impressora são adicionadas aos limites da página para auxiliar no alinhamento, corte e seleção de cores adequados durante a impressão. Ao selecionar uma marca de impressora, o limite da página é estendido para acomodar a marca, que é aparada durante a impressão. Você pode optar por exibir as seguintes marcas de impressora na saída do PDF:
   * **Marcas de aparagem**: selecione a opção para colocar uma marca em cada canto da área de aparagem para indicar onde o papel precisa ser aparado após a impressão.
   * **Marcas de sangria**: selecione para colocar uma marca em cada canto da caixa de sangria para indicar a área de aparagem da imagem estendida.
   * **Marcas de registro**: selecione para colocar uma marca fora da área de corte para alinhar as diferentes separações em um documento colorido.
   * **Barras de Cores**: selecione para adicionar uma faixa de cores fora da área de aparagem para manter a consistência de cores e ajustar a densidade da tinta ao imprimir.

  Defina dimensões para as marcas de impressora selecionadas usando as opções **Largura da Linha**, **Cor da Linha** e **Largura da Caixa de Sangria**.

* **Tamanho da Caixa de Mídia**: este é o tamanho geral da página, incluindo a área estendida ocupada pelas marcas da impressora. Use a opção suspensa para selecionar o tamanho da página para a saída do PDF ou criar seu próprio tamanho personalizado.

* **Espaço de Cores**: você tem a opção de escolher espaços de cores RGB ou CMYK para imprimir seu documento PDF. Escolha RGB para exibir o PDF gerado digitalmente e o CMYK para impressão física. As cores definidas no documento são convertidas no espaço de cores escolhido.

* **Perfil ICC**: aqui, você pode gerenciar a precisão de cores entre dispositivos especificando um perfil ICC. Isso garante uma renderização de cores consistente na saída impressa.

Para definir essa configuração, especifique o caminho do arquivo de perfil ICC no servidor e forneça o nome do perfil ICC para facilitar a identificação. Como alternativa, se o perfil ICC for armazenado on-line, você poderá fornecer o URL em vez do caminho do arquivo.

>[!NOTE]
>
> Um perfil de cores ICC é necessário para a criação do PDF/A se estiver usando o espaço de cores CMYK.

<!--For more information on applying these print settings, see *Printing preferences*.-->

**Avançado**

Use as opções a seguir para especificar configurações avançadas para mesclar PDFs, usar compactação, selecionar o padrão de conformidade e muito mais.

| Configuração | Descrição |
| --- | --- |
| **Criar PDF acessível (marcado)** | Selecione essa opção para gerar uma PDF com tags. Um PDF marcado facilita a leitura e a navegação dos leitores de tela por conteúdo, hiperlinks, marcadores e assim por diante. Por exemplo, se uma tabela estiver marcada, o leitor de tela saberá que está lendo a tabela e não apenas linhas e texto. |
| **Mesclar PDFs incluídos no índice** | Selecione essa opção para mesclar PDFs existentes na saída, adicionando-os ao mapa DITA como um arquivo de recurso. Os PDFs serão inseridos no local representado no mapa e as páginas serão aumentadas de acordo. |
| **Incorporar fontes usadas** | Selecione esta opção ao usar fontes que podem não estar instaladas no computador do usuário final. Com essa opção selecionada, as fontes usadas são incorporadas ao PDF, garantindo que o usuário possa visualizar o PDF conforme pretendido, mesmo que as fontes não estejam instaladas em sua máquina. <br> **Observação**: uma fonte só poderá ser inserida se contiver uma configuração do fornecedor da fonte que permita sua inserção. Verifique se você tem a configuração ou licença necessária antes de incorporar uma fonte. |
| **Usar hifenização automática** | Com a hifenização automática ativada, as palavras no final das linhas são quebradas em locais gramaticalmente corretos com um hífen. |
| **Habilitar JavaScript** | Ative essa opção se tiver um código JavaScript que deseja usar para transformar dinamicamente seu conteúdo antes de gerar uma PDF. |
| **Incorporar arquivos multimídia** | Selecione esta opção para incluir qualquer conteúdo de áudio, vídeo e interativo na PDF. |
| **Usar compactação completa para otimizar o tamanho do PDF** | Selecione essa opção se desejar compactar/reduzir o tamanho de um PDF grande. Lembre-se de que compactar o PDF pode reduzir a qualidade do arquivo. |
| **Usar compactação de imagem para otimizar o tamanho do PDF** | Selecione essa opção se desejar compactar/reduzir o tamanho das imagens usadas no PDF. Lembre-se de que compactar uma imagem pode reduzir sua qualidade. |
| **Usar resolução personalizada (pixels por polegada)** | É a resolução de exibição da página em pixels por polegada. Insira um valor preferencial no campo que aparece quando esta opção é selecionada. O valor padrão é de 96 pixels por polegada. Defina um valor maior para ajustar mais conteúdo em uma polegada e vice-versa, se você definir um valor menor. |
| **Mostrar Marca D&#39;Água** | Selecione essa opção para sobrepor uma marca d&#39;água na saída. Você pode inserir uma nova cadeia de caracteres de texto na caixa de texto com o caractere no formato desejado. <br><br>Use texto estático ou variáveis de idioma para publicar a versão localizada da marca d&#39;água.  Dependendo do idioma escolhido, o valor localizado é escolhido automaticamente na saída do PDF. Por exemplo, você pode imprimir ‘Publisher’ como uma marca d&#39;água em inglês e ‘Auteure’ em francês.  <br> Formato: `${lng:<variable name>}`. Por exemplo, `$ {lng:publisher-label}` onde `publisher-label` é uma variável de idioma. <br> Passe o cursor <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo à opção para ver mais detalhes sobre ele. |
| **Habilitar equações do MathML** | Selecione essa opção para renderizar as equações do MathML presentes no seu conteúdo. As equações serão ignoradas caso contrário, por padrão. |
| **Criar formulário interativo do PDF** | Selecione essa opção se desejar incluir campos de formulário interativos e personalizáveis do PDF para entrada aprimorada do usuário em saídas geradas do PDF. |
| **Incluir alterações de controle** | Selecione essa opção se desejar incluir alterações controladas no PDF gerado para facilitar a revisão e a comparação. |
| **Reter arquivos temporários** | Selecione essa opção se quiser manter os arquivos provisórios do HTML criados ao gerar a saída do PDF nativo. Posteriormente, você pode baixar os arquivos temporários depois de gerar a saída. |
| **Conformidade do PDF** | É o padrão para o qual você pretende salvar seu PDF para garantir sua conformidade. Selecione na lista suspensa para escolher na lista de padrões disponíveis do PDF. Para obter mais detalhes sobre os padrões compatíveis, consulte [Sobre os padrões da PDF](https://helpx.adobe.com/br/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Propriedades do arquivo** | Selecione os metadados que deseja passar para a publicação nativa do PDF. A lista suspensa lista as propriedades personalizadas e padrão. Por exemplo, `dc:description`, `dc:language`, `dc:title` e `docstate` são as propriedades padrão, enquanto você pode ter `author` como a propriedade personalizada. As propriedades de metadados selecionadas são passadas para o arquivo PDF gerado usando o PDF Nativo. <br> Essas propriedades são selecionadas do arquivo `metadataList` disponível em:`/libs/fmdita/config/metadataList`. <br>Este arquivo pode ser sobreposto em: `/apps/fmdita/config/metadataList`. |



<!--------------


### Additional notes for PDF output

**Download temporary files after generating the Native PDF output**

If you select the **Download temporary files** option in the Advanced settings, you can also download the interim HTML files created while generating the Native PDF output. Once you’ve generated the output, you can download the temporary files using the **Download temporary files** ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg)icon on the top bar. This feature helps you view your interim HTML styles and layouts and helps you correct or change your CSS styles according to your requirements.


>[!NOTE]
>
> The **Download temporary files**  ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg) icon appears only if you have generated the last PDF output using the preset wherein you have selected the option in the **Advanced** tab. 


**Use language variables**

AEM Guides also provides the support for language variables. Select **Language Variables** <img src="assets/language-variables.svg" width="25">  in the left panel to define a localized version of the out-of-the-box labels like Note, Caution, and Warning or static text in the PDF output. For more details, view [Support for language variables](../native-pdf/native-pdf-language-variables.md).


**Support for Markdown documents**

Experience Manager Guides also provides support for your Markdown documents.  Markdown files are easy to author and also provide a variety of formatting options. Learn how to [author Markdown documents from the Editor](../user-guide/web-editor-markdown-topic.md). 

You can add the Markdown topics to your DITA map and generate the PDF output using the Native PDF output presets.  Learn how to configure or [create a PDF output preset](#create-a-pdf-output-preset-create-output-preset). 

--------------->