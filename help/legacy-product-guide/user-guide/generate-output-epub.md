---
title: Predefinição do ePub
description: Saiba como criar uma predefinição do EPUB no painel de mapa. Configure a predefinição de saída do EPUB no AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 1d914a5f-df1f-45eb-86ac-72485fdf07fe
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 1%

---

# EPUB {#id205BED020YT}

É possível criar a predefinição do EPUB no painel de mapa.

>[!NOTE]
>
> Você pode escolher o método para gerar o HTML5 usando o DITA-OT ou FMPS \(se o administrador do sistema o tiver configurado\).

Para abrir predefinições de saída para o EPUB, clique em um arquivo de mapa DITA, em seguida, clique em Predefinições de saída e, em seguida, clique na opção EPUB. As seguintes opções estão disponíveis para a Saída do EPUB:

| Opções do ePub | Descrição |
| --- | --- |
| Tipo de saída | O tipo de saída que você deseja gerar. Para gerar a saída do EPUB, escolha a opção EPUB. |
| Nome de configuração | Dê um nome descritivo para as configurações de saída do EPUB que você está criando. Por exemplo, você pode especificar _saída de clientes internos_ ou _saída de usuários finais_. |
| Argumentos de linha de comando DITA-OT | Especifique os argumentos adicionais que você deseja que o DITA-OT processe ao gerar saída. Para obter detalhes sobre os argumentos de linha de comando com suporte no DITA-OT, consulte a [documentação do DITA-OT](https://www.dita-ot.org/). |
| Gerar o EPUB usando | Selecione DITA-OT para gerar a saída do EPUB. |
| Aplicar condições usando | Selecione uma das seguintes opções:<br><br>* **Nenhuma aplicada**: selecione esta opção se não quiser aplicar nenhuma condição na saída publicada.<br>* **Arquivo DITAVal**: selecione o(s) arquivo(s) DITAVal para gerar conteúdo personalizado. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para ver o caminho no repositório do AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você tiver selecionado qualquer outro tipo de arquivo. O FrameMaker Publishing Server não é compatível com vários arquivos DITAVAL.<br>* **Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. A opção estará visível se você tiver adicionado uma condição na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, consulte [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Caminho de destino | O caminho no repositório do AEM onde a saída do EPUB está armazenada. |
| Nome do arquivo | Especifique o nome do arquivo com o qual deseja salvar a saída do EPUB.<br><br>**Observação**: se você não fornecer um nome de arquivo, o título do mapa DITA será usado para gerar o nome final do arquivo de saída do EPUB. Se o mapa não tiver um título, o nome do arquivo do mapa DITA usado para nomear será a saída final do EPUB. O nome do arquivo é limpo usando as regras configuradas no sistema para lidar com qualquer caractere inválido. |
| Nome da transformação | Especifique o tipo de saída que deseja gerar. Isso é necessário se você quiser gerar saída usando seu próprio plug-in personalizado, que está integrado ao plug-in DITA-OT. Por exemplo, se você deseja gerar saída XHTML, especifique `xhtml`. Para obter uma lista de transformações disponíveis no DITA-OT, consulte [Transformações do DITA-OT (formatos de saída)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) no Guia do Usuário do OASIS DITA-OT. |
| Limpar arquivos temporários DITA-OT | Selecione esta opção para limpar os arquivos temporários gerados pelo DITA-OT. O local onde o DITA-OT armazena arquivos temporários pode ser encontrado no log de geração de saída.<br><br>Se ocorrerem erros durante a geração de saída pelo DITA-OT, você poderá desmarcar essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar problemas de erros de geração de saída. |
| Executar fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída.<br><br>**Observação**: para obter mais informações sobre como criar um fluxo de trabalho personalizado de geração de pós-saída, consulte _Personalizar fluxo de trabalho de geração de pós-saída_ em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service. |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Consulte [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Propriedades | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa estão listadas abaixo do campo Propriedades e são removidas da lista suspensa. Depois de definidas, essas propriedades também são copiadas para os tópicos no mapa.<br><br>**Observação**: você também pode passar os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Passe os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tópico pai:**&#x200B;[ Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
