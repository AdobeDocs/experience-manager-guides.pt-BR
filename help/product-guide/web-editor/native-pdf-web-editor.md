---
title: PDF nativo | Geração de saída de PDF
description: Saiba como usar a publicação de PDF nativo, criar e gerar uma predefinição de saída de PDF, baixar arquivos temporários após gerar a saída de PDF AEM nativo e usar variáveis de idioma nos Guias do.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Web Editor, Native PDF Output
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '3196'
ht-degree: 0%

---

# Publicar saída de PDF

Com o AEM Guides, você pode gerar PDF de tópicos individuais ou um arquivo de mapa inteiro. Você pode publicar seu conteúdo em um formato PDF usando um dos três métodos abaixo:

* **DITA-OT**

Use esse método para gerar uma saída de PDF para um mapa no painel de mapa. É possível definir as propriedades de publicação antes de gerar o PDF, criando uma predefinição de saída para o mapa que está aberto no painel de mapa. Para criar ou editar uma predefinição de saída, *Noções básicas sobre as predefinições de saída* na seção [Guia do usuário as a Cloud Service do AEM](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Para obter mais informações sobre como gerar um PDF usando o método DITA-OT, consulte [Gerar PDF usando DITA-OT](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-pdf.html).

* **FrameMaker Publishing Server (FMPS)**

Use esse método para gerar uma saída de PDF não apenas do conteúdo DITA, mas também de documentos do FrameMaker (.book e .fm) disponíveis no repositório do AEM. O PDF pode ser criado configurando uma predefinição de saída e publicado usando o FrameMaker Publishing Server (FMPS). Você pode projetar e configurar a aparência da sua saída para PDF e outros formatos e armazenar o mesmo em um arquivo de configuração (.sts). Esse arquivo de configuração é então usado pelo FMPS para gerar saída para um mapa DITA ou arquivo .book. Para criar ou editar uma predefinição de saída, consulte  *Noções básicas sobre as predefinições de saída* na seção [Guia do usuário as a Cloud Service do AEM](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Para obter mais informações sobre como configurar o FMPS, consulte [Gerar saída de documentos de FrameMaker](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Ffm-output-generatation.html).

* **Publicação de PDF nativo**

Use este método para gerar uma saída de PDF repleta de recursos com base nos padrões W3C CSS3 e CSS de mídia paginada. Com a publicação em PDF nativo, você pode usar modelos para definir o layout e o estilo do conteúdo e aplicar várias configurações para ajustar o PDF. Além disso, você pode modificar e criar seus próprios modelos com o editor de modelos.

Para obter mais informações sobre a publicação de PDF nativo, consulte [Uso da publicação de PDF nativo](#native-pdf-publishing).


## Uso da publicação de PDF nativo {#native-pdf-publishing}

Ao criar conteúdo, é essencial garantir que o conteúdo seja otimizado para visualização, edição e impressão. Usando padrões como o W3C CSS3 para estilos de conteúdo e padrões de mídia paginada CSS para propriedades de definição de página, como tamanho, margens, orientação, quebras de página, cabeçalhos, rodapés e numeração de página, você pode definir a exibição e o layout do seu documento PDF, garantindo consistência e usabilidade. O recurso de publicação PDF nativo usa esses padrões para gerar um PDF.

Com a publicação em PDF nativo, você pode usar modelos predefinidos para garantir a consistência no layout e na estrutura do conteúdo, aplicar folhas de estilos para alterar a aparência da saída, otimizar o PDF, definir marcas de impressora, permitir suporte a leitores de tela, definir a conformidade de PDF, incorporar fontes e muito mais.

A geração de um PDF usando a publicação de PDF nativo tem dois aspectos:

* Uso de modelos para aplicar o estilo ao conteúdo, definir layouts de página e várias configurações para ajustar o PDF. Os autores podem optar por usar/modificar os modelos de amostra fornecidos ou criar modelos personalizados e definir opções de configuração avançadas usadas por editores e desenvolvedores.

* Crie ou configure uma predefinição de saída de PDF para controlar as configurações de PDF. Depois de criar uma predefinição de saída PDF, você pode gerar o PDF.

Para obter mais informações, consulte [Gerar uma saída de PDF](#generate-pdf-output).

## Criar uma predefinição de saída de PDF {#create-output-preset}

A primeira etapa na geração de uma saída de PDF é criar uma predefinição de saída de PDF, que é uma coleção de propriedades de publicação atribuídas a um mapa. Você pode criar uma predefinição de saída para qualquer mapa que esteja aberto no painel Exibição de mapa ou configurar uma predefinição existente para gerar rapidamente um PDF para o mesmo mapa.

Na predefinição de saída PDF, é possível selecionar um modelo, aplicar condições, definir restrições para controlar como um usuário interage com seu PDF, definir configurações avançadas como compactação, conformidade e muito mais.

Para criar ou configurar uma predefinição de saída de PDF:

1. Na guia Saída, clique em **Predefinições** na barra lateral esquerda.
O painel Predefinição é aberto. <br>
<img src="assets/preset-panel.png" alt="painel predefinido" width="600">

1. Na saída **Predefinições** , siga um destes procedimentos:
   * Clique duas vezes em uma predefinição de saída de PDF predefinida para visualizá-la.
   * Clique no ícone + contra **Predefinições** para adicionar uma nova predefinição de saída de **Tipo: PDF**

1. Para definir as configurações de uma predefinição de PDF existente:
   * Clique em  **Opções** ![opções](assets/options.svg) ícone ao lado da Predefinição de saída desejada e selecione **Editar**.
Você pode usar as seguintes configurações no **Geral**, **Metadados**, **Layout**, **Segurança**, e **Avançado** guias para configurar uma predefinição de saída de PDF:

**Geral**

Use para especificar configurações básicas de saída, como caminho de saída, nome do arquivo de PDF e muito mais.

| Configuração | Descrição |
| --- | --- |
| **Caminho de saída** | O caminho dentro do repositório AEM onde a saída de PDF está armazenada. Verifique se o caminho de saída não está localizado na pasta do projeto. Se deixado em branco, a saída é gerada no local de saída do mapa DITA padrão.<br>Você também pode usar as variáveis prontas para uso a seguir para definir o Caminho de saída. Você pode usar uma única variável ou uma combinação de variáveis para definir essa opção. <br> `${map_filename}`: usa o nome dos arquivos de mapa DITA para criar o caminho de destino. <br> `${map_title}`: usa o título do mapa DITA para criar o caminho de destino. <br>`${preset_name}`: usa o nome da predefinição de saída para criar o caminho de destino. <br> `${language_code}`: usa o código de idioma em que o arquivo de mapa está localizado para criar o caminho de destino. <br> `${map_parentpath}`: usa o caminho completo do arquivo de mapa para criar o caminho de destino.  <br>`${path_after_langfolder}`: usa o caminho do arquivo de mapa após a pasta de idioma para criar o caminho de destino. |
| **Arquivo PDF** | Especifique um nome de arquivo para salvar o PDF. Por padrão, o nome do arquivo PDF adiciona o nome do mapa DITA ao nome predefinido. Por exemplo, ditamap é &#39;TestMap&#39; e o nome da predefinição é &#39;preset1&#39;, então o nome padrão do pdf será &#39;TestMap_preset1.pdf&#39;. <br>Você também pode usar as variáveis prontas para uso a seguir para definir o Arquivo PDF. Você pode usar uma única variável ou uma combinação de variáveis para definir essa opção. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Aplicar condições usando** | Para conteúdo condicional, escolha entre as opções abaixo para gerar uma saída de PDF com base nessas condições: <br><ul> <li> **Nenhum Aplicado** Selecione essa opção se não quiser aplicar nenhuma condição no mapa e no conteúdo de origem. <br><li> **Arquivo Digital** Selecione um arquivo DITAVAL para gerar conteúdo condicional. Para selecionar, clique em Predefinição de condição e localize o arquivo. <br> <li> **Predefinição de condição** Selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. Essa opção estará visível se você tiver adicionado uma condição para o arquivo de mapa DITA. As configurações condicionais estão disponíveis na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, consulte [Usar predefinições de condição](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Usar Linha de Base** | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar. Consulte [Trabalhar com linha de base](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) para obter mais detalhes. |
| **Criar PDF com barra de alterações entre versões publicadas** | Use as seguintes opções para criar um PDF que mostre as diferenças no conteúdo entre duas versões usando as barras de alteração:   <br><ul><li> **Linha de base da versão anterior** Escolha a versão da linha de base que você deseja comparar com a versão atual ou outra linha de base. Uma barra de alteração aparece no PDF para indicar o conteúdo modificado. Uma barra de alteração é uma linha vertical que identifica visualmente o conteúdo novo ou revisado. A barra de alterações aparece à esquerda do conteúdo que foi inserido, alterado ou excluído. <br> **Nota**: Se você selecionar **Usar Linha de Base** e escolher uma linha de base para publicar, a comparação será feita entre as duas versões de linha de base selecionadas. Por exemplo, se você escolher a versão de linha de base 1.3 em **Usar Linha de Base** e versão 1.1 em **Linha de base da versão anterior**, a comparação será feita entre a versão de base 1.1 e a versão de base 1.3. <br><li> **Mostrar texto adicionado** Selecione para mostrar o texto inserido em verde e sublinhado. Essa opção é selecionada por padrão. <br> <li> **Mostrar texto excluído** Selecione para mostrar o texto excluído em vermelho e marcado com um tachado. Essa opção é selecionada por padrão. <br>**Nota** Você também pode personalizar o estilo da barra de alterações, o conteúdo inserido ou o conteúdo excluído usando a folha de estilos.<br></ul> |
| **Fluxo de trabalho de pós-geração** | Selecione para mostrar uma lista suspensa que contém todos os workflows configurados no AEM. Você pode selecionar o workflow que deseja executar após a conclusão do workflow de geração de PDF. |

**Metadados**

Os metadados são a descrição ou definição do seu conteúdo. Os metadados ajudam na gestão de conteúdo e na pesquisa de arquivos na Internet.

Use a guia Metadados para definir os campos de metadados, como nome do autor, título do documento, palavras-chave, informações de direitos autorais e outros campos de dados para a saída de PDF. Você também pode adicionar metadados personalizados para a saída do PDF.

Esses metadados são mapeados na guia Descrição, nas Propriedades do documento do PDF de saída.

**Nota**: esses metadados substituem os definidos no nível de livro.

<img src="assets/pdf-metadata.png" alt="guia metadados" width="600">

Nas predefinições de Saída, **selecionar PDF** > **Metadados** para adicionar e personalizar opções de metadados.
* **Fornecer arquivo XMP**

  Os campos de metadados podem ser preenchidos diretamente com a importação [XMP](https://www.adobe.com/products/xmp.html) arquivo (Extensible Metadata Platform). Você pode baixar um arquivo XMP de amostra daqui.

[Download](assets/SampleXMP.xmp)

  Como alternativa, você pode gerar um arquivo XMP usando o Adobe Acrobat.
   1. Clique em **Arquivo** > **Propriedades** no Acrobat.
   1. Em **Descrição**, clique em **Metadados adicionais**.
   1. No painel esquerdo, selecione **Avançado**.
   1. Clique em **Salvar**.

  O arquivo XMP é salvo no dispositivo.

* **Fornecer nomes e valores de metadados**

   1. Adicione um nome selecionando no menu suspenso ou adicione um metadado personalizado digitando diretamente no campo de nome.
   1. Insira o valor dos metadados e clique no ícone &quot;+&quot;.
Os metadados são adicionados à lista para o PDF.

Também é possível usar variáveis para definir os valores de metadados.  Você pode usar os metadados definidos para o mapa DITA ou arquivo de mapa como variáveis. Os metadados podem ser encontrados no `/jcr:content/metadata` nó do mapa DITA ou arquivo de mapa.
Quando você usa uma variável, seu valor é escolhido das propriedades dos metadados.

Para usar uma variável, você precisa defini-la na variável `${<variable>}` formato.

Por exemplo, uma das propriedades de metadados definidas em /`jcr:content/metadata` o nó é
`dc:title`. Você pode especificar `${dc:title}`, e o valor de título é usado na saída final.

Você pode usar uma única variável ou uma combinação de variáveis para definir os metadados. Por exemplo, `${dc:title} ${dc:docstate}`. Também é possível usar a combinação de uma variável e uma string.  Por exemplo, `View ${dc:title} in ${dc:language}`.

Use variáveis de idioma para definir o valor localizado das propriedades de metadados. Dependendo do idioma escolhido, o valor localizado é escolhido automaticamente na saída do PDF. Por exemplo, você pode imprimir &quot;Author&quot; como o valor dos metadados em inglês e &quot;Autorin&quot; em alemão.

Formato: `${lng:<variable name>}`. Por exemplo, `${lng:author-label}` onde `author-label` é uma variável de idioma.

Focalizar <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo à opção para ver mais detalhes sobre ele.


**Layout**

Use para definir layouts de página e especificar opções de exibição de página para saída de PDF, como Exibição de página e definir níveis de Zoom.

| Configuração | Descrição |
| --- | --- |
| **Modelo PDF** | Os modelos de PDF fornecem uma estrutura clara para definir layouts de página, estilo do conteúdo e aplicar várias configurações à saída de PDF. Selecione nas opções suspensas do modelo de PDF para escolher o modelo de sua preferência. <br> Também é possível selecionar **Procurar Modelo** <img src="./assets/browse-templates-icon.svg"  alt= "ícone procurar modelos" width="25">  para escolher um modelo. No **Selecionar modelo de PDF** caixa de diálogo, também é possível visualizar a miniatura e exibir o título e a descrição do modelo selecionado. |
| **Exibição da página** | Use a Exibição de página para a exibição de página que mostra como o PDF é exibido quando é aberto. Selecione nas opções suspensas Exibição da página para escolher uma exibição preferencial. <br><ul><li> **Padrão**  É exibido de acordo com a configuração padrão do visualizador de PDF na máquina de um usuário.  <br> <li> **Exibição de página única** Exibe uma página de cada vez.   <br> <li> **Rolagem de página única** Exibe uma única página em uma coluna vertical contínua.  <br> <li> **Exibição de duas páginas** Exibe duas páginas espelhadas lado a lado de cada vez. .<br> <li> **Rolagem de duas páginas** Exibe páginas espelhadas lado a lado com rolagem contínua. </ul> |
| **Zoom** | Selecione para redimensionar a exibição de página que mostra como o PDF é exibido quando é aberto.  <br><ul><li> **Padrão** É exibido de acordo com a configuração padrão do visualizador de PDF na máquina de um usuário    <br> <li> **100%** Faz a página aparecer em seu tamanho real.     <br> <li> **Ajustar página** Torna a largura e a altura da página ajustáveis dentro do painel de documentos. .<br> <li> **Ajustar largura da página** Faz com que a largura da página preencha a largura do painel do documento.  <br> <li> **Ajustar altura da página** Faz com que a altura da página preencha a altura do painel do documento. </ul> |

**Segurança**

Protect seu PDF adicionando restrições para abrir e ler o arquivo. Use as opções abaixo para evitar acesso não autorizado.

| Configuração | Descrição |
| --- | --- |
| **Definir senha para abrir o documento** | Selecione para adicionar uma senha segura para exibir seu arquivo PDF. Especifique uma senha no **Senha do usuário** campo. Os usuários podem abrir o PDF somente digitando a senha fornecida neste campo. |
| **Definir as restrições do documento** | Selecione para restringir como os usuários podem interagir com o seu PDF. Especifique uma senha no **Senha do proprietário** para que as configurações de restrição abaixo funcionem.  <br><ul><li> **Impressão** Selecione para permitir que um usuário imprima o PDF. <br> <li> **Impressão com qualidade de rascunho** Selecione para permitir que um usuário imprima o PDF em uma resolução mais baixa.  <br> <li> **Cópia de conteúdo** Selecione para permitir que um usuário copie o conteúdo do PDF.   <br> <li> **Anotações** Selecione para permitir que um usuário adicione uma observação ou comentário no PDF.  <br> <li> **Modificações de conteúdo** Selecione para permitir que um usuário altere o conteúdo no PDF.  <br> <li> **Cópia de conteúdo para acessibilidade** Selecione para permitir que os leitores de tela leiam e naveguem pelo conteúdo no PDF.  <br>  **Montagem do documento** Selecione para permitir que os usuários insiram páginas no PDF.  <br> **Nota**: Os usuários precisam inserir a senha de proprietário para alterar qualquer restrição em Arquivo > Propriedades no Adobe Acrobat. |

**Avançado**

Use as opções a seguir para especificar configurações avançadas para mesclar PDF, usar compactação, selecionar padrão de conformidade e muito mais.

| Configuração | Descrição |
| --- | --- |
| **Criar PDF acessível (marcado)** | Selecione esta opção para gerar um PDF com tags. Um PDF marcado facilita a leitura e a navegação de conteúdo, hiperlinks, marcadores, entre outros, pelos leitores de tela. Por exemplo, se uma tabela estiver marcada, o leitor de tela saberá que está lendo a tabela e não apenas linhas e texto. |
| **Mesclar PDF incluídos no índice** | Selecione essa opção para mesclar PDF existentes na saída, adicionando-os ao mapa DITA como um arquivo de recurso. Os PDF serão inseridos no local representado no mapa e as páginas serão aumentadas de acordo. |
| **Incorporar fontes usadas** | Selecione esta opção ao usar fontes que podem não estar instaladas no computador do usuário final. Com essa opção selecionada, as fontes usadas são incorporadas ao PDF, garantindo que o usuário possa ver o PDF como pretendido, mesmo que as fontes não estejam instaladas em sua máquina. <br> **Nota**: uma fonte pode ser incorporada somente se contiver uma configuração do fornecedor da fonte que permita sua incorporação. Verifique se você tem a configuração ou licença necessária antes de incorporar uma fonte. |
| **Usar hifenização automática** | Com a hifenização automática ativada, as palavras no final das linhas são quebradas em locais gramaticalmente corretos com um hífen. |
| **Ativar JavaScript** | Ative esta opção se você tiver um código JavaScript que deseja usar para transformar seu conteúdo dinamicamente antes de gerar um PDF. |
| **Incorporar arquivos multimídia** | Selecione esta opção para incluir qualquer conteúdo de áudio, vídeo e interativo no PDF. |
| **Usar compactação total para otimizar o tamanho do PDF** | Selecione esta opção se desejar compactar/reduzir o tamanho de um PDF grande. Lembre-se de que compactar o PDF pode reduzir a qualidade do arquivo. |
| **Usar compactação de imagem para otimizar o tamanho do PDF** | Selecione esta opção se você deseja compactar/reduzir o tamanho das imagens usadas em seu PDF. Lembre-se de que compactar uma imagem pode reduzir sua qualidade. |
| **Usar resolução personalizada (pixels por polegada)** | É a resolução de exibição da página em pixels por polegada. Insira um valor preferencial no campo que aparece quando esta opção é selecionada. O valor padrão é de 96 pixels por polegada. Defina um valor maior para ajustar mais conteúdo em uma polegada e vice-versa, se você definir um valor menor. |
| **Mostrar marca d&#39;água** | Selecione essa opção para sobrepor uma marca d&#39;água na saída. Você pode inserir uma nova cadeia de caracteres de texto na caixa de texto com o caractere no formato desejado. <br><br>Use texto estático ou variáveis de idioma para publicar a versão localizada da marca d&#39;água.  Dependendo do idioma escolhido, o valor localizado é escolhido automaticamente na saída do PDF. Por exemplo, você pode imprimir ‘Publisher’ como uma marca d&#39;água em inglês e ‘Auteure’ em francês.  <br> Formato: `${lng:<variable name>}`. Por exemplo, `$ {lng:publisher-label}` onde `publisher-label` é uma variável de idioma. <br> Focalizar <img src="./assets/info-details.svg" alt= "ícone de informações" width="25"> próximo à opção para ver mais detalhes sobre ele. |
| **Habilitar equações MathML** | Selecione esta opção para renderizar as equações MathML presentes no seu conteúdo. As equações serão ignoradas caso contrário, por padrão. |
| **Baixar arquivos temporários** | Selecione esta opção se você deseja fazer download dos arquivos de HTML provisórios criados durante a geração da saída de PDF nativo. Posteriormente, você pode baixar os arquivos temporários depois de gerar a saída. |
| **Conformidade de PDF** | É o padrão para o qual você pretende salvar o PDF para garantir sua conformidade. Selecione na lista suspensa para escolher os padrões de PDF disponíveis. Para obter mais detalhes sobre os padrões suportados, consulte [Sobre os padrões PDF](https://helpx.adobe.com/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |


## Gerar uma saída de PDF {#generate-pdf-output}

Depois de configurar a predefinição de saída, você pode gerar a saída a partir do painel Predefinições, usando o **Gerar predefinição** recurso.

1. No **Autor** , selecione a **Repositório** Exibir.\
   Isso abre o painel Repositório.

1. No painel Repositório, abra o arquivo de mapa DITA em **Exibição de mapa**.

1. No **Output** clique em **Predefinições** para exibir o painel Predefinição.
Para criar ou configurar uma predefinição de saída, consulte [Criar uma predefinição de saída de PDF](#create-output-preset).
1. Para salvar as configurações, clique no link **Salvar tudo** ![salvar tudo](assets/SaveFloppy_icon.svg) no canto superior esquerdo da barra de ferramentas padrão na visualização Saída.
1. Clique em **Gerar predefinição** ![gerar predefinição](assets/generate-output.svg) ícone na barra superior.
No painel Predefinições de saída, é possível exibir uma barra de progresso ao lado da predefinição de saída selecionada.
1. Quando a geração de saída estiver concluída, clique em  **Exibir saída** ![exibir saída](assets/view-output.svg) ícone na barra superior para exibir a saída.\
   A **Sucesso** está visível no canto inferior direito da tela.
Se uma saída não for bem-sucedida, a mensagem de erro abaixo será exibida.
<img src="assets/error-log.png" alt="log de erros" width="250">

Para exibir o log de erros, clique em **Ignorar**, passe o mouse sobre a guia de predefinição selecionada e clique em ![opções](assets/options.svg) **Opções** > **Exibir registro**.

### Baixar arquivos temporários depois de gerar a saída de PDF nativa

Se você selecionar a variável **Baixar arquivos temporários** nas Configurações avançadas, você também pode baixar os arquivos de HTML provisórios criados durante a geração da saída de PDF nativo. Depois de gerar a saída, você pode baixar os arquivos temporários usando o **Baixar arquivos temporários** ![baixar arquivos temporários](assets/native-pdf-download-temporary-files-icon.svg)ícone na barra superior. Esse recurso ajuda a visualizar os estilos e layouts provisórios do HTML e ajuda a corrigir ou alterar os estilos de CSS de acordo com os requisitos.


>[!NOTE]
>
> A variável **Baixar arquivos temporários**  ![baixar arquivos temporários](assets/native-pdf-download-temporary-files-icon.svg) O ícone será exibido somente se tiver gerado a última saída de PDF usando a predefinição na qual você selecionou a opção no **Avançado** guia.



### Usar variáveis de idioma

Guias de AEM também fornecem suporte para variáveis de idioma. Selecionar **Variáveis de idioma** <img src="./assets/language-variables.svg" width="25">  no painel esquerdo para definir uma versão localizada dos rótulos prontos para uso como Observação, Cuidado e Aviso ou texto estático na saída de PDF. Para obter mais detalhes, consulte [Suporte para variáveis de idioma](../native-pdf/native-pdf-language-variables.md).

