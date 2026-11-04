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
source-git-commit: b3c2c68321080aa4dde16befe4bfd0022bf9f61c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%
---
# Assistente de IA

>[!NOTE]
>
> O recurso Assistente de IA está disponível no momento para o Adobe Experience Manager Guides as a Cloud Service.

O Assistente de IA no Adobe Experience Manager Guides é uma ferramenta alimentada por IA projetada para melhorar a produtividade simplificando a criação de conteúdo, o gerenciamento e os fluxos de trabalho de criação. Ela oferece dois modos: Agentic e Standard. No **Modo de agente**, o AI Assistant permite executar tarefas relacionadas a conteúdo por meio de interações de linguagem natural, com habilidades como Importar, Criar e Marcação inteligente para simplificar a criação de conteúdo, a organização e o gerenciamento de metadados. No **modo Padrão**, o Assistente de IA fornece assistência de criação, ajudando você a criar, refinar e gerenciar conteúdo com mais eficiência.

## Modos do Assistente de IA

O Assistente de IA está disponível de dois modos: **Agente** e **Padrão**. Os administradores podem selecionar o modo na seção **Recursos de IA** da guia **Geral** nas **configurações do Workspace**. O painel Assistente de IA no Editor permanece o mesmo em ambos os modos, mas os recursos disponíveis são diferentes:

- **Modo de agente:** usa habilidades **Importar**, **Criar** e **Marcação inteligente** para converter arquivos em tópicos estruturados, criar o primeiro rascunho de conteúdo e recomendar marcas relevantes com base na taxonomia da sua organização.
- **Modo padrão:** fornece assistência de criação baseada em IA por meio de ações contextuais, como reutilização de conteúdo, tradução e melhorias na qualidade do conteúdo, para simplificar fluxos de trabalho de criação.

## Modo agente

>[!NOTE]
>
> Para usar o Assistente de IA no modo Agente, sua organização precisa ser integrada à Adobe CX Enterprise Coworker e ter créditos disponíveis; uma vez integrado, entre em contato com a equipe de sucesso do cliente para ativar o recurso. Para obter detalhes sobre a configuração, consulte [Configurar o Assistente de IA no Modo Agencial](../install-conf-guide/configure-ai-assistant-agentic-mode-cs.md).

O modo Agente no Assistente de IA permite executar uma grande variedade de tarefas relacionadas a conteúdo por meio de interações de linguagem natural, como criar e importar conteúdo, resumir tópicos, adicionar tópicos a mapas e gerenciar metadados. Você pode descrever seus requisitos no painel de chat, e o Assistente de IA planeja e executa tarefas enquanto fornece visibilidade sobre seu progresso. O modo de agente fornece acesso rápido às seguintes habilidades:

- **Importar**: converte arquivos do PDF, Word ou Markdown do repositório de dispositivo ou conteúdo em tópicos estruturados. Para obter mais detalhes, consulte [Importar conteúdo com o Assistente de IA](./import-ai-assistant.md).

- **Criar**: gera tópicos e mapas de rascunho a partir de materiais de entrada, como especificações, imagens do quadro de comunicações, capturas de tela e outros conteúdos de referência, com a opção de usar conteúdo existente para tom e estilo. Para obter mais detalhes, consulte [Criar conteúdo com o Assistente de IA](./create-ai-assistant.md).

- **Marcação inteligente**: recomenda marcas relevantes para tópicos com base na taxonomia da sua organização para melhorar a consistência dos metadados. Para obter mais detalhes, consulte [Marcação inteligente com o Assistente de IA](./ai-assistant-agentic.md).

Os seguintes componentes do painel do Assistente de IA ajudam a adicionar conteúdo, inserir prompts e iniciar tarefas:

![Marcação inteligente do assistente de ia](./images/panel-new-agentic.png)

- **(A)** Histórico da conversa: exibir e reabrir conversas anteriores para rever solicitações e respostas anteriores.
- **(B)** Tela cheia: expande o painel Assistente de IA para tela cheia.
- **(C)** Espaço de aviso: digite uma solicitação de aviso ou digite `/` para adicionar arquivos e gerar marcas.
- **(D)** Anexar arquivos ou adicionar contexto: adiciona tópicos, mapas ou arquivos do sistema local para fornecer o conteúdo com o qual o AI Assistant trabalha.
- **(E)** Enviar: envia seu prompt e o conteúdo anexado ao Assistente de IA.
- **(F)** Ações rápidas: iniciar uma tarefa diretamente de um dos seguintes atalhos: **Importar**, **Criar** ou **Marca**.

## Modo padrão

O modo Padrão torna seu processo de criação mais inteligente e rápido. Quando você seleciona um texto no Editor, o AI Assistant oferece ações rápidas, como gerar sugestões inteligentes para reutilização de conteúdo, tradução de conteúdo, melhoria da qualidade do conteúdo e muito mais, tudo com base no conteúdo selecionado. Isso melhora a experiência geral de criação e a produtividade dos autores.

Para obter mais detalhes, exiba [Criar documentos com o Assistente de IA](./ai-assistant-right-panel.md).

![assistente de ia](./images/ai-assistant-panel.png)


## Introdução ao Assistente de IA

Ao usar o **Assistente de IA** pela primeira vez, você será solicitado a enviar seu consentimento antes de usar os recursos de IA gerativa da Experience Manager Guides.

Execute as seguintes etapas para iniciar o Assistente de IA:

1. Faça logon no Experience Manager Guides.
1. Na página inicial, selecione **Assistente de IA** na parte superior. Certifique-se de que o administrador ativou o recurso Assistente de IA no modo desejado.
O Assistente de IA exibe os principais recursos, o link de diretrizes do usuário e um botão **Introdução**.
1. Leia as diretrizes de usuário cuidadosamente e selecione **Introdução** para iniciar o Assistente de IA.

>[!NOTE]
>
>Se você já consentiu com as diretrizes de uso do recurso Assistente de ajuda, você não será solicitado a consentir novamente e poderá continuar usando o recurso Assistente de IA.

**Tópicos relacionados**

[Perguntas frequentes sobre segurança do Assistente de IA](./ai-assistant-faq.md)

[Divulgações da IA geradora da Adobe Experience Manager Guides](./adobe-generative-ai-disclosures.md)

[Configurar o AI Assistant para obter ajuda e criação inteligentes](../cs-install-guide/conf-smart-suggestions.md)
