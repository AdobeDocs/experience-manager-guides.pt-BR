---
title: Usar o Assistente de IA para criar documentos com inteligência &grave;
description: Saiba como usar o Assistente de IA para criar documentos com eficiência inteligente.
exl-id: 47d37323-20bf-4444-a2c9-41c44b2c8daf
source-git-commit: 3d344a1d1b8d51ddadd618db5296531f549dc70b
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 0%

---

# Crie documentos com inteligência com o Assistente de IA (Beta)

O Adobe Experience Manager Guides fornece uma ferramenta de Assistente de IA que ajuda a tornar a criação mais inteligente e rápida. Com essa ferramenta, visualize as sugestões inteligentes para reutilizar o conteúdo do repositório de conteúdo existente. Use o recurso de prompt de texto para fornecer um prompt e alterar o conteúdo de acordo com seus requisitos. Use o Assistente de IA para converter um parágrafo em uma lista de maneira inteligente. Você pode criar uma breve descrição para o tópico atual com base no conteúdo selecionado. Esse recurso também ajuda a melhorar e traduzir facilmente o conteúdo selecionado.

>[!NOTE]
>
> Esse recurso de criação está disponível somente para tópicos DITA e pode ser acessado somente na interface do Editor. Na Home page e no console Mapa, somente o painel **Ajuda** é exibido. As opções disponíveis no recurso de Criação são configuradas em nível de perfil da pasta pelos Administradores usando as configurações do Editor.

Depois de selecionar o texto em um tópico, você pode optar por executar qualquer uma das ações do Assistente do AI:

![assistente de ia](./images/ai-assistant-panel.png){width="300" align="left"}

## Sugerir conteúdo reutilizável


Use o recurso **Sugerir conteúdo reutilizável** ![ai sugerir ícone de conteúdo reutilizável ](./images/ai-suggest-reusable-content-icon.svg) para criar conteúdo de forma consistente e precisa. Você pode selecionar o conteúdo, e o Experience Manager Guides fornece sugestões sobre como reutilizar o conteúdo existente no repositório.
Saiba mais sobre como usar as [sugestões inteligentes habilitadas por IA para criar conteúdo](authoring-ai-based-smart-suggestions.md).


## Usar prompt de texto

Um prompt de texto é uma instrução, pergunta ou instrução que orienta o Assistente de IA a gerar uma resposta específica.

Você pode usar um prompt de texto para alterar o conteúdo. Por exemplo, você pode selecionar o conteúdo do seu tópico atual e usar o prompt *Tornar o texto mais conciso*. Da mesma forma, você pode usar um prompt de texto para adicionar um atributo à tag usada no conteúdo selecionado.

1. Selecione o texto para o qual deseja usar o prompt de texto.
1. Selecione **Usar prompt de texto** ![ai usar ícone de prompt de texto](./images/ai-use-text-prompt.svg)no painel **Criação**.
1. Forneça um prompt de uma das seguintes maneiras:

   - Escolha um prompt entre os prompts sugeridos.
   - Revise ou edite um prompt sugerido para criar um prompt personalizado de acordo com seus requisitos.

     >[!NOTE]
     >
     > Os prompts sugeridos são configurados no `ui_config.json` pelo seu administrador.

   - Digite seu prompt na caixa de texto.


1. Selecione **Gerar novamente** ![Ícone Gerar novamente](./images/refresh-icon.svg) para outra resposta ou saída com base no seu prompt.

1. (Opcional) Selecione **Expandir** ![expandicon](./images/expand-icon.svg) para abrir o editor **Usar prompt de texto**. Ele exibe o conteúdo atual e o gerado. É possível editar o conteúdo do layout de origem e verificar a visualização.

   ![editor de prompt de texto do assistente da ia](./images/text-prompt.png)


   >[!NOTE]
   >
   > As respostas são geradas com base no conteúdo selecionado.



1. Você também pode editar o prompt no editor e gerar novamente a resposta. Por exemplo, você pode alterar o prompt para tornar o texto mais conciso para aproximadamente 40 palavras.

1. Você pode verificar a origem do conteúdo gerado e editá-lo, se necessário.

1. Selecione **Aceitar** para substituir o conteúdo selecionado no tópico pelo conteúdo gerado.
1. **Cancelar**: cancela a ação de prompt de texto. Retorna ao painel Criação.

   >[!NOTE]
   >
   > Ao selecionar o ícone **Dispensar** no painel Criação, você retornará ao estado inicial do Assistente de IA.

## Melhorar o conteúdo

Use o recurso **Melhorar conteúdo** para melhorar a qualidade do conteúdo selecionado do tópico atual. Você pode selecionar o conteúdo para verificar a ortografia, o idioma e a estrutura gramatical, e sugerir uma versão melhor do conteúdo. Também melhora a qualidade das frases.

1. Selecione o conteúdo.
1. Selecione **Melhorar conteúdo** ![ai ícone melhorar conteúdo](./images/ai-improve-icon.svg) para encontrar as sugestões para o conteúdo aprimorado.
1. Selecione **Regenerar** para outra sugestão de conteúdo aprimorado.

1. (Opcional) Selecione **Expandir** para abrir o editor de conteúdo aprimorado. Ele exibe o conteúdo atual e gerado. É possível editar o conteúdo no layout de origem e também verificar a pré-visualização.



   ![assistente de ia para melhorar o editor de conteúdo](./images/ai-assisstant-improve-content.png)

Aceite a sugestão, edite a resposta na exibição de origem antes de aceitar, gere novamente para uma resposta diferente ou cancele a ação para voltar ao estado anterior.





## Criar resumos

Crie uma breve descrição para o tópico com base no conteúdo selecionado em cerca de 30 a 50 palavras. A breve descrição ajuda os usuários a pesquisar e encontrar conteúdo relevante.
Por exemplo, você pode listar os requisitos do sistema e gerar uma breve descrição de acordo.



1. Selecione o conteúdo.
1. Selecione **Criar descrição curta** ![ai ícone criar descrição curta](./images/ai-create-shortdesc-icon.svg) para criar uma descrição curta para o tópico atual.
1. Selecione **Aceitar** para criar uma nova descrição curta se ela ainda não estiver presente. Se existir uma descrição curta, é necessário confirmá-la antes de substituí-la pela nova descrição curta.

Você também pode executar as seguintes ações:

- Selecione **Gerar novamente** para gerar outra descrição curta para o seu tópico.
- Selecione **Expandir** para abrir o editor **Criar atalhos**.

  ![assistente de ia criar editor de descrição curta](./images/ai-assistant-create-short-desc.png)




## Discriminar conteúdo

Esse recurso converte de forma inteligente um parágrafo selecionado em uma lista.  Ele analisa o conteúdo e cria uma lista lógica de itens. Não é necessário criar os itens manualmente. Por exemplo, se você tiver um parágrafo detalhando as etapas para criar uma conta de usuário, a ferramenta poderá transformá-lo em uma lista passo a passo, eliminando a necessidade de criar itens manualmente um por um.

![ícone de assistente de ia discriminar conteúdo](./images/ai-assisstant-itemise-content.png)



1. Selecione o conteúdo.
1. Selecione **Itemizar conteúdo** ![ai itemizar ícone de conteúdo](./images/ai-itemize-icon.svg) para converter o conteúdo selecionado em uma lista.
A ferramenta de Criação no painel Assistente de IA converte o conteúdo inteligentemente em uma lista de itens.
1. (Opcional) Selecione **Expandir** para abrir o editor **Discriminar conteúdo**.
1. Quando a lista estiver pronta, aceite as alterações no conteúdo gerado. O conteúdo gerado substitui o conteúdo selecionado.



## Traduzir conteúdo

Use esse recurso inteligente para traduzir o conteúdo selecionado para o idioma de destino, tornando-o altamente útil ao adicionar notas em diferentes idiomas. Por exemplo, você pode adicionar conteúdo em inglês e traduzi-lo rapidamente para árabe.

Execute as seguintes etapas para traduzir o conteúdo:

1. Selecione o conteúdo que deseja traduzir.
1. Selecione **Traduzir conteúdo** ![ícone de conteúdo de tradução de ia](./images/ai-translate-content-icon.svg) no painel **Criação**.
1. Selecione o idioma de destino na lista suspensa. O conteúdo traduzido é exibido no painel Assistente de IA.

1. (Opcional) Selecione **Expandir** para abrir o editor **Traduzir conteúdo**.
1. Você também pode selecionar outro idioma no menu suspenso e gerar novamente o conteúdo no idioma escolhido. Por exemplo, se você selecionar Francês e **Regenerar**, o conteúdo será traduzido para Francês.

![conteúdo de tradução do assistente de ia](./images/ai-assisstant-translate-content.png)
