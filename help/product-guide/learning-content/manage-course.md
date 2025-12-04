---
title: Gerenciar um curso em Treinamento e aprendizado de produtos
description: Saiba mais sobre os vários recursos presentes no Experience Manager Guides que permitem gerenciar seu curso com eficiência.
feature: Authoring
role: User
exl-id: 0f480d08-2f8a-494e-ab56-4965e5eeb960
source-git-commit: 0171f7b798686a0a16942e98133001a4c05bb76b
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 0%

---

# Gerenciar seu curso

Depois de criar um curso, ele é aberto no painel Gerenciador de cursos. Você pode bloquear o curso e fazer todas as alterações necessárias no nível dele. As seções a seguir explicam as opções disponíveis para editar o curso.

## Adicionar novo conteúdo

Execute as seguintes etapas para adicionar novo conteúdo ao curso:

1. Selecione o menu **Opções** > **Adicionar novo**.

   ![](assets/learning-course-content.png)
2. Selecione o tipo de conteúdo que deseja criar. As opções disponíveis são:
   - **Visão geral**: o primeiro tópico do curso que fornece uma introdução rápida sobre o que ele aborda.
   - **Tópico**: O material principal de um curso consiste em peças curtas e focadas como etapas, exemplos ou explicações que ensinam uma habilidade ou ideia específica. Para obter mais detalhes, consulte [Criar e personalizar o Tópico](./create-content.md).
   - **Resumo**: uma revisão rápida no final de um capítulo do curso que lembra aos alunos os pontos-chave que eles acabaram de aprender.
   - **Questionário**: um conjunto de perguntas usado para verificar se alguém entende o que aprendeu. Para obter mais detalhes, consulte [Criar e gerenciar questionário](./create-quiz.md).
   - **Banco de perguntas**: um pool compartilhado de perguntas reutilizáveis que podem ser usadas para criar testes de forma rápida e consistente. Para obter mais detalhes, consulte [Banco de perguntas](./create-qb.md).
   - **Grupo**: um grupo de aprendizado ajuda a organizar tópicos relacionados, como capítulos, tópicos e outros módulos em uma ordem lógica, criando uma hierarquia clara que facilita o gerenciamento e a reutilização de materiais de treinamento.
3. Selecione **Criar**.

O conteúdo selecionado é criado e adicionado ao curso. Para ter uma visão geral em vídeo, assista [Adicionar novo conteúdo a um curso](https://video.tv.adobe.com/v/3469537/aem-guides-learning-content?quality=12&learn=on) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Adicionar conteúdo existente

Você pode adicionar conteúdo existente do seu repositório de conteúdo ao curso. Execute as seguintes etapas para adicionar conteúdo existente:

1. Selecione o menu **Opções** > **Adicionar existente**.
2. Selecione o tipo de conteúdo do curso que deseja criar.
3. Na caixa de diálogo **Selecionar caminho**, navegue até o local do conteúdo e selecione o conteúdo de Aprendizado desejado.

   ![](assets/add-existing-learning-content.png)
4. Escolha **Selecionar**.

O conteúdo selecionado do curso é adicionado ao curso a partir do repositório.

>[!NOTE]
>
>Você também pode usar a opção **Adicionar existente** > **Arquivo (zip somente recurso)** para incluir um arquivo zip que é descompactado e integrado à estrutura de pastas da saída final do SCORM. Isso ajuda a simplificar o empacotamento de recursos durante a publicação do curso.

Para ter uma visão geral em vídeo, assista [Adicionar conteúdo existente a um curso](https://video.tv.adobe.com/v/3469537/aem-guides-learning-content?quality=12&learn=on) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Remover conteúdo

Você pode remover qualquer tópico do curso selecionando o menu **Opções** para esse tópico específico e selecionando **Remover entrada** como mostrado abaixo.

![](assets/remove-learning-content.png)

Para obter uma visão geral em vídeo, assista [Remover conteúdo do curso](https://video.tv.adobe.com/v/3475210/learning-content-aem-guides) ![](assets/Smock_VideoCheckedOut_18_N.svg).


## Criar versões do curso

Você pode controlar o controle de versão do seu curso selecionando o menu **Opções** > **Controle de Versão**.

![](assets/course-versioning.png)

Você tem as seguintes opções para o controle de versão de um curso:

- **Salvar como nova versão**: salva seu curso com um novo número de versão.
- **Histórico de versões**: mostra a pré-visualização da versão atual e também permite que você a compare com as outras versões disponíveis do curso.
- **Rótulo de versão**: permite que você especifique rótulos em um formato de texto livre ou use um conjunto de rótulos predefinidos.

## Configurações de exibição: Mostrar

A opção **Mostrar** determina como os tópicos são exibidos. Você pode optar por apresentá-las usando caixas de seleção para várias seleções de tópico, numeração para indicar a estrutura hierárquica ou mostrando o título do tópico ou o nome do arquivo.

>[!NOTE]
>
> Essas configurações de visualização se aplicam somente ao Gerenciador de cursos e não têm impacto na saída publicada.

![](assets/course-display-settings.png)

Para obter uma visão geral do vídeo, exiba [Mostrar configurações](https://video.tv.adobe.com/v/3475210/learning-content-aem-guides) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Criar tarefa de revisão

Como Autor de um curso de aprendizado ou Administrador, você pode criar uma tarefa de revisão para o curso e atribuí-la a um Revisor para feedback. Comece abrindo o curso no painel **Gerenciador de cursos** e selecione **Criar tarefa de revisão** no menu **Opções**, conforme mostrado abaixo:

![](assets/create-review-task-lc.png)

Você é direcionado à página **Criar Tarefa de Revisão**, na qual precisa adicionar detalhes da tarefa, como o título da tarefa de revisão, especificar o projeto DITA do qual ele faz parte, definir linhas do tempo da tarefa, atribuir revisores e muito mais. Depois de concluído, o(s) Revisor(es) receberá(ão) uma notificação para essa tarefa. Os tópicos selecionados do curso são abertos na interface de revisão, onde o(s) revisor(es) pode(m) adicionar comentários e enviar os tópicos novamente para atualizações.

Para entender o fluxo de trabalho de revisão no Experience Manager Guides, exiba [Enviar tópicos para revisão](../user-guide/review-send-topics-for-review.md).


