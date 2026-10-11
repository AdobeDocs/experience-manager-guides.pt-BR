---
title: Converter conteúdo não UUID sem versões em conteúdo UUID
description: Saiba como migrar conteúdo não UUID sem versões.
exl-id: 44b5660d-9961-4463-9686-53085249fb05
feature: Migration
role: Admin
level: Experienced
hidefromtoc: 'yes'
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: 5be0fc8f-1cff-5c3e-bb92-2903a56a3de6
    internal-label: Migration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 0%
---
# Migrar conteúdo sem versão

>[!IMPORTANT]
>
> Você pode escolher essa abordagem de migração se quiser ignorar ou não as versões de ativos.


1. Baixe e carregue ativos da instância não UUID para a instância UUID diretamente da interface do usuário do AEM Assets usando ferramentas do Adobe, como o aplicativo de desktop do AEM.

1. Habilite o fluxo de trabalho do ativo de atualização do DAM e execute-o em todos os ativos depois de importar o conteúdo para criação de GUID.
