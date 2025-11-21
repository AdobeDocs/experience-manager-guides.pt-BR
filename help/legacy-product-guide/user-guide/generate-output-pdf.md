---
title: Gerar PDF
description: Saiba como criar uma predefinição do PDF no editor da Web e no painel de mapa. Configure a predefinição de saída do PDF no AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: fae55104-fef6-4994-911a-139598332b96
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1032'
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
| Tipo de saída | O tipo de saída que você deseja gerar. Para gerar a saída do PDF, escolha a opção PDF. |
| Nome de configuração | Dê um nome descritivo para as configurações de saída do PDF que você está criando. Por exemplo, você pode especificar _saída de clientes internos_ ou _saída de usuários finais_. |
| Argumentos de linha de comando DITA-OT | Especifique os argumentos adicionais que você deseja que o DITA-OT processe ao gerar saída. Para obter detalhes sobre os argumentos de linha de comando com suporte no DITA-OT, consulte a [documentação do DITA-OT](https://www.dita-ot.org/). |
| Aplicar condições usando | Selecione uma das seguintes opções:<br><br>* **Nenhuma aplicada**: selecione esta opção se não quiser aplicar nenhuma condição na saída publicada.<br>* **Arquivo DITAVal**: selecione o(s) arquivo(s) DITAVal para gerar conteúdo personalizado. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para ver o caminho no repositório do AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você tiver selecionado qualquer outro tipo de arquivo. O FrameMaker Publishing Server não é compatível com vários arquivos DITAVAL.<br>* **Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. A opção estará visível se você tiver adicionado uma condição na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, consulte [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Gerar o PDF usando | Selecione DITA-OT para gerar o PDF. |
| Executar fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída.<br><br>**Observação**: para obter mais informações sobre como criar um fluxo de trabalho personalizado de geração de pós-saída, consulte Personalizar fluxo de trabalho de geração de pós-saída em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service. |
| Nome da transformação | Especifique o tipo de saída que deseja gerar. Isso é necessário se você quiser gerar saída usando seu próprio plug-in personalizado, que está integrado ao plug-in DITA-OT. Por exemplo, se você deseja gerar saída XHTML, especifique `xhtml`. Para obter uma lista de transformações disponíveis no DITA-OT, consulte [Transformações do DITA-OT (formatos de saída)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) no Guia do Usuário do OASIS DITA-OT. |
| Nome do arquivo | Especifique o nome do arquivo com o qual deseja salvar a PDF.<br><br>Você também pode usar variáveis ao definir o Nome do Arquivo do PDF. Para obter mais detalhes sobre o uso de variáveis, consulte [Usar variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Observação**: se você não fornecer um nome de arquivo, o título do mapa DITA será usado para gerar o nome de arquivo final do PDF. Se o mapa não tiver um título, o nome do arquivo do mapa DITA usado para nomear será o PDF final. O nome do arquivo é limpo usando as regras configuradas no sistema para lidar com qualquer caractere inválido. |
| Caminho de destino | O caminho no repositório do AEM onde o PDF está armazenado.<br><br>Você também pode usar variáveis ao definir o Caminho de Destino. Para obter mais detalhes sobre o uso de variáveis, consulte [Usar variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Reter arquivos temporários | Selecione essa opção para manter os arquivos temporários gerados pelo DITA-OT. Se ocorrerem erros durante a geração de saída pelo DITA-OT, selecione essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar erros de geração de saída.<br> <br> Depois de gerar a saída, selecione o ícone **Baixar arquivos temporários** ![baixar arquivos temporários](images/download-temp-files-icon.png) para baixar a pasta ZIP que contém os arquivos temporários. <br><br> **Observação**: se as propriedades do arquivo forem adicionadas durante a geração, os arquivos temporários de saída também incluirão um arquivo *metadata.xml* contendo essas propriedades. |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Consulte [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Propriedades do arquivo | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa aparecem no campo **Propriedades do arquivo**. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>Observação: você também pode passar os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Passe os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tópico pai:**&#x200B;[&#x200B; Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
