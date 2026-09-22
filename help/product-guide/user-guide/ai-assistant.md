---
title: Usar o Assistente de IA para criar documentos com inteligência `
description: Saiba como usar o Assistente de IA para pesquisar e criar documentos de forma inteligente no Adobe Experience Manager Guides.
exl-id: c18e8761-333e-40ef-9e16-e71a194a754a
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
source-git-commit: 71ddd55d2a6848449d5810701b60e9f69a29112b
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 0%
---
# Assistente de IA (Beta)

O **Assistente de IA** do Adobe Experience Manager Guides é uma ferramenta avançada orientada por IA, projetada para aprimorar sua produtividade por meio de recursos inteligentes de ajuda, criação e marcação. No modo **Padrão**, ele reúne dois recursos avançados de IA: **Criação** e **Ajuda** para a interface do Experience Manager Guides, permitindo que você crie conteúdo e acesse informações da documentação do Experience Manager Guides de forma mais rápida e eficiente. No modo **Agente**, o Assistente de IA oferece **Marcação inteligente**, permitindo que você solicite, por meio de uma janela de prompt conversacional, recomendações de marcas para o seu conteúdo e as aplique em um ou mais tópicos.

>[!NOTE]
>
> O recurso Assistente de IA está disponível no momento para o Adobe Experience Manager Guides as a Cloud Service.

## Modos do Assistente de IA

>[!NOTE]
>
>Para ativar o Assistente de IA no modo Agente para o seu ambiente, entre em contato com a Equipe de sucesso do cliente.

O Assistente de IA está disponível de dois modos: **Agente** e **Padrão**. Os administradores podem escolher entre os dois modos na seção **Assistente de IA** da guia **Geral** nas **configurações do Workspace**. O painel Assistente de IA permanece o mesmo em ambos os modos no Editor, mas os recursos disponíveis nele são diferentes:

* O modo **Agente** usa a habilidade **Marcação inteligente** da Adobe CX Enterprise Coworker para analisar seu conteúdo e recomendar marcas relevantes com base na taxonomia de sua organização.
* O modo **Padrão** fornece a experiência existente do Assistente de IA, com as guias **Ajuda** e **Criação** no painel Assistente de IA.

## Modo agente

### Marcação inteligente

O Assistente de IA no modo Agente torna a marcação de conteúdo mais rápida e fácil por meio de uma janela de prompt de conversação. Usando a habilidade de marcação inteligente agêntica da Adobe CX Enterprise Coworker, o Assistente de IA recomenda tags relevantes para o seu conteúdo quando você solicita. Você permanece no controle revisando as tags sugeridas e optando por aplicá-las a um ou mais tópicos, incluindo vários tópicos em um mapa.

Para obter mais detalhes, consulte [Introdução ao Assistente de IA Agêntica](./ai-assistant-agentic.md).

![Marcação inteligente do assistente de ia](./images/suggested-prompts.png)

## Modo padrão

### Criação

Quando o Assistente de IA é configurado no modo **Padrão**, o recurso **Criação** do Assistente de IA torna seu processo de criação mais inteligente e rápido. Ele oferece recursos como geração de sugestões inteligentes para reutilização de conteúdo, tradução de conteúdo, melhoria da qualidade do conteúdo e muito mais, tudo com base no conteúdo selecionado. Esse recurso melhora a experiência geral de criação e a produtividade dos autores.

Para obter mais detalhes, consulte [Criação](./ai-assistant-right-panel.md).

![assistente de ia](./images/ai-assistant-panel.png)

### Ajuda

Quando o Assistente de IA é configurado no modo **Padrão**, o recurso **Ajuda** fornece uma experiência de chat intuitiva que ajuda você a entender o Experience Manager Guides, solucionar problemas e encontrar informações na documentação do Adobe Experience Manager Guides. Em vez de pesquisar nos guias de usuário e documentos de referência, você pode usar o recurso **Ajuda** para encontrar rapidamente respostas relevantes para suas consultas. Isso ajuda a economizar tempo e permite que você se concentre na criação de conteúdo, resultando em maior produtividade e eficiência.

Para obter mais detalhes, consulte a [Ajuda](./ai-based-smart-help.md).


![Painel Ajuda Inteligente](images/smart-help-panel.png)

## Introdução ao Assistente de IA no modo Padrão

Ao usar o **Assistente de IA** no modo Padrão pela primeira vez, você será solicitado a enviar seu consentimento antes de usar os recursos do Experience Manager Guides Generative AI.

Execute as seguintes etapas para iniciar o Assistente de IA:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **Assistente de IA** na parte superior. Certifique-se de que o administrador ativou o recurso Assistente de IA no modo desejado.

O Assistente de IA exibe os principais recursos, o link de diretrizes do usuário e um botão **Introdução**.

![Painel Ajuda Inteligente](images/get-started-ai.png)

Leia as diretrizes de usuário cuidadosamente e selecione **Introdução** para iniciar o Assistente de IA.

**Tópicos relacionados**

[Perguntas frequentes sobre segurança do Assistente de IA](./ai-assistant-faq.md)

[Divulgações da IA geradora da Adobe Experience Manager Guides](./adobe-generative-ai-disclosures.md)

[Configurar o AI Assistant para obter ajuda e criação inteligentes](../cs-install-guide/conf-smart-suggestions.md)
