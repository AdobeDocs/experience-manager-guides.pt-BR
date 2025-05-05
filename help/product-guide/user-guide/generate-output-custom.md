---
title: Personalizado
description: Saiba como criar uma predefinição personalizada no console de mapas e no painel de mapas. Configure uma predefinição de saída personalizada no Experience Manager Guides.
exl-id: 1bb14411-ec94-4960-92ba-3b2ff7a29932
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 0%

---

# Personalizado {#id205BEF00PX0}

As predefinições de saída personalizadas estão disponíveis para plug-ins DITA-OT personalizados. É possível criar uma predefinição de saída DITA-OT personalizada para publicar a saída usando o plug-in DITA-OT personalizado.

É possível criar a predefinição Personalizada de duas maneiras:

- [Criar a predefinição Personalizada no console Mapa](#create-the-custom-preset-from-the-map-console)
- [Criar a predefinição personalizada a partir do painel de Mapa](#create-the-custom-preset-from-the-map-dashboard)

## Criar a predefinição Personalizada no console Mapa

Execute as seguintes etapas para criar a predefinição Personalizada no console Mapa:

1. [Abra um arquivo de mapa DITA no Console de mapa](./open-files-map-console.md).

   Você também pode acessar o arquivo de mapa no widget **Arquivos recentes** na [seção Visão geral](./intro-home-page.md#overview). O arquivo de mapa selecionado seria aberto no console Mapa.
1. Na guia **Predefinições de saída**, selecione o ícone + para criar uma predefinição de saída.
1. Selecione **Personalizado** na lista suspensa Tipo na caixa de diálogo **Nova predefinição de saída**.
1. No campo **Nome**, forneça um nome para esta predefinição.
1. Selecione a opção **Adicionar ao perfil de pasta atual** para criar uma predefinição de saída no perfil de pasta atual. O ![ícone de perfil de pasta](images/global-preset-icon.svg) indica uma predefinição de nível de perfil de pasta.

   Saiba mais sobre [Gerenciar predefinições de saída de perfil Global e de Pasta](./web-editor-manage-output-presets.md).

1. Selecione **Adicionar**.

   A predefinição Personalizada é criada.

   ![](images/custom-preset-dialog.png){width="300" align="left"}

No console Mapa, as opções de configuração predefinidas estão organizadas nas guias **Geral** e **Avançado**.

![](images/custom-preset-config.png){align="left"}

A guia **Geral** contém as seguintes opções de configuração:

- Argumentos da linha de comando DITA-OT
- Nome da transformação
- Nome do arquivo
- Caminho de saída
- Filtragem condicional \(Se as condições forem definidas para um mapa\)
- Usar linha de base \(Se uma linha de base for criada para um mapa\)
- Fluxo de trabalho de pós-geração

**Avançado**

A guia Advanced contém as seguintes opções de configuração:

- Reter arquivos temporários
- Propriedades do arquivo

Para obter detalhes sobre as opções de configuração de predefinição, consulte a seção [Configuração de predefinição personalizada](#custom-preset-configuration).


## Criar a predefinição Personalizada no painel Mapa

Execute as seguintes etapas para criar a predefinição Personalizada no painel Mapa:

1. Na interface do usuário do Assets, navegue até o mapa DITA e selecione-o para abri-lo no painel Mapa.
1. Verifique se a guia **Predefinições de Saída** está selecionada.
1. Selecione **Criar** na barra de ferramentas.

   Um novo formulário de criação de predefinição de saída é exibido.

   ![](images/new-output-preset-map-dashboard.png){width="650" align="left"}

1. Insira os detalhes de configuração necessários para a predefinição personalizada.
1. Selecione **Concluído** para salvar as configurações predefinidas.

Para obter detalhes sobre as opções de configuração de predefinição, consulte a seção [Configuração de predefinição personalizada](#custom-preset-configuration).

## Configuração de predefinição personalizada

As opções de configuração variam um pouco, dependendo se você está configurando a predefinição no console Mapa ou no painel Mapa. Algumas opções se aplicam somente ao painel Mapa, enquanto outras se aplicam a ambos.

Nos casos em que a mesma configuração tem dois rótulos de campo diferentes, um **/** os separa na tabela abaixo. O primeiro representa o rótulo no console Mapa e o segundo representa o rótulo no painel Mapa.

Por exemplo, **Caminho de saída/Caminho de destino** - Aqui, **Caminho de saída** é o rótulo usado no console de Mapa, enquanto **Caminho de destino** é o rótulo usado no painel de Mapa para a mesma configuração.

| Opções de saída personalizadas | Descrição |
| --- | --- |
| Tipo de Saída (*Aplicável somente ao painel do Mapa*) | O tipo de saída que você deseja gerar. Para gerar saída usando o plug-in DITA-OT personalizado, escolha a opção Personalizado. |
| Nome da Configuração (*Aplicável somente ao painel de Mapa*) | Dê um nome descritivo para as configurações de saída que você está criando. Por exemplo, você pode especificar _saída de clientes internos_ ou _saída de usuários finais_. |
| Argumentos da linha de comando DITA-OT | Especifique os argumentos adicionais que você deseja que o DITA-OT processe ao gerar saída. Para obter detalhes sobre os argumentos de linha de comando com suporte no DITA-OT, exiba a [documentação do DITA-OT](https://www.dita-ot.org/). |
| Nome da transformação | Especifique o tipo de saída que deseja gerar. Isso é necessário se você quiser gerar saída usando seu próprio plug-in personalizado, que está integrado ao plug-in DITA-OT. Por exemplo, se você deseja gerar saída XHTML, especifique `xhtml`. Para obter uma lista de transformações disponíveis no DITA-OT, exiba [transformações do DITA-OT (formatos de saída)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) no Guia do Usuário do OASIS DITA-OT. |
| Nome do arquivo | Especifique o nome do arquivo com o qual deseja salvar a saída.<br><br>**Observação**: se você não fornecer um nome de arquivo, o título do mapa DITA será usado para gerar o nome final do arquivo de saída. Se o mapa não tiver um título, o nome do arquivo do mapa DITA será usado para nomear a saída final. O nome do arquivo é limpo usando as regras configuradas no sistema para lidar com qualquer caractere inválido. |
| Filtragem condicional/Aplicar condições usando | Selecione uma das seguintes opções:<br><br>* **Nenhuma aplicada**: selecione esta opção se não quiser aplicar nenhuma condição na saída publicada.<br>* **Arquivo DITAVal**: selecione o(s) arquivo(s) DITAVal para gerar conteúdo personalizado. Você pode selecionar vários arquivos DITAVal usando a caixa de diálogo Procurar ou digitando o caminho do arquivo. Use o ícone de cruz próximo ao nome do arquivo para removê-lo. Os arquivos DITAVal são avaliados na ordem especificada, de modo que as condições especificadas no primeiro arquivo têm precedência sobre as condições correspondentes especificadas em arquivos posteriores. É possível manter a ordem dos arquivos adicionando ou excluindo arquivos. Se o arquivo DITAVal for movido para algum outro local ou excluído, ele não será excluído automaticamente do painel de mapa. Você precisa atualizar o local caso os arquivos sejam movidos ou excluídos. Você pode passar o mouse sobre o nome do arquivo para visualizar o caminho no repositório do AEM onde o arquivo está armazenado. Você só pode selecionar arquivos DITAVal e um erro será exibido se você tiver selecionado qualquer outro tipo de arquivo.<br>* **Predefinição de condição**: selecione uma predefinição de condição no menu suspenso para aplicar uma condição ao publicar a saída. A opção estará visível se você tiver adicionado uma condição na guia Predefinições de condição do console do mapa DITA. Para saber mais sobre a predefinição de condição, exiba [Usar predefinições de condição](generate-output-use-condition-presets.md#id1825FL004PN). |
| Caminho de saída/Caminho de destino | O caminho no repositório do AEM onde a saída do EPUB está armazenada. |
| Reter arquivos temporários | Selecione essa opção para manter os arquivos temporários gerados pelo DITA-OT. Se ocorrerem erros durante a geração de saída pelo DITA-OT, selecione essa opção para manter os arquivos temporários. Você pode usar esses arquivos para solucionar erros de geração de saída.<br> <br> Depois de gerar a saída, selecione o ícone **Baixar arquivos temporários** ![baixar arquivos temporários](images/download-temp-files-icon.png) para baixar a pasta ZIP que contém os arquivos temporários. <br><br> **Observação**: se as propriedades do arquivo forem adicionadas durante a geração, os arquivos temporários de saída também incluirão um arquivo *metadata.xml* contendo essas propriedades. |
| Executar fluxo de trabalho de pós-geração | Ao escolher essa opção, uma nova lista suspensa Fluxo de trabalho de pós-geração é exibida contendo todos os fluxos de trabalho configurados no AEM. Você deve selecionar um workflow que deseja executar após a conclusão do workflow de geração de saída.<br><br>**Observação**: para obter mais informações sobre como criar um fluxo de trabalho personalizado de geração de pós-saída, exiba _Personalizar fluxo de trabalho de geração de pós-saída_ em Instalar e configurar o Adobe Experience Manager Guides as a Cloud Service. |
| Usar Linha de Base | Se tiver criado uma Linha de Base para o mapa DITA selecionado, selecione essa opção para especificar a versão que deseja publicar.<br><br> Exiba [Trabalhar com Linha de Base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) para obter mais detalhes. |
| Propriedades/propriedades do arquivo | Selecione as propriedades que deseja processar como metadados. Essas propriedades são definidas na página Propriedades do mapa DITA ou do arquivo de mapa. As propriedades selecionadas na lista suspensa aparecem no campo **Propriedades do arquivo**. Selecione o ícone cruzado ao lado da propriedade para removê-la. <br><br>**Observação**: você também pode passar os metadados para a saída usando a publicação DITA-OT. Para obter mais detalhes, [Passe os metadados para a saída usando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Tópico pai:**&#x200B;[ Noções básicas sobre as predefinições de saída](generate-output-understand-presets.md)

