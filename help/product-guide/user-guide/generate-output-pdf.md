---
title: Gerar PDF
description: Saiba como criar uma predefinição de PDF no editor da Web e no painel de mapa. Configurar a predefinição de saída PDF nos Guias AEM.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# PDF {#id205BE600HAH}

É possível criar a predefinição de PDF de duas maneiras:

**No Editor da Web:** No painel Repositório, abra o arquivo de mapa DITA na Exibição de mapa e, na guia Saída, selecione o ícone + para criar uma predefinição de saída e selecione PDF no menu suspenso de tipo na caixa de diálogo Adicionar predefinição.

>[!NOTE]
>
> Você pode escolher o método para gerar o PDF usando DITA-OT, PDF nativo ou FMPS \(se o administrador do sistema o tiver configurado\).

No editor da Web, as configurações foram organizadas em guias Gerais e Avançadas:

**Geral**

A variável **Geral** contém as seguintes configurações:

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
- Limpar arquivos temporários DITA-OT

Para obter detalhes, consulte [configuração de PDF](#id231KIM004X1).

**No painel do mapa**

Para abrir as predefinições de saída para o PDF, clique em um arquivo de mapa DITA na interface do usuário do Assets, clique em Predefinições de saída e, em seguida, clique na opção PDF. No painel do Mapa, clique em **Editar** na parte superior para atualizar as várias configurações e clique em **Salvar**.

**configuração de PDF**

As seguintes opções estão disponíveis para a saída de PDF:

| opções de PDF | Descrição |
| --- | --- |
| Tipo de saída | O tipo de saída que você deseja gerar. Para gerar saída de PDF, escolha a opção PDF. |
| Nome da configuração | Dê um nome descritivo para as configurações de saída de PDF que você está criando. Por exemplo, você pode especificar _Saída interna de clientes_ ou _saída de usuários finais_. |
| Argumentos de linha de comando DITA-OT | Especifique os argumentos adicionais que você deseja que o DITA-OT processe ao gerar saída. Para obter detalhes sobre os argumentos de linha de comando compatíveis com DITA-OT, consulte [Documentação do DITA-OT](https://www.dita-ot.org/). |
| Aplicar condições usando | Selecione uma das seguintes opções:<br><br>* **Nenhum aplicado**: selecione essa opção se não quiser aplicar nenhuma condição à saída publicada.<br>* **Arquivo DITAVal**: selecione os arquivos DITAVal para gerar conteúdo personalizado. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para ver o caminho no repositório AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você tiver selecionado qualquer outro tipo de arquivo. O FrameMaker Publishing Server não é compatível com vários arquivos DITAVAL.<br>* **Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. A opção estará visível se você tiver adicionado uma condição na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, consulte [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Gerar PDF usando | Selecione DITA-OT para gerar o PDF. |
| Executar fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída.<br><br>**Nota**: para obter mais informações sobre como criar um fluxo de trabalho personalizado de geração de pós-saída, consulte Personalizar fluxo de trabalho de geração de pós-saída em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service. |
| Nome da transformação | Especifique o tipo de saída que deseja gerar. Isso é necessário se você quiser gerar saída usando seu próprio plug-in personalizado, que está integrado ao plug-in DITA-OT. Por exemplo, se você deseja gerar uma saída XHTML, especifique `xhtml`. Para obter uma lista de transformações disponíveis no DITA-OT, consulte [Transformações DITA-OT (formatos de saída)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) no Guia do usuário do OASIS DITA-OT. |
| Nome do arquivo | Especifique o nome do arquivo com o qual deseja salvar o PDF.<br><br>Você também pode usar variáveis ao configurar o Nome do arquivo de PDF. Para obter mais detalhes sobre o uso de variáveis, consulte [Use variáveis para definir as opções Caminho de destino, Nome do site ou Nome do arquivo](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Nota**: Se você não fornecer um nome de arquivo, o título do mapa DITA será usado para gerar o nome final do arquivo de PDF. Se o mapa não tiver um título, o nome do arquivo do mapa DITA será usado para nomear o PDF final. O nome do arquivo é limpo usando as regras configuradas no sistema para lidar com qualquer caractere inválido. |
| Caminho de destino | O caminho no repositório AEM onde o PDF está armazenado.<br><br>Você também pode usar variáveis ao definir o Caminho de destino. Para obter mais detalhes sobre o uso de variáveis, consulte [Use variáveis para definir as opções Caminho de destino, Nome do site ou Nome do arquivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Limpar arquivos temporários DITA-OT | Selecione esta opção para limpar os arquivos temporários gerados pelo DITA-OT. O local onde o DITA-OT armazena arquivos temporários pode ser encontrado no log de geração de saída.<br><br>Se ocorrerem erros durante a geração de saída por meio do DITA-OT, é possível desmarcar essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar problemas de erros de geração de saída. |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Consulte [Trabalhar com linha de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Propriedades | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa são exibidas na **Propriedades** campo. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>Observação: você também pode transmitir os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, consulte [Transmita os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tópico pai:**[ Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
