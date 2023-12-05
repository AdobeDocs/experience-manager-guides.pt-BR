---
title: Usar a especialização personalizada do DITA-OT e do DITA
description: Saiba como usar a especialização personalizada do DITA-OT e do DITA
exl-id: ddc1393b-b269-40e5-9627-96dad82b42e9
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '2093'
ht-degree: 0%

---

# Usar a especialização personalizada do DITA-OT e do DITA {#id181GAJ0005Z}

O DITA Open Toolkit \(DITA-OT\) é um conjunto de ferramentas de código aberto baseadas em Java que fornecem processamento para mapas DITA e conteúdo de tópico. O Guia de AEM permite importar e usar facilmente plug-ins DITA-OT personalizados. Depois de importados, os Guias do AEM podem ser configurados para usar o plug-in DITA-OT personalizado para gerar saída em qualquer formato. No momento de gerar a saída, basta selecionar a opção DITA-OT e o Guia do AEM usa o plug-in DITA-OT personalizado para gerar a saída necessária.

Se você quiser processar parâmetros Ant ao publicar qualquer saída, o Guia AEM oferece uma maneira fácil de fazer isso. Você pode especificar quais parâmetros Ant você deseja usar e os mesmos serão processados pelo processo de publicação.

>[!NOTE]
>
> O AEM Guides é fornecido com o DITA-OT versão 3.3.2. No entanto, o AEM Guides é compatível com o DITA-OT versão 1.7 e superior. Para obter a lista completa das versões do DITA-OT, consulte [Versões DITA-OT](http://www.dita-ot.org/download).

>[!TIP]
>
> Consulte a *Configuração de perfis DITA-OT* e *Uso do DITA-OT personalizado* seções no Guia de práticas recomendadas para obter as práticas recomendadas sobre o uso de plug-ins DITA-OT personalizados.

## Usar plug-ins personalizados do DITA-OT {#id181NH1020L7}

Há duas maneiras de usar o plug-in DITA-OT personalizado para publicação. O primeiro método é carregar o plug-in DITA-OT personalizado no repositório AEM. O outro método é salvar o plug-in DITA-OT personalizado no servidor, criar um Perfil e fornecer a localização do plug-in DITA-OT personalizado no Perfil.

Por padrão, os Guias do AEM vêm com um Perfil pré-configurado que contém as configurações dos modelos padrão a serem usados para editar e publicar conteúdo. Você pode criar perfis personalizados com modelos personalizados que serão usados ao editar documentos e plug-ins DITA-OT personalizados para publicar conteúdo.

O pacote padrão DITA-OT disponível com Guias AEM vem com o processador Apache FOP XSL-FO, que não suporta a renderização de equações MathML. Se estiver usando equações MathML em seu conteúdo, verifique se você integrou um plug-in de mecanismo de renderização MathML para Apache FOP ou usou um processador XSL-FO diferente.

>[!IMPORTANT]
>
> Se você atualizou os Guias do AEM da versão 2.2 para 2.5.1 ou 2.6, todas as alterações feitas por meio do gerenciador de configurações serão automaticamente selecionadas e armazenadas no Perfil padrão.

Execute as seguintes etapas para fazer upload do plug-in DITA-OT personalizado no repositório AEM:

1. Faça logon no AEM e abra o modo CRXDE Lite.

1. Baixe o `DITA-OT.ZIP` arquivo.

   A localização do `DITA-OT.ZIP` o arquivo é `/libs/fmdita/dita_resources/DITA-OT.zip`.

   ![](assets/dita-ot-zip-in-crx.png)

1. Extraia o conteúdo do arquivo zip em seu servidor.

1. Use um mecanismo integrador de plug-ins DITA-OT para integrar a nova versão do DITA-OT ao plug-in DITA-OT personalizado.

   >[!NOTE]
   >
   > O separador de caminho de classe no arquivo ZIP do plug-in depende do sistema operacional, o que significa que, se o servidor estiver hospedado no Windows, o separador de caminho de classe será diferente do usado no Linux. Para obter mais informações sobre a integração manual de plug-ins, consulte a *Instalação manual de plug-ins* tópico na documentação DITA-OT.

1. Crie o arquivo ZIP novamente mantendo o mesmo nome \(`DITA-OT.ZIP`\) e a estrutura de pastas.

1. Carregue o arquivo ZIP atualizado de volta no repositório AEM.

   Verifique as seguintes verificações antes de fazer upload do arquivo ZIP:

   - Execute o integrador \(para instalar o plug-in personalizado\) em um sistema operacional Mac/Linux para evitar problemas com separadores de arquivos - como os sistemas operacionais Windows e Linux têm separadores de arquivos diferentes, o plug-in integrado no sistema operacional Mac/Linux é compatível com a configuração do Windows e do Linux.
   - Certifique-se de que o `DITA-OT.ZIP` O arquivo contém uma pasta chamada &quot;DITA-OT&quot; que tem todos os plug-ins e arquivos relevantes.
   - Verifique se `DITA-OT.ZIP` o arquivo criado é do tipo mime: &quot;nt:file&quot; \(corresponde ao tipo primário de arquivo ZIP quando carregado para AEM\). Use uma ferramenta WebDAV ou implantação de código para fazer upload desse arquivo ZIP para o caminho desejado no AEM. \(Não use o gerenciador de pacotes AEM para implantar este arquivo ZIP, pois este ZIP não é um pacote de conteúdo AEM, mas apenas um arquivo morto.\)
   >[!NOTE]
   >
   > É recomendável não substituir o pacote DITA-OT padrão. Você deve carregar seu pacote DITA-OT personalizado contendo seu plug-in em algum outro local na `apps` pasta.

1. Abra o Perfil DITA padrão para editá-lo e salve-o \(sem fazer atualizações\) para que as alterações entrem em vigor.


Execute as seguintes etapas para criar um novo perfil e configurá-lo para usar o plug-in DITA-OT personalizado armazenado no servidor:

1. Armazene o plug-in DITA-OT personalizado no servidor.

   >[!NOTE]
   >
   > A estrutura de pastas para armazenar o plug-in DITA-OT personalizado deve ser: `\*<parent-folder\>*\DITA-OT`.

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecionar **Guias** na lista de ferramentas.

1. Clique no link **Perfis DITA** bloco.

   >[!NOTE]
   >
   > As informações do Perfil padrão são exibidas na página Perfis. Se você atualizou os Guias do AEM da versão 2.2 para 2.5.1 ou 2.6, todas as alterações feitas por meio do gerenciador de configurações serão automaticamente selecionadas e armazenadas no Perfil padrão.

1. Você pode optar por editar o Perfil padrão, criar um novo perfil ou duplicar configurações do Perfil padrão para criar um novo perfil.

   >[!NOTE]
   >
   > Você pode atualizar o perfil Padrão, mas não pode excluí-lo. No entanto, todos os novos perfis que você criar poderão ser editados e excluídos.

1. Configure as seguintes propriedades para usar o plug-in DITA-OT personalizado:

   | Nome da propriedade | Descrição |
   |-------------|-----------|
   | **Propriedades do perfil** |
   | Nome do perfil | Forneça um nome exclusivo para este perfil. |
   | Reutilizar saída | *\(Opcional\)* Se o seu perfil for baseado em um perfil existente, selecione essa opção. Selecionar essa opção garante que os Guias do AEM não extraiam o conteúdo do pacote DITA-OT novamente e reutilizem o pacote DITA-OT existente. |
   | Caminho de extração de perfil | *\(Opcional\)* Especifique o caminho onde o DITA-OT é mantido no disco. Por padrão, o AEM Guides agrupa um pacote DITA-OT em seu repositório e ele é extraído no disco nesse caminho.<br>**Nota** Você pode definir esse caminho usando qualquer variável ou propriedade do sistema existente. Consulte a descrição do [Variáveis de ambiente DITA-OT](#id181NH0YN0AX) para obter mais informações. |
   | Caminho atribuído | \(*Opcional*\) Especifique o caminho no repositório de conteúdo ao qual esse perfil se aplica. Você pode especificar vários locais. |
   | **Propriedades de DITA-OT** |
   | Tempo limite do DITA-OT | \(*Opcional*\) Especifique o tempo \(em segundos\) pelo qual o AEM Guides aguarda uma resposta do plug-in DITA-OT. Se nenhuma resposta for recebida no tempo especificado, os Guias do AEM encerram a tarefa de publicação e a tarefa é sinalizada como com falha. Além disso, os logs de falha são disponibilizados no arquivo de log de geração de saída. <br>Valor padrão: 300 segundos \(5 minutos\) |
   | Argumentos de PDF DITA-OT | Especifique os argumentos de linha de comando que são processados pelo plug-in DITA-OT personalizado para gerar a saída de PDF. Para todos os perfis DITA-OT personalizados, especifique o seguinte argumento de linha de comando:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | Argumentos AEM do DITA-OT | \(*Opcional*\) Especifique os argumentos de linha de comando personalizados que são processados pelo plug-in DITA-OT personalizado para gerar a saída do site AEM. |
   | Caminhos da biblioteca DITA-OT | \(*Opcional*\) Especifique os caminhos de biblioteca adicionais do plug-in DITA-OT. |
   | DITA-OT Build XML | \(*Opcional*\) Especifique o caminho do script de construção personalizado Ant fornecido com o plug-in DITA-OT personalizado. Esse caminho é relativo ao diretório DITA-OT no sistema de arquivos. |
   | Pasta de script DITA-OT Ant | \(Opcional\) Especifique o caminho da pasta de script DITA-OT Ant. Esse caminho é relativo ao diretório DITA-OT no sistema de arquivos. |
   | Variáveis de ambiente DITA-OT | *\(Opcional\)* Especifique as variáveis de ambiente a serem transmitidas para o processo DITA-OT. Por padrão, o AEM Guides adiciona quatro variáveis - `ANT_OPTS`, `ANT_HOME`, `PATH`, e `CLASSPATH`. <br> Você pode reutilizar qualquer uma das variáveis ou propriedades existentes do ambiente do sistema para criar novas variáveis de ambiente. Por exemplo, se você tiver `JAVA_HOME` definida no sistema e que você deseje definir uma nova variável de ambiente chamada `JAVA_BIN` que é criado usando `JAVA_HOME`. Em seguida, adicione a definição de `JAVA_BIN` como:<br> `JAVA_BIN= ${JAVA_HOME}/bin` <br> **Nota** Você também pode usar as propriedades do sistema Java para construir variáveis de ambiente. Por exemplo, se o script de inicialização AEM definir uma propriedade do sistema Java `java.io.tmpdir` em um diretório temporário, você pode usar essa propriedade para definir uma nova variável como: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Importante** Para reutilizar qualquer variável ou propriedade do sistema existente, ela deve estar entre `${}`. |
   | Substituir saída DITA-OT | *\(Opcional\)* Se essa opção estiver selecionada, você poderá especificar o pacote DITA-OT disponível no sistema local para gerar saída usando o DITA-OT. Essa configuração é definida na ativação do ConfigManager. <br> Se quiser especificar o caminho de um pacote DITA-OT armazenado no servidor AEM, desmarque essa opção. |
   | Caminho do zip do AEM DITA-OT/ caminho do diretório local do DITA-OT | Dependendo da sua seleção na Saída do DITA-OT de Substituição, especifique o caminho completo onde o arquivo DITA-OT.zip personalizado é armazenado. Esse pode ser o caminho no repositório AEM ou sistema local. |
   | Caminho do plug-in DITA-OT | Caminho do plugin personalizado. Esse plug-in é integrado automaticamente ao pacote DITA-OT principal. |
   | Catálogos integrados | \(*Opcional*\) Caminho dos arquivos DTD e XSD catalog.xml personalizados no repositório AEM. Isso deve ser fornecido somente quando os catálogos estiverem ausentes no pacote DITA-OT. Esses catálogos são integrados automaticamente ao DITA-OT principal como um plug-in. |
   | Adicionar catálogo de ID do sistema | \(*Opcional*\) Selecione essa opção somente se houver entradas de ID pública ausentes no catálogo ou se os arquivos DITA usarem somente as IDs do sistema relativas ao caminho do servidor de onde foram carregados. |
   | Caminho temporário DITA-OT | *\(Opcional\)* Especifique um local temporário onde os arquivos DITA são copiados para processamento. Antes de o DITA-OT processar os arquivos, eles são copiados neste local temporário. Por padrão, o local de armazenamento temporário é: <br> **Nota** Você pode definir esse caminho usando qualquer variável ou propriedade do sistema existente. Consulte a descrição do [Variáveis de ambiente DITA-OT](#id181NH0YN0AX) para obter mais informações. |

   >[!NOTE]
   >
   >  O instalador dos Guias do AEM cria duas variáveis de ambiente que podem ser usadas para especificar o caminho dos arquivos de plug-in DITA-OT personalizados. Essas variáveis de ambiente são: DITAOT\_DIR, que contém o caminho do diretório DITA-OT no sistema de arquivos, e DITAMAP\_DIR, que contém o caminho onde o conteúdo do mapa DITA é extraído no sistema de arquivos.

1. Clique em **Concluído** para salvar o perfil.


>[!NOTE]
>
> É possível exportar o perfil DITA personalizado como um pacote e carregá-lo em outras instâncias do AEM Guides para economizar tempo. Para obter mais informações, consulte [Apêndice](appendix.md).

## Integrar especialização de DITA {#id211MB0E00XA}

A especialização DITA é o processo de criar novas estruturas DITA adicionando novos elementos ou removendo elementos existentes. Para criar um novo elemento DITA, você pode pegar um elemento DITA existente como base e modificá-lo de acordo com seus requisitos de criação. Basicamente, a especialização DITA permite criar modelos de informações personalizados que atendam aos requisitos de negócios, além de manter os benefícios da arquitetura DITA existente.

Você pode usar o recurso de Perfil para armazenar configurações de especialização DITA personalizadas. Essas configurações podem ser usadas no momento da criação e publicação de conteúdo DITA personalizado. Guias do AEM permitem usar o ID público e o ID do sistema nos DTDs/XSDs personalizados.

>[!NOTE]
>
> O Editor da Web de Guias de AEM não tem suporte para XSDs.

Execute as seguintes etapas para criar um novo perfil e configurá-lo para usar DTDs e Guias de AEM XSDs especializados:

1. Crie uma pasta de especialização no computador local que contenha DTDs e XSDs especializados.

1. Especifique os detalhes de DTD na variável `catalog.xml` arquivo que também deve ser incluído na pasta de especialização.

   >[!NOTE]
   >
   > No caso de DITA 1.3, o local padrão para DTD `catalog.xml` no repositório AEM é: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Especifique os detalhes de XSD na `catalog.xml` arquivo que também deve ser incluído na pasta de especialização.

   >[!NOTE]
   >
   > No caso do DITA 1.3, o local padrão do arquivo catalog.xml XSD no repositório AEM é: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Faça upload da pasta para o seguinte local:

   `/libs/fmdita/dita_resources`

1. Clique no link Adobe Experience Manager na parte superior e escolha **Ferramentas**.

1. Selecionar **Guias** na lista de ferramentas.

1. Clique no link **Perfis DITA** bloco.

   >[!NOTE]
   >
   > As informações do Perfil padrão são exibidas na página Perfis. Se você atualizou os Guias do AEM da versão 2.2 para 2.5.1 ou 2.6, todas as alterações feitas por meio do gerenciador de configurações serão automaticamente selecionadas e armazenadas no Perfil padrão.

1. Você pode optar por editar o Perfil padrão, criar um novo perfil ou duplicar configurações do Perfil padrão para criar um novo perfil.

   >[!NOTE]
   >
   > Não é possível excluir o Perfil padrão. No entanto, todos os novos perfis que você criar poderão ser editados e excluídos.

1. No **Esquema** \> **Catálogo** configurações, especifique o caminho da DTD e do XSD personalizados `catalog.xml` arquivos no repositório AEM.

1. Selecione o **Adicionar catálogo de ID do sistema** opção.

   >[!NOTE]
   >
   > Selecione essa opção somente se houver entradas de ID pública ausentes no catálogo ou se os arquivos DITA usarem somente as IDs do sistema relativas ao caminho do arquivo local de onde são carregados.

   Para obter mais informações sobre outras propriedades na página Perfis, consulte a tabela de propriedades em [Etapa 6](#id17A9F0D075Z) do [Usar plug-ins personalizados do DITA-OT](#id181NH1020L7) seção.

1. Clique em **Concluído** para salvar o perfil.


>[!NOTE]
>
> É possível exportar o perfil DITA personalizado como um pacote e carregá-lo em outras instâncias do AEM Guides para economizar tempo. Para obter mais informações, consulte [Apêndice.md](appendix.md).
