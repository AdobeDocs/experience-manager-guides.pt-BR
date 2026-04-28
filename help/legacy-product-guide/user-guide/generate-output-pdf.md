---
title: Gerar PDF
description: Saiba como criar uma predefinição do PDF no editor da Web e no painel de mapa. Configure a predefinição de saída do PDF no AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: fae55104-fef6-4994-911a-139598332b96
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 1%

---

# PDF {#id205BE600HAH}

É possível criar a predefinição do PDF de duas maneiras:

**No Editor da Web:** no painel Repositório, abra o arquivo de mapa DITA no Modo de Exibição de Mapa e, na guia Saída, selecione o ícone + para criar uma predefinição de saída e selecione PDF no menu suspenso de tipo na caixa de diálogo Adicionar predefinição.

>[!NOTE]
>
> Você pode escolher o método para gerar o PDF usando DITA-OT, Native PDF ou FMPS \(se o administrador do sistema o tiver configurado\).

No editor da Web, as configurações foram organizadas em guias Gerais e Avançadas:

**Geral**

A guia **Geral** contém as seguintes configurações:

- Caminho de saída
- Argumentos de linha de comando DITA-OT
- Nome da transformação
- Nome de arquivo do PDF
- Aplicar Condições Usando \(Se as condições forem definidas para um mapa\)
- Usar Linha de Base \(Se uma linha de base for criada para um mapa\)
- Fluxo de trabalho de pós-geração

**Avançado**

A guia Advanced contém as seguintes configurações:

- Ativar controle de versão
- Reter arquivos temporários

Para obter detalhes, consulte [configuração do PDF](#id231KIM004X1).

**No painel de mapa**

Para abrir predefinições de saída para o PDF, clique em um arquivo de mapa DITA na interface do usuário do Assets, em seguida, clique em Predefinições de saída e, em seguida, clique na opção PDF. No painel Mapa, clique em **Editar** na parte superior para atualizar as várias configurações e clique em **Salvar**.

**Configuração do PDF**

As seguintes opções estão disponíveis para a Saída do PDF:

| Opções do PDF | Descrição |
| --- | --- |
| Tipo de saída | The type of output you want to generate. To generate PDF output, choose the PDF option. |
| Nome de configuração | Give a descriptive name for the PDF output settings you are creating. For example, you can specify _Internal customers output_ or _end-users output_. |
| Argumentos de linha de comando DITA-OT | Specify the additional arguments that you want DITA-OT to process while generating output. For details about the command-line arguments supported in DITA-OT, see [DITA-OT documentation](https://www.dita-ot.org/). |
| Apply conditions using | Select one of the following options:<br><br>* **None applied**: Select this option if you do not want to apply any condition on the published output.<br>* **DITAVal file**: Select DITAVal file(s) to generate personalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to see the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you have selected any other file type. FrameMaker Publishing Server doesn&#39;t support multiple DITAVAL files.<br>* **Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. The option is visible if you have added a condition present in the Condition Presets tab of the DITA map console. To know more about condition preset, see [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Generate PDF Using | Select DITA-OT to generate the PDF. |
| Run Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow.<br><br>**Note**: For more information about creating a custom post-output generation workflow, see Customize post-output generation workflow in Install and configure Adobe Experience Manager Guides as a Cloud Service. |
| Nome da transformação | Especifique o tipo de saída que deseja gerar. Isso é necessário se você quiser gerar saída usando seu próprio plug-in personalizado, que está integrado ao plug-in DITA-OT. Por exemplo, se você deseja gerar saída XHTML, especifique `xhtml`. Para obter uma lista de transformações disponíveis no DITA-OT, consulte [Transformações do DITA-OT (formatos de saída)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) no Guia do Usuário do OASIS DITA-OT. |
| Nome do arquivo | Especifique o nome de arquivo com o qual deseja salvar o PDF.<br><br>Você também pode usar variáveis ao definir o Nome de Arquivo do PDF. Para obter mais detalhes sobre o uso de variáveis, consulte [Usar variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Observação**: se você não fornecer um nome de arquivo, o título do mapa DITA será usado para gerar o nome de arquivo final do PDF. Se o mapa não tiver um título, o nome do arquivo do mapa DITA usado para nomear será o PDF final. O nome do arquivo é limpo usando as regras configuradas no sistema para lidar com qualquer caractere inválido. |
| Caminho de destino | O caminho no repositório do AEM onde o PDF está armazenado.<br><br>Você também pode usar variáveis ao definir o Caminho de Destino. Para obter mais detalhes sobre o uso de variáveis, consulte [Usar variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Reter arquivos temporários | Selecione essa opção para manter os arquivos temporários gerados pelo DITA-OT. Se ocorrerem erros durante a geração de saída pelo DITA-OT, selecione essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar erros de geração de saída.<br> <br> Depois de gerar a saída, selecione o ícone **Baixar arquivos temporários** ![baixar arquivos temporários](images/download-temp-files-icon.png) para baixar a pasta ZIP que contém os arquivos temporários. <br><br> **Observação**: se as propriedades do arquivo forem adicionadas durante a geração, os arquivos temporários de saída também incluirão um arquivo *metadata.xml* contendo essas propriedades. |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Consulte [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Propriedades do arquivo | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa aparecem no campo **Propriedades do arquivo**. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>Observação: você também pode passar os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Passe os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tópico pai:**[ Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
