---
title: JSON
description: Saiba como criar uma predefinição JSON no editor da Web e no painel de mapa. Configure a predefinição de saída JSON no AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: dbc082e9-e75e-414d-a1d1-41f919b345af
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Você pode criar a predefinição JSON no Editor da Web:

No painel Repositório, abra o arquivo de mapa DITA na Exibição de mapa e, na guia Saída, selecione o ícone + para criar uma predefinição de saída e selecione JSON no menu suspenso de tipo na caixa de diálogo Adicionar predefinição.

No editor da Web, as seguintes configurações foram organizadas na guia **Geral**:

- Caminho de saída
- Arquivo de índice
- Aplicar Condições Usando \(Se as condições forem definidas para um mapa\)
- Usar Linha de Base \(Se uma linha de base for criada para um mapa\)
- Reter arquivos temporários
- Propriedades a serem Propagadas na Saída
- Fluxo de trabalho de pós-geração

Para obter detalhes, consulte [Configuração JSON](#id231KJA00REJ).


**Configuração JSON**

As seguintes opções estão disponíveis para a predefinição JSON:

>[!NOTE]
>
> Você também pode editar o arquivo JSON no Editor da Web.

| Opções de JSON | Descrição |
| --- | --- |
| Caminho de saída | O caminho no repositório do AEM onde a saída JSON é armazenada. |
| Arquivo de índice | Você pode dar um nome para o arquivo de índice que está criando para a saída JSON. Por padrão, ele escolhe o nome de arquivo do mapa DITA e adiciona um sufixo (como `map_filename_index.json`).<br><br>Você também pode usar variáveis ao definir o Arquivo de Índice. Para obter mais detalhes sobre o uso de variáveis, consulte [Usar variáveis para definir as opções Caminho de Destino, Nome do Site ou Nome do Arquivo](generate-output-use-variables.md#id18BUG70K05Z). |
| Aplicar condições usando | Selecione uma das seguintes opções:<br><br>* **Nenhuma aplicada**: selecione esta opção se não quiser aplicar nenhuma condição na saída publicada.<br>* **Arquivo DITAVAL**: selecione o(s) arquivo(s) DITAVAL para gerar conteúdo personalizado. Você pode selecionar vários arquivos DITAVAL usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVAL são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVAL for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para ver o caminho no repositório do AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVAL e um erro será exibido se você tiver selecionado qualquer outro tipo de arquivo.<br>* **Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. A opção estará visível se você tiver adicionado uma condição na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, consulte [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Consulte [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Reter arquivos temporários | Selecione essa opção para manter os arquivos temporários gerados pelo DITA-OT. Se ocorrerem erros durante a geração de saída pelo DITA-OT, selecione essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar erros de geração de saída.<br> <br> Depois de gerar a saída, selecione o ícone **Baixar arquivos temporários** ![baixar arquivos temporários](images/download-temp-files-icon.png) para baixar a pasta ZIP que contém os arquivos temporários. <br><br> **Observação**: se as propriedades do arquivo forem adicionadas durante a geração, os arquivos temporários de saída também incluirão um arquivo *metadata.xml* contendo essas propriedades. |
| Propriedades a serem Propagadas na Saída | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa estão listadas abaixo do campo Propriedades.<br><br>**Observação**: você também pode definir propriedades personalizadas e transmitir os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Trabalhe com metadados](metadata-dita.md#id21BJ00QD0XA). |
| Fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída.<br><br>**Observação**: para obter mais informações sobre como criar um fluxo de trabalho personalizado de geração pós-saída, consulte _Personalizar fluxo de trabalho de geração pós-saída_ no guia Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service. |

**Tópico pai:**&#x200B;[ Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
