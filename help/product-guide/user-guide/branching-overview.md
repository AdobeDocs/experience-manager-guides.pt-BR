---
title: Ramificação no AEM Guides | Adobe Experience Manager Guides`
description: Saiba como criar e gerenciar ramificações de um mapa DITA no AEM Guides para oferecer suporte à criação paralela, à publicação independente e à mesclagem de alterações na documentação.
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
    internal-label: Generative AI
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: 3f0d8e31537ade58a4eab5ddf73eb6d263d3dd96
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 0%
---
# Visão geral

>[!NOTE]
>
> O recurso de ramificação e mesclagem foi introduzido na versão 2026.11.0 do Experience Manager Guides as a Cloud Service e está desativado por padrão. Para ativar o recurso para seu ambiente, entre em contato com a equipe de sucesso do cliente.

A ramificação no Adobe Experience Manager Guides permite criar e gerenciar várias ramificações fora da ramificação **principal** para que um mapa DITA funcione em diferentes versões de documentação em paralelo. Cada ramificação permite que os autores gerenciem as alterações de conteúdo de maneira independente, sem afetar o conteúdo correspondente em outras ramificações.

Com a ramificação, várias equipes podem trabalhar simultaneamente em diferentes versões, recursos ou correções associados ao mesmo mapa DITA. Você pode mesclar as alterações de uma ramificação na ramificação padrão (`main`) quando as atualizações estiverem prontas.

## Como a ramificação funciona

Você pode criar uma ramificação a partir da **principal** ou de qualquer ramificação existente de um mapa DITA. Depois de criar uma ramificação, você pode alternar para ela e começar a editar o mapa e seu conteúdo. Você também pode publicar conteúdo da ramificação selecionada ou mesclar alterações em `main` quando estiver pronto.

Por exemplo, considere um mapa DITA chamado `install-the-lift.ditamap` que contém instruções de instalação para um produto. Sua equipe de documentação pode criar duas ramificações deste mapa a partir de `main`:

- **Versão 1:** A Equipe A mantém instruções de instalação existentes e endereça correções.
- **Versão 2:** A equipe B desenvolve instruções de instalação para novos recursos.

Ambas as equipes podem trabalhar de forma independente em suas respectivas ramificações de mapa sem afetar as alterações umas das outras.

>[!NOTE]
>
>Uma ramificação é criada com base em um mapa DITA. Você também pode adicionar e editar tópicos que não são referenciados pelo mapa dentro da ramificação selecionada. Para obter mais informações, exiba [Abrir ou editar tópicos fora do mapa atual](./create-manage-branch.md#open-or-edit-topics-outside-the-current-map-context).

Ao criar uma ramificação de um mapa DITA, o Experience Manager Guides não copia automaticamente os tópicos referenciados do mapa para a nova ramificação. Os tópicos inalterados são lidos na ramificação de origem ou na ramificação padrão (principal). Um tópico é copiado na nova ramificação somente quando você o edita e o salva nessa ramificação.

Por exemplo, um mapa DITA faz referência a 100 tópicos, e o repositório contém 50 tópicos adicionais que não são referenciados pelo mapa. Ao criar uma nova ramificação (versão 1.0), todos os 100 tópicos referenciados tornam-se automaticamente parte da versão 1.0, mesmo que nenhum deles seja editado. Os 50 tópicos não referenciados não se tornam automaticamente parte da nova ramificação. Se você editar 10 deles, somente eles se tornarão parte da versão 1.0. Os 40 tópicos restantes inalterados continuam a ser usados na ramificação padrão (principal).

>[!NOTE]
>
> O controle de versão de tópico continua a funcionar com ramificação. Você pode criar e gerenciar versões de tópicos em uma ramificação selecionada de um mapa DITA. Cada ramificação mantém seu próprio histórico de versões, independente de outras ramificações.

## Principais benefícios

Trabalhar com uma ramificação no Experience Manager Guides oferece os seguintes benefícios:

- **Edição isolada:** Faça alterações em uma ramificação de mapa selecionada sem afetar o conteúdo correspondente em outras ramificações.
- **Criação paralela**: permite que várias equipes trabalhem simultaneamente em diferentes versões, recursos ou correções em suas respectivas ramificações de mapa.
- **Publicação independente:** publique a documentação de ramificações de mapa individuais sem esperar que as alterações em outras ramificações sejam concluídas.
- **Mesclagem controlada:** mescla as alterações de uma ramificação de mapa na ramificação padrão (`main`), com a capacidade de revisar e resolver conflitos.

## Ramificação versus linhas de base

>[!NOTE]
>
> Linhas de base e ramificações são recursos mutuamente exclusivos. Quando a ramificação é ativada, a funcionalidade da linha de base fica indisponível. No entanto, as linhas de base existentes permanecem intactas e não são excluídas. Se a ramificação for desativada posteriormente, as linhas de base existentes se tornarão disponíveis para uso novamente.

Uma **linha de base** identifica uma combinação específica de versões de tópico para um mapa DITA, permitindo gerar saída usando essas versões selecionadas.

Uma **ramificação** fornece um ambiente de edição separado para um mapa DITA e seu conteúdo, permitindo que os autores façam alterações sem afetar outras ramificações do mesmo mapa.

| Linhas de Base | Ramificação |
|---|---|
| Selecione versões específicas de tópicos em um mapa DITA. | Crie ramificações separadas de um mapa DITA para gerenciar as alterações de maneira independente. |
| Usado para publicar combinações específicas de versões de tópicos. | Usado para desenvolver e publicar diferentes versões em paralelo. |
| Não forneça contextos de edição isolados. | Suporte para edição e mesclagem isoladas. |

## Futuras funcionalidades

Atualmente, as seguintes funcionalidades são suportadas apenas na ramificação padrão (`main`) e estão planejadas para serem suportadas em outras ramificações de um mapa DITA em versões futuras do Experience Manager Guides:

- Pesquisar
- Localizar e substituir
- Revisar workflows

