---
title: Inserir perguntas em um questionário
description: Saiba como inserir perguntas em um questionário no Treinamento e aprendizado do produto,
feature: Authoring
role: User
exl-id: dff38476-c078-4970-b967-05a902430015
source-git-commit: 41ea5e91b5ee096ede2eb06dae7a44f01e0c0571
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Inserir perguntas em um questionário

Execute as seguintes etapas para inserir perguntas em um questionário:

1. Escolha o tipo de pergunta desejado no menu suspenso **Perguntas** da barra de ferramentas. Com base em suas necessidades, você pode adicionar perguntas usando qualquer um dos quatro formatos disponíveis: Verdadeiro ou Falso, Único correto, Vários corretos e Corresponder ao seguinte, conforme mostrado abaixo. Para obter mais detalhes, consulte [Tipos de pergunta](#question-types).

   ![](assets/question-types.png){width="650" align="left"}

   Ao inserir uma pergunta, se o cursor estiver em um bloco de perguntas, a nova pergunta será adicionada logo após ela por padrão.

   Para inserir uma pergunta entre as duas existentes, primeiro [insira um parágrafo](#insert-paragraph-within-the-quiz) e depois insira perguntas.

1. Uma pergunta é inserida no formato selecionado. É possível editar a pergunta com base nas suas necessidades.

1. Você pode selecionar qualquer pergunta e configurar suas propriedades usando o painel **Propriedades de conteúdo**. Por exemplo, você pode especificar a resposta correta, definir as marcas a serem atribuídas e definir qualquer penalidade para respostas incorretas.

   ![](assets/question-properties.png){width="650" align="left"}

1. Salve todas as alterações feitas no questionário.

## Inserir parágrafo no questionário

Quando você coloca o cursor em uma pergunta específica ou em um espaço em branco entre as duas perguntas, uma linha horizontal azul é exibida com uma seta azul no canto superior direito da tela. Selecionar a seta azul permite inserir um parágrafo na interface de criação do questionário.

![](assets/insert-paragraph-here-arrow.png){width="650" align="left"}

- Quando usado em uma pergunta, permite adicionar mais elementos, como imagens, tabela, elementos de texto e muito mais na pergunta.
- Quando usado entre as perguntas, permite inserir outra pergunta ou adicionar outros elementos de criação, conforme mencionado acima.

## Excluir pergunta ou opção

Execute as seguintes etapas para excluir uma pergunta ou uma opção específica de um questionário:

1. Clique com o botão direito do mouse na pergunta ou opção que deseja remover.
1. No menu de contexto, selecione **Excluir pergunta** (para remover a pergunta inteira) ou **Excluir opção** (para remover apenas a opção selecionada).

![](assets/delete-options-lc.png){width="650" align="left"}

## Tipos de pergunta

Os seguintes tipos de perguntas são suportados em um questionário:

- **Única correção**: uma pergunta com várias opções em que apenas uma resposta está correta.

  ![](assets/single-correct.png){width="650" align="left"}

- **Verdadeiro/Falso**: uma pergunta baseada em instruções em que os alunos escolhem se é Verdadeiro ou Falso.

  ![](assets/true-false.png){width="650" align="left"}


- **Várias Correções**: uma pergunta com várias opções em que mais de uma resposta pode estar correta.

  ![](assets/multi-correct.png){width="650" align="left"}

- **Corresponder ao seguinte**: permite que os alunos correspondam itens de duas listas para formar os pares corretos. Você pode adicionar novos conjuntos de opções a partir do painel **Propriedades de conteúdo**. Para aumentar a complexidade, você pode remover uma opção da primeira lista e incluir uma correspondência extra na coluna Correspondência. Isso cria um elemento de dificuldade ao exigir que os alunos pensem criticamente sobre qual opção não tem um par direto.

  ![](assets/match-the-following.png){width="650" align="left"}

  Na saída publicada, a pergunta **Corresponder à seguinte** é exibida com o menu suspenso para cada item, permitindo que você selecione a correspondência correta dentre as opções disponíveis.

  ![](assets/question-type-publishing.png){width="650" align="left"}