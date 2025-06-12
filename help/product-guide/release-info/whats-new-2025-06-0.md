---
title: Notas de versão | Novidades da versão 2025.06.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2025.06.0 do Adobe Experience Manager Guides
role: Leader
exl-id: 48f27aa6-d870-4228-8e62-db81699a25f7
source-git-commit: 158c2a99ac43fd70726bedf30f4de1a970a48864
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# Novidades da versão 2025.06.0 (junho de 2025)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2025.06.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2025.06.0](fixed-issues-2025-06-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.06.0](../release-info/upgrade-instructions-2025-06-0.md).

## Os arquivos temporários para saída publicada agora incluem Autor e URLs de publicação em um novo arquivo de configuração

Os últimos aprimoramentos de publicação no Experience Manager Guides agora adicionam um novo arquivo `system_config.json` aos arquivos temporários gerados ao publicar saídas do HTML, PDF e JSON usando DITA-OT, bem como saída do PDF nativo. Este arquivo é incluído automaticamente no trabalho de publicação e também pode ser acessado por meio de arquivos temporários quando você habilita a opção **Reter arquivos temporários** para as predefinições e gera a saída.

O arquivo `system_config.json` contém detalhes importantes da instância, incluindo a URL do Autor, a URL Local e a URL de Publicação, que fornecem um contexto mais claro e melhoram a rastreabilidade das URLs baixadas.

Para obter mais detalhes, consulte [Compreender as predefinições de saída](../user-guide/generate-output-understand-presets.md).

## Solicitação de tempo limite da sessão para evitar perda acidental de conteúdo

Uma mensagem pop-up agora o notifica quando a sessão do Adobe Experience Manager expira e você é desconectado devido a inatividade. Essa mensagem é disparada quando você tenta editar o conteúdo no Experience Manager Guides após o término da sessão. O recurso ajuda a reduzir o risco de perda de trabalho não salvo e melhora a confiabilidade e a fluidez gerais da experiência, mesmo durante períodos de inatividade.

![](assets/sign-out-prompt.png)

Saiba mais sobre [prompt de tempo limite de sessão](../user-guide/session-timeout-prompt.md) no Experience Manager Guides.

## Opções aprimoradas de download de mapa no Editor

O Experience Manager Guides apresenta uma nova opção **Usar nomes de arquivos reais** na caixa de diálogo **Baixar mapa**. Agora, ao baixar arquivos de mapa, você pode optar por manter os nomes de arquivo originais em vez dos UUIDs padrão, facilitando muito o reconhecimento e o gerenciamento dos arquivos. Esta opção só estará disponível se você selecionar **Manter hierarquia de arquivos** e estiver desabilitada ao escolher **Nivelar hierarquia de arquivos**, dando a você mais flexibilidade na organização dos mapas baixados.

Para obter mais detalhes, consulte [Baixar arquivos](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}


## Manuseio de `navref` aprimorado no Editor

Os últimos aprimoramentos do Editor melhoram a manipulação de elementos `navref` em um mapa DITA. Agora, quando você adiciona um elemento `navref` a um mapa, a caixa de diálogo **Selecionar caminho** é aberta, permitindo que você escolha facilmente as referências de mapa a serem incluídas como links de navegação em seu mapa. Depois de adicionado, o título do mapa adicionado é exibido na exibição Autor e Layout, fornecendo melhor visibilidade da navegação incluída durante a criação.  Além disso, o elemento `navref` adicionado é resolvido automaticamente para exibir o mapa referido no Editor.

Para obter mais detalhes, consulte [Adicionar referências de navegação](../user-guide/map-editor-other-features.md#add-navigation-references).

## Aprimoramentos de desempenho no Assistente de IA

A versão apresenta aprimoramentos ao mecanismo de back-end do Assistente de IA, oferecendo melhor desempenho e maior estabilidade. Para habilitar esta atualização e continuar usando a Ajuda do Assistente de IA:

- Atualize a configuração `chat.url` para refletir a nova URL do ponto de extremidade.
- Adicione uma nova variável de ambiente `GUIDES_AI_SITE_ID` no Cloud Manager.

Para obter detalhes, consulte [Configurar o Assistente de IA](../cs-install-guide/conf-smart-suggestions.md).

