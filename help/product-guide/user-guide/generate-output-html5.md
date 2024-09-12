---
title: Usar HTML5
description: Saiba como criar uma predefinição HTML5 no editor da Web e no painel de mapa. Configure a predefinição de saída HTML5 no AEM Guides.
exl-id: b54bf3a0-7a13-41a0-ae72-cdf2caf8d974
feature: Publishing
role: User
source-git-commit: c2a97a134b9e7367689778a2a1e1f4bbead9860b
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 1%

---

# HTML 5 {#id205BE700XO1}

A saída do HTML 5 é gerada em uma hierarquia de pasta simples. Isso implica que a estrutura de pastas usada pelo conteúdo no repositório não é replicada na saída HTML5. O conteúdo inteiro é publicado no formato de saída HTML5 e salvo em uma única pasta. Os nomes dos arquivos também são substituídos pelos UUIDs dos arquivos na saída gerada. O único arquivo que não tem um nome de arquivo baseado em UUID é o arquivo index.html.

É possível criar a predefinição de HTML de duas maneiras:

**No Editor da Web:** no painel Repositório, abra o arquivo de mapa DITA no Modo de Exibição de Mapa e, na guia Saída, selecione o ícone + para criar uma predefinição de saída e, em seguida, selecione HTML5 no menu suspenso de tipo na caixa de diálogo Adicionar predefinição.

>[!NOTE]
>
> Você pode escolher o método para gerar o HTML5 usando o DITA-OT ou FMPS \(se o administrador do sistema o tiver configurado\).

No editor da Web, as configurações foram organizadas em guias Gerais e Avançadas:

**Geral**

A guia **Geral** contém as seguintes configurações:

- Caminho de saída
- Argumentos de linha de comando DITA-OT
- Nome do arquivo
- Aplicar Condições Usando \(Se as condições forem definidas para um mapa\)
- Usar Linha de Base \(Se uma linha de base for criada para um mapa\)
- Fluxo de trabalho de pós-geração

**Avançado**

A guia Advanced contém as seguintes configurações:

- Nome da transformação
- Reter arquivos temporários
- Propriedades do arquivo

Para obter detalhes, consulte [configuração de HTML](#id231KJA00REJ).

**No painel de mapa**

Para abrir predefinições de saída para o PDF, clique em um arquivo de mapa DITA na interface do usuário do Assets, em seguida, clique em Predefinições de saída e, em seguida, clique na opção HTML 5. No painel Mapa, clique em **Editar** na parte superior para atualizar as várias configurações e clique em **Salvar**.

**configuração de HTML**

As seguintes opções estão disponíveis para a saída de HTML5:

| opções de HTML 5 | Descrição |
| --- | --- |
| Tipo de saída | O tipo de saída que você deseja gerar. Para gerar saída de HTML, escolha a opção HTML 5. |
| Nome de configuração | Dê um nome descritivo para as configurações de saída de HTML5 que você está criando. Por exemplo, você pode especificar _saída de clientes internos_ ou _saída de usuários finais_. |
| Argumentos de linha de comando DITA-OT | Especifique os argumentos adicionais que você deseja que o DITA-OT processe ao gerar saída. Para obter detalhes sobre os argumentos de linha de comando com suporte no DITA-OT, consulte a [documentação do DITA-OT](https://www.dita-ot.org/). |
| Gerar responsivo usando | Selecione DITA-OT para gerar a saída do HTML5. |
| Aplicar condições usando | Selecione uma das seguintes opções:<br><br>* **Nenhuma aplicada**: selecione esta opção se não quiser aplicar nenhuma condição na saída publicada.<br>* **Arquivo DITAVal**: selecione o(s) arquivo(s) DITAVal para gerar conteúdo personalizado. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para ver o caminho no repositório AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você tiver selecionado qualquer outro tipo de arquivo. O FrameMaker Publishing Server não é compatível com vários arquivos DITAVAL.<br>* **Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. A opção estará visível se você tiver adicionado uma condição na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, consulte [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>Você pode selecionar vários arquivos DITAVAL usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVAL são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para ver o caminho no repositório AEM onde o arquivo está armazenado. Você só pode salvar arquivos DITAVAL. Um erro será exibido se você tiver selecionado qualquer outro arquivo.<br><br>**Observação**: o FrameMaker Publishing Server não oferece suporte a vários arquivos DITAVAL. |
| Nome da transformação | Especifique o tipo de saída que deseja gerar. Isso é necessário se você quiser gerar saída usando seu próprio plug-in personalizado, que está integrado ao plug-in DITA-OT. Por exemplo, se você deseja gerar saída XHTML, especifique `xhtml`. Para obter uma lista de transformações disponíveis no DITA-OT, consulte [Transformações do DITA-OT (formatos de saída)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) no Guia do Usuário do OASIS DITA-OT. |
| Nome do arquivo | Especifique o nome do arquivo com o qual deseja salvar a saída de HTML 5.<br><br>**Nota**:Se você não fornecer um nome de arquivo, o título do mapa DITA será usado para gerar o nome final do arquivo de saída HTML5. Se o mapa não tiver um título, o nome do arquivo do mapa DITA será usado para nomear a saída final em HTML5. O nome do arquivo é limpo usando as regras configuradas no sistema para lidar com qualquer caractere inválido. |
| Executar fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída.<br><br>**Observação**:Para obter mais informações sobre como criar um fluxo de trabalho personalizado de geração de pós-saída, consulte _Personalizar fluxo de trabalho de geração de pós-saída_ em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service. |
| Caminho de destino | O caminho dentro do repositório AEM onde a saída de HTML5 é armazenada. |
| Reter arquivos temporários | Selecione essa opção para manter os arquivos temporários gerados pelo DITA-OT. Se ocorrerem erros durante a geração de saída pelo DITA-OT, selecione essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar erros de geração de saída.<br> <br> Depois de gerar a saída, selecione o ícone **Baixar arquivos temporários** ![baixar arquivos temporários](images/download-temp-files-icon.png) para baixar a pasta ZIP que contém os arquivos temporários. <br><br> **Observação**: se as propriedades do arquivo forem adicionadas durante a geração, os arquivos temporários de saída também incluirão um arquivo *metadata.xml* contendo essas propriedades. |
| Nivelar hierarquia de arquivos | Selecione a opção para gerar a saída de HTML 5 em uma hierarquia de pastas simples. O conteúdo inteiro é publicado no formato de saída HTML5 em uma hierarquia de arquivos simples e salvo em uma única pasta. <br> Se você desmarcar esta opção, a saída será gerada em uma hierarquia de pastas aninhada e toda a estrutura de pastas será replicada. |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br>Consulte [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Propriedades do arquivo | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa aparecem no campo **Propriedades do arquivo**. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>**Observação**: você também pode passar os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Passe os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tópico pai:**[ Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)
