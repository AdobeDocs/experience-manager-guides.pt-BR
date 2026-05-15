---
title: Notas de versão | Novidades na versão 2025.06.0 do Adobe Experience Manager Guides
description: Saiba mais sobre os recursos novos e aprimorados da versão 2025.06.0 do Adobe Experience Manager Guides
role: Leader
exl-id: 48f27aa6-d870-4228-8e62-db81699a25f7
TQID: https://experienceleague.adobe.com/Lu9Ebb7OEpxiRmjkho1KnXiry5Kz5kDwfAYbXJD8-uI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 0%

---

# Novidades da versão 2025.06.0 (junho de 2025)

Este artigo aborda os recursos novos e aprimorados introduzidos com a versão 2025.06.0 do Adobe Experience Manager Guides as a Cloud Service.

Para obter a lista de problemas corrigidos nesta versão, consulte [Problemas corrigidos na versão 2025.06.0](fixed-issues-2025-06-0.md).

Saiba mais sobre [as instruções de atualização para a versão 2025.06.0](../release-info/upgrade-instructions-2025-06-0.md).

## Solicitação de tempo limite da sessão para evitar perda acidental de conteúdo

Uma mensagem pop-up agora o notifica quando a sessão do Adobe Experience Manager expira e você é desconectado devido a inatividade. Essa mensagem é disparada quando você tenta editar o conteúdo no Experience Manager Guides após o término da sessão. O recurso ajuda a reduzir o risco de perda de trabalho não salvo e melhora a confiabilidade e a fluidez gerais da experiência, mesmo durante períodos de inatividade.

![](assets/sign-out-prompt.png)

Saiba mais sobre [prompt de tempo limite de sessão](../user-guide/session-timeout-prompt.md) no Experience Manager Guides.

## Opções aprimoradas de download de mapa no Editor

O Experience Manager Guides apresenta uma nova opção **Usar nomes de arquivos reais** na caixa de diálogo **Baixar mapa**. Agora, ao baixar arquivos de mapa, você pode optar por manter os nomes de arquivo originais em vez dos UUIDs padrão, facilitando muito o reconhecimento e o gerenciamento dos arquivos. Esta opção só estará disponível se você selecionar **Manter hierarquia de arquivos** e estiver desabilitada ao escolher **Nivelar hierarquia de arquivos**, dando a você mais flexibilidade na organização dos mapas baixados.

Para obter mais detalhes, consulte [Baixar arquivos](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300"}


## Manuseio de `navref` aprimorado no Editor

Os últimos aprimoramentos do Editor melhoram a manipulação de elementos `navref` em um mapa DITA. Agora, quando você adiciona um elemento `navref` a um mapa, a caixa de diálogo **Selecionar caminho** é aberta, permitindo que você escolha facilmente as referências de mapa a serem incluídas como links de navegação em seu mapa. Depois de adicionado, o título do mapa adicionado é exibido na exibição Autor e Layout, fornecendo melhor visibilidade da navegação incluída durante a criação.  Além disso, o elemento `navref` adicionado é resolvido automaticamente para exibir o mapa referido no Editor.

Para obter mais detalhes, consulte [Adicionar referências de navegação](../user-guide/map-editor-other-features.md#add-navigation-references).

## Aprimoramentos de desempenho no Assistente de IA

A versão apresenta aprimoramentos ao mecanismo de back-end do Assistente de IA, oferecendo melhor desempenho e maior estabilidade. Para habilitar esta atualização e continuar usando a Ajuda do Assistente de IA:

- Atualize a configuração `chat.url` para refletir a nova URL do ponto de extremidade.
- Adicione uma nova variável de ambiente `GUIDES_AI_SITE_ID` no Cloud Manager.

Para obter detalhes, consulte [Configurar o Assistente de IA](../cs-install-guide/conf-smart-suggestions.md).

